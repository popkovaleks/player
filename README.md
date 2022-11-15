# Пример видеоплеера в браузере

Видеоплеер создан с помощью [библиотеки](https://github.com/devmanorg/video-player-jslib), основанной на базе библиотеки [Playable](https://wix.github.io/playable/).
 
<a href="https://popkovaleks.github.io/player/" target="_blank">Пример работы</a>

 ![Пример работы](https://github.com/popkovaleks/player/blob/main/screenshots/Снимок%20экрана%202022-11-11%20в%2002.19.22.png?raw=true)

 # Как встроить на страницу
Необходимо скачать файл [player.js](/player.js) и папку font-awesome положить их в директорию с проектом, например, туда, где у вас находится статика.
Затем в документе html необходимо подключить шрифты внутри тега head:
```
<link rel="stylesheet" href="путь_до_папки/font-awesome/css/font-awesome.min.css">
```

 Для того чтобы встроить плеер на страницу, необходимо из файла [index.html](/index.html) скопировать из тега body контейнер класса video-player и вставить его там, где он должен находиться.
 ```
 <div class="video-player" id="player">
        <div class="js-video-container video-player-container"></div>
        <div class="video-player-control-panel">
            <button class="control-panel-button js-play-button"><i class="fa fa-play" aria-hidden="true"></i></button>
            <button class="control-panel-button js-pause-button" hidden><i class="fa fa-pause" aria-hidden="true"></i></button>
            <button class="control-panel-button js-mute-button" hidden><i class="fa fa-volume-up" aria-hidden="true"></i></button>
            <button class="control-panel-button js-volume-button" hidden><i class="fa fa-volume-off" aria-hidden="true"></i></button>
            <div class="control-panel-space"></div>
            <button class="control-panel-button js-fullscreen-button"><i class="fa fa-expand" aria-hidden="true"></i></button>
        </div>
    </div>
 ```

Внизу, перед закрытием тега body необходимо подключить скрипты:
```
 <script src="https://code.jquery.com/jquery-3.4.1.min.js"></script>
    <script src="https://unpkg.com/playable@2.10.3/dist/statics/playable.bundle.min.js"></script>
    <script src="player.js"></script>
    
    <script type="text/javascript">
      createPlayer({elementId: 'player'});
    </script>
```

Затем нужно добавить стили, они находятся также в файле [index.html](/index.html). Стили можно вставить аналогично на страницу или в файл css со стилями.

# Как проигрывать другое видео
Для того чтобы проигрывать другое видео, необходимо указать на него ссылку через параметр.
```
<script type="text/javascript">
  createPlayer({
    elementId: 'player',
    src: 'https://dvmn.org/media/filer_public/d0/16/d016d9b8-4180-4bb9-ad83-0241f61627b8/samsung_demo_-_alive_in_color.mp4'
});
</script>
```