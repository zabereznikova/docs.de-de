---
title: <type1><typename> muss <membername> für die Schnittstelle <interfacename> implementieren.
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 7b74ee3a05000f5d6cd94176b48dea116b647a2a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872170"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a>\<type1>\<typename> muss \<membername> für die Schnittstelle \<interfacename> implementieren.

' \<typename> ' muss ' \<membername> ' für die-Schnittstelle implementieren \<interfacename> . Die implementierende Eigenschaft muss über übereinstimmende "schreibgeschützte"/"schreibgeschützte"-spezifiatoren verfügen.  
  
 Eine Klasse oder Struktur beansprucht, eine Schnittstelle zu implementieren, implementiert jedoch keine Prozedur, Eigenschaft oder ein Ereignis, das von der Schnittstelle definiert wird. Jeder Member der Schnittstelle muss implementiert werden.  
  
 **Fehler-ID:** BC30154  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Deklarieren Sie einen Member mit dem gleichen Namen und der gleichen Signatur wie in der-Schnittstelle definiert. Stellen Sie sicher, dass Sie mindestens die- `End Function` ,- `End Sub` oder-Anweisung einschließen `End Property` .  
  
2. Fügen Sie eine-Klausel am Ende der-,-,- `Implements` oder- `Function` Anweisung hinzu `Sub` `Property` `Event` . Beispiel:  
  
    ```vb  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. Wenn Sie eine Eigenschaft implementieren, stellen Sie sicher, dass `ReadOnly` oder `WriteOnly` auf die gleiche Weise wie in der Schnittstellen Definition verwendet wird.  
  
4. Wenn Sie eine Eigenschaft implementieren, deklarieren Sie nach Bedarf `Get` -und- `Set` Prozeduren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Implements-Anweisung](../statements/implements-statement.md)
- [Schnittstellen](../../programming-guide/language-features/interfaces/index.md)
