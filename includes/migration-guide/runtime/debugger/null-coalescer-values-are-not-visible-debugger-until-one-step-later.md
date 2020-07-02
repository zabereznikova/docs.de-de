---
ms.openlocfilehash: 907c4aa5573c392a68afad0a4d937eadcd556440
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620293"
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
