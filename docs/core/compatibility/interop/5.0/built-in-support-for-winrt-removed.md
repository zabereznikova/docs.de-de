---
title: 'Breaking Change: Integrierte Unterstützung für WinRT wird aus .NET entfernt'
description: Hier erfahren Sie mehr über den Interop-Breaking-Change in .NET 5.0, bei dem die integrierte Unterstützung für WinRT aus .NET entfernt wurde.
ms.date: 10/13/2020
ms.openlocfilehash: 61d8e26d06c232a7bfa1891a2159f5232f747b8a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759482"
---
# <a name="built-in-support-for-winrt-is-removed-from-net"></a>Integrierte Unterstützung für WinRT wird aus .NET entfernt

Die integrierte Unterstützung für die Nutzung von [WinRT-APIs (Windows Runtime)](/uwp/winrt-cref/winrt-type-system) in .NET wird entfernt.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="change-description"></a>Änderungsbeschreibung

Zuvor konnte CoreCLR [Windows-Metadatendateien (WinMD)](/uwp/winrt-cref/winmd-files) verwenden, um WinRT-Typen zu aktivieren und zu nutzen. Ab .NET 5.0 kann CoreCLR WinMD-Dateien nicht mehr direkt nutzen.

Wenn Sie versuchen, auf eine nicht unterstützte Assembly zu verweisen, wird eine <xref:System.IO.FileNotFoundException> zurückgegeben. Wenn Sie eine WinRT-Klasse aktivieren, wird eine <xref:System.PlatformNotSupportedException> zurückgegeben.

Dieser Breaking Change wurde aus den folgenden Gründen vorgenommen:

- WinRT kann jetzt unabhängig von der .NET-Runtime entwickelt und verbessert werden.
- Außerdem dient dies der Symmetrie mit Interopsystemen, die für andere Betriebssysteme wie iOS und Android bereitgestellt werden.
- Andere .NET-Features wie C#-Features, IL-Verknüpfungen (Intermediate Language) und die AOT-Kompilierung (Ahead-of-Time) können genutzt werden.
- Die .NET-Runtimecodebasis kann vereinfacht werden.

## <a name="recommended-action"></a>Empfohlene Aktion

- Entfernen Sie Verweise auf das [Microsoft.Windows.SDK.Contracts-Paket](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts).  Geben Sie stattdessen die Version der Windows-APIs an, auf die Sie über die `TargetFramework`-Eigenschaft des Projekts zugreifen möchten.  Beispiel:

  ```xml
  <TargetFramework>net5.0-windows10.0.19041</TargetFramework>
  ```

- Verwenden Sie die [C#/WinRT](/windows/uwp/csharp-winrt/)-Toolkette, um WinRT-APIs und Typen für .NET 5.0 und höheren Versionen zu generieren oder anzupassen.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

### Category

Interop

-->
