# dumpsys Related Commands

## Related Commands

- `am` – Activity Manager
- `pm` – Package Manager
- `dumpsys` – Dump system service info
- `logcat` – View Android system logs

<!-- vim-markdown-toc GFM -->
* [Get Current Activity](Get Current activity)
* [Get Current Window](Get Current Window)
<!-- vim-markdown-toc -->


### Get Current Activity

Linux:
```sh
adb shell dumpsys activity | grep "mFocusedActivity"
```

Windows:
```sh
adb shell dumpsys activity  | findstr "mFocusedActicity"
```

### Get Current Window

```sh
adb shell dumpsys window w | grep \/  |  grep name=
```

