---
title: <type1> '<typename>' muss '<methodname>' für die <interfacename>-Schnittstelle implementieren.
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: c387b0225375f4675042bef593b23a084305b4fd
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591599"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a>\<Typ1 >'\<Typname > 'implementieren muss'\<Methodname > 'für Schnittstelle'\<Schnittstellenname >'
Eine Klasse oder Struktur beansprucht, eine Schnittstelle zu implementieren, implementiert jedoch keine durch die Schnittstelle definierte Prozedur. Jeder Member der Schnittstelle muss implementiert werden.  
  
 **Fehler-ID:** BC30149  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Deklarieren Sie eine Prozedur mit dem gleichen Namen und der gleichen Signatur wie in der-Schnittstelle definiert. Stellen Sie sicher, dass Sie mindestens die `End Function`-oder `End Sub`-Anweisung einschließen.  
  
2. Fügen Sie am Ende der `Function`-oder `Sub`-Anweisung eine `Implements`-Klausel hinzu. Zum Beispiel:  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)
- [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
