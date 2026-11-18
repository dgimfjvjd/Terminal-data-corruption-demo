# 参与贡献

感谢你愿意改进 Phosphor Decay。这个项目刻意保持为**零依赖、无构建、单文件优先**的静态演示，提交改动时请尽量遵守这一方向。

## 可以贡献什么

- 修复兼容性、性能或无障碍问题
- 改进 `prefers-reduced-motion` 降级体验
- 优化动画时序、视觉效果和移动端布局
- 完善 README、示例和错误说明

## 本地运行

无需安装依赖。直接双击 `index.html` 即可；也可以在本目录启动静态服务器：

```bash
python -m http.server 8000
```

然后打开 `http://localhost:8000`。

## 代码约束

- 不引入框架、构建工具、CDN 或运行时依赖。
- 保持视觉效果与转场 API 向后兼容；新增配置项必须有默认值。
- 新增动画必须同时处理 `prefers-reduced-motion: reduce`，不得只关闭 CSS 而遗漏 JavaScript 定时器。
- 所有 `setTimeout`、`setInterval` 和 `requestAnimationFrame` 都必须能被 `destroy()` 清理。
- 触发入口优先使用原生可键盘操作元素，装饰层保持 `aria-hidden="true"`。
- 禁止提交密钥、本地绝对路径、用户隐私数据或来源不明的素材。

## 提交前检查

- [ ] 在 Chrome 或 Edge 中完整走通 `DECRYPT → REPLAY` 流程。
- [ ] 浏览器控制台没有 JavaScript 错误。
- [ ] 开启系统“减少动态效果”后，页面没有频闪或高频抖动。
- [ ] 桌面端与窄屏下文字、按钮和提示条均可见。
- [ ] 若修改了行为或配置，同步更新 `README.md`。

## Pull Request

请保持每次 PR 聚焦一个问题，说明复现步骤、改动内容和验证环境。涉及视觉变化时，建议附上截图或短录屏。