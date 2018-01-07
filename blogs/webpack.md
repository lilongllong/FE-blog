# webpack在前端工程里面的优化
## 1. 对依赖模块的构成进行分析
## 2. 合理使用externals减少Bundle的体积
这件事要两方面来看，
- 一方面对于稳定性强并且需要其持续更新的类库，简而言之，我们信赖的依赖库并且其体积偏大，我们需要通过externals来避免变异这些库，减少体积并在HTML中引入官方最近的小体积的资源文件，优点也在于package.json在设置一般是自动更新包，因此当你git clone & npm install的时候你再次编译的依赖包module可能发生的变化，可能引入bug或者项目不能运行，这种方式则可以避免这种问题，且不需要再次编译。
- 另一方面，对于一些不稳定的依赖包或者你需要其更新的包或者不允许改变的依赖包，则需要在package.json中固定版本号，并编译到bundle中，避免风险

## 3. 利用happypack做多核编译资源，提升开发效率
## 4. 利用tree-shaking和Scope Hoisting减小文件
## 5.对bundle进行code split
## 6.合理使用dev-tool
## 7.使用HMR提升开发调试效率
