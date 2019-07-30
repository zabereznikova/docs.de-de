---
title: 'Vorgehensweise: Eine Variable mit dem gleichen Namen wie die Variable ausblenden (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- declarations [Visual Basic], elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
ms.openlocfilehash: 487e0a15ba6b52f92ab39fe0bae4ab15fa92707f
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629990"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="c2307-102">Vorgehensweise: Eine Variable mit dem gleichen Namen wie die Variable ausblenden (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c2307-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>

<span data-ttu-id="c2307-103">Sie können eine Variable ausblenden, indem Sie Sie *shadoauen* , d. h., indem Sie Sie mit einer gleichnamigen Variablen neu definieren.</span><span class="sxs-lookup"><span data-stu-id="c2307-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="c2307-104">Sie können die Variable, die Sie ausblenden möchten, auf zwei Arten schattieren:</span><span class="sxs-lookup"><span data-stu-id="c2307-104">You can shadow the variable you want to hide in two ways:</span></span>

- <span data-ttu-id="c2307-105">**Shadodown durch den Gültigkeitsbereich.**</span><span class="sxs-lookup"><span data-stu-id="c2307-105">**Shadowing Through Scope.**</span></span> <span data-ttu-id="c2307-106">Sie können den Bereich durch den Gültigkeitsbereich schattieren, indem Sie ihn in einem Teilbereich des Bereichs mit der Variablen, die Sie ausblenden möchten, erneut deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c2307-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>

- <span data-ttu-id="c2307-107">**Über schattung durch Vererbung.**</span><span class="sxs-lookup"><span data-stu-id="c2307-107">**Shadowing Through Inheritance.**</span></span> <span data-ttu-id="c2307-108">Wenn die Variable, die Sie ausblenden möchten, auf Klassenebene definiert ist, können Sie Sie durch die Vererbung schattieren, indem Sie Sie mit dem [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) -Schlüsselwort in einer abgeleiteten Klasse erneut deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c2307-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>

## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="c2307-109">Zwei Möglichkeiten zum Ausblenden einer Variablen</span><span class="sxs-lookup"><span data-stu-id="c2307-109">Two Ways to Hide a Variable</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="c2307-110">So blenden Sie eine Variable durch shadoauen durch</span><span class="sxs-lookup"><span data-stu-id="c2307-110">To hide a variable by shadowing it through scope</span></span>

1. <span data-ttu-id="c2307-111">Bestimmen Sie die Region, in der die Variable definiert ist, die Sie ausblenden möchten, und bestimmen Sie, in welcher Region Sie mit der Variablen neu definiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c2307-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>

    |<span data-ttu-id="c2307-112">Bereich der Variablen</span><span class="sxs-lookup"><span data-stu-id="c2307-112">Variable's region</span></span>|<span data-ttu-id="c2307-113">Zulässiger Unterbereich für Neudefinition</span><span class="sxs-lookup"><span data-stu-id="c2307-113">Allowable subregion for redefining it</span></span>|
    |-----------------------|-------------------------------------------|
    |<span data-ttu-id="c2307-114">Modul</span><span class="sxs-lookup"><span data-stu-id="c2307-114">Module</span></span>|<span data-ttu-id="c2307-115">Eine Klasse innerhalb des Moduls</span><span class="sxs-lookup"><span data-stu-id="c2307-115">A class within the module</span></span>|
    |<span data-ttu-id="c2307-116">Klasse</span><span class="sxs-lookup"><span data-stu-id="c2307-116">Class</span></span>|<span data-ttu-id="c2307-117">Eine Unterklasse innerhalb der Klasse.</span><span class="sxs-lookup"><span data-stu-id="c2307-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="c2307-118">Eine Prozedur innerhalb der Klasse</span><span class="sxs-lookup"><span data-stu-id="c2307-118">A procedure within the class</span></span>|

    <span data-ttu-id="c2307-119">Sie können eine Prozedur Variable in einem-Block innerhalb dieser Prozedur nicht neu definieren, z `If`. b. in einer... `End If` Konstruktion`For` oder Schleife.</span><span class="sxs-lookup"><span data-stu-id="c2307-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>

2. <span data-ttu-id="c2307-120">Erstellen Sie die unterregion, wenn Sie nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c2307-120">Create the subregion if it does not already exist.</span></span>

3. <span data-ttu-id="c2307-121">Schreiben Sie innerhalb des unter Bereichs eine [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) , die die Shadowingvariable deklariert.</span><span class="sxs-lookup"><span data-stu-id="c2307-121">Within the subregion, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>

    <span data-ttu-id="c2307-122">Wenn sich Code in der Unterregion auf den Variablennamen bezieht, löst der Compiler den Verweis auf die Shadowingvariable auf.</span><span class="sxs-lookup"><span data-stu-id="c2307-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>

    <span data-ttu-id="c2307-123">Das folgende Beispiel veranschaulicht shadothrough durch den Gültigkeitsbereich sowie einen Verweis, der den shadodown umgeht.</span><span class="sxs-lookup"><span data-stu-id="c2307-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>

    ```vb
    Module shadowByScope
        ' The following statement declares num as a module-level variable.
        Public num As Integer
        Sub show()
            ' The following statement declares num as a local variable.
            Dim num As Integer
            ' The following statement sets the value of the local variable.
            num = 2
            ' The following statement displays the module-level variable.
            MsgBox(CStr(shadowByScope.num))
        End Sub
        Sub useModuleLevelNum()
            ' The following statement sets the value of the module-level variable.
            num = 1
            show()
        End Sub
    End Module
    ```

    <span data-ttu-id="c2307-124">Im vorangehenden Beispiel wird die `num` -Variable auf Modulebene und auf Prozedur Ebene (in der `show`-Prozedur) deklariert.</span><span class="sxs-lookup"><span data-stu-id="c2307-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="c2307-125">Die lokale Variable `num` gibt eine Schatten der Variablen `num` auf Modul `show`Ebene in aus, sodass die lokale Variable auf 2 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c2307-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="c2307-126">Es ist jedoch keine lokale Variable zum Schatten `num` in der `useModuleLevelNum` Prozedur vorhanden.</span><span class="sxs-lookup"><span data-stu-id="c2307-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="c2307-127">Daher wird `useModuleLevelNum` der Wert der Variablen auf Modulebene auf 1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c2307-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>

    <span data-ttu-id="c2307-128">Der `MsgBox` -Befehl `show` in umgeht den shadoingmechanismus, indem `num` er mit dem Modulnamen qualifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="c2307-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="c2307-129">Daher wird anstelle der lokalen Variablen die Variable auf Modulebene angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c2307-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="c2307-130">So blenden Sie eine Variable aus, indem Sie Sie durch Vererbung shadoauen</span><span class="sxs-lookup"><span data-stu-id="c2307-130">To hide a variable by shadowing it through inheritance</span></span>

1. <span data-ttu-id="c2307-131">Stellen Sie sicher, dass die Variable, die Sie ausblenden möchten, in einer Klasse und auf Klassenebene (außerhalb der Prozeduren) deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="c2307-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="c2307-132">Andernfalls können Sie Sie nicht durch Vererbung schattieren.</span><span class="sxs-lookup"><span data-stu-id="c2307-132">Otherwise you cannot shadow it through inheritance.</span></span>

2. <span data-ttu-id="c2307-133">Definieren Sie eine Klasse, die von der-Klasse der Variablen abgeleitet ist, wenn Sie noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c2307-133">Define a class derived from the variable's class if one does not already exist.</span></span>

3. <span data-ttu-id="c2307-134">Schreiben Sie in der abgeleiteten Klasse `Dim` eine-Anweisung, die die Variable deklariert.</span><span class="sxs-lookup"><span data-stu-id="c2307-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="c2307-135">Schließt das [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) -Schlüsselwort in die Deklaration ein.</span><span class="sxs-lookup"><span data-stu-id="c2307-135">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>

    <span data-ttu-id="c2307-136">Wenn sich der Code in der abgeleiteten Klasse auf den Variablennamen bezieht, löst der Compiler den Verweis auf die Variable auf.</span><span class="sxs-lookup"><span data-stu-id="c2307-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>

    <span data-ttu-id="c2307-137">Das folgende Beispiel veranschaulicht shadothrough durch Vererbung.</span><span class="sxs-lookup"><span data-stu-id="c2307-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="c2307-138">Es werden zwei Verweise erstellt, eine, die auf die Shadowingvariable zugreift, und eine, die den shadodown umgeht.</span><span class="sxs-lookup"><span data-stu-id="c2307-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>

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

    <span data-ttu-id="c2307-139">Im vorangehenden Beispiel wird die `shadowString` -Variable in der-Basisklasse deklariert und in der abgeleiteten Klasse als Schatten angegeben.</span><span class="sxs-lookup"><span data-stu-id="c2307-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="c2307-140">Die Prozedur `showStrings` in der abgeleiteten Klasse zeigt die Shadowingversion der Zeichenfolge an, `shadowString` wenn der Name nicht qualifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="c2307-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="c2307-141">Anschließend wird die Schatten Version angezeigt, `shadowString` wenn mit dem `MyBase` -Schlüsselwort qualifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="c2307-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="c2307-142">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="c2307-142">Robust Programming</span></span>

<span data-ttu-id="c2307-143">Mit shadowingwird mehr als eine Version einer Variablen mit demselben Namen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c2307-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="c2307-144">Wenn sich eine Code Anweisung auf den Variablennamen bezieht, hängt die Version, auf die der Compiler den Verweis auflöst, von Faktoren wie dem Speicherort der Code Anweisung und dem vorhanden sein einer qualifizierenden Zeichenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="c2307-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="c2307-145">Dadurch kann das Risiko erhöht werden, dass auf eine unbeabsichtigte Version einer schattiert-Variablen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c2307-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="c2307-146">Sie können dieses Risiko verringern, indem Sie alle Verweise auf eine Schatten Variable vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="c2307-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2307-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2307-147">See also</span></span>

- [<span data-ttu-id="c2307-148">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="c2307-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="c2307-149">Shadodown in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c2307-149">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="c2307-150">Unterschiede zwischen Shadowing und Überschreiben</span><span class="sxs-lookup"><span data-stu-id="c2307-150">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="c2307-151">Vorgehensweise: Vererbte Variable ausblenden</span><span class="sxs-lookup"><span data-stu-id="c2307-151">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="c2307-152">Vorgehensweise: Zugreifen auf eine Variable, die durch eine abgeleitete Klasse ausgeblendet</span><span class="sxs-lookup"><span data-stu-id="c2307-152">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="c2307-153">Overrides</span><span class="sxs-lookup"><span data-stu-id="c2307-153">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="c2307-154">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="c2307-154">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="c2307-155">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="c2307-155">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
