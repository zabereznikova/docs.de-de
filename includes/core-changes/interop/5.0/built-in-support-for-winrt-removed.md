---
ms.openlocfilehash: d21b2e092d460fdfc367d0f490228ed44ad5c6cc
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365646"
---
### <a name="built-in-support-for-winrt-is-removed-from-net"></a>Integrierte Unterstützung für WinRT wird aus .NET entfernt

Die integrierte Unterstützung für die Nutzung von [WinRT-APIs (Windows Runtime)](/uwp/winrt-cref/winrt-type-system) in .NET wird entfernt.

#### <a name="version-introduced"></a>Eingeführt in Version

Version 5.0 Vorschau 6

#### <a name="change-description"></a>Änderungsbeschreibung

Zuvor konnte CoreCLR [Windows-Metadatendateien (WinMD)](/uwp/winrt-cref/winmd-files) verwenden, um WinRT-Typen zu aktivieren und zu nutzen. Ab .NET 5.0 kann CoreCLR WinMD-Dateien nicht mehr direkt nutzen.

Wenn Sie versuchen, auf eine nicht unterstützte Assembly zu verweisen, wird eine <xref:System.IO.FileNotFoundException> zurückgegeben. Wenn Sie eine WinRT-Klasse aktivieren, wird eine <xref:System.PlatformNotSupportedException> zurückgegeben.

Dieser Breaking Change wurde aus den folgenden Gründen vorgenommen:

- WinRT kann jetzt unabhängig von der .NET-Runtime entwickelt und verbessert werden.
- Außerdem dient dies der Symmetrie mit Interopsystemen, die für andere Betriebssysteme wie iOS und Android bereitgestellt werden.
- Andere .NET-Features wie C#-Features, IL-Verknüpfungen (Intermediate Language) und die AOT-Kompilierung (Ahead-of-Time) können genutzt werden.
- Die .NET-Runtimecodebasis kann vereinfacht werden.

#### <a name="recommended-action"></a>Empfohlene Aktion

- Entfernen Sie Verweise auf das [Microsoft.Windows.SDK.Contracts-Paket](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts), und ersetzen Sie sie durch Verweise auf das [Microsoft.Windows.SDK.NET-Paket](https://www.nuget.org/packages/microsoft.windows.sdk.net).

- Verwenden Sie die [C#/WinRT](/windows/uwp/csharp-winrt/)-Toolkette, um WinRT-APIs und Typen in .NET 5.0 und höheren Versionen zu generieren oder anzupassen.

#### <a name="category"></a>Kategorie

Interop

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

-->
