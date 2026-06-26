# Introdução

Recentemente, eu vi um [vídeo](https://www.youtube.com/watch?v=UH8RjH5vJcI) do [Diolinux](https://www.youtube.com/@Diolinux) onde, inspirado na copa do mundo de 2026, ele criou um site no qual ele fez distros linux concorrerem para ver qual delas era a melhor de acordo com a sua opinião. Eu achei super interessante a ideia de ir escolhendo a melhor entre duas distros até chegar na vencedora, e fiquei com vontade de fazer algo similar, mas um pouco mais simples, para me ajudar a criar meus própios top 5, 10, 15, etc. 

# Ideia de um script auxiliar para gerar um "Top X coisas"

No caso, a minha ideia foi adaptar um algoritmo de ordenação comum, desses que se usa em programação para ordenar listas de números em ordem crescente, de modo a enumerar com base em "pior" e "melhor". Para isso, eu fiz a seguinte troca:

>Comparações do tipo "$a \leq b$?" foram trocadas por "$b$ é melhor que $a$?" 

Em outras palavras, ser "maior" no meu algoritmo adaptado é o mesmo que ser "melhor". Da mesma forma, ser "menor" é o mesmo que ser "pior". Com esta  simples adaptação, qualquer algoritmo de ordenação pode ser adaptado para criar essas listas de top X coisas. No entanto, a eficiência dos algoritmos pode variar. Alguns deles vão te obrigar a fazer mais comparações, e outros menos. Por conta disso, pedi ao Gemini para me sugerir um algoritmo que de modo geral exigisse menos comparações. Ele me sugeriu o Quicksort, e me forneceu o seguinte pseudo-código:

	Função Quicksort(A, inicio, fim)
	    Se inicio < fim Então
	        // p é o índice onde o pivô foi parar após o particionamento
	        p = Particionar(A, inicio, fim)
	        
	        // Ordena recursivamente a sublista da esquerda
	        Quicksort(A, inicio, p - 1)
	        
	        // Ordena recursivamente a sublista da direita
	        Quicksort(A, p + 1, fim)
	    FimSe
	FimFunção
	
	Função Particionar(A, inicio, fim)
	    // Escolhe o último elemento como o pivô
	    pivo = A[fim]
	    
	    // Índice do menor elemento (indica a posição correta do pivô até agora)
	    i = inicio - 1
	    
	    Para j de inicio até fim - 1 Faça
	        // Se o elemento atual for menor ou igual ao pivô
	        Se A[j] <= pivo Então
	            i = i + 1
	            Trocar A[i] por A[j]
	        FimSe
	    FimPara
	    
	    // Coloca o pivô na sua posição correta (logo após os menores)
	    Trocar A[i + 1] por A[fim]
	    
	    // Retorna o índice do pivô
	    Retornar i + 1
	FimFunção

# Script em Julia que eu fiz

Com o pseudo-código fornecido, eu escrevi o meu código na linguagem julia:

	function Quicksort(A, inicio, fim)
	  if inicio < fim
	    # p é o índice onde o pivô foi parar após o particionamento
	    p = Particionar(A, inicio, fim)
	
	    # Ordena recursivamente a sublista da esquerda
	    Quicksort(A, inicio, p - 1)
	
	    # Ordena recursivamente a sublista da direita
	    Quicksort(A, p + 1, fim)
	  end
	end
	
	function Particionar(A, inicio, fim)
	  # Escolhe o último elemento como o pivô
	  pivo = A[fim]
	
	  # Índice do menor elemento (indica a posição correta do pivô até agora)
	  i = inicio - 1
	
	  for j=inicio:fim-1
	    # Se o elemento atual for menor ou igual ao pivô
	    println("Qual dos dois é o melhor? \n 1. ", A[j],"\n 2. ", pivo, "\n Responda 1 ou 2:")
	    resposta = readline(stdin)
	    if resposta == "2" #A[j] <= pivo:
	      i = i + 1
	      #Trocar A[i] por A[j]
	      A[i], A[j] = A[j], A[i]
	    end
	  end
	
	  # Coloca o pivô na sua posição correta (logo após os menores)
	  #Trocar A[i + 1] por A[fim]
	  A[i+1], A[fim] = A[fim], A[i+1]
	
	  # Retorna o índice do pivô
	  return i + 1
	end
	
	lista = ["Kingdom Hearts (2002) - PlayStation 2", "Kingdom Hearts II (2005) - PlayStation 2", "Kingdom Hearts Re:Chain of Memories (2007) - PlayStation 2 (Remake em 3D)", "Kingdom Hearts 358/2 Days (2009) - Nintendo DS", "Kingdom Hearts Birth by Sleep (2010) - PlayStation Portable (PSP)", "Kingdom Hearts Re:coded (2010) - Nintendo DS (Remake do Coded)", "Kingdom Hearts 3D: Dream Drop Distance (2012) - Nintendo 3DS", "Kingdom Hearts χ [chi] / Unchained χ / Union χ (2013–2017) - Navegadores e Mobile","Kingdom Hearts III (2019) - PlayStation 4, Xbox One, PC"]
	
	Quicksort(lista, 1, length(lista))
	
	# display(lista)
	
	for name in lista
	  println(name)
	end

O código acima vai pegar uma lista de *strings* (textos), vai escolher dois e perguntar qual é o melhor. Isso será repetido até que todos os itens da lista estejam ordenados do pior ao melhor.
# Testando o código

Para testar o código, eu resolvi listar os jogos da franquia Kingdom Hearts do pior ao melhor **na minha opinião**. Primeiramente, vou listar todos os jogos lançados até o momento abaixo:

 - ✅ **Kingdom Hearts (2002)** - *PlayStation 2* 
 - ❌ **Kingdom Hearts: Chain of Memories (2004)** - *Game Boy Advance*
 - ✅ **Kingdom Hearts II (2005)** - *PlayStation 2*
 - ✅ **Kingdom Hearts Re:Chain of Memories (2007)** - *PlayStation 2*
 - ❌ **Kingdom Hearts Coded (2008)** - *Celulares*
 - ✅ **Kingdom Hearts 358/2 Days (2009)** - *Nintendo DS*
 - ✅ **Kingdom Hearts Birth by Sleep (2010)** - *PlayStation Portable (PSP)*
 - ✅ **Kingdom Hearts Re:coded (2010)** - *Nintendo DS*
 - ✅ **Kingdom Hearts 3D: Dream Drop Distance (2012)** - *Nintendo 3DS*
 - ✅ **Kingdom Hearts χ chi / Unchained χ / Union χ (2013–2017)** - *Navegadores e Mobile*
 - ❌ **Kingdom Hearts 0.2 Birth by Sleep** – A Fragmentary Passage (2017) - *PlayStation 4*
 - ✅ **Kingdom Hearts III (2019)** - *PlayStation 4, Xbox One, PC* 
 - ❌ **Kingdom Hearts Dark Road (2020)** - *Mobile*
 - ❌ **Kingdom Hearts Melody of Memory (2020)** - *PlayStation 4, Xbox One, Nintendo Switch, PC*

Os itens marcados nesta lista com um ✅ são os jogos que eu já joguei. Para fazer as comparações, considerei apenas os jogos que eu já tinha jogado. Após fazer as comparações com o auxilio do meu programa, eu obtive o seguinte resultado:

# Meu Top 9 Melhores jogos da franquia Kingdom Hearts, do pior ao melhor

## 9. Kingdom Hearts χ \[chi\] / Unchained χ / Union χ (2013–2017) - Navegadores e Mobile

![[Pasted image 20260625131953.png]]

## 8. Kingdom Hearts 3D: Dream Drop Distance (2012) - Nintendo 3DS

![[Pasted image 20260625133033.png]]
**OBS:** esta imagem passou por um upscale usando o Gemini, pois a original estava em uma resolução muito baixa.
## 7. Kingdom Hearts 358/2 Days (2009) - Nintendo DS

![[Pasted image 20260625132411.png]]

## 6. Kingdom Hearts Re:Chain of Memories (2007) - PlayStation 2 (Remake em 3D)

![[Pasted image 20260625133347.png]]

## 5. Kingdom Hearts Re:coded (2010) - Nintendo DS (Remake do Coded)

![[Pasted image 20260625133520.png]]

## 4. Kingdom Hearts (2002) - PlayStation 2

![[Pasted image 20260625133552.png]]

## 3. Kingdom Hearts Birth by Sleep (2010) - PlayStation Portable (PSP)

![[Pasted image 20260625133620.png]]

## 2. Kingdom Hearts II (2005) - PlayStation 2

![[Pasted image 20260625133758.png]]

## 1. Kingdom Hearts III (2019) - PlayStation 4, Xbox One, PC

![[Pasted image 20260625133846.png]]