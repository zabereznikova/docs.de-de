---
ms.openlocfilehash: 415eb1960c20fb662469e126560d6f366309eb0d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496495"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a>Verbesserungen für den Algorithmus zur Speicherplatzreservierung bei Grid-Sternzeilen

#### <a name="details"></a>Details

Es wurde ein Fehler im [Algorithmus zur Größenzuordnung ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) behoben, der in einem <xref:System.Windows.Controls.Grid> in .NET Framework 4.7 eingeführt wurde.  Wenn ein Grid dieser Art mit <code>Height=&quot;Auto&quot;</code> leere Zeilen enthielt, wurden Zeilen gelegentlich an der falschen Position, möglicherweise sogar außerhalb des Grids angeordnet.

#### <a name="suggestion"></a>Vorschlag

Damit die Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.8 oder höher ausgeführt werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Hauptversion|
|Version|4.8|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
