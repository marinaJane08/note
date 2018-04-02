- 窗体`require('electron').remote.BrowserWindow`创建与管理浏览器窗口
    - on():unresponsive,responsive
    - show(),focus(),getSize(),getPosition(),close()
    - loadURL()
    - webContents
        - on():crashed,context-menu
- 处理路径`require('path')`
- 弹出框`require('electron').remote.dialog`
    - showMessageBox
- 进程`process`
    - crash(),hang()
    - platform
- 主进程`app`
    - on():ready,browser-window-created,window-all-closed,browser-window-created
    - getVersion()
    - emit()
- 菜单`electron.Menu`
    - setApplicationMenu(Menu.buildFromTemplate(template))
    - popup()
- 上下文菜单`electron.MenuItem`
- 进程通信`electron.ipcMain`
    - on():show-context-menu
- 自动更新`autoUpdater`
- 壳`shell`
    - openExternal()
- 帮助菜单的区别，加速器设置的区别，设置与首选项的区别
- **vue-cli**的**elctron-vue**模板安装
    - **ESLint、Karma、Mocha、Spectron**等测试工具
    - `karma`是测试运行框架，供`mocha、jasmine`测试框架运行，主要是监控文件与配合`karma-coverage`展示代码覆盖率，与`babel-plugin-istanbul`结合可去除其它文件对覆盖率的影响
- **electron-packager/electron-builder**（是安装文件/可执行文件、是否有源码、是否可以[自动打包发布](https://simulatedgreg.gitbooks.io/electron-vue/content/cn/using-electron-builder.html)
- 进行开发环境`管理员权限`install
    - **yarn**包管理器与npm相比：离线缓存使速度提升，锁住依赖包的版本，并行安装
        - **yarn指令**yarn/yarn install安装包、global全局、add [--dev]添加、upgrade @[version]/@[tag]、remove、license、why、init
- `src/main`主进程：
    - 开发环境：开发工具、载入主文件
    - 主进程（ready、全关闭、再激活、更新检查）、窗口（窗口实例、打开文件、关闭事件）、global全局数据
- `pack`脚本将打包应用（当前OS）的可运行文件包、`build/*-unpacked/`
- `build`脚本将打包四个不同系统的可运行文件包、`build/*-OS-x64`