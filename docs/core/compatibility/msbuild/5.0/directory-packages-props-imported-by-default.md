---
title: 'Breaking Change: Directory.Packages.props-Dateien werden standardmäßig importiert'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den NuGet-Dateien des Typs „.props“ automatisch eine Datei namens „Directory.Packages.props“ importieren, wenn sie im Projektordner gefunden wird.
ms.date: 09/17/2020
ms.openlocfilehash: ee8a2999b801e81750d96a0bc985e3c8169224a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759406"
---
# <a name="directorypackagesprops-files-is-imported-by-default"></a>Directory.Packages.props-Dateien werden standardmäßig importiert

NuGet-Dateien des Typs *.props* importieren automatisch eine Datei namens *Directory.Packages.props*, wenn sie im Projektordner oder einem seiner Vorgänger gefunden wird.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen konnte eine Datei mit dem Namen *Directory.Packages.props* in Ihrer Projektdatei enthalten sein, die zur Buildzeit nicht automatisch von der NuGet-Datei *.props* importiert wurde.

Ab .NET 5.0 wird eine solche Datei *automatisch* importiert, wenn sie im Projektordner oder einem seiner Vorgänger vorhanden ist. Wenn Sie eine Datei mit diesem Namen in Ihrem Projektordner haben, könnte dieser automatische Import das Verhalten des Builds ändern. Die Datei wird z. B. importiert, was vorher aber nicht der Fall war, oder die Reihenfolge, in der sie importiert wird, könnte sich ändern, wenn Sie sie gezielt importieren.

## <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung wurde vorgenommen, um eine [zentrale Paketversionsverwaltung](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) für NuGet zu unterstützen.

## <a name="recommended-action"></a>Empfohlene Maßnahme

Benennen Sie die vorhandene Datei *Directory.Packages.props* um, wenn sie nicht automatisch importiert werden soll.

## <a name="affected-apis"></a>Betroffene APIs

Nicht zutreffend

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
