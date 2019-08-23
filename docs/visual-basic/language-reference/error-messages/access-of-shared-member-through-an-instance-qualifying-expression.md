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
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a><span data-ttu-id="83dad-102">Zugriff des freigegebenen Members, konstanten Members, Enumerationsmembers oder geschachtelten Typs über eine Instanz; der qualifizierende Ausdruck wird nicht ausgewertet</span><span class="sxs-lookup"><span data-stu-id="83dad-102">Access of shared member through an instance; qualifying expression will not be evaluated</span></span>
<span data-ttu-id="83dad-103">Eine Instanzvariable einer Klasse oder Struktur wird verwendet, um auf `Shared` eine Variable, eine Eigenschaft, eine Prozedur oder ein Ereignis zuzugreifen, die in dieser Klasse oder Struktur definiert ist.</span><span class="sxs-lookup"><span data-stu-id="83dad-103">An instance variable of a class or structure is used to access a `Shared` variable, property, procedure, or event defined in that class or structure.</span></span> <span data-ttu-id="83dad-104">Diese Warnung kann auch auftreten, wenn eine Instanzvariable für den Zugriff auf einen implizit freigegebenen Member einer Klasse oder Struktur verwendet wird, z. b. eine Konstante oder Enumeration oder eine geclusterte Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="83dad-104">This warning can also occur if an instance variable is used to access an implicitly shared member of a class or structure, such as a constant or enumeration, or a nested class or structure.</span></span>  
  
 <span data-ttu-id="83dad-105">Der Zweck der Freigabe eines Members besteht darin, nur eine einzige Kopie dieses Members zu erstellen und diese einzelne Kopie für jede Instanz der Klasse oder Struktur verfügbar zu machen, in der Sie deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="83dad-105">The purpose of sharing a member is to create only a single copy of that member and make that single copy available to every instance of the class or structure in which it is declared.</span></span> <span data-ttu-id="83dad-106">Der Zugriff auf ein `Shared` Member über den Namen der Klasse oder Struktur ist konsistent, anstatt über eine Variable, die eine einzelne Instanz dieser Klasse oder Struktur enthält.</span><span class="sxs-lookup"><span data-stu-id="83dad-106">It is consistent with this purpose to access a `Shared` member through the name of its class or structure, rather than through a variable that holds an individual instance of that class or structure.</span></span>  
  
 <span data-ttu-id="83dad-107">Wenn Sie `Shared` über eine Instanzvariable auf einen Member zugreifen, kann es schwieriger sein, den Code zu verstehen, indem die `Shared`Tatsache verdeckt wird, dass der Member ist.</span><span class="sxs-lookup"><span data-stu-id="83dad-107">Accessing a `Shared` member through an instance variable can make your code more difficult to understand by obscuring the fact that the member is `Shared`.</span></span> <span data-ttu-id="83dad-108">Wenn ein solcher Zugriff außerdem Teil eines Ausdrucks ist, der andere Aktionen ausführt, z. b `Function` . eine Prozedur, die eine Instanz des freigegebenen Members zurückgibt, Visual Basic den Ausdruck und alle anderen Aktionen, die andernfalls durchgeführt werden, umgangen.</span><span class="sxs-lookup"><span data-stu-id="83dad-108">Furthermore, if such access is part of an expression that performs other actions, such as a `Function` procedure that returns an instance of the shared member, Visual Basic bypasses the expression and any other actions it would otherwise perform.</span></span>  
  
 <span data-ttu-id="83dad-109">Weitere Informationen und ein Beispiel finden Sie unter [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="83dad-109">For more information and an example, see [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
 <span data-ttu-id="83dad-110">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="83dad-110">By default, this message is a warning.</span></span> <span data-ttu-id="83dad-111">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="83dad-111">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="83dad-112">**Fehler-ID:** BC42025</span><span class="sxs-lookup"><span data-stu-id="83dad-112">**Error ID:** BC42025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="83dad-113">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="83dad-113">To correct this error</span></span>  
  
- <span data-ttu-id="83dad-114">Verwenden Sie den Namen der Klasse oder Struktur, die den `Shared` Member definiert, um darauf zuzugreifen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="83dad-114">Use the name of the class or structure that defines the `Shared` member to access it, as shown in the following example.</span></span>  
  
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
> <span data-ttu-id="83dad-115">Geben Sie eine Warnung für die Auswirkungen des Bereichs an, wenn zwei Programmier Elemente denselben Namen haben.</span><span class="sxs-lookup"><span data-stu-id="83dad-115">Be alert for the effects of scope when two programming elements have the same name.</span></span> <span data-ttu-id="83dad-116">Wenn Sie im vorherigen Beispiel mithilfe `Dim testClass as testClass = Nothing`von eine-Instanz deklarieren, behandelt der Compiler einen Aufrufen von als Zugriff auf die-Methode über den Klassennamen, und es tritt keine Warnung auf. `testClass.sayHello()`</span><span class="sxs-lookup"><span data-stu-id="83dad-116">In the previous example, if you declare an instance by using `Dim testClass as testClass = Nothing`, the compiler treats a call to `testClass.sayHello()` as an access of the method through the class name, and no warning occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83dad-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83dad-117">See also</span></span>

- [<span data-ttu-id="83dad-118">Shared</span><span class="sxs-lookup"><span data-stu-id="83dad-118">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="83dad-119">Bereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="83dad-119">Scope in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
