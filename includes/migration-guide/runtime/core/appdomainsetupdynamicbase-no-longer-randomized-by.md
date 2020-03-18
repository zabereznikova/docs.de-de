---
ms.openlocfilehash: 3f553f95941eaf36cf335e9765a670a05bd157f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858500"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a>AppDomainSetup.DynamicBase wird mithilfe von UseRandomizedStringHashAlgorithm nicht mehr zufällig festgelegt

|   |   |
|---|---|
|Details|Vor .NET Framework 4.6 wurde der Wert von <xref:System.AppDomainSetup.DynamicBase> für Anwendungsdomänen oder Prozesse zufällig festgelegt, wenn UseRandomizedStringHashAlgorithm in der Konfigurationsdatei der App aktiviert war. Ab .NET Framework 4.6 gibt <xref:System.AppDomainSetup.DynamicBase> ein stabiles Ergebnis zurück, das zwischen verschiedenen Instanzen einer ausgeführten App und zwischen verschiedenen App-Domänen besteht. Verschiedene Apps haben auch unterschiedliche dynamische Basen. Diese Änderung entfernt nur die Elemente von verschiedenen Instanzen einer App, die zufällig benannt werden.|
|Vorschlag|Beachten Sie, dass bei der Aktivierung von <code>UseRandomizedStringHashAlgorithm</code><xref:System.AppDomainSetup.DynamicBase> nicht zufällig festgelegt wird. Wenn eine zufällige Basis benötigt wird, muss diese im Code Ihrer App anstelle einer API erstellt werden.|
|`Scope`|Edge|
|Version|4.6|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType></li></ul>|
