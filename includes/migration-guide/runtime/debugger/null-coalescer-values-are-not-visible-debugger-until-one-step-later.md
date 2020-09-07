---
ms.openlocfilehash: af8de731ee93d0bfb01042d894f5730570dcdd78
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497137"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a>NULL-Zusammenfügungswerte werden erst im nächsten Schritt angezeigt

#### <a name="details"></a>Details

Durch einen Fehler in .NET Framework 4.5 werden Werte, die über einen zusammenfügenden NULL-Vorgang festgelegt werden, nicht unmittelbar im Anschluss an die Zuweisung im Debugger angezeigt, wenn sie auf einer 64-Bit-Version des Frameworks ausgeführt werden.

#### <a name="suggestion"></a>Vorschlag

Wenn Sie im Debugger einen zusätzlichen Schritt ausführen, wird der lokale Wert bzw. der Feldwert ohne Probleme aktualisiert. Dieses Problem wurde auch in .NET Framework 4.6 behoben und sollte nach einem Upgrade auf diese Version nicht mehr auftreten.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
