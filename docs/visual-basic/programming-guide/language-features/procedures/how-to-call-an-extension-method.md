---
title: 'Gewusst wie: Aufrufen einer Erweiterungsmethode (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 25b5a86af15694e6f64f96a5d5d645a01f8f1f12
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-extension-method-visual-basic"></a><span data-ttu-id="48382-102">Gewusst wie: Aufrufen einer Erweiterungsmethode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48382-102">How to: Call an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="48382-103">Erweiterungsmethoden können Sie Methoden zur einer vorhandenen Klasse hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="48382-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="48382-104">Nachdem eine Erweiterungsmethode deklariert und in den Gültigkeitsbereich eingebunden ist, können Sie es wie eine Instanzmethode des Typs aufrufen, die sie erweitert.</span><span class="sxs-lookup"><span data-stu-id="48382-104">After an extension method is declared and brought into scope, you can call it like an instance method of the type that it extends.</span></span> <span data-ttu-id="48382-105">Weitere Informationen über das Schreiben einer Erweiterungsmethode finden Sie unter [wie: Schreiben einer Erweiterungsmethode](./how-to-write-an-extension-method.md).</span><span class="sxs-lookup"><span data-stu-id="48382-105">For more information about how to write an extension method, see [How to: Write an Extension Method](./how-to-write-an-extension-method.md).</span></span>  
  
 <span data-ttu-id="48382-106">Nachfolgend finden Sie unter Erweiterungsmethode `PrintAndPunctuate`, die die Zeichenfolgeninstanz angezeigt werden, die, gefolgt von den Wert, den aufgerufen, für den zweiten Parameter gesendet `punc`.</span><span class="sxs-lookup"><span data-stu-id="48382-106">The following instructions refer to extension method `PrintAndPunctuate`, which will display the string instance that invokes it, followed by whatever value is sent in for the second parameter, `punc`.</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="48382-107">Die Methode muss im Gültigkeitsbereich sein, wenn sie aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="48382-107">The method must be in scope when it is called.</span></span>  
  
### <a name="to-call-an-extension-method"></a><span data-ttu-id="48382-108">Aufrufen eine Erweiterungsmethode</span><span class="sxs-lookup"><span data-stu-id="48382-108">To call an extension method</span></span>  
  
1.  <span data-ttu-id="48382-109">Deklarieren Sie eine Variable, die den Datentyp des ersten Parameters der Erweiterungsmethode aufweist.</span><span class="sxs-lookup"><span data-stu-id="48382-109">Declare a variable that has the data type of the first parameter of the extension method.</span></span> <span data-ttu-id="48382-110">Für `PrintAndPunctuate`, müssen Sie eine <xref:System.String> Variablen:</span><span class="sxs-lookup"><span data-stu-id="48382-110">For `PrintAndPunctuate`, you need a <xref:System.String> variable:</span></span>  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2.  <span data-ttu-id="48382-111">Variable wird die Erweiterungsmethode aufgerufen, und sein Wert wird auf den ersten Parameter gebunden `aString`.</span><span class="sxs-lookup"><span data-stu-id="48382-111">That variable will invoke the extension method, and its value is bound to the first parameter, `aString`.</span></span> <span data-ttu-id="48382-112">Zeigt die folgenden aufrufanweisung `Ready?`.</span><span class="sxs-lookup"><span data-stu-id="48382-112">The following calling statement will display `Ready?`.</span></span>  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     <span data-ttu-id="48382-113">Beachten Sie, die den Aufruf dieser Erweiterungsmethode nur aussieht wie einen Aufruf eines der <xref:System.String> Instanzmethoden, die einen Parameter erfordern:</span><span class="sxs-lookup"><span data-stu-id="48382-113">Notice that the call to this extension method looks just like a call to any one of the <xref:System.String> instance methods that require one parameter:</span></span>  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3.  <span data-ttu-id="48382-114">Deklarieren Sie eine weitere Zeichenfolgenvariable, und rufen Sie die Methode erneut, um festzustellen, dass sie mit einer beliebigen Zeichenfolge funktioniert.</span><span class="sxs-lookup"><span data-stu-id="48382-114">Declare another string variable and call the method again to see that it works with any string.</span></span>  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     <span data-ttu-id="48382-115">Das Ergebnis dieser Zeit ist: `or not!!!`.</span><span class="sxs-lookup"><span data-stu-id="48382-115">The result this time is: `or not!!!`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48382-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48382-116">Example</span></span>  
 <span data-ttu-id="48382-117">Der folgende Code ist ein vollständiges Beispiel für die Erstellung und Verwendung einer Erweiterung für einfachen-Methode.</span><span class="sxs-lookup"><span data-stu-id="48382-117">The following code is a complete example of the creation and use of a simple extension method.</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
Imports ConsoleApplication1.StringExtensions  
  
Module Module1  
  
    Sub Main()  
  
        Dim example = "Hello"  
        example.PrintAndPunctuate(".")  
        example.PrintAndPunctuate("!!!!")  
  
        Dim example2 = "Goodbye"  
        example2.PrintAndPunctuate("?")  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
End Module  
  
' Output:  
' Hello.  
' Hello!!!!  
' Goodbye?  
```  
  
## <a name="see-also"></a><span data-ttu-id="48382-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48382-118">See Also</span></span>  
 [<span data-ttu-id="48382-119">Gewusst wie: Schreiben einer Erweiterungsmethode</span><span class="sxs-lookup"><span data-stu-id="48382-119">How to: Write an Extension Method</span></span>](./how-to-write-an-extension-method.md)  
 [<span data-ttu-id="48382-120">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="48382-120">Extension Methods</span></span>](./extension-methods.md)  
 [<span data-ttu-id="48382-121">Gültigkeitsbereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="48382-121">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
