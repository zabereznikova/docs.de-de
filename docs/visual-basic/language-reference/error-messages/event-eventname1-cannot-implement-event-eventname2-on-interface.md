---
title: Das "<eventname1>"-Ereignis kann das "<eventname2>"-Ereignis für die "<interface>"-Schnittstelle nicht implementieren, da die entsprechenden Delegattypen "<delegate1>" und "<delegate2>" nicht übereinstimmen.
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: b1e0728a4f865b432b142df4ded1efddb376201e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874334"
---
# <a name="event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a>Das "\<eventname1>"-Ereignis kann das "\<eventname2>"-Ereignis für die "\<interface>"-Schnittstelle nicht implementieren, da die entsprechenden Delegattypen "\<delegate1>" und "\<delegate2>" nicht übereinstimmen.

Visual Basic kann kein Ereignis implementieren, da der Delegattyp des Ereignisses nicht mit dem Delegattyp des Ereignisses in der Schnittstelle identisch ist. Dieser Fehler kann auftreten, wenn Sie mehrere Ereignisse in einer Schnittstelle definieren und anschließend versuchen, sie mit demselben Ereignis zu implementieren. Ein Ereignis kann zwei oder mehrere Ereignisse nur implementieren, wenn alle implementierten Ereignisse mit der `As` -Syntax deklariert werden und denselben Delegattyp angeben.  
  
 **Fehler-ID:** BC31423  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Implementieren Sie die Ereignisse separat.  
  
     – oder –  
  
- Definieren Sie die Ereignisse in der Schnittstelle mithilfe der `As` -Syntax, und geben Sie den gleichen Delegattyp an.  
  
## <a name="see-also"></a>Weitere Informationen

- [Event-Anweisung](../statements/event-statement.md)
- [Delegate-Anweisung](../statements/delegate-statement.md)
- [Ereignisse](../../programming-guide/language-features/events/index.md)
