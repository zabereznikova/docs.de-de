---
title: "Zugriff des freigegebenen Members über eine Instanz; qualifizierende Ausdruck wird nicht ausgewertet | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42025
- BC42025
dev_langs:
- VB
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 39be3c95d5acc20afe3a33be9d4db48c09f99a9c
ms.lasthandoff: 03/13/2017

---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a>Zugriff des freigegebenen Members, konstanten Members, Enumerationsmembers oder geschachtelten Typs über eine Instanz; der qualifizierende Ausdruck wird nicht ausgewertet
Eine Instanzvariable einer Klasse oder Struktur dient für den Zugriff auf eine `Shared` Variable, Eigenschaft, Prozedur oder Ereignis in dieser Klasse oder Struktur definiert. Diese Warnung kann auch auftreten, wenn eine Instanzvariable zum Zugriff auf einen implizit freigegebenen Member einer Klasse oder Struktur, z. B. eine Konstante oder Enumeration oder einer geschachtelten Klasse oder Struktur verwendet wird.  
  
 Der Zweck der Freigabe ist nur eine einzige Kopie dieses Members zu erstellen, und diese einzelne Kopie für jede Instanz der Klasse oder Struktur, in der sie deklariert ist, verfügbar zu machen. Es ist diesem Grund für den Zugriff auf eine `Shared` Member über den Namen der Klasse oder Struktur, statt über eine Variable, die eine einzelne Instanz dieser Klasse oder Struktur enthält.  
  
 Zugreifen auf eine `Shared` Member über eine Instanzvariable kann erschweren, Code zu verstehen, indem die Tatsache, dass der Member verdeckt `Shared`. Darüber, wenn ein solcher Zugriff Bestandteil eines Ausdrucks ist, der weitere Aktionen ausführt, z. B. ein `Function` Prozedur, die eine Instanz des freigegebenen Members zurückgibt [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] umgeht den Ausdruck sowie ggf. Weitere Aktionen, die sie andernfalls führen würde.  
  
 Weitere Informationen und ein Beispiel finden Sie unter [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder Warnungen als Fehler behandeln, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42025  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwenden Sie den Namen der Klasse oder Struktur, definiert die `Shared` Member zugreifen, wie im folgenden Beispiel gezeigt.  
  
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
>  Warnung für die Effekte der Bereich sein, wenn zwei Programmierelemente denselben Namen haben. Im vorherigen Beispiel, wenn Sie eine Instanz mithilfe von deklarieren `Dim testClass as testClass = Nothing`, behandelt der Compiler einen Aufruf von `testClass.sayHello()` wie ein Zugriff auf die Methode über den Klassennamen und keine Warnung auftritt.  
  
## <a name="see-also"></a>Siehe auch  
 [Freigegebene](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Gültigkeitsbereich in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
