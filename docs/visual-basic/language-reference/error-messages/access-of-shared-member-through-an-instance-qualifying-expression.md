---
title: Zugriff des freigegebenen Members, konstanten Members, Enumerationsmembers oder geschachtelten Typs über eine Instanz; der qualifizierende Ausdruck wird nicht ausgewertet
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 773a97c301e7cb5bec0234ae466d487ec9716437
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250349"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Zugriff des freigegebenen Members, konstanten Members, Enumerationsmembers oder geschachtelten Typs über eine Instanz; der qualifizierende Ausdruck wird nicht ausgewertet

Eine Instanzvariable einer Klasse oder Struktur wird verwendet, um auf eine Variable, eine Eigenschaft, eine Prozedur oder ein Ereignis in @no__t 0 zuzugreifen, die in dieser Klasse oder Struktur definiert ist. Diese Warnung kann auch auftreten, wenn eine Instanzvariable für den Zugriff auf einen implizit freigegebenen Member einer Klasse oder Struktur verwendet wird, z. b. eine Konstante oder Enumeration oder eine geclusterte Klasse oder Struktur.

Der Zweck der Freigabe eines Members besteht darin, nur eine einzige Kopie dieses Members zu erstellen und diese einzelne Kopie für jede Instanz der Klasse oder Struktur verfügbar zu machen, in der Sie deklariert ist. Der Zugriff auf ein `Shared`-Member über den Namen der Klasse oder Struktur ist konsistent, anstatt über eine Variable, die eine einzelne Instanz dieser Klasse oder Struktur enthält.

Wenn Sie über eine Instanzvariable auf ein `Shared`-Element zugreifen, kann Ihr Code schwieriger zu verstehen sein, da die Tatsache verdeckt wird, dass der Member `Shared` ist. Wenn ein solcher Zugriff außerdem Teil eines Ausdrucks ist, der andere Aktionen ausführt, z. b. eine `Function`-Prozedur, die eine Instanz des freigegebenen Members zurückgibt, umgeht Visual Basic den Ausdruck und alle anderen Aktionen, die er andernfalls ausführen würde.  
  
Weitere Informationen und ein Beispiel finden Sie unter [Shared](../modifiers/shared.md).  
  
Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
**Fehler-ID:** BC42025  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
Verwenden Sie den Namen der Klasse oder Struktur, die das `Shared`-Member definiert, um darauf zuzugreifen, wie im folgenden Beispiel gezeigt:
  
```vb
Public Class TestClass
    Public Shared Sub SayHello()
        MsgBox("Hello")
    End Sub
End Class
  
Module Program
    Public Sub Main()  
        ' Access a shared method through an instance variable.  
        ' This generates a warning.  
        Dim tc As New TestClass()
        tc.SayHello()
  
        ' Access a shared method by using the class name.  
        ' This does not generate a warning.  
        TestClass.SayHello()
    End Sub  
End Module  
```  
  
> [!NOTE]
> Geben Sie eine Warnung für die Auswirkungen des Bereichs an, wenn zwei Programmier Elemente denselben Namen haben. Wenn Sie im vorherigen Beispiel eine Instanz mit `Dim testClass as testClass = Nothing` deklarieren, behandelt der Compiler einen Aufrufen von `testClass.sayHello()` als Zugriff auf die Methode über den Klassennamen, und es tritt keine Warnung auf.
  
## <a name="see-also"></a>Siehe auch

- [Shared](../modifiers/shared.md)
- [Bereich in Visual Basic](../../programming-guide/language-features/declared-elements/scope.md)
