# Гид по стилю [![Состояние сборки](https://camo.githubusercontent.com/ff352d8acea83b3d696ecb5c86d4bfa16ce0f403/68747470733a2f2f7472617669732d63692e6f72672f68756765696e632f7374796c6567756964652e7376673f6272616e63683d6d6173746572)](https://travis-ci.org/hugeinc/styleguide)

#### Инструмент, который упрощает создание и поддержку стилей.

\##### v2.0.8

Для загрузки, как начать работу и подробную документацию см. На [веб-сайте Styleguide](http://hugeinc.github.io/styleguide/)

#### Благодаря

- [Node.js](http://nodejs.org/)
- [Harp.js](http://harpjs.com/)
- [Узел Livereload](https://www.npmjs.com/package/livereload)
- [Узел Часы](https://www.npmjs.com/package/watch)

### Известные вопросы

1 - Вы должны разрешить запуск незарегистрированных приложений для использования файла Start.app. Вы можете сделать это в настройках> Безопасность и конфиденциальность

2 - Скомпилированная версия офлайн имеет меньшую проблему в Chrome. У Chrome есть политика безопасности, запрещающая общение с iframes в файле file: //, поэтому любое взаимодействие, требующее такой связи, будет удалено (в основном меню боковой панели). Это только для автономной скомпилированной версии.

3 - Если вы пользователь Mac, и после запуска Start.app у вас есть эта ошибка:

```
npm ERR! Please try running this command again as root/Administrator.
```

Возможно, вы установили Node с правами sudo или root. Вам нужно будет установить разрешения для папки .npm со следующей командой:

```
sudo chown -R $(whoami) ~/.npm
sudo chown -R $(whoami) /usr/local/lib/node_modules
```

После этого попробуйте запустить Start.app еще раз.

4 - Если у вас установлен XCode, но вы не согласны с лицензией, вы получите эту ошибку:

```
Agreeing to the Xcode/iOS license requires admin privileges, please re-run as root via sudo.
```

Откройте XCode и примите лицензию, затем повторите попытку запуска Start.app.

5 - Если вы **получили** ошибку **404 - Нет данных** , у вас может возникнуть конфликт портов, есть два способа изменить номер порта (по умолчанию - **9241** ):

- Измените переменную PORT внутри styleguide / structure / _node-files / watch.js

- Установите переменную среды (PORT или STYLEGUIDE_PORT):

  Если вы запускаете Styleguide вручную, на последнем шаге вы можете сделать следующее:

  ```
  PORT=7000 node watch.js
  ```

  или

  ```
  STYLEGUIDE_PORT=7000 node watch.js
  ```

  Start.app является автономным, и по соображениям безопасности он не имеет доступа к внешним переменным. Если вы хотите изменить порт для Start.app, рекомендуется изменить файл watch.js. Вы можете, если хотите, добавить переменную в свой .bashrc-файл, и она будет доступна для Start.app:

  ```
  touch ~/.bashrc
  echo 'export PORT=1234' >> ~/.bashrc
  ```

  или

  ```
  echo 'export STYLEGUIDE_PORT=1234' >> ~/.bashrc
  ```
