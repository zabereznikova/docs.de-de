---
ms.openlocfilehash: 770e303ab261b97efb49a3e0865a015d8de33247
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802721"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a>Verbesserungen für den Algorithmus zur Speicherplatzreservierung bei Grid-Sternzeilen

|   |   |
|---|---|
|Details|Es wurde ein Fehler im [Algorithmus zur Größenzuordnung ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) behoben, der in einem <xref:System.Windows.Controls.Grid> in .NET Framework 4.7 eingeführt wurde.  Wenn ein Grid dieser Art mit <code>Height=&quot;Auto&quot;</code> leere Zeilen enthielt, wurden Zeilen gelegentlich an der falschen Position, möglicherweise sogar außerhalb des Grids angeordnet.|
|Vorschlag|Damit die Anwendung von diesen Änderungen profitieren kann, muss sie unter .NET Framework 4.8 oder höher ausgeführt werden.|
|Bereich|Hauptversion|
|Version|4.8|
|Typ|Laufzeit|

