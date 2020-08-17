---
title: AddConsoleAlias function
description: See reference information about the AddConsoleAlias function, which defines a console alias for the specified executable.
author: bitcrazed
ms.author: richturn
ms.topic: article
keywords: console, character mode applications, command line applications, terminal applications, console api
MS-HAID:
- 'base.addconsolealias'
- 'consoles.addconsolealias'
MSHAttr:
- 'PreferredSiteName:MSDN'
- 'PreferredLib:/library/windows/desktop'
ms.assetid: e4072c3c-cf32-4992-847e-efdb846e5784
topic_type:
- apiref
api_name:
- AddConsoleAlias
- AddConsoleAliasA
- AddConsoleAliasW
api_location:
- Kernel32.dll
api_type:
- DllExport
---

# AddConsoleAlias function


Defines a console alias for the specified executable.

Syntax
------

```C
BOOL WINAPI AddConsoleAlias(
  _In_ LPCTSTR Source,
  _In_ LPCTSTR Target,
  _In_ LPCTSTR ExeName
);
```

Parameters
----------

*Source* \[in\]  
The console alias to be mapped to the text specified by *Target*.

*Target* \[in\]  
The text to be substituted for *Source*. If this parameter is **NULL**, then the console alias is removed.

*ExeName* \[in\]  
The name of the executable file for which the console alias is to be defined.

Return value
------------

If the function succeeds, the return value is **TRUE**.

If the function fails, the return value is **FALSE**. To get extended error information, call [**GetLastError**](https://msdn.microsoft.com/library/windows/desktop/ms679360).

Remarks
-------

To compile an application that uses this function, define **\_WIN32\_WINNT** as 0x0501 or later. For more information, see [Using the Windows Headers](https://msdn.microsoft.com/library/windows/desktop/aa383745).

Examples
--------

For an example, see [Console Aliases](console-aliases.md).

Requirements
------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Minimum supported client</p></td>
<td><p>Windows 2000 Professional [desktop apps only]</p></td>
</tr>
<tr class="even">
<td><p>Minimum supported server</p></td>
<td><p>Windows 2000 Server [desktop apps only]</p></td>
</tr>
<tr class="odd">
<td><p>Header</p></td>
<td>ConsoleApi3.h (via Wincon.h, include Windows.h)</td>
</tr>
<tr class="even">
<td><p>Library</p></td>
<td>Kernel32.lib</td>
</tr>
<tr class="odd">
<td><p>DLL</p></td>
<td>Kernel32.dll</td>
</tr>
<tr class="even">
<td><p>Unicode and ANSI names</p></td>
<td><p><strong>AddConsoleAliasW</strong> (Unicode) and <strong>AddConsoleAliasA</strong> (ANSI)</p></td>
</tr>
<tr class="odd">
</tr>
<tr class="even">
</tr>
<tr class="odd">
</tr>
<tr class="even">
</tr>
</tbody>
</table>

## <span id="see_also"></span>See also


[Console Aliases](console-aliases.md)

[Console Functions](console-functions.md)

[**GetConsoleAlias**](getconsolealias.md)

[**GetConsoleAliases**](getconsolealiases.md)

[**GetConsoleAliasExes**](getconsolealiasexes.md)

 

 




