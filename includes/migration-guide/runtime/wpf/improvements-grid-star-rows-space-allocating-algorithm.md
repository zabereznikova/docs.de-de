---
ms.openlocfilehash: 62702de022656e45466a45f4150e518226a3fecc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621995"
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
