## [0.8.21](https://github.com/warpech/jquery-handsontable/tree/v0.8.21) (Apr 24, 2013)

Feature:
- [Fixed rows & columns](http://handsontable.com/demo/fixed.html)

Bugfix:
- focusCatcher produced a 1x1 px red pixel in top left corner

## [0.8.20](https://github.com/warpech/jquery-handsontable/tree/v0.8.20) (Apr 19, 2013)

Bugfixes:
- source parameter should be `edit` when cell value is changed through editor ([#566](https://github.com/warpech/jquery-handsontable/issues/566))
- getRowHeaders returns NaN when no argument given - should return array of all row headers ([#568](https://github.com/warpech/jquery-handsontable/issues/568), [#352](https://github.com/warpech/jquery-handsontable/issues/352))
- getColHeaders returns NaN when no argument given - should return array of all column headers ([#569](https://github.com/warpech/jquery-handsontable/issues/569), [#382](https://github.com/warpech/jquery-handsontable/issues/382))
- selected area class name was not applied on scrolling (tdCache was not bound to instance)
- fix cell focusing problems ([#549](https://github.com/warpech/jquery-handsontable/issues/549), [#506](https://github.com/warpech/jquery-handsontable/issues/506), [#573](https://github.com/warpech/jquery-handsontable/issues/573))
- currentRowClassName and currentColClassName not kept while scrolling ([#455](https://github.com/warpech/jquery-handsontable/issues/455))

Other:
- refactor row and column header DOM operations to be consistently defined in `tableView.js`
- remove `asyncRendering` mode that was causing more trouble than benefit
- as the result, code is now 100 lines shorter and more stable!

## [0.8.19](https://github.com/warpech/jquery-handsontable/tree/v0.8.19) (Apr 12, 2013)

Bugfix:
- table width was not correctly read from container width

## [0.8.18](https://github.com/warpech/jquery-handsontable/tree/v0.8.18) (Apr 12, 2013)

Features:
- added "Maximize HOT table" button in first example on [Scroll demo](handsontable.com/demo/scroll.html) page ([#495](https://github.com/warpech/jquery-handsontable/issues/495))

Bugfixes:
- clicking on checkbox renderer does not change state ([#543](https://github.com/warpech/jquery-handsontable/issues/543))
- checkbox readonly is not working ([#555](https://github.com/warpech/jquery-handsontable/issues/555))

Other:
- refactored Walkontable code that measures column width strategy (for better performance and stability)
- moved reading DOM settings from tableView.js core.js (new method `parseSettingsFromDOM`)

## [0.8.17](https://github.com/warpech/jquery-handsontable/tree/v0.8.17) (Mar 31, 2013)

Features:
- performance: remove jQuery dependency from many places
- performance: in cell renderers, replace `innerHTML` with `createTextNode`
- better integration with Twitter Bootstrap (fixes [#78](https://github.com/warpech/jquery-handsontable/issues/78))

Bugfixes:
- empty cell not shown in Firefox when not in standards mode ([#418](https://github.com/warpech/jquery-handsontable/issues/418)). This is questionable as a bug but anyway we fixed it.
- continued fix for #461
- fix problems when removing rows/columns using context menu ([#523](https://github.com/warpech/jquery-handsontable/pull/523))

Other:
- new editor inheritance model ([#516](https://github.com/warpech/jquery-handsontable/pull/516))
- `src/3rdparty/walkontable.js` has been divided into many source files in `src/3rdparty/walkontable/src/*`. Build process is updated to use Walkontable source files now
- 3 Grunt test tasks are available now: `grunt test`, `grunt test:handsontable`, `grunt test:walkontable`

## [0.8.16](https://github.com/warpech/jquery-handsontable/tree/v0.8.16) (Mar 26, 2013)

Features:
- [Handsontable in Handsontable editor](http://handsontable.com/demo/handsontable.html)
- performance and code quality fixes
- `height` and `width` settings can now be functions (that return a number)

Bugfixes:
- autocomplete menu did not reset `<li>` margin
- `destroy()` of one Handsontable instance made other instances on the same page unfunctional
- Autocomplete (Bootstrap Typeahead) did not allow empty string as a value ([#254](https://github.com/warpech/jquery-handsontable/issues/254))
- outsideClickDeselects : false disables all focus in other inputs outside the table ([#408](https://github.com/warpech/jquery-handsontable/issues/408))
- can't scroll all the way horizontally ([#430](https://github.com/warpech/jquery-handsontable/issues/430))
- scrollable Handsontable does not work well with Twitter Bootstrap ([#224](https://github.com/warpech/jquery-handsontable/issues/224))
- weirdly shrinking table when height attribute was not set ([#461](https://github.com/warpech/jquery-handsontable/issues/461))

Other:
- trying to load a string as a data source now throws an error

## [0.8.15](https://github.com/warpech/jquery-handsontable/tree/v0.8.15) (Mar 18, 2013)

Features:
- new callbacks: `onSelectionEnd` and `onSelectionEndByProp` (see [README.md](https://github.com/warpech/jquery-handsontable) for usage information)
- new demo page [Callbacks](http://handsontable.com/demo/callbacks.html)
- **breaking change:** `getSelected` method output has slightly changed. Was: [`topLeftRow`, `topLeftCol`, `bottomRightRow`, `bottomRightCol`]. Is: [`startRow`, `startCol`, `endRow`, `endCol`]. This gives information about the direction of the selection - now you can tell if the selection started from left to right or otherwise.

Bugfixes:
- `outsideClickDeselects: false` disables all focus in other inputs outside the table ([#408](https://github.com/warpech/jquery-handsontable/issues/408))
- copy paste in Mac Safari didn't work ([#470](https://github.com/warpech/jquery-handsontable/issues/470))
- table jumps back and forth when scrolling ([#432](https://github.com/warpech/jquery-handsontable/issues/432))
- destroy doesn't unload context menu functionality ([#434](https://github.com/warpech/jquery-handsontable/issues/434))
- throwed error when Enter key was pressed on autocomplete cell in the last row ([#497](https://github.com/warpech/jquery-handsontable/issues/497))
- Autocomplete in strict mode allows values other than predefined ([#405](https://github.com/warpech/jquery-handsontable/issues/405))

## [0.8.14](https://github.com/warpech/jquery-handsontable/tree/v0.8.14) (Mar 14, 2013)

Features:
- now, your data source can be a function! See the last section of the [Array, object and function data sources](http://handsontable.com/demo/datasources.html) page for examples (fixes [#471](https://github.com/warpech/jquery-handsontable/pull/471), [#435](https://github.com/warpech/jquery-handsontable/pull/435), [#261](https://github.com/warpech/jquery-handsontable/issues/261))
- also the column `data` property can be a function as well! Again, see the last section of the [data sources](http://handsontable.com/demo/datasources.html) page for examples
- new methods: `countEmptyRows`, `countEmptyCols`, `isEmptyRow`, `isEmptyCol`. You can define your own functions for `isEmptyRow` and `isEmptyCol` (see [README.md](https://github.com/warpech/jquery-handsontable) for details)

Bugfix:
- replace reference to non-existent Exception with Error ([#494](https://github.com/warpech/jquery-handsontable/pull/494))
- textarea copyPaste covering page elements ([#488](https://github.com/warpech/jquery-handsontable/issues/488), [#490](https://github.com/warpech/jquery-handsontable/issues/490))

## [0.8.13](https://github.com/warpech/jquery-handsontable/tree/v0.8.13) (Mar 12, 2013)

This release adds a `min-width: 600px` to the test suite to make sure that 100% of current tests are passing in [Travis CI](https://travis-ci.org/warpech/jquery-handsontable) (PhantomJS) as well as in the desktop browsers.

There are still many bugs to be fixed, but now it should be much easier to keep the increasing quality of future versions.

## [0.8.12](https://github.com/warpech/jquery-handsontable/tree/v0.8.12) (Mar 12, 2013)

This release doesn't really bring any improvements for the end user but is a big step towards test automation. From now on, a push to the `master` branch triggers a [Travis CI](https://travis-ci.org/warpech/jquery-handsontable) build that performs automated testing using [grunt-contrib-jasmine](https://github.com/gruntjs/grunt-contrib-jasmine). Thanks @bollwyvl for your [help](https://github.com/warpech/jquery-handsontable/pull/474)!

As a side effect, tests are now be runnable using PhantomJS. To run the test suite in PhantomJS, type `grunt test` (first run `npm install` to make sure you have all dependencies installed). PhantomJS runs the test suite much faster than desktop browsers, so it may come handy.

Bugfixes:
- `destroy` method now clears all pending timeouts

## [0.8.11](https://github.com/warpech/jquery-handsontable/tree/v0.8.11) (Mar 8, 2013)

Features:
- this may be a **breaking change** for some applications: Now the third parameter to the `alter` method tells the amount of rows/columns to be inserted/removed. This adds more consistency to the API. ([#368](https://github.com/warpech/jquery-handsontable/issues/368), [67fe67c](https://github.com/warpech/jquery-handsontable/commit/67fe67c3cf6bf4df47c02ea8c7aa6802864e97de))
- merged pull request [#474](https://github.com/warpech/jquery-handsontable/pull/474) - Travis-CI integration. The tests don't pass yet but don't worry about it yet. It is a work in progress on complete test automation. Making all tests pass on Travis CI headless browser may take few more days or weeks :)

Bugfix:
- again, this may be a **breaking change** for some applications: Fix very long standing inconsistency. Restored original `setDataAtCell` requirement of the second parameter to be a column number (as described in [README.md](https://github.com/warpech/jquery-handsontable) since always). If you happen to experience an error in `setDataAtCell` after upgrade, change your usage of this method to the new method `setDataAtRowProp` ([#284](https://github.com/warpech/jquery-handsontable/issues/284), [90e1b67](https://github.com/warpech/jquery-handsontable/commit/90e1b6765cf3aa6e0e5c5a9156b9d45da74fa055))
- new methods `setDataAtRowProp` and `getDataAtRowProp` that set/get data according to the property name in data source. See [README.md](https://github.com/warpech/jquery-handsontable) for clarification ([#284](https://github.com/warpech/jquery-handsontable/issues/284), [90e1b67](https://github.com/warpech/jquery-handsontable/commit/90e1b6765cf3aa6e0e5c5a9156b9d45da74fa055))
- merged pull request [#266](https://github.com/warpech/jquery-handsontable/pull/266) - fix countCols for arrays with column settings

## [0.8.10](https://github.com/warpech/jquery-handsontable/tree/v0.8.10) (Mar 7, 2013)

Bugfix:
- inline cell styles applied by cell renderer were not removed on table scroll ([#353](https://github.com/warpech/jquery-handsontable/issues/353), [#376](https://github.com/warpech/jquery-handsontable/issues/376), [a9b328d](https://github.com/warpech/jquery-handsontable/commit/a9b328d2fcbcb7e7a05f1d2494a1f9062bd17a37))

Docs:
- simplify CSS for demo pages (get rid of `bottomSpace` classes)
- refresh the style of jsFiddle links

## [0.8.9](https://github.com/warpech/jquery-handsontable/tree/v0.8.9) (Mar 6, 2013)

This is a feature release of a new cell type. For people waiting for some bug fixes, I promise next release will focus on fixing some important bugs!

Features:
- **Date cell type**. Updated pages [Date](http://handsontable.com/demo/date.html) and [Cell types](http://handsontable.com/demo/renderers.html). Solves issue [#431](https://github.com/warpech/jquery-handsontable/issues/431)
- refactored the `text`, `autocomplete` and `date` cell editors to share as much code as possible

## [0.8.8](https://github.com/warpech/jquery-handsontable/tree/v0.8.8) (Mar 4, 2013)

Bugfixes:
- `startRows`/`startCols` option did not work as described in README.md. This parameters should be only taken into account when NO data source is provided ([5c865ba](https://github.com/warpech/jquery-handsontable/commit/5c865ba15dcb7d9f93a47b14aedfc96751bcbb7a))
- finish editing should move the focus aways from textarea to table cell ([f4f6496](https://github.com/warpech/jquery-handsontable/commit/f4f649600311ba527c19dc2e8f73af2e764c54d6))

## [0.8.7](https://github.com/warpech/jquery-handsontable/tree/v0.8.7) (Mar 1, 2013)

Bugfixes:
- use default cell editor for a cell that has declared only cell renderer ([#453](https://github.com/warpech/jquery-handsontable/issues/453), [a5c61a2](https://github.com/warpech/jquery-handsontable/commit/a5c61a26b9e833abd25afa31aee4199cc6810590))
- copy/paste did not work on Mac since 0.8.6 ([#348](https://github.com/warpech/jquery-handsontable/issues/348), [463d5c9](https://github.com/warpech/jquery-handsontable/commit/463d5c918b85b2dc74df2669047134c23ae15fcc))
- global shortcuts (like CTRL+A) should be blocked when cell is being edited ([8363008](https://github.com/warpech/jquery-handsontable/commit/8363008c3756ea869f50b2ad8a213839a50ad807))
- numeric cell editor did not convert cell data to number type when data source was an object ([b09f6d3](https://github.com/warpech/jquery-handsontable/commit/b09f6d3666d238ac0ae849937152baffa6fb2824))
- another attempt to solve scrolling to the top of table on any key press if the top is not on the screen ([#348](https://github.com/warpech/jquery-handsontable/issues/348), [d37859b](https://github.com/warpech/jquery-handsontable/commit/d37859b6acdaef0be8b886b33404144c7cf21227))

## [0.8.6](https://github.com/warpech/jquery-handsontable/tree/v0.8.6) (Feb 27, 2013)

Features:
- **Numeric cell type**. Updated pages [Numeric](http://handsontable.com/demo/numeric.html) and [Column sorting](http://handsontable.com/demo/sorting.html). Solves issues [#443](https://github.com/warpech/jquery-handsontable/issues/443), [#397](https://github.com/warpech/jquery-handsontable/issues/397), [#336](https://github.com/warpech/jquery-handsontable/issues/336). Partially solves issue [#121](https://github.com/warpech/jquery-handsontable/issues/121) ([a052013](https://github.com/warpech/jquery-handsontable/commit/a052013049ccf6ca75a7104ddeaaec2f84961f93))
- autoColumnSize feature is now aware of renderer functions (before this, cells rendered with autocomplete and numeric renderer were too narrow) ([7770f8a](https://github.com/warpech/jquery-handsontable/commit/7770f8a499e5c21891308bdb4d1111bfc79dd2dc))

Bugfix:
- scrolls to top of table on any key press if the top is not on the screen ([#348](https://github.com/warpech/jquery-handsontable/issues/348), [290cde9](https://github.com/warpech/jquery-handsontable/commit/290cde93503686f1a89e5533662e3c9ca80d880e), [408f29d](https://github.com/warpech/jquery-handsontable/commit/408f29d6a65e797572adf45873780c3adfc0bf4d))
- cell editor was using a wrong cell value if column order was manually changed ([#367](https://github.com/warpech/jquery-handsontable/issues/367))
- cell editor dimensions were not refreshed if table was rerendered during editing
- fix recalculation of container dimensions after window resize ([#400](https://github.com/warpech/jquery-handsontable/issues/400), [#428](https://github.com/warpech/jquery-handsontable/issues/428))

Other:
- reimplement cell editing abstraction. Now TextEditor `<textarea>` is decoupled from cell selection and copy/paste keyboard handling ([14e4cc1](https://github.com/warpech/jquery-handsontable/commit/14e4cc1d61d92b49317aed53604b87cdd1f522b0), [1eb01bd](https://github.com/warpech/jquery-handsontable/commit/1eb01bdcc975dec4fe8f2557a668d057d34b65d2), [f2b412f](https://github.com/warpech/jquery-handsontable/commit/f2b412f50027d3b4594bef464994ca8ad4f551a6), [e5af5d7](https://github.com/warpech/jquery-handsontable/commit/e5af5d7c8cbd8990398e8029c2955d7f8e22386c))
- upgrade Bootstrap Typeahead to v2.3.0
- build system now requires Grunt 0.4.0 (read instructions how to upgrade here: http://gruntjs.com/upgrading-from-0.3-to-0.4) ([3ebed1d](https://github.com/warpech/jquery-handsontable/commit/3ebed1ddb771b1d21ebf810f82df004755d420f4), [6d01ae5](https://github.com/warpech/jquery-handsontable/commit/6d01ae528ed84171d72f34eb3f25f4137f96a7ec))

## [0.8.5](https://github.com/warpech/jquery-handsontable/tree/v0.8.5) (Feb 18, 2013)

Bugfix:
- clear currentRowClassName and currentColumnClassName when refreshing selections ([#398](https://github.com/warpech/jquery-handsontable/issues/398), [8df5de9](https://github.com/warpech/jquery-handsontable/commit/8df5de9a345a650a8e588bc4fe3da5d3e2075972)) - thanks @jaycfields

## [0.8.4](https://github.com/warpech/jquery-handsontable/tree/v0.8.4) (Feb 17, 2013)

Features:
- add $.browser shim for compatibility with jQuery 1.9 ([#378](https://github.com/warpech/jquery-handsontable/issues/378), [#389](https://github.com/warpech/jquery-handsontable/issues/389), [13d72c8](https://github.com/warpech/jquery-handsontable/commit/13d72c8cb10f733e1149f71f156a6c6a4f8cb3dc))

Other:
- add jQuery Plugins Registry manifest file

## [0.8.3](https://github.com/warpech/jquery-handsontable/tree/v0.8.3) (Jan 23, 2013)

Features:
- optimize jquery-autoresize plugin: arclones element is emptied before injecting another node
- new configuration options `currentRowClassName` and `currentColClassName` along with new example page [Highlight current row & column](http://handsontable.com/demo/current.html) [TODO: write tests]
- [Manual column resize](http://handsontable.com/demo/column_resize.html)
- [Column sorting](http://handsontable.com/demo/sorting.html)
- compability: automatic column size is asserted `true` when `colWidths` option is not provided
- apply automatic column size when double clicked on manual resize handle [TODO: write tests]
- Scroll example page describes difference between available [column stretching modes](http://handsontable.com/demo/scroll.html) (all, last [default], none)
- manual column move

Breaking changes:
- `loadData` no longer sends list of changes to `onChange` callback. That was not performant. Now if sends `null` changes object and `loadData` as source string.

Bugfixes:
- overflow auto only worked when declared in inline style (not in CSS class) (issue #339 point 6)
- during initialization, sliders were shown for a while in the top left corner
- scrolling issues (#343, #331, partially #360)
- deselection when param `outsideClickDeselects` set to true (issue #351)
- order of callbacks when clicked outside of a cell (issue #269)
- context menu was shown when clicked outside of the table (issue #306)

## [0.8.2](https://github.com/warpech/jquery-handsontable/tree/v0.8.2) (Jan 7, 2013)

Features:
- new options `copyRowsLimit`, `copyColsLimit` and callback `onCopyLimit`. The options configure the amount of rows and columns that can be copied to clipboard (default 1000). The callback will ba called if the limit is exceeded (response to an issue first reported by @itanex / #295)
- performance fixes for selecting all cells (CTRL+A)
- auto width [TODO: write more]
- auto stretch [TODO: write more]

Bugfix:
- `selectCells` did not perform multiple selection when given 4 parameters

## [0.8.1](https://github.com/warpech/jquery-handsontable/tree/v0.8.1) (Jan 6, 2013)

Bugfixes:
- fixed error when loading a new data source with fewer rows/columns
- using `minCols` with `columns` option caused an infinite loop. Now `columns` length sets a fixed number of columns (options `startCols`, `minCols`, `maxCols` will be ignored when `columns` is set) (fix #334)
- onChange was triggered before data was rendered (fix #333)
- public `destroy` method did not unbind Handsontable events (fix #335)
- fix error when data row was externally removed while scrolling

Other changes:
- [Custom HTML demo page](http://handsontable.com/demo/renderers_html.html) (Rendering custom HTML in header) did not work well
- JSFiddle links now also work in [Context Menu demo page](http://handsontable.com/demo/contextmenu.html)
- tests are now passing 100% in Chrome, FF, IE9 and Opera. Tests are 99% passing in IE7-8, but remaining 1% does not affect normal operation in these browsers

## [0.8.0](https://github.com/warpech/jquery-handsontable/tree/v0.8.0) (Jan 2, 2013)

After series of bugfixes in last 3 beta version, this is the first stable release in 0.8.x branch. From now on, I will try to update critical issues more frequently.

New features since 0.8.0-beta3:
- new methods `rowOffset`, `colOffset`, `countVisibleRows`, `countVisibleCols`
- new callback `onCreateRow` [TODO: write tests]
- `dataSchema` can now be a function that returns object/array [TODO: write tests]
- when using `overflow: auto`, only relevant scrollbars should be displayed (first reported by @dansabirov / #295)
- fixed scrolling with arrow keys
- column title can be given as `columns[].title` (not only colHeaders[]) [TODO: write tests]
- column width can be given as `columns[].width` (not only colWidths[]) [TODO: write tests]
- column type can be set using simple strings: `autocomplete`, `checkbox`

Other changes:
- public methods `colCount`, `rowCount` are removed. Use `countRows()` and `countCols()` public methods instead
- public methods `setCellReadOnly`, `setCellEditable` are removed. Use `readOnly` cell property to make a cell read-only. See `demo/readonly.html` for examples
- options `minWidth`, `minHeight` are removed. Their definitions were to blurry and usage case too limited. Use `width` and `height` options instead and provide as many rows/columns in your data source as you need
- add `render` method to README.md

Bugfixes since 0.8.0-beta3:
- enter on last row/col should add more rows/cols if minSpareRows/minSpareCols > 0
- double clicking on fill handle fills the column to the last non-empty row
- pressing enter/tab in autocomplete moves to next row/column
- CTRL+A works slow on large data sets (as reported by @brivazac / #295)
- CTRL+A, CTRL+C sequence did not work well if CTRL was not released
- page up/page down worked wrongly

Known issues:
- clicking on cell & row borders has no effect (first reported by @cscribner / #295)
- copy of large selection (5k, 10k, 100k rows etc) freezes IE8 (first reported by @itanex / #295). Below 1k rows works fine. The only solution I can think of right now is to set copy limit in IE8 to 1000 rows.
- paste of large selection (100k rows) freezes Firefox (first reported by @ravio / #303)
- autocomplete does not work with empty field in source; autocomplete strict mode looks broken (as reported by @MDron / #303)
- scrolling mouse wheel/page up/page down should not block the window scroll if the first row/last row was reached
- page up/page down does not behave exactly as in Google Docs (moves selected cell to first visible row). This is because transformStart implies scrollToCell. It should be decoupled sometime in future

## [0.8.0-beta3](https://github.com/warpech/jquery-handsontable/tree/v0.8.0-beta3) (Dec 18, 2012)

Beta preview has been updated: http://handsontable.com/0.8.0/

Bugfixes since 0.8.0-beta2:
- fixed scrolling with touchpad (as reported by @codename- / #303)
- fixed double click on cell (as reported by @MDron, @ravio / #303)
- CTRL+A then Delete did not remove redundant empty rows in scroll example (as reported by @ravio / 303)
- fill handle (drag-down) feature is currently broken (as reported by @chaowarat / 301)
- CTRL+Enter while editing multiselection did not work (should apply the value to all the selected cells)
- now works in IE7

Other changes since 0.8.0-beta2:
- removed `jquery.ui.position.js` from `jquery.handsontable.full.js`, because it seems to have no effect (explained in `demo/contextmenu.html`)

## [0.8.0-beta2](https://github.com/warpech/jquery-handsontable/tree/v0.8.0-beta2) (Dec 14, 2012)

Beta preview has been updated: http://handsontable.com/0.8.0/

New features since 0.8.0-beta1:
- now the table is rendered even faster with `requestAnimationFrame`

Bugfixes since 0.8.0-beta1:
- fixed known issue "selecting an area and clicking one of its cells within 500 ms starts editing of that cell"
- fixed known issue "table width and height is now configured using `width` and `height` settings"
- fixed error when clicking on row/column header (related to @cscribner / #295)
- fix copy-paste in Chrome (thanks @ravio  / #295)
- `getRowHeader()` referenced to colHeaders instead of rowHeaders (thanks @marint / #295)
- fix performance of `loadData` (thanks @codename- / #295)
- now works in IE8, still not yet in IE7

## [0.8.0-beta1](https://github.com/warpech/jquery-handsontable/tree/v0.8.0-beta1) (Dec 11, 2012)

Beta of new upcoming version 0.8.0 can be previewed here: http://handsontable.com/0.8.0/

Features:
- completely new rendering engine codenamed "Walkontable" that uses a `canvas` type approach to draw the visible part of the table on screen. Works smoothly even with data sources above 100 000k rows.

Bugfixes:
- fixed CSS problems with Foundation framework

Other changes:
- Handsontable core properties `colCount`, `rowCount` do not exist anymore. Use `countRows()` and `countCols()` public methods instead

## [0.7.5](https://github.com/warpech/jquery-handsontable/tree/v0.7.5) (Nov 26, 2012)

Features:

- new settings: `minRows`, `minCols`, `maxRows`, `maxCols` (fixes [#225](https://github.com/warpech/jquery-handsontable/issues/225))
- `startRows` and `startCols` should now be only used to define how many empty rows should be created on grid initialization
- now you can use `columns` to configure number of autocomplete items (fixes [#242](https://github.com/warpech/jquery-handsontable/issues/242))

Bugfixes:

- `loadData` now will remove empty rows from grid if new data source has less rows
- new rows are now correctly created when using nested object data source ([#255](https://github.com/warpech/jquery-handsontable/pull/255))
- copy and paste issues with nested object data source ([#250](https://github.com/warpech/jquery-handsontable/issues/250))

## [0.7.4](https://github.com/warpech/jquery-handsontable/tree/v0.7.4) (Nov 19, 2012)

Bugfixes:

- fix error when pasting values to a grid with dataSchema (issue #237)
- loadData should remove empty row if source data has more empty rows than allowed by minSpareRows (issue #239)
- textarea dimensions were not updated if grid was rerendered while editing

## [0.7.3](https://github.com/warpech/jquery-handsontable/tree/v0.7.3) (Nov 14, 2012)

Features:

- big news: build now contains full and minified JS and CSS packages. See [dist/](https://github.com/warpech/jquery-handsontable/tree/master/dist) directory for details.
- added experimental "Edit in jsFiddle" link in [autocomplete example](http://handsontable.com/demo/autocomplete.html). If no issues are observed, I will add it to all example pages.

Bugfixes:

- fixed [issue with setCellReadOnly](http://stackoverflow.com/questions/13127501/sets-cell-to-be-readonly) that was reported on Stack Overflow.
- fixed performance issue with cells being rendered twice in `loadData` (issue #233)

## [0.7.2](https://github.com/warpech/jquery-handsontable/tree/v0.7.2) (Nov 12, 2012)

Fixes exeption when editing cell in IE8 (issue #232) and problems when using Autocomplete with Ajax.

Added Ajax example on [autocomplete.html](handsontable.com/demo/autocomplete.html)

## [0.7.1](https://github.com/warpech/jquery-handsontable/tree/v0.7.1) (Nov 9, 2012)

Mosty fixes for the Autocomplete feature as well as a new (easier) syntax for the Autocompelte. See [autocomplete.html](http://handsontable.com/demo/autocomplete.html) for examples. Old syntax should still work due to the [legacy layer](https://github.com/warpech/jquery-handsontable/blob/master/src/plugins/legacy.js).

Features (described in [README.md](https://github.com/warpech/jquery-handsontable)):

  - new public method `destroyEditor` (#229). 

## [0.7.0](https://github.com/warpech/jquery-handsontable/tree/v0.7.0) (Nov 5, 2012)

Please note that this release has partial incompability with previous releases. It is step in a direction to make Handsontable more flexible and customisable.

Adds binding to object data source (prior versions only allow 2-dimensional array data source)  
Adds selective column rendering (using `columns` option)
Now data is assigned to Handsontable as reference (prior versions had data copied)
Adds custom cell types (currently text, autocomplete or checkbox)

Features removed:

 - Legend (use [cell renderers](http://handsontable.com/demo/renderers.html) instead)

## [0.6.0](https://github.com/warpech/jquery-handsontable/tree/v0.6.0) (Sep 27, 2012)

Please note that this release has partial incompability with previous releases, though it should affect only border cases.

Potential incompabilities with version 0.5.1:
  - public method `getData` no longer has `asReference` parameter (use `getDataReference` instead)
  - to have scrollable grid, you must set "overflow: scroll" or "overflow: auto" directly on Handsontable container. Until now, it worked also when you set overflow scroll/auto on any of the container parents, but that turned out to be not compatible with Twitter Bootstrap

Features added in 0.6.0 (described in [README.md](https://github.com/warpech/jquery-handsontable)):
  - virtual scrolling that solves problem with row/column header flicker in IE and FF when the grids quickly scrolled
  - public method `getData` now accepts optional arguments to return only fragment of grid data (e.g. current selection)
  - new public method `getDataReference` works the same as `getData` but returns data as reference, which is faster but can mess up if manipulated outside the plugin

Bugfixes:
  - keyword `this` in onChange, onBeforeChange, onSelection callbacks points to container HTML element
  - editing a field in Firefox 3.6.28 skipped the first character
  - added default font-family and font-size for .typeahead
  - TAB does not move cell selection if cell is not being edited (#151)
  - HTML special chars should be preserved in data map but escaped in DOM (#147)
  - rowHeaders/colHeaders false should not init row/col headers (#141)
  - legend icon did not resize column header

## [0.5.1](https://github.com/warpech/jquery-handsontable/tree/v0.5.1) (Sep 7, 2012)

- features (described in [README.md](https://github.com/warpech/jquery-handsontable)):
  - allow icons in Legends (see [example](http://warpech.github.com/jquery-handsontable/#example2))
  - new public method `refreshLegend`
  - new configuration option `outsideClickDeselects`
  - added data function reference in autocomplete match (`match: function (row, col, data)`)
- bugfix:
  - option `fillHandle: 'horizontal'` and `'vertical'` did not work 

## [0.5.0](https://github.com/warpech/jquery-handsontable/tree/v0.5.0) (Aug 15, 2012)

- features (described in [README.md](https://github.com/warpech/jquery-handsontable)):
  - public methods `getDataAtCell`, `setCellReadOnly` - thanks @Dinesh-Ramakrishnan
  - public methods `getSelected` - thanks @littley!
  - public methods `getRowHeader`, `getColHeader`, `getCellMeta`
  - configuration `autoWrapRow`, `autoWrapCol`, `enterBeginsEditing`
  - now Enter key behaves more like in Excel (see issue #56)
- code quality:
  - add `"use strict";` (ECMAScript strict mode) to all components
  - allow to run in jQuery noConflict mode
  - namespace was changed from `handsontable` to `Handsontable` to avoid var name conflicts that people were having by accident
  - now code is divided into components and built with [Grunt](http://weblog.bocoup.com/introducing-grunt/)
- tests: added four Selenium IDE tests to automate testing of bugfixes. This is a start - more tests will be added in future versions. Tests are located in [test/](https://github.com/warpech/jquery-handsontable/tree/master/test) directory.
- 75 bugfixes

## [0.4.2](https://github.com/warpech/jquery-handsontable/tree/v0.4.2) (Jun 18, 2012)

- features:
  - row and column headers (options: `rowHeaders`, `colHeaders`)
  - public methods `selectCell`, `deselectCell`

## [0.4.1](https://github.com/warpech/jquery-handsontable/tree/v0.4.1) (Jun 15, 2012)

- feature: public methods `setDataAtCell`, `loadData` now have a new parameter `allowHtml` that will omit escaping of HTML code

## [0.4.0](https://github.com/warpech/jquery-handsontable/tree/v0.4.0) (Jun 04, 2012)

- first version number to be documented here
- feature: undo/redo
