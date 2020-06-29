---
title: Unterschiede zwischen dem .NET Framework und .NET Core
description: In diesem Artikel werden die Unterschiede zwischen der .NET Framework-Implementierung von Windows Presentation Foundation (WPF) und .NET Core WPF beschrieben. Beim Migrieren einer App sollten Sie diese Inkompatibilitäten berücksichtigen.
author: adegeo
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 3bedc30046c36d4c5430feedf5854276ebaef8aa
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325682"
---
# <a name="differences-in-wpf"></a>Unterschiede in WPF

In diesem Artikel werden die Unterschiede in .NET Core und dem .NET Framework bezüglich Windows Presentation Foundation (WPF) beschrieben. WPF für .NET Core ist ein [Open-Source-Framework](https://github.com/dotnet/wpf), das aus dem Quellcode des ursprünglichen WPF-Systems für das .NET Framework geforkt wurde.

Einige Features des .NET Framework werden jedoch von .NET Core nicht unterstützt. Weitere Informationen zu nicht unterstützten Technologien finden Sie unter [.NET Framework-Technologien, die auf .NET Core nicht verfügbar sind](../../core/porting/net-framework-tech-unavailable.md).

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a>Projekte im SDK-Format

.Net Core verwendet Projektdateien im SDK-Stil. Diese Projektdateien unterscheiden sich von herkömmlichen .NET Framework-Projektdateien, die von Visual Studio verwaltet werden. Sie müssen Ihre Projekte konvertieren, wenn Sie Ihre .NET Framework-WPF-Apps zu .NET Core migrieren möchten. Weitere Informationen finden Sie unter [Migrieren von WPF-Apps zu .NET Core](convert-project-from-net-framework.md).

## <a name="nuget-package-references"></a>NuGet-Paketverweise

Wenn Ihre .NET Framework-App ihre NuGet-Abhängigkeiten in einer *packages.config*-Datei auflistet, migrieren Sie zum Format [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files):

1. Öffnen Sie in Visual Studio den Bereich **Projektmappen-Explorer**.
1. Klicken Sie in Ihrem WPF-Projekt mit der rechten Maustaste auf **packages.config** >  **"packages.config" zu PackageReference migrieren**.

![Aktualisieren auf PackageReference](media/differences-from-net-framework/package-reference-migration.png)

Es wird ein Dialogfeld mit berechneten NuGet-Abhängigkeiten auf oberster Ebene angezeigt, und Sie werden gefragt, welche anderen NuGet-Pakete auf die oberste Ebene höher gestuft werden sollen. Klicken Sie auf **OK**. Die *packages.config*-Datei wird daraufhin aus dem Projekt entfernt, und der Projektdatei werden `<PackageReference>`-Elemente hinzugefügt.

Wenn Ihr Projekt `<PackageReference>` verwendet, werden Pakete nicht lokal in einem *Packages*-Ordner gespeichert, sondern global. Öffnen Sie die Projektdatei, und entfernen Sie alle `<Analyzer>`-Elemente, die auf den *Packages*-Ordner verweisen. Diese Analysetools sind automatisch in den NuGet-Paketverweisen enthalten.

## <a name="code-access-security"></a>Codezugriffssicherheit

Die Codezugriffssicherheit (Code Access Security, CAS) wird weder von .NET Core noch von WPF für .NET Core unterstützt. Alle CAS-bezogenen Funktionen gelten als vollständig vertrauenswürdig. In WPF für .NET Core wird CAS-bezogener Code entfernt. Die öffentliche API-Oberfläche dieser Typen ist weiterhin vorhanden. Damit wird sichergestellt, dass die Aufrufe dieser Typen erfolgreich sind.

Öffentlich definierte CAS-bezogene Typen wurden aus den WPF-Assemblys und in die wichtigsten .NET-Bibliotheksassemblys verschoben. Für die WPF-Assemblys ist die Typweiterleitung an den neuen Speicherort der verschobenen Typen festgelegt.

| Quellassembly | Zielassembly | Typ                |
| --------------- | --------------- | ------------------- |
| *WindowsBase.dll* | *System.Security.Permissions.dll* | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| *System.Xaml.dll* | *System.Security.Permissions.dll* | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| *System.Xaml.dll* | *System.Windows.Extension.dll*    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> Die Funktionalität für das Speichern und Abrufen von Informationen über die folgenden Eigenschaften wurde im `XamlAccessLevel`-Typ beibehalten, um die Probleme bei der Portierung so gering wie möglich zu halten.
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a>Nächste Schritte

- [Migrieren von WPF-Apps zu .NET Core](convert-project-from-net-framework.md)
