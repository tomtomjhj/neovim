do_put
changed_lines
buf_updates_send_changes
* no coc: !buf_updates_active(buf)
* coc: kv_size(buf->update_channels) == 1
buf_collect_lines(..., 3, 2, true, ..., ...)
4 > 3

buf_



```
1
2
31
 2 // ml_line_count
 3 // lnum
```
```
changed_lines(
    linenr_T lnum = 3,        // first line with change
    colnr_T col ,          // column in first line with change
    linenr_T lnume = 6,       // line below last changed line
    long xtra = 2,            // number of extra lines (negative when deleting)
    bool do_buf_event  // some callers like undo/redo call changed_lines()
                       // and then increment changedtick *again*. This flag
                       // allows these callers to send the nvim_buf_lines_event
                       // events after they're done modifying changedtick.
void buf_updates_send_changes(
  buf_T *buf,
  linenr_T firstline = lnum = 3,
  int64_t num_added = lnume + xtra - lnum = 6 + 2 - 3 = 5,
  int64_t num_removed = lnume - lnum = 6 - 3 = 3,
  bool send_tick)
```


num_added = 6 + 2 - 3 = 5


