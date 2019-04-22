---
title: 'Vorgehensweise: Zugreifen auf eine Variable ausgeblendet, die durch eine abgeleitete Klasse (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: a97a51d4570d87eaa873fb3152ad810f528dff46
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832176"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a><span data-ttu-id="f0bb8-102">Vorgehensweise: Zugreifen auf eine Variable ausgeblendet, die durch eine abgeleitete Klasse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0bb8-102">How to: Access a Variable Hidden by a Derived Class (Visual Basic)</span></span>
<span data-ttu-id="f0bb8-103">Wenn Code in einer abgeleiteten Klasse eine Variable zugreift, löst der Compiler normalerweise dem Verweis auf den nächstgelegenen zugegriffen werden kann Version, d. h. die zugegriffen werden kann die wenigsten Ableitungsschritte von der Klasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f0bb8-103">When code in a derived class accesses a variable, the compiler normally resolves the reference to the closest accessible version, that is, the accessible version the fewest derivational steps backward from the accessing class.</span></span> <span data-ttu-id="f0bb8-104">Wenn die Variable in der abgeleiteten Klasse definiert ist, greift der Code normalerweise dieser Definition.</span><span class="sxs-lookup"><span data-stu-id="f0bb8-104">If the variable is defined in the derived class, the code normally accesses that definition.</span></span>  
  
 <span data-ttu-id="f0bb8-105">Wenn die Variable der abgeleiteten Klasse eine Variable in der Basisklasse überschattet, blendet sie die Basisklassenversion.</span><span class="sxs-lookup"><span data-stu-id="f0bb8-105">If the derived class variable shadows a variable in the base class, it hides the base class version.</span></span> <span data-ttu-id="f0bb8-106">Sie können jedoch die Basisklassenvariable zugreifen, durch die Qualifizierung mit dem `MyBase` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="f0bb8-106">However, you can access the base class variable by qualifying it with the `MyBase` keyword.</span></span>  
  
### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a><span data-ttu-id="f0bb8-107">Auf eine Basisklasse-Variable, die von einer abgeleiteten Klasse ausgeblendet wird.</span><span class="sxs-lookup"><span data-stu-id="f0bb8-107">To access a base class variable hidden by a derived class</span></span>  
  
-   <span data-ttu-id="f0bb8-108">In einem Ausdruck oder eine zuweisungsanweisung, vorausgehen den Variablennamen den `MyBase` -Schlüsselwort und einem Punkt (`.`).</span><span class="sxs-lookup"><span data-stu-id="f0bb8-108">In an expression or assignment statement, precede the variable name with the `MyBase` keyword and a period (`.`).</span></span>  
  
     <span data-ttu-id="f0bb8-109">Der Compiler löst den Verweis auf die Basisklassenversion der Variablen.</span><span class="sxs-lookup"><span data-stu-id="f0bb8-109">The compiler resolves the reference to the base class version of the variable.</span></span>  
  
     <span data-ttu-id="f0bb8-110">Das folgende Beispiel veranschaulicht die shadowings durch Vererbung.</span><span class="sxs-lookup"><span data-stu-id="f0bb8-110">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="f0bb8-111">Es macht zwei Verweise enthalten, von denen eine, die die shadowing Variable zugreift und eine, die das shadowing umgeht.</span><span class="sxs-lookup"><span data-stu-id="f0bb8-111">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>  
  
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
  
     <span data-ttu-id="f0bb8-112">Das vorhergehende Beispiel deklariert die Variable `shadowString` in der Basisklasse und in der abgeleiteten Klasse ein Shadowing.</span><span class="sxs-lookup"><span data-stu-id="f0bb8-112">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="f0bb8-113">Die Prozedur `showStrings` zeigt Sie in der abgeleiteten Klasse die shadowing-Version der Zeichenfolge bei den Namen `shadowString` sind nicht gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="f0bb8-113">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="f0bb8-114">Es zeigt dann die Variable an bei `shadowString` ist qualifiziert, mit der `MyBase` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="f0bb8-114">It then displays the shadowed version when `shadowString` is qualified with the `MyBase`  keyword.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f0bb8-115">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="f0bb8-115">Robust Programming</span></span>  
 <span data-ttu-id="f0bb8-116">Um das Risiko von Verweisen auf eine unerwünschte Version eine solche Variable zu reduzieren, können Sie alle Verweise auf eine solche Variable vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="f0bb8-116">To lower the risk of referring to an unintended version of a shadowed variable, you can fully qualify all references to a shadowed variable.</span></span> <span data-ttu-id="f0bb8-117">Shadowing führt mehr als eine Version einer Variablen mit dem gleichen Namen.</span><span class="sxs-lookup"><span data-stu-id="f0bb8-117">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="f0bb8-118">Die Version, die auf die der Compiler den Verweis löst hängt eine codeanweisung dem Variablennamen verweist, von Faktoren ab, wie z. B. den Speicherort der codeanweisung und das Vorhandensein einer qualifizierenden Zeichenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="f0bb8-118">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="f0bb8-119">Dies kann das Risiko von Verweisen auf die falsche Version der Variablen verbessern.</span><span class="sxs-lookup"><span data-stu-id="f0bb8-119">This can increase the risk of referring to the wrong version of the variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0bb8-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0bb8-120">See also</span></span>

- [<span data-ttu-id="f0bb8-121">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="f0bb8-121">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="f0bb8-122">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0bb8-122">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="f0bb8-123">Unterschiede zwischen Shadowing und Überschreiben</span><span class="sxs-lookup"><span data-stu-id="f0bb8-123">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="f0bb8-124">Vorgehensweise: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable</span><span class="sxs-lookup"><span data-stu-id="f0bb8-124">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="f0bb8-125">Vorgehensweise: Ausblenden einer geerbten Variablen</span><span class="sxs-lookup"><span data-stu-id="f0bb8-125">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="f0bb8-126">Shadows</span><span class="sxs-lookup"><span data-stu-id="f0bb8-126">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="f0bb8-127">Overrides</span><span class="sxs-lookup"><span data-stu-id="f0bb8-127">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="f0bb8-128">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="f0bb8-128">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="f0bb8-129">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="f0bb8-129">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
