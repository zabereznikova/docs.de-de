---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379671"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a>Die CheckForOverflowUnderflow-Eigenschaft von WinForm ist jetzt für System.Drawing auf TRUE festgelegt

|   |   |
|---|---|
|Details|Die CheckForOverflowUnderflow-Eigenschaft für die Assembly „System.Drawing.dll“ ist auf TRUE festgelegt.|
|Vorschlag|Zuvor wurde das Ergebnis im Fall von Überläufen automatisch abgeschnitten. Nun wird eine <xref:System.OverflowException?displayProperty=name>-Ausnahme ausgelöst.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
