---
title: <type1>"<typename>"implementieren muss"<membername>"für Schnittstelle"<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 86b0d46e0e27b2fd8d1fccb37f4a3c45e95f5f63
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295327"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a>\<Typ1 >'\<Typename > 'implementieren müssen'\<Membername >' für die Schnittstelle '\<Schnittstellenname >'
'\<Typename >' implementieren muss '\<Membername >' für die Schnittstelle '\<Schnittstellenname >'. Die implementierende Eigenschaft müssen übereinstimmen 'ReadOnly' / 'WriteOnly' Spezifizierer.  
  
 Eine Klasse oder Struktur vorgibt, eine Schnittstelle zu implementieren, aber eine Prozedur, Eigenschaft oder das Ereignis definiert, die von der Schnittstelle nicht implementiert. Jeder Member der Schnittstelle muss implementiert werden.  
  
 **Fehler-ID:** BC30154  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Deklarieren Sie ein Element mit dem gleichen Namen und die gleiche Signatur wie in der Schnittstelle definiert. Müssen Sie mindestens die `End Function`, `End Sub`, oder `End Property` Anweisung.  
  
2. Hinzufügen einer `Implements` Klausel am Ende der `Function`, `Sub`, `Property`, oder `Event` Anweisung. Zum Beispiel:  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3. Wenn Sie eine Eigenschaft zu implementieren, stellen sicher, dass `ReadOnly` oder `WriteOnly` wird verwendet, auf die gleiche Weise wie die Schnittstellendefinition.  
  
4. Wenn Sie eine Eigenschaft implementieren möchten, deklarieren `Get` und `Set` Verfahren nach Bedarf.  
  
## <a name="see-also"></a>Siehe auch

- [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
