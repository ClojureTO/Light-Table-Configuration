## Enabling paredit mode in Light Table

Open Light Table, use `<ctrl>+<space>` to open the menu then
type in `user keymap` in the search prompt and press `<enter>`.

Replace the contents of the file with the following:

```clojure
[
 [:editor "shift-pmeta-down" :paredit.select.clear]
 [:editor "alt-shift-w" :editor.watch.unwatch]
 [:editor "pmeta-shift-," :paredit.shrink.right]
 [:editor "pmeta-shift-." :paredit.grow.right]
 [:editor "alt-s" (:paredit.select.parent "(") :smart-indent-selection :paredit.select.clear]
 [:editor "alt-w" :editor.watch.watch-selection]
 [:editor "alt-enter" (:paredit.select.parent "(") :eval-editor-form :paredit.select.clear]
 [:editor "shift-pmeta-up" :paredit.select.parent]
]
```

Save the file to apply changes.

Next, repeat the process and search for `user behaviors`, then paste
the following configuration there:

```clojure
[
 [:app :lt.objs.style/set-skin "dark"]
 [:app :lt.objs.sidebar.workspace/workspace.open-on-start]
 [:app :-lt.objs.intro/show-intro]

 [:editor :lt.objs.editor/no-wrap]
 [:editor :lt.plugins.rainbow/hide-rainbow-parens]
 [:editor :lt.objs.editor/line-numbers]

 [:editor.clojure :lt.objs.langs.clj/print-length 1000]
 [:app :lt.objs.settings/pair-keymap-diffs]
]
```

Save the file to apply changes.

Once this is done, you should be able to grow and shrink selection  by pressing
`<cmd>+<shift>+<up>/<down>`.

You should be able to evaluate code by pressing `<cmd>+<enter>`.
