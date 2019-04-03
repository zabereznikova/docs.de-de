---
title: <type1> '<typename>' muss '<methodname>' für die <interfacename>-Schnittstelle implementieren.
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: b8bcb16798284a09608ba6942226ef07c6859d4f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824201"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a>\<Typ1 >'\<Typname > 'implementieren muss'\<Methodname > 'für Schnittstelle'\<Schnittstellenname >'
Eine Klasse oder Struktur vorgibt, eine Schnittstelle zu implementieren, ohne dass eine Prozedur, die von der Schnittstelle definierten implementiert. Jeder Member der Schnittstelle muss implementiert werden.  
  
 **Fehler-ID:** BC30149  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Deklarieren Sie eine Prozedur mit dem gleichen Namen und die gleiche Signatur wie in der Schnittstelle definiert. Müssen Sie mindestens die `End Function` oder `End Sub` Anweisung.  
  
2.  Hinzufügen einer `Implements` Klausel am Ende der `Function` oder `Sub` Anweisung. Zum Beispiel:  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
