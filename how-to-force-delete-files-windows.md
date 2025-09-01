## Take ownership

```ps1
takeown /f "path_to_file" /r /d y
```

* `/r` (Recursive)
* `/d y` (Auto reply Yes)

```ps1
icacls "path_to_file" /grant administrators:F /t
```

* `icacls` (Access Control Management Tool)
* `/grant administrators:F` (Group administrators and Full control)
* `/t` (Traverse)

## Kill process
```ps1
taskkill /F /IM example.exe
```

* `/F` (Force)
* `/IM` (Image name)

## Delete files
```ps1
Remove-Item "path_to_file" -Recurse -Force
```