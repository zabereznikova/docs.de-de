---
title: Ereignisse freigegebener WithEvents-Variablen können nicht von freigegebenen Methoden behandelt werden.
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: 09f56d340322ee88afc54e7e8a53716777782d47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505769"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>Ereignisse freigegebener WithEvents-Variablen können nicht von freigegebenen Methoden behandelt werden.
Eine Variable mit dem `Shared` Modifizierer ist eine freigegebene Variable. Eine freigegebene Variable gibt genau einen Speicherort an. Eine Variable mit dem `WithEvents` Modifizierer bestätigt, dass der Typ, der die Variable angehört, den Satz von Ereignissen verarbeitet der Variablen ausgelöst. Ein Wert der Variablen zugewiesen ist, die Eigenschaft erstellt, wenn die `WithEvents` Deklaration hebt alle vorhandenen Ereignishandler und verknüpft den neuen Ereignishandler über die `Add` Methode.  
  
 **Fehler-ID:** BC30594  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Deklarieren Sie Ihre Ereignishandler `Shared`.  
  
## <a name="see-also"></a>Siehe auch
- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
