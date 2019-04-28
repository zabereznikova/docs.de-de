---
title: Das "<eventname1>"-Ereignis kann das "<eventname2>"-Ereignis für die "<interface>"-Schnittstelle nicht implementieren, da die entsprechenden Delegattypen "<delegate1>" und "<delegate2>" nicht übereinstimmen.
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: 9581168fa86f8f0715e004b60c2eb2a813cd38ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803297"
---
# <a name="event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a>Ereignis '\<ereignisname1 >' kann Ereignis nicht implementieren, '\<eventname2 >' Schnittstelle '\<Schnittstelle >' da ihren Delegattypen\<delegate1 > 'und'\<delegate2 >' stimmen nicht überein
Visual Basic kann kein Ereignis implementiert werden, weil der Delegattyp des Ereignisses nicht den Delegattyp des Ereignisses in der Schnittstelle entspricht. Dieser Fehler kann auftreten, wenn Sie mehrere Ereignisse in einer Schnittstelle definieren und anschließend versuchen, sie mit demselben Ereignis zu implementieren. Ein Ereignis kann zwei oder mehrere Ereignisse nur implementieren, wenn alle implementierten Ereignisse mit der `As` -Syntax deklariert werden und denselben Delegattyp angeben.  
  
 **Fehler-ID:** BC31423  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Implementieren Sie die Ereignisse separat.  
  
     – oder –  
  
- Definieren Sie die Ereignisse in der Schnittstelle mithilfe der `As` Syntax, und geben Sie den gleichen Delegattyp.  
  
## <a name="see-also"></a>Siehe auch

- [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)
- [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)
