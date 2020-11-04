---
title: SetStdHandle function
description: Sets the handle for the specified standard device (standard input, standard output, or standard error).
author: miniksa
ms.author: miniksa
ms.topic: article
keywords: console, character mode applications, command line applications, terminal applications, console api
f1_keywords:
- processenv/SetStdHandle
- winbase/SetStdHandle
- SetStdHandle
MS-HAID:
- '_win32_setstdhandle'
- 'base.setstdhandle'
- 'consoles.setstdhandle'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/desktop'
ms.assetid: f5952460-1839-415e-b400-2f04425f288a

topic_type:
- apiref
api_name:
- SetStdHandle
api_location:
- Kernel32.dll
- API-MS-Win-Core-ProcessEnvironment-l1-1-0.dll
- KernelBase.dll
- API-MS-Win-Core-ProcessEnvironment-l1-2-0.dll
- API-MS-Win-DownLevel-Kernel32-l1-1-0.dll
- MinKernelBase.dll
api_type:
- DllExport
---

# SetStdHandle function

Sets the handle for the specified standard device (standard input, standard output, or standard error).

## Syntax

```cpp
BOOL WINAPI SetStdHandle(
  _In_ DWORD  nStdHandle,
  _In_ HANDLE hHandle
);
```

## Parameters

*nStdHandle* \[in\]  
The standard device for which the handle is to be set. This parameter can be one of the following values.

| Value | Meaning |
|-|-|
| `STD_INPUT_HANDLE` (DWORD) -10 | The standard input device. Initially, this is the console input buffer, `CONIN$`. |
| `STD_OUTPUT_HANDLE` (DWORD) -11 | The standard output device. Initially, this is the active console screen buffer, `CONOUT$`. |
| `STD_ERROR_HANDLE` (DWORD) -12 | The standard error device. Initially, this is the active console screen buffer, `CONOUT$`. |

*hHandle* \[in\]  
The handle for the standard device.

## Return value

If the function succeeds, the return value is nonzero.

If the function fails, the return value is zero. To get extended error information, call [`GetLastError`](https://msdn.microsoft.com/library/windows/desktop/ms679360).

## Remarks

The standard handles of a process may have been redirected by a call to `SetStdHandle`, in which case [`GetStdHandle`](getstdhandle.md) will return the redirected handle. If the standard handles have been redirected, you can specify the CONIN$ value in a call to the [`CreateFile`](https://msdn.microsoft.com/library/windows/desktop/aa363858) function to get a handle to a console's input buffer. Similarly, you can specify the CONOUT$ value to get a handle to the console's active screen buffer.

## Examples

For an example, see [Creating a Child Process with Redirected Input and Output](https://msdn.microsoft.com/library/windows/desktop/ms682499).

## Requirements

| &nbsp; | &nbsp; |
|-|-|
| Minimum supported client | Windows 2000 Professional \[desktop apps only\] |
| Minimum supported server | Windows 2000 Server \[desktop apps only\] |
| Header | ProcessEnv.h (via Winbase.h, include Windows.h) |
| Library | Kernel32.lib |
| DLL | Kernel32.dll |

## See also

[Console Functions](console-functions.md)

[Console Handles](console-handles.md)

[`CreateFile`](https://msdn.microsoft.com/library/windows/desktop/aa363858)

[`GetStdHandle`](getstdhandle.md)
