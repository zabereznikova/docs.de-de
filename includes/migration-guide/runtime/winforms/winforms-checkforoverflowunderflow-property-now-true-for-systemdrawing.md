---
ms.openlocfilehash: 4cd06fd02fadbaa9f74e40f850e688ee883454ed
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620447"
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
