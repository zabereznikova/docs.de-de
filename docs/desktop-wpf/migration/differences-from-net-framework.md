---
title: Unterschiede zwischen .NET Framework und .NET Core
description: Beschreibt die Unterschiede zwischen der .NET Framework-Implementierung von Windows Presentation Foundation (WPF) und .NET Core WPF. Beim Migrieren Ihrer App sollten Sie diese Inkompatibilitäten berücksichtigen.
author: thraka
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 4386654aad205e3c9f2cbd986d7b812e261e737f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "81433133"
---
# <a name="differences-in-wpf"></a>Unterschiede in WPF

In diesem Artikel werden die Unterschiede zwischen Windows Presentation Foundation (WPF) in .NET Core und .NET Framework beschrieben. WPF für .NET Core ist ein [Open-Source-Framework,](https://github.com/dotnet/wpf) das aus dem ursprünglichen WPF für .NET Framework-Quellcode gegabelt wird.

Es gibt einige Features von .NET Framework, die .NET Core nicht unterstützt. Weitere Informationen zu nicht unterstützten Technologien finden Sie unter [.NET Framework-Technologien,](../../core/porting/net-framework-tech-unavailable.md)die unter .NET Core nicht verfügbar sind.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a>Projekte im SDK-Stil

.NET Core verwendet Projektdateien im SDK-Stil. Diese Projektdateien unterscheiden sich von den herkömmlichen .NET Framework-Projektdateien, die von Visual Studio verwaltet werden. Um Ihre .NET Framework WPF-Apps in .NET Core zu migrieren, müssen Sie Ihre Projekte konvertieren. Weitere Informationen finden Sie unter [Migrieren von WPF-Apps nach .NET Core 3.0](convert-project-from-net-framework.md).

## <a name="nuget-package-references"></a>NuGet-Paketverweise

Wenn Ihre .NET Framework-App ihre NuGet-Abhängigkeiten in einer *packages.config-Datei* auflistet, migrieren Sie in das [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) folgende Format:

1. Öffnen Sie in Visual Studio den Bereich **Projektmappen-Explorer.**
1. Klicken Sie in Ihrem WPF-Projekt mit der rechten Maustaste auf **packages.config** > **Migrate packages.config to PackageReference**.

![Aktualisieren auf PackageReference](media/differences-from-net-framework/package-reference-migration.png)

Es wird ein Dialogfeld angezeigt, in dem berechnete NuGet-Abhängigkeiten der obersten Ebene angezeigt und gefragt werden, welche anderen NuGet-Pakete auf die oberste Ebene heraufgestuft werden sollen. Wählen Sie **OK** aus, und die Datei *packages.config* wird aus dem Projekt entfernt, und `<PackageReference>` Elemente werden der Projektdatei hinzugefügt.

Wenn Ihr `<PackageReference>`Projekt verwendet, werden Pakete nicht lokal in einem *Paketordner* gespeichert, sondern global gespeichert. Öffnen Sie die Projektdatei, und entfernen Sie alle `<Analyzer>` Elemente, die auf den Ordner *Pakete* verwiesen haben. Diese Analysatoren werden automatisch in die NuGet-Paketreferenzen aufgenommen.

## <a name="code-access-security"></a>Codezugriffssicherheit

Code Access Security (CAS) wird von .NET Core oder WPF für .NET Core nicht unterstützt. Alle CAS-bezogenen Funktionen werden unter der Annahme von Full-Trust behandelt. WPF für .NET Core entfernt CAS-bezogenen Code. Die öffentliche API-Oberfläche dieser Typen ist weiterhin vorhanden, um sicherzustellen, dass Aufrufe dieser Typen erfolgreich ausgeführt werden.

Öffentlich definierte CAS-bezogene Typen wurden aus den WPF-Assemblys in die CoreFX-Assemblys verschoben. Für die WPF-Assemblys ist die Typweiterleitung auf die neue Position der verschobenen Typen festgelegt.

| Quellassembly | Zielassembly | type                |
| --------------- | --------------- | ------------------- |
| *WindowsBase.dll* | *System.Security.Permissions.dll* | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| *System.Xaml.dll* | *System.Security.Permissions.dll* | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| *System.Xaml.dll* | *System.Windows.Extension.dll*    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> Um die Portierungsreibung zu minimieren, wurde die Funktionalität zum Speichern und `XamlAccessLevel` Abrufen von Informationen zu den folgenden Eigenschaften im Typ beibehalten.
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a>Nächste Schritte

- [Erfahren Sie, wie Sie eine .NET Framework WPF-App in .NET Core portieren.](convert-project-from-net-framework.md)
