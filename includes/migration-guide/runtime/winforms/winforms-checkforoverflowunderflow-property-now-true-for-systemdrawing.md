---
ms.openlocfilehash: 68b0c4bb032b9744ef585eaef3d68e31afebee24
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497741"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>Die CheckForOverflowUnderflow-Eigenschaft von WinForm ist jetzt für System.Drawing auf TRUE festgelegt

#### <a name="details"></a>Details

Die CheckForOverflowUnderflow-Eigenschaft für die Assembly „System.Drawing.dll“ ist auf TRUE festgelegt.

#### <a name="suggestion"></a>Vorschlag

Zuvor wurde das Ergebnis im Fall von Überläufen automatisch abgeschnitten. Nun wird eine <xref:System.OverflowException?displayProperty=fullName>-Ausnahme ausgelöst.

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
