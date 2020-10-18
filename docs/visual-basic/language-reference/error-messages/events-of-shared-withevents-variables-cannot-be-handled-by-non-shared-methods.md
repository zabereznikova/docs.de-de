---
title: Ereignisse freigegebener WithEvents-Variablen können nicht von freigegebenen Methoden behandelt werden.
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: 02039b81251e59a951a0fe37ec2c9534b458b6a5
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161919"
---
# <a name="bc30594-events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>BC30594: Ereignisse von freigegebenen widervents-Variablen können nicht von nicht freigegebenen Methoden behandelt werden.

Eine mit dem- `Shared` Modifizierer deklarierte Variable ist eine freigegebene Variable. Eine freigegebene Variable identifiziert genau einen Speicherort. Eine mit dem-Modifizierer deklarierte Variable bestätigt `WithEvents` , dass der Typ, zu dem die Variable gehört, den Satz von Ereignissen behandelt, den die Variable auslöst. Wenn der Variablen ein Wert zugewiesen wird, entbindet die von der `WithEvents` Deklaration erstellte Eigenschaft jeden vorhandenen Ereignishandler und verknüpft den neuen Ereignishandler über die- `Add` Methode.

 **Fehler-ID:** BC30594

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Deklarieren Sie den Ereignishandler `Shared` .

## <a name="see-also"></a>Siehe auch

- [Freigegeben](../modifiers/shared.md)
- [WithEvents](../modifiers/withevents.md)
