---
title: Zugriff des freigegebenen Members, konstanten Members, Enumerationsmembers oder geschachtelten Typs über eine Instanz; der qualifizierende Ausdruck wird nicht ausgewertet
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 8e6ddab16c59d7ce95d96b377e3f372f6ebe5278
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61751604"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Zugriff des freigegebenen Members, konstanten Members, Enumerationsmembers oder geschachtelten Typs über eine Instanz; der qualifizierende Ausdruck wird nicht ausgewertet
Eine Instanzvariable für eine Klasse oder Struktur wird verwendet, für den Zugriff auf eine `Shared` Variable, Eigenschaft, Prozedur oder das Ereignis in dieser Klasse oder Struktur definiert. Diese Warnung kann auch auftreten, wenn eine Instanzvariable Zugriff auf eine implizit freigegebenen Member einer Klasse oder Struktur, z. B. eine Konstante oder -Enumeration oder eine geschachtelte Klasse oder Struktur verwendet wird.  
  
 Ein Element freigeben dient nur eine einzige Kopie dieses Elements zu erstellen und Verfügbarmachen dieser einzelnen Kopie für jede Instanz der Klasse oder Struktur, die in der sie deklariert ist. Sie ist konsistent mit diesem Zweck den Zugriff auf eine `Shared` Member über den Namen der Klasse oder Struktur und nicht durch eine Variable, die eine einzelne Instanz dieser Klasse oder Struktur enthält.  
  
 Zugreifen auf eine `Shared` Member durch Instanzvariable kann erschweren den Code, zu verstehen, die Tatsache, dass das Element verdeckt `Shared`. Darüber hinaus Zugriff ist Teil eines Ausdrucks, der andere Aktionen ausführt, z. B. eine `Function` Prozedur, die eine Instanz des freigegebenen Members zurückgibt, Visual Basic umgeht den Ausdruck sowie alle weiteren erforderlichen Aktionen sie würden andernfalls ausführen.  
  
 Weitere Informationen und ein Beispiel finden Sie unter [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42025  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verwenden Sie den Namen der Klasse oder Struktur, die definiert die `Shared` Member darauf zugreifen, wie im folgenden Beispiel gezeigt.  
  
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
>  Warnung für die Auswirkungen des Bereichs sein, wenn zwei Programmierelemente mit den gleichen Namen haben. Im vorherigen Beispiel, wenn Sie eine Instanz mit deklarieren `Dim testClass as testClass = Nothing`, behandelt der Compiler einen Aufruf von `testClass.sayHello()` tritt ebenfalls ein Zugriff auf die Methode durch den Namen der Klasse und keine Warnung.  
  
## <a name="see-also"></a>Siehe auch

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Gültigkeitsbereich in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
