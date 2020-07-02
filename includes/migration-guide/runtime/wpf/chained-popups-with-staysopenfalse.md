---
ms.openlocfilehash: 171b7a3a962f8259e64b88f1ae893e649b5f24bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621257"
---
### <a name="chained-popups-with-staysopenfalse"></a>Verkettete Popups mit „StaysOpen=FALSE“

#### <a name="details"></a>Details

Ein Popup mit „StaysOpen=FALSE“ sollte geschlossen werden, wenn Sie außerhalb des Popups klicken. Wenn zwei oder mehr Popups verkettet sind (d.h. ein Popup enthält ein anderes), treten viele Probleme auf, unter anderem folgende:<ul><li>Öffnen Sie zwei Ebenen. Klicken Sie außerhalb von P2, aber innerhalb von P1.  Es geschieht nichts.</li><li>Öffnen Sie zwei Ebenen. Klicken Sie außerhalb von P1.  Beide Popups werden geschlossen.</li><li>Öffnen und schließen Sie zwei Ebenen.  Versuchen Sie dann, P2 erneut zu öffnen.  Es geschieht nichts.</li><li>Versuchen Sie, drei Ebenen zu öffnen.  Dies ist nicht möglich.  (Je nachdem, wo Sie klicken, geschieht entweder nichts oder die ersten zwei Ebenen werden geschlossen.) Diese Fälle (und andere Varianten) funktionieren nun wie erwartet.</li></ul>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.7.1|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType></li></ul>|
