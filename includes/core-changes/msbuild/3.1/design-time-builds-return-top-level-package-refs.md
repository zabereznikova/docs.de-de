---
ms.openlocfilehash: 53840ddd59ae3463bae2930fd0151ab2cd2d65cb
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593323"
---
### <a name="design-time-builds-only-return-top-level-package-references"></a>Entwurfszeitbuilds geben nur allgemeine Paketverweise zurück

Ab .NET Core SDK 3.1.400 werden vom `RunResolvePackageDependencies`-Ziel nur Verweise auf Pakete der obersten Ebene zurückgegeben.

#### <a name="version-introduced"></a>Eingeführt in Version

.NET Core SDK 3.1.400

#### <a name="change-description"></a>Änderungsbeschreibung

In früheren Versionen des .NET Core SDK erstellte das `RunResolvePackageDependencies`-Ziel die folgenden MSBuild-Elemente, die Informationen aus der NuGet-Ressourcendatei enthielten:

- `PackageDefinitions`
- `PackageDependencies`
- `TargetDefinitions`
- `FileDefinitions`
- `FileDependencies`

Mit diesen Daten füllt Visual Studio den Knoten „Abhängigkeiten“ im Projektmappen-Explorer auf. Es kann sich dabei jedoch um eine große Menge von Daten handeln, die nur benötigt werden, wenn der Knoten „Abhängigkeiten“ aufgeklappt wird.

Ab Version 3.1.400 des .NET Core SDK werden die meisten dieser Elemente nicht standardmäßig generiert. Nur Elemente vom Typ `Package` werden zurückgegeben. Wenn Visual Studio die Elemente zum Auffüllen des Knotens „Abhängigkeiten“ benötigt, liest Visual Studio die betreffenden Informationen direkt aus der Ressourcendatei.

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung wurde eingeführt, um die Leistung beim Laden von Projektmappen in Visual Studio zu verbessern. Zuvor wurden alle Paketverweise geladen, darunter viele, die von den meisten Benutzern nie angezeigt wurden.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Sie über eine MSBuild-Logik verfügen, die von der Erstellung dieser Elemente abhängt, legen Sie die Eigenschaft `EmitLegacyAssetsFileItems` in Ihrer Projektdatei auf `true` fest. Mit dieser Einstellung aktivieren Sie das vorherige Verhalten, bei dem alle Elemente erstellt werden.

#### <a name="category"></a>Kategorie

MSBuild

#### <a name="affected-apis"></a>Betroffene APIs

Nicht zutreffend
