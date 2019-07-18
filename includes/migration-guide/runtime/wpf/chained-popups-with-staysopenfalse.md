---
ms.openlocfilehash: 2bb40294685c987de84138ee889e6b88f7184bb0
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857650"
---
### <a name="chained-popups-with-staysopenfalse"></a>Verkettete Popups mit „StaysOpen=FALSE“

|   |   |
|---|---|
|Details|Ein Popup mit „StaysOpen=FALSE“ sollte geschlossen werden, wenn Sie außerhalb des Popups klicken. Wenn zwei oder mehr Popups verkettet sind (d.h. ein Popup enthält ein anderes), treten viele Probleme auf, unter anderem folgende:<ul><li>Öffnen Sie zwei Ebenen. Klicken Sie außerhalb von P2, aber innerhalb von P1.  Es geschieht nichts.</li><li>Öffnen Sie zwei Ebenen. Klicken Sie außerhalb von P1.  Beide Popups werden geschlossen.</li><li>Öffnen und schließen Sie zwei Ebenen.  Versuchen Sie dann, P2 erneut zu öffnen.  Es geschieht nichts.</li><li>Versuchen Sie, drei Ebenen zu öffnen.  Dies ist nicht möglich.  (Je nachdem, wo Sie klicken, geschieht entweder nichts oder die ersten zwei Ebenen werden geschlossen.) Diese Fälle (und andere Varianten) funktionieren nun wie erwartet.</li></ul>|
|Bereich|Microsoft Edge|
|Version|4.7.1|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType></li></ul>|

