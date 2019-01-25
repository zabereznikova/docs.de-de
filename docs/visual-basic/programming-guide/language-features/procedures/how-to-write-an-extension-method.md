---
title: 'Vorgehensweise: Schreiben einer Erweiterungsmethode (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 019104956b21e527c0498c286d85da27abdc5695
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576070"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a><span data-ttu-id="1931f-102">Vorgehensweise: Schreiben einer Erweiterungsmethode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1931f-102">How to: Write an Extension Method (Visual Basic)</span></span>
<span data-ttu-id="1931f-103">Erweiterungsmethoden können Sie einer vorhandenen Klasse Methoden hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1931f-103">Extension methods enable you to add methods to an existing class.</span></span> <span data-ttu-id="1931f-104">Die Erweiterungsmethode kann aufgerufen werden, als handele es sich um eine Instanz dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="1931f-104">The extension method can be called as if it were an instance of that class.</span></span>  
  
### <a name="to-define-an-extension-method"></a><span data-ttu-id="1931f-105">So definieren Sie eine Extension-Methode</span><span class="sxs-lookup"><span data-stu-id="1931f-105">To define an extension method</span></span>  
  
1.  <span data-ttu-id="1931f-106">Öffnen Sie eine neue oder vorhandene Visual Basic-Anwendung in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1931f-106">Open a new or existing Visual Basic application in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="1931f-107">Am Anfang der Datei, in der Sie eine Erweiterungsmethode definieren möchten, müssen schließen Sie die folgende importanweisung ein:</span><span class="sxs-lookup"><span data-stu-id="1931f-107">At the top of the file in which you want to define an extension method, include the following import statement:</span></span>  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  <span data-ttu-id="1931f-108">Beginnen Sie in einem Modul in Ihrer neuen oder vorhandenen Anwendung die Definition der Methode mit dem Erweiterungsattribut:</span><span class="sxs-lookup"><span data-stu-id="1931f-108">Within a module in your new or existing application, begin the method definition with the extension attribute:</span></span>  
  
    ```  
    <Extension()>  
    ```  
  
4.  <span data-ttu-id="1931f-109">Deklarieren Sie die Methode auf die normale Weise, außer dass der Typ des ersten Parameters den Datentyp sein muss, die, den Sie erweitern möchten.</span><span class="sxs-lookup"><span data-stu-id="1931f-109">Declare your method in the ordinary way, except that the type of the first parameter must be the data type you want to extend.</span></span>  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a><span data-ttu-id="1931f-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1931f-110">Example</span></span>  
 <span data-ttu-id="1931f-111">Das folgende Beispiel deklariert eine Erweiterungsmethode in Modul `StringExtensions`.</span><span class="sxs-lookup"><span data-stu-id="1931f-111">The following example declares an extension method in module `StringExtensions`.</span></span> <span data-ttu-id="1931f-112">Das zweite Modul `Module1`, importiert `StringExtensions` und ruft die Methode.</span><span class="sxs-lookup"><span data-stu-id="1931f-112">A second module, `Module1`, imports `StringExtensions` and calls the method.</span></span> <span data-ttu-id="1931f-113">Wenn sie aufgerufen wird, muss die Erweiterungsmethode im Gültigkeitsbereich befinden.</span><span class="sxs-lookup"><span data-stu-id="1931f-113">The extension method must be in scope when it is called.</span></span> <span data-ttu-id="1931f-114">Erweiterungsmethode `PrintAndPunctuate` erweitert die <xref:System.String> Klasse mit einer Methode, die die Zeichenfolgeninstanz zeigt gefolgt durch eine Folge von Interpunktionszeichen, die als Parameter gesendet.</span><span class="sxs-lookup"><span data-stu-id="1931f-114">Extension method `PrintAndPunctuate` extends the <xref:System.String> class with a method that displays the string instance followed by a string of punctuation symbols sent in as a parameter.</span></span>  
  
```vb  
' Declarations will typically be in a separate module.  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
```vb  
' Import the module that holds the extension method you want to use,   
' and call it.  
  
Imports ConsoleApplication2.StringExtensions  
  
Module Module1  
  
    Sub Main()  
        Dim example = "Hello"  
        example.PrintAndPunctuate("?")  
        example.PrintAndPunctuate("!!!!")  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="1931f-115">Beachten Sie, dass die Methode mit zwei Parametern definiert und mit nur einem aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1931f-115">Notice that the method is defined with two parameters and called with only one.</span></span> <span data-ttu-id="1931f-116">Der erste Parameter, `aString`, in der Methode ist die Definition an gebunden `example`, die Instanz von `String` , die die Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="1931f-116">The first parameter, `aString`, in the method definition is bound to `example`, the instance of `String` that calls the method.</span></span> <span data-ttu-id="1931f-117">Die Ausgabe des Beispiels sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="1931f-117">The output of the example is as follows:</span></span>  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a><span data-ttu-id="1931f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1931f-118">See also</span></span>
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="1931f-119">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="1931f-119">Extension Methods</span></span>](./extension-methods.md)
- [<span data-ttu-id="1931f-120">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1931f-120">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="1931f-121">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="1931f-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="1931f-122">Gültigkeitsbereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1931f-122">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
