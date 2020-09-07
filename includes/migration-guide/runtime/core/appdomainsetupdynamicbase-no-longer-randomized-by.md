---
ms.openlocfilehash: 26c50ac8b0e570e31a38b1913f73acbe21fae08b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497405"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a>AppDomainSetup.DynamicBase wird mithilfe von UseRandomizedStringHashAlgorithm nicht mehr zufällig festgelegt

#### <a name="details"></a>Details

Vor .NET Framework 4.6 wurde der Wert von <xref:System.AppDomainSetup.DynamicBase> für Anwendungsdomänen oder Prozesse zufällig festgelegt, wenn UseRandomizedStringHashAlgorithm in der Konfigurationsdatei der App aktiviert war. Ab .NET Framework 4.6 gibt <xref:System.AppDomainSetup.DynamicBase> ein stabiles Ergebnis zurück, das zwischen verschiedenen Instanzen einer ausgeführten App und zwischen verschiedenen App-Domänen besteht. Verschiedene Apps haben auch unterschiedliche dynamische Basen. Diese Änderung entfernt nur die Elemente von verschiedenen Instanzen einer App, die zufällig benannt werden.

#### <a name="suggestion"></a>Vorschlag

Beachten Sie, dass bei der Aktivierung von <code>UseRandomizedStringHashAlgorithm</code><xref:System.AppDomainSetup.DynamicBase> nicht zufällig festgelegt wird. Wenn eine zufällige Basis benötigt wird, muss diese im Code Ihrer App anstelle einer API erstellt werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.6|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.AppDomainSetup.DynamicBase`

-->
