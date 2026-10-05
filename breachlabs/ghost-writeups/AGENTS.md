# AGENTS.md

## Shell commands

Batch before you iterate. A directory of N small files is one command, not N.

| Instead of | Use |
|---|---|
| N sequential reads | `cat *`, or `cat f1 f2 f3` |
| `ls` then read each | `cat *.md`, `head -n 20 *` |
| One `grep` per pattern | `grep -nE 'a\|b\|c' files` |
| Repeated `find` | one `find` with a combined expression |

Fall back to per-file reads only when you need byte-level detail, the glob output
is ambiguous about which file a line came from, or a single file is large enough
that whole-file output would bury the signal.

Parallelize independent tool calls in a single message rather than one per turn.

## File state

Re-read on-disk state before trusting a summary. Files can change mid-session —
editors create `.save`/`.swp` backups and rewrite the original on save, and a glob
will pick those up alongside real content.

If two reads disagree, check `wc -c` / `md5sum` rather than assuming which is
correct. Report the discrepancy instead of silently picking a side.