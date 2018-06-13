---
title: Zugriff des freigegebenen Members, konstanten Members, Enumerationsmembers oder geschachtelten Typs über eine Instanz; der qualifizierende Ausdruck wird nicht ausgewertet
ms.date: 07/20/2015
f1_keywords:
- vbc42025
- BC42025
helpviewer_keywords:
- BC42025
ms.assetid: db3337e5-c349-42bf-86df-d9c1e00952a5
ms.openlocfilehash: 035882b60c90d9a6141ad0d34b4c40682e0c32a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588982"
---
# <a name="access-of-shared-member-through-an-instance-qualifying-expression-will-not-be-evaluated"></a><span data-ttu-id="318dd-102">Zugriff des freigegebenen Members, konstanten Members, Enumerationsmembers oder geschachtelten Typs über eine Instanz; der qualifizierende Ausdruck wird nicht ausgewertet</span><span class="sxs-lookup"><span data-stu-id="318dd-102">Access of shared member through an instance; qualifying expression will not be evaluated</span></span>
<span data-ttu-id="318dd-103">Eine Instanzvariable einer Klasse oder Struktur wird verwendet, für den Zugriff auf eine `Shared` Variable, Eigenschaft, Prozedur oder Ereignis in dieser Klasse oder Struktur definiert.</span><span class="sxs-lookup"><span data-stu-id="318dd-103">An instance variable of a class or structure is used to access a `Shared` variable, property, procedure, or event defined in that class or structure.</span></span> <span data-ttu-id="318dd-104">Diese Warnung kann auch auftreten, wenn eine Instanzvariablen verwendet wird, um eine implizit freigegebenen Member einer Klasse oder Struktur, z. B. eine Konstante oder -Enumeration, oder eine geschachtelte Klasse oder Struktur zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="318dd-104">This warning can also occur if an instance variable is used to access an implicitly shared member of a class or structure, such as a constant or enumeration, or a nested class or structure.</span></span>  
  
 <span data-ttu-id="318dd-105">Der Zweck der Freigabe ist nur eine einzige Kopie dieses Element zu erstellen, und diese einzelne Kopie für jede Instanz der Klasse oder Struktur, die in der sie deklariert ist verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="318dd-105">The purpose of sharing a member is to create only a single copy of that member and make that single copy available to every instance of the class or structure in which it is declared.</span></span> <span data-ttu-id="318dd-106">Sie ist konsistent mit diesem Zweck den Zugriff auf eine `Shared` Member über den Namen der Klasse oder Struktur, anstatt über eine Variable, eine einzelne Instanz dieser Klasse oder Struktur enthält.</span><span class="sxs-lookup"><span data-stu-id="318dd-106">It is consistent with this purpose to access a `Shared` member through the name of its class or structure, rather than through a variable that holds an individual instance of that class or structure.</span></span>  
  
 <span data-ttu-id="318dd-107">Zugreifen auf eine `Shared` Member über eine Instanzvariable kann Lesbarkeit Ihres Codes schwieriger zu verstehen, indem die Tatsache, dass das Element verdeckt `Shared`.</span><span class="sxs-lookup"><span data-stu-id="318dd-107">Accessing a `Shared` member through an instance variable can make your code more difficult to understand by obscuring the fact that the member is `Shared`.</span></span> <span data-ttu-id="318dd-108">Darüber hinaus solcher Zugriff ist Teil eines Ausdrucks, der weitere Aktionen ausführt, z. B. eine `Function` Prozedur, die eine Instanz des freigegebenen Members zurückgibt, Visual Basic umgeht den Ausdruck und alle weiteren erforderlichen Aktionen es andernfalls führen würde.</span><span class="sxs-lookup"><span data-stu-id="318dd-108">Furthermore, if such access is part of an expression that performs other actions, such as a `Function` procedure that returns an instance of the shared member, Visual Basic bypasses the expression and any other actions it would otherwise perform.</span></span>  
  
 <span data-ttu-id="318dd-109">Weitere Informationen und ein Beispiel finden Sie unter [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="318dd-109">For more information and an example, see [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
 <span data-ttu-id="318dd-110">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="318dd-110">By default, this message is a warning.</span></span> <span data-ttu-id="318dd-111">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="318dd-111">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="318dd-112">**Fehler-ID:** BC42025</span><span class="sxs-lookup"><span data-stu-id="318dd-112">**Error ID:** BC42025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="318dd-113">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="318dd-113">To correct this error</span></span>  
  
-   <span data-ttu-id="318dd-114">Verwenden Sie den Namen der Klasse oder Struktur, definiert der `Shared` Member darauf zugreifen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="318dd-114">Use the name of the class or structure that defines the `Shared` member to access it, as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="318dd-115">Warnung für die Auswirkungen des Bereichs vorliegen, wenn zwei Programmierelemente denselben Namen haben.</span><span class="sxs-lookup"><span data-stu-id="318dd-115">Be alert for the effects of scope when two programming elements have the same name.</span></span> <span data-ttu-id="318dd-116">Im vorherigen Beispiel, wenn Sie eine Instanz mit deklarieren `Dim testClass as testClass = Nothing`, behandelt der Compiler einen Aufruf von `testClass.sayHello()` wie ein Zugriff auf die Methode über den Klassennamen und keine Warnung auftritt.</span><span class="sxs-lookup"><span data-stu-id="318dd-116">In the previous example, if you declare an instance by using `Dim testClass as testClass = Nothing`, the compiler treats a call to `testClass.sayHello()` as an access of the method through the class name, and no warning occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="318dd-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="318dd-117">See Also</span></span>  
 [<span data-ttu-id="318dd-118">Shared</span><span class="sxs-lookup"><span data-stu-id="318dd-118">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="318dd-119">Gültigkeitsbereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="318dd-119">Scope in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
