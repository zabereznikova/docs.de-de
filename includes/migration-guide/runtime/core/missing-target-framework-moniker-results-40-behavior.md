---
ms.openlocfilehash: 26a001ec2009a1a66dd9038b9bd3a42d7bcefb73
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620253"
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
