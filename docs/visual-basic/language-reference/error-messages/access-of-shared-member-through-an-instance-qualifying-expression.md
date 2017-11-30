---
title: "Zugriff des freigegebenen Members, konstanten Members, Enumerationsmembers oder geschachtelten Typs über eine Instanz; der qualifizierende Ausdruck wird nicht ausgewertet"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords: BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bcf3c37852e73464eec612e9e1d458ca707342e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Zugriff des freigegebenen Members, konstanten Members, Enumerationsmembers oder geschachtelten Typs über eine Instanz; der qualifizierende Ausdruck wird nicht ausgewertet
Eine Instanzvariable einer Klasse oder Struktur wird verwendet, für den Zugriff auf eine `Shared` Variable, Eigenschaft, Prozedur oder Ereignis in dieser Klasse oder Struktur definiert. Diese Warnung kann auch auftreten, wenn eine Instanzvariablen verwendet wird, um eine implizit freigegebenen Member einer Klasse oder Struktur, z. B. eine Konstante oder -Enumeration, oder eine geschachtelte Klasse oder Struktur zuzugreifen.  
  
 Der Zweck der Freigabe ist nur eine einzige Kopie dieses Element zu erstellen, und diese einzelne Kopie für jede Instanz der Klasse oder Struktur, die in der sie deklariert ist verfügbar zu machen. Sie ist konsistent mit diesem Zweck den Zugriff auf eine `Shared` Member über den Namen der Klasse oder Struktur, anstatt über eine Variable, eine einzelne Instanz dieser Klasse oder Struktur enthält.  
  
 Zugreifen auf eine `Shared` Member über eine Instanzvariable kann Lesbarkeit Ihres Codes schwieriger zu verstehen, indem die Tatsache, dass das Element verdeckt `Shared`. Darüber hinaus solcher Zugriff ist Teil eines Ausdrucks, der weitere Aktionen ausführt, z. B. eine `Function` Prozedur, die eine Instanz des freigegebenen Members zurückgibt [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] umgeht den Ausdruck und alle weiteren erforderlichen Aktionen es andernfalls führen würde.  
  
 Weitere Informationen und ein Beispiel finden Sie unter [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42025  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwenden Sie den Namen der Klasse oder Struktur, definiert der `Shared` Member darauf zugreifen, wie im folgenden Beispiel gezeigt.  
  
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
>  Warnung für die Auswirkungen des Bereichs vorliegen, wenn zwei Programmierelemente denselben Namen haben. Im vorherigen Beispiel, wenn Sie eine Instanz mit deklarieren `Dim testClass as testClass = Nothing`, behandelt der Compiler einen Aufruf von `testClass.sayHello()` wie ein Zugriff auf die Methode über den Klassennamen und keine Warnung auftritt.  
  
## <a name="see-also"></a>Siehe auch  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [Gültigkeitsbereich in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
