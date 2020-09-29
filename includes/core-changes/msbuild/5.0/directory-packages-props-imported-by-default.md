---
ms.openlocfilehash: 4a916a4178535763712ebd58fde1a81e456da0d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538817"
---
### <a name="directorypackagesprops-files-is-imported-by-default"></a>Directory.Packages.props-Dateien werden standardmäßig importiert

NuGet-Dateien des Typs *.props* importieren automatisch eine Datei namens *Directory.Packages.props*, wenn sie im Projektordner oder einem seiner Vorgänger gefunden wird.

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 8

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen konnte eine Datei mit dem Namen *Directory.Packages.props* in Ihrer Projektdatei enthalten sein, die zur Buildzeit nicht automatisch von der NuGet-Datei *.props* importiert wurde.

Ab .NET 5.0 wird eine solche Datei *automatisch* importiert, wenn sie im Projektordner oder einem seiner Vorgänger vorhanden ist. Wenn Sie eine Datei mit diesem Namen in Ihrem Projektordner haben, könnte dieser automatische Import das Verhalten des Builds ändern. Die Datei wird z. B. importiert, was vorher aber nicht der Fall war, oder die Reihenfolge, in der sie importiert wird, könnte sich ändern, wenn Sie sie gezielt importieren.

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung wurde vorgenommen, um eine [zentrale Paketversionsverwaltung](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) für NuGet zu unterstützen.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Benennen Sie die vorhandene Datei *Directory.Packages.props* um, wenn sie nicht automatisch importiert werden soll.

#### <a name="category"></a>Kategorie

MSBuild

#### <a name="affected-apis"></a>Betroffene APIs

Nicht zutreffend

<!--

#### Affected APIs

Not detectable via API analysis.

-->
