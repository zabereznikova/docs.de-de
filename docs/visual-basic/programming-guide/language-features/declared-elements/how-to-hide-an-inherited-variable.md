---
title: 'Gewusst wie: Ausblenden einer geerbten Variablen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
- variables [Visual Basic], hiding inherited
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
ms.openlocfilehash: c59fdd8c6c6d2444b8d687c78c61f4e0d4bf9a52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649138"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a><span data-ttu-id="90a87-102">Gewusst wie: Ausblenden einer geerbten Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90a87-102">How to: Hide an Inherited Variable (Visual Basic)</span></span>
<span data-ttu-id="90a87-103">Eine abgeleitete Klasse erbt alle Definitionen ihrer Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="90a87-103">A derived class inherits all the definitions of its base class.</span></span> <span data-ttu-id="90a87-104">Wenn Sie eine Variable mit dem gleichen Namen wie ein Element der Basisklasse definieren möchten, können Sie ausblenden, oder *Schatten*, diese Basisklasse-Element, wenn Sie die Variable in der abgeleiteten Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="90a87-104">If you want to define a variable using the same name as an element of the base class, you can hide, or *shadow*, that base class element when you define your variable in the derived class.</span></span> <span data-ttu-id="90a87-105">Wenn Sie so vorgehen, greift Code in der abgeleiteten Klasse die Variable auf, es sei denn, sie explizit das Shadowing umgeht.</span><span class="sxs-lookup"><span data-stu-id="90a87-105">If you do this, code in the derived class accesses your variable unless it explicitly bypasses the shadowing mechanism.</span></span>  
  
 <span data-ttu-id="90a87-106">Ein weiterer Grund, dass Sie eine geerbte Variablen ausblenden möchten, können ist zum Schutz vor Revision Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="90a87-106">Another reason you might want to hide an inherited variable is to protect against base class revision.</span></span> <span data-ttu-id="90a87-107">Die Basisklasse kann eine Änderung unterzogen werden, die das Element ändert, das geerbt wird.</span><span class="sxs-lookup"><span data-stu-id="90a87-107">The base class might undergo a change that alters the element you are inheriting.</span></span> <span data-ttu-id="90a87-108">In diesem Fall die `Shadows` Modifizierer erzwingt, dass Verweise in die abgeleitete Klasse Ihre Variablen zu, anstatt auf das Element der Basisklasse aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="90a87-108">If this happens, the `Shadows` modifier forces references from the derived class to be resolved to your variable, instead of to the base class element.</span></span>  
  
### <a name="to-hide-an-inherited-variable"></a><span data-ttu-id="90a87-109">Ausblenden eine geerbte Variablen</span><span class="sxs-lookup"><span data-stu-id="90a87-109">To hide an inherited variable</span></span>  
  
1.  <span data-ttu-id="90a87-110">Achten Sie darauf, dass die Variable, die Sie ausblenden möchten, auf Klassenebene (außerhalb einer Prozedur) deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="90a87-110">Be sure the variable you want to hide is declared at class level (outside any procedure).</span></span> <span data-ttu-id="90a87-111">Andernfalls müssen Sie nicht ihn auszublenden.</span><span class="sxs-lookup"><span data-stu-id="90a87-111">Otherwise you do not need to hide it.</span></span>  
  
2.  <span data-ttu-id="90a87-112">Schreiben Sie in der abgeleiteten Klasse eine [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) Deklarieren der Variablen.</span><span class="sxs-lookup"><span data-stu-id="90a87-112">Inside your derived class, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring your variable.</span></span> <span data-ttu-id="90a87-113">Verwenden Sie den gleichen Namen wie die geerbten Variablen.</span><span class="sxs-lookup"><span data-stu-id="90a87-113">Use the same name as that of the inherited variable.</span></span>  
  
3.  <span data-ttu-id="90a87-114">Enthalten die [Schatten](../../../../visual-basic/language-reference/modifiers/shadows.md) Schlüsselwort in der Deklaration.</span><span class="sxs-lookup"><span data-stu-id="90a87-114">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>  
  
     <span data-ttu-id="90a87-115">Wenn Code in der abgeleiteten Klasse den Variablennamen verwiesen wird, löst der Compiler den Verweis auf die Variable an.</span><span class="sxs-lookup"><span data-stu-id="90a87-115">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>  
  
     <span data-ttu-id="90a87-116">Das folgende Beispiel veranschaulicht das shadowing von einer geerbten Variablen.</span><span class="sxs-lookup"><span data-stu-id="90a87-116">The following example illustrates shadowing of an inherited variable.</span></span>  
  
    ```  
    Public Class shadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class shadowDerivedClass  
        Inherits shadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub showStrings()  
            Dim s As String = "Unqualified shadowString: " & shadowString &  
                vbCrLf & "MyBase.shadowString: " & MyBase.shadowString  
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     <span data-ttu-id="90a87-117">Das vorhergehende Beispiel deklariert Variablen `shadowString` in der Basisklasse und Shadowing in der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="90a87-117">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="90a87-118">Die Prozedur `showStrings` zeigt Sie in der abgeleiteten Klasse die shadowing-Version der Zeichenfolge bei den Namen `shadowString` sind nicht gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="90a87-118">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="90a87-119">Es zeigt dann die Version bei `shadowString` ist qualifiziert, mit der `MyBase` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="90a87-119">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="90a87-120">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="90a87-120">Robust Programming</span></span>  
 <span data-ttu-id="90a87-121">Shadowing führt zu mehr als eine Version einer Variablen mit dem gleichen Namen.</span><span class="sxs-lookup"><span data-stu-id="90a87-121">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="90a87-122">Die Version, der Compiler den Verweis löst, hängt eine codeanweisung dem Variablennamen verweist, von Faktoren wie z. B. den Speicherort der codeanweisung und das Vorhandensein einer qualifizierenden Zeichenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="90a87-122">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="90a87-123">Dies kann das Risiko von Verweisen auf eine unbeabsichtigte Version einer Shadowing Variablen verbessern.</span><span class="sxs-lookup"><span data-stu-id="90a87-123">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="90a87-124">Sie können dieses Risiko verringern, indem Sie alle Verweise auf eine solche Variable vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="90a87-124">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90a87-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90a87-125">See Also</span></span>  
 [<span data-ttu-id="90a87-126">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="90a87-126">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="90a87-127">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="90a87-127">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [<span data-ttu-id="90a87-128">Unterschiede zwischen Shadowing und Überschreiben</span><span class="sxs-lookup"><span data-stu-id="90a87-128">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [<span data-ttu-id="90a87-129">Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable</span><span class="sxs-lookup"><span data-stu-id="90a87-129">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [<span data-ttu-id="90a87-130">Gewusst wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird</span><span class="sxs-lookup"><span data-stu-id="90a87-130">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [<span data-ttu-id="90a87-131">Overrides</span><span class="sxs-lookup"><span data-stu-id="90a87-131">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="90a87-132">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="90a87-132">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="90a87-133">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="90a87-133">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
