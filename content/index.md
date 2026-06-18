---
title: Pedroh99z - Wiki
---

Bem-vindo a minha Wiki pessoal. Aqui estão reunidos meus trabalhos, minhas aulas, listas de exercícios, etc, para fácil acesso. Para encontrar qualquer tipo de conteúdo, basta pesquisar por termos relevantes, ou procurar no explorador. Esta Wiki está em constante desenvolvimento, então novos conteúdos, bem como correções, podem chegar a qualquer momento.

---

#### 🎵 Música de fundo (vai tocar assim que você interagir com a página):
<div id="player-escondido"></div>

<div id="player-escondido"></div>

<div id="player-escondido"></div>
<div id="player-escondido"></div>

<script>
// sim, aqui eu fui preguiçoso e fiz vibe coding mesmo
(function() {
    var vol = 2; 
    var player;
    var intervaloSalvamento;
    var usuarioJaInteragiu = false; // Controle rigoroso de interação

    // 1. Carrega a API do YouTube apenas uma vez se não existir
    if (!window.YT) {
        var tag = document.createElement('script');
        tag.src = "https://www.youtube.com/iframe_api";
        var firstScriptTag = document.getElementsByTagName('script')[0];
        firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);
    }

    // 2. Esta função SÓ é chamada quando o usuário REALMENTE interage
    function forcarInicializacaoComSom() {
        usuarioJaInteragiu = true;

        // Remove os ouvintes para não disparar em cliques futuros
        window.removeEventListener('pointerdown', forcarInicializacaoComSom);
        window.removeEventListener('keydown', forcarInicializacaoComSom);

        var playerDiv = document.getElementById('player-escondido');
        if (!playerDiv) return;

        // Se o player já existe (ex: voltou de outro link), só dá o play
        if (player && typeof player.playVideo === 'function') {
            player.unMute();
            player.setVolume(vol);
            player.playVideo();
            iniciarSalvamentoTempo();
            return;
        }

        // Se não existe, CRIA o player agora, direto com som e play legítimo
        player = new YT.Player('player-escondido', {
            height: '315',
            width: '560',
            videoId: 'Ey8wSKvxWfI',
            playerVars: {
                'autoplay': 1, // Aqui pode ser 1 porque o usuário ACABOU de interagir na página
                'loop': 1,
                'playlist': 'Ey8wSKvxWfI',
                'controls': 1,
                'showinfo': 0,
                'rel': 0
            },
            events: {
                'onReady': function(event) {
                    event.target.unMute();
                    event.target.setVolume(vol);
                    
                    // Recupera o tempo salvo do localStorage se houver
                    var tempoSalvo = localStorage.getItem('tempo_musica_fundo');
                    if (tempoSalvo) {
                        event.target.seekTo(parseFloat(tempoSalvo), true);
                    }
                    
                    event.target.playVideo();
                    iniciarSalvamentoTempo();
                }
            }
        });
    }

    // Função que salva o progresso do vídeo a cada 1 segundo
    function iniciarSalvamentoTempo() {
        clearInterval(intervaloSalvamento);
        intervaloSalvamento = setInterval(function() {
            if (player && typeof player.getCurrentTime === 'function' && player.getPlayerState() === YT.PlayerState.PLAYING) {
                var tempoAtual = player.getCurrentTime();
                localStorage.setItem('tempo_musica_fundo', tempoAtual);
            }
        }, 1000);
    }

    // Gerenciador de rotas do Quartz
    function gerenciarNavegacaoQuartz() {
        var playerDiv = document.getElementById('player-escondido');
        if (!playerDiv) {
            clearInterval(intervaloSalvamento);
            return;
        }

        // Se o usuário já interagiu nesta sessão do site antes, podemos restabelecer o vídeo direto
        if (usuarioJaInteragiu && window.YT && window.YT.Player) {
            forcarInicializacaoComSom();
        } else {
            // Se ele ainda não interagiu nesta página/sessão, bota os ganchos de espera
            window.addEventListener('pointerdown', forcarInicializacaoComSom);
            window.addEventListener('keydown', forcarInicializacaoComSom);
        }
    }

    // Define a função global da API do YouTube
    window.onYouTubeIframeAPIReady = function() {
        gerenciarNavegacaoQuartz();
    };

    // Escuta as navegações do Quartz (voltar/avançar notas)
    document.addEventListener("nav", gerenciarNavegacaoQuartz);

    // Configuração inicial ao abrir a página pela primeira vez
    window.addEventListener('pointerdown', forcarInicializacaoComSom);
    window.addEventListener('keydown', forcarInicializacaoComSom);
})();
</script>