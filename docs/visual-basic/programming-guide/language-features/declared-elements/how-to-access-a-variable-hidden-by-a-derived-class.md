---
title: 'Gewusst wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: 276cb1411c66e1f7205507a1b1053cc8642c7cb0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345408"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a><span data-ttu-id="d271c-102">Gewusst wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d271c-102">How to: Access a Variable Hidden by a Derived Class (Visual Basic)</span></span>

<span data-ttu-id="d271c-103">Wenn Code in einer abgeleiteten Klasse auf eine Variable zugreift, löst der Compiler normalerweise den Verweis auf die nächstgelegene Barrierefreie Version, d. h</span><span class="sxs-lookup"><span data-stu-id="d271c-103">When code in a derived class accesses a variable, the compiler normally resolves the reference to the closest accessible version, that is, the accessible version the fewest derivational steps backward from the accessing class.</span></span> <span data-ttu-id="d271c-104">Wenn die Variable in der abgeleiteten Klasse definiert ist, greift der Code normalerweise auf diese Definition zu.</span><span class="sxs-lookup"><span data-stu-id="d271c-104">If the variable is defined in the derived class, the code normally accesses that definition.</span></span>

<span data-ttu-id="d271c-105">Wenn die abgeleitete Klassen Variable eine Variable in der Basisklasse Shadowing, verbirgt Sie die Basisklassen Version.</span><span class="sxs-lookup"><span data-stu-id="d271c-105">If the derived class variable shadows a variable in the base class, it hides the base class version.</span></span> <span data-ttu-id="d271c-106">Allerdings können Sie auf die Basisklassen Variable zugreifen, indem Sie Sie mit dem Schlüsselwort "`MyBase`" qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="d271c-106">However, you can access the base class variable by qualifying it with the `MyBase` keyword.</span></span>

### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a><span data-ttu-id="d271c-107">So greifen Sie auf eine von einer abgeleiteten Klasse verborgene Basisklassen Variable zu</span><span class="sxs-lookup"><span data-stu-id="d271c-107">To access a base class variable hidden by a derived class</span></span>

- <span data-ttu-id="d271c-108">Stellen Sie in einer Ausdrucks-oder Zuweisungsanweisung vor dem Variablennamen das `MyBase`-Schlüsselwort und einen Period (`.`) vor.</span><span class="sxs-lookup"><span data-stu-id="d271c-108">In an expression or assignment statement, precede the variable name with the `MyBase` keyword and a period (`.`).</span></span>

    <span data-ttu-id="d271c-109">Der Compiler löst den Verweis auf die Basisklassen Version der Variablen auf.</span><span class="sxs-lookup"><span data-stu-id="d271c-109">The compiler resolves the reference to the base class version of the variable.</span></span>

    <span data-ttu-id="d271c-110">Das folgende Beispiel veranschaulicht shadothrough durch Vererbung.</span><span class="sxs-lookup"><span data-stu-id="d271c-110">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="d271c-111">Es werden zwei Verweise erstellt, eine, die auf die Shadowingvariable zugreift, und eine, die den shadodown umgeht.</span><span class="sxs-lookup"><span data-stu-id="d271c-111">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>

    ```vb
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

    <span data-ttu-id="d271c-112">Im vorangehenden Beispiel wird die Variable `shadowString` in der Basisklasse deklariert und in der abgeleiteten Klasse als Schatten angegeben.</span><span class="sxs-lookup"><span data-stu-id="d271c-112">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="d271c-113">Die Prozedur `showStrings` in der abgeleiteten Klasse zeigt die Shadowingversion der Zeichenfolge an, wenn der Name `shadowString` nicht qualifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="d271c-113">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="d271c-114">Daraufhin wird die Schatten Version angezeigt, wenn `shadowString` mit dem Schlüsselwort `MyBase` qualifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="d271c-114">It then displays the shadowed version when `shadowString` is qualified with the `MyBase`  keyword.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="d271c-115">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="d271c-115">Robust Programming</span></span>

<span data-ttu-id="d271c-116">Sie können alle Verweise auf eine Schatten Variable vollständig qualifizieren, um das Risiko zu verringern, dass Sie auf eine unbeabsichtigte Version einer schattiert-Variablen verweisen.</span><span class="sxs-lookup"><span data-stu-id="d271c-116">To lower the risk of referring to an unintended version of a shadowed variable, you can fully qualify all references to a shadowed variable.</span></span> <span data-ttu-id="d271c-117">Mit shadowingwird mehr als eine Version einer Variablen mit demselben Namen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="d271c-117">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="d271c-118">Wenn sich eine Code Anweisung auf den Variablennamen bezieht, hängt die Version, auf die der Compiler den Verweis auflöst, von Faktoren wie dem Speicherort der Code Anweisung und dem vorhanden sein einer qualifizierenden Zeichenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="d271c-118">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="d271c-119">Dadurch kann das Risiko erhöht werden, dass auf die falsche Version der Variablen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="d271c-119">This can increase the risk of referring to the wrong version of the variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="d271c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d271c-120">See also</span></span>

- [<span data-ttu-id="d271c-121">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="d271c-121">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="d271c-122">Shadodown in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d271c-122">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="d271c-123">Unterschiede zwischen Shadowing und Überschreiben</span><span class="sxs-lookup"><span data-stu-id="d271c-123">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="d271c-124">Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable</span><span class="sxs-lookup"><span data-stu-id="d271c-124">How to: Hide a Variable with the Same Name as Your Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [<span data-ttu-id="d271c-125">Gewusst wie: Ausblenden einer geerbten Variablen</span><span class="sxs-lookup"><span data-stu-id="d271c-125">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="d271c-126">Shadows</span><span class="sxs-lookup"><span data-stu-id="d271c-126">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="d271c-127">Overrides</span><span class="sxs-lookup"><span data-stu-id="d271c-127">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="d271c-128">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="d271c-128">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="d271c-129">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="d271c-129">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
