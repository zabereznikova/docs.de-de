---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235565"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>Die CheckForOverflowUnderflow-Eigenschaft von WinForm ist jetzt für System.Drawing auf TRUE festgelegt

|   |   |
|---|---|
|Details|Die CheckForOverflowUnderflow-Eigenschaft für die Assembly „System.Drawing.dll“ ist auf TRUE festgelegt.|
|Vorschlag|Zuvor wurde das Ergebnis im Fall von Überläufen automatisch abgeschnitten. Nun wird eine <xref:System.OverflowException?displayProperty=name>-Ausnahme ausgelöst.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
