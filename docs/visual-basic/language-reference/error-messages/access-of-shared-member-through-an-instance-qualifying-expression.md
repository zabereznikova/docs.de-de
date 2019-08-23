---
title: Zugriff des freigegebenen Members, konstanten Members, Enumerationsmembers oder geschachtelten Typs über eine Instanz; der qualifizierende Ausdruck wird nicht ausgewertet
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 3174d463744303e8c90ed0b2e1a4d86ed08fbcfb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947699"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Zugriff des freigegebenen Members, konstanten Members, Enumerationsmembers oder geschachtelten Typs über eine Instanz; der qualifizierende Ausdruck wird nicht ausgewertet
Eine Instanzvariable einer Klasse oder Struktur wird verwendet, um auf `Shared` eine Variable, eine Eigenschaft, eine Prozedur oder ein Ereignis zuzugreifen, die in dieser Klasse oder Struktur definiert ist. Diese Warnung kann auch auftreten, wenn eine Instanzvariable für den Zugriff auf einen implizit freigegebenen Member einer Klasse oder Struktur verwendet wird, z. b. eine Konstante oder Enumeration oder eine geclusterte Klasse oder Struktur.  
  
 Der Zweck der Freigabe eines Members besteht darin, nur eine einzige Kopie dieses Members zu erstellen und diese einzelne Kopie für jede Instanz der Klasse oder Struktur verfügbar zu machen, in der Sie deklariert ist. Der Zugriff auf ein `Shared` Member über den Namen der Klasse oder Struktur ist konsistent, anstatt über eine Variable, die eine einzelne Instanz dieser Klasse oder Struktur enthält.  
  
 Wenn Sie `Shared` über eine Instanzvariable auf einen Member zugreifen, kann es schwieriger sein, den Code zu verstehen, indem die `Shared`Tatsache verdeckt wird, dass der Member ist. Wenn ein solcher Zugriff außerdem Teil eines Ausdrucks ist, der andere Aktionen ausführt, z. b `Function` . eine Prozedur, die eine Instanz des freigegebenen Members zurückgibt, Visual Basic den Ausdruck und alle anderen Aktionen, die andernfalls durchgeführt werden, umgangen.  
  
 Weitere Informationen und ein Beispiel finden Sie unter [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42025  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verwenden Sie den Namen der Klasse oder Struktur, die den `Shared` Member definiert, um darauf zuzugreifen, wie im folgenden Beispiel gezeigt.  
  
```vb  
Public Class testClass  
    Public Shared Sub sayHello()  
        MsgBox("Hello")  
    End Sub  
End Class  
  
Module testModule  
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New testClass  
        tc.sayHello()  
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        testClass.sayHello()  
    End Sub  
End Module  
```  
  
> [!NOTE]
> Geben Sie eine Warnung für die Auswirkungen des Bereichs an, wenn zwei Programmier Elemente denselben Namen haben. Wenn Sie im vorherigen Beispiel mithilfe `Dim testClass as testClass = Nothing`von eine-Instanz deklarieren, behandelt der Compiler einen Aufrufen von als Zugriff auf die-Methode über den Klassennamen, und es tritt keine Warnung auf. `testClass.sayHello()`  
  
## <a name="see-also"></a>Siehe auch

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Bereich in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
