---
ms.openlocfilehash: 49740d3b1890d72935e6e329a4f4be836ed70b25
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497384"
---
### <a name="missing-target-framework-moniker-results-in-40-behavior"></a>Fehlender Zielframeworkmoniker führt zum Verhalten der Version 4.0

#### <a name="details"></a>Details

Anwendungen, bei denen auf Assemblyebene kein <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> angewendet wurde, werden automatisch mit der Semantik (den Quirks) von .NET Framework 4.0 ausgeführt. Um eine hohe Qualität sicherzustellen, empfiehlt es sich, dass alle Binärdateien ein <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> als Attribut erhalten, wodurch die Version von .NET Framework angegeben wird, mit denen sie erstellt wurden. Beachten Sie, dass die Verwendung eines Zielframeworkmonikers in einer Projektdatei dazu führt, dass MSBuild automatisch ein <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> anwendet.

#### <a name="suggestion"></a>Vorschlag

Es sollte ein <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> bereitgestellt werden, entweder durch direktes Hinzufügen des Attributs zur Assembly oder durch Angeben eines Zielframeworks in der [Projektdatei oder über die Visual Studio-GUI für Projekteigenschaften](https://devblogs.microsoft.com/visualstudio/visual-studio-managed-multi-targeting-part-1-concepts-target-framework-moniker-target-framework/).

| name    | Wert       |
|:--------|:------------|
| Bereich   |Hauptversion|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
