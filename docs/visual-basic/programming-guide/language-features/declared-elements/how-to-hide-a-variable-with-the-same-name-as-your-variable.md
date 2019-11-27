---
title: 'Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable'
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
ms.openlocfilehash: 0915adbbabb778b1bdd3b6b30e56725a7e74867c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345367"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a><span data-ttu-id="a48db-102">Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a48db-102">How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)</span></span>

<span data-ttu-id="a48db-103">Sie können eine Variable ausblenden, indem Sie Sie *shadoauen* , d. h., indem Sie Sie mit einer gleichnamigen Variablen neu definieren.</span><span class="sxs-lookup"><span data-stu-id="a48db-103">You can hide a variable by *shadowing* it, that is, by redefining it with a variable of the same name.</span></span> <span data-ttu-id="a48db-104">Sie können die Variable, die Sie ausblenden möchten, auf zwei Arten schattieren:</span><span class="sxs-lookup"><span data-stu-id="a48db-104">You can shadow the variable you want to hide in two ways:</span></span>

- <span data-ttu-id="a48db-105">**Shadodown durch den Gültigkeitsbereich.**</span><span class="sxs-lookup"><span data-stu-id="a48db-105">**Shadowing Through Scope.**</span></span> <span data-ttu-id="a48db-106">Sie können den Bereich durch den Gültigkeitsbereich schattieren, indem Sie ihn in einem Teilbereich des Bereichs mit der Variablen, die Sie ausblenden möchten, erneut deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a48db-106">You can shadow it through scope by redeclaring it inside a subregion of the region containing the variable you want to hide.</span></span>

- <span data-ttu-id="a48db-107">**Über schattung durch Vererbung.**</span><span class="sxs-lookup"><span data-stu-id="a48db-107">**Shadowing Through Inheritance.**</span></span> <span data-ttu-id="a48db-108">Wenn die Variable, die Sie ausblenden möchten, auf Klassenebene definiert ist, können Sie Sie durch die Vererbung schattieren, indem Sie Sie mit dem [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) -Schlüsselwort in einer abgeleiteten Klasse erneut deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a48db-108">If the variable you want to hide is defined at class level, you can shadow it through inheritance by redeclaring it with the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in a derived class.</span></span>

## <a name="two-ways-to-hide-a-variable"></a><span data-ttu-id="a48db-109">Zwei Möglichkeiten zum Ausblenden einer Variablen</span><span class="sxs-lookup"><span data-stu-id="a48db-109">Two Ways to Hide a Variable</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a><span data-ttu-id="a48db-110">So blenden Sie eine Variable durch shadoauen durch</span><span class="sxs-lookup"><span data-stu-id="a48db-110">To hide a variable by shadowing it through scope</span></span>

1. <span data-ttu-id="a48db-111">Bestimmen Sie die Region, in der die Variable definiert ist, die Sie ausblenden möchten, und bestimmen Sie, in welcher Region Sie mit der Variablen neu definiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a48db-111">Determine the region defining the variable you want to hide, and determine a subregion in which to redefine it with your variable.</span></span>

    |<span data-ttu-id="a48db-112">Bereich der Variablen</span><span class="sxs-lookup"><span data-stu-id="a48db-112">Variable's region</span></span>|<span data-ttu-id="a48db-113">Zulässiger Unterbereich für Neudefinition</span><span class="sxs-lookup"><span data-stu-id="a48db-113">Allowable subregion for redefining it</span></span>|
    |-----------------------|-------------------------------------------|
    |<span data-ttu-id="a48db-114">Modul</span><span class="sxs-lookup"><span data-stu-id="a48db-114">Module</span></span>|<span data-ttu-id="a48db-115">Eine Klasse innerhalb des Moduls</span><span class="sxs-lookup"><span data-stu-id="a48db-115">A class within the module</span></span>|
    |<span data-ttu-id="a48db-116">Klasse</span><span class="sxs-lookup"><span data-stu-id="a48db-116">Class</span></span>|<span data-ttu-id="a48db-117">Eine Unterklasse innerhalb der Klasse.</span><span class="sxs-lookup"><span data-stu-id="a48db-117">A subclass within the class</span></span><br /><br /> <span data-ttu-id="a48db-118">Eine Prozedur innerhalb der Klasse</span><span class="sxs-lookup"><span data-stu-id="a48db-118">A procedure within the class</span></span>|

    <span data-ttu-id="a48db-119">Sie können eine Prozedur Variable in einem-Block innerhalb dieser Prozedur nicht neu definieren, z. b. in einer `If`...`End If` Konstruktion oder einer `For`-Schleife.</span><span class="sxs-lookup"><span data-stu-id="a48db-119">You cannot redefine a procedure variable in a block within that procedure, for example in an `If`...`End If` construction or a `For` loop.</span></span>

2. <span data-ttu-id="a48db-120">Erstellen Sie die unterregion, wenn Sie nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a48db-120">Create the subregion if it does not already exist.</span></span>

3. <span data-ttu-id="a48db-121">Schreiben Sie innerhalb des unter Bereichs eine [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) , die die Shadowingvariable deklariert.</span><span class="sxs-lookup"><span data-stu-id="a48db-121">Within the subregion, write a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) declaring the shadowing variable.</span></span>

    <span data-ttu-id="a48db-122">Wenn sich Code in der Unterregion auf den Variablennamen bezieht, löst der Compiler den Verweis auf die Shadowingvariable auf.</span><span class="sxs-lookup"><span data-stu-id="a48db-122">When code inside the subregion refers to the variable name, the compiler resolves the reference to the shadowing variable.</span></span>

    <span data-ttu-id="a48db-123">Das folgende Beispiel veranschaulicht shadothrough durch den Gültigkeitsbereich sowie einen Verweis, der den shadodown umgeht.</span><span class="sxs-lookup"><span data-stu-id="a48db-123">The following example illustrates shadowing through scope, as well as a reference that bypasses the shadowing.</span></span>

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

    <span data-ttu-id="a48db-124">Im vorangehenden Beispiel wird die-Variable `num` auf Modulebene und auf Prozedur Ebene (in der Prozedur `show`) deklariert.</span><span class="sxs-lookup"><span data-stu-id="a48db-124">The preceding example declares the variable `num` both at module level and at procedure level (in the procedure `show`).</span></span> <span data-ttu-id="a48db-125">Die lokale Variable `num` überschattet die `num` Variable auf Modulebene innerhalb `show`, sodass die lokale Variable auf 2 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a48db-125">The local variable `num` shadows the module-level variable `num` within `show`, so the local variable is set to 2.</span></span> <span data-ttu-id="a48db-126">Es ist jedoch keine lokale Variable zum Schatten `num` in der `useModuleLevelNum` Prozedur vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a48db-126">However, there is no local variable to shadow `num` in the `useModuleLevelNum` procedure.</span></span> <span data-ttu-id="a48db-127">Daher wird von `useModuleLevelNum` der Wert der Variablen auf Modulebene auf 1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a48db-127">Therefore, `useModuleLevelNum` sets the value of the module-level variable to 1.</span></span>

    <span data-ttu-id="a48db-128">Der `MsgBox`-Aufrufe in `show` umgeht den shadoingmechanismus, indem `num` mit dem Modulnamen qualifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="a48db-128">The `MsgBox` call inside `show` bypasses the shadowing mechanism by qualifying `num` with the module name.</span></span> <span data-ttu-id="a48db-129">Daher wird anstelle der lokalen Variablen die Variable auf Modulebene angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a48db-129">Therefore, it displays the module-level variable instead of the local variable.</span></span>

#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a><span data-ttu-id="a48db-130">So blenden Sie eine Variable aus, indem Sie Sie durch Vererbung shadoauen</span><span class="sxs-lookup"><span data-stu-id="a48db-130">To hide a variable by shadowing it through inheritance</span></span>

1. <span data-ttu-id="a48db-131">Stellen Sie sicher, dass die Variable, die Sie ausblenden möchten, in einer Klasse und auf Klassenebene (außerhalb der Prozeduren) deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="a48db-131">Be sure the variable you want to hide is declared in a class, and at class level (outside any procedure).</span></span> <span data-ttu-id="a48db-132">Andernfalls können Sie Sie nicht durch Vererbung schattieren.</span><span class="sxs-lookup"><span data-stu-id="a48db-132">Otherwise you cannot shadow it through inheritance.</span></span>

2. <span data-ttu-id="a48db-133">Definieren Sie eine Klasse, die von der-Klasse der Variablen abgeleitet ist, wenn Sie noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a48db-133">Define a class derived from the variable's class if one does not already exist.</span></span>

3. <span data-ttu-id="a48db-134">Schreiben Sie in der abgeleiteten Klasse eine `Dim`-Anweisung, die die Variable deklariert.</span><span class="sxs-lookup"><span data-stu-id="a48db-134">Inside the derived class, write a `Dim` statement declaring your variable.</span></span> <span data-ttu-id="a48db-135">Schließt das [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) -Schlüsselwort in die Deklaration ein.</span><span class="sxs-lookup"><span data-stu-id="a48db-135">Include the [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) keyword in the declaration.</span></span>

    <span data-ttu-id="a48db-136">Wenn sich der Code in der abgeleiteten Klasse auf den Variablennamen bezieht, löst der Compiler den Verweis auf die Variable auf.</span><span class="sxs-lookup"><span data-stu-id="a48db-136">When code in the derived class refers to the variable name, the compiler resolves the reference to your variable.</span></span>

    <span data-ttu-id="a48db-137">Das folgende Beispiel veranschaulicht shadothrough durch Vererbung.</span><span class="sxs-lookup"><span data-stu-id="a48db-137">The following example illustrates shadowing through inheritance.</span></span> <span data-ttu-id="a48db-138">Es werden zwei Verweise erstellt, eine, die auf die Shadowingvariable zugreift, und eine, die den shadodown umgeht.</span><span class="sxs-lookup"><span data-stu-id="a48db-138">It makes two references, one that accesses the shadowing variable and one that bypasses the shadowing.</span></span>

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

    <span data-ttu-id="a48db-139">Im vorangehenden Beispiel wird die Variable `shadowString` in der Basisklasse deklariert und in der abgeleiteten Klasse als Schatten angegeben.</span><span class="sxs-lookup"><span data-stu-id="a48db-139">The preceding example declares the variable `shadowString` in the base class and shadows it in the derived class.</span></span> <span data-ttu-id="a48db-140">Die Prozedur `showStrings` in der abgeleiteten Klasse zeigt die Shadowingversion der Zeichenfolge an, wenn der Name `shadowString` nicht qualifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="a48db-140">The procedure `showStrings` in the derived class displays the shadowing version of the string when the name `shadowString` is not qualified.</span></span> <span data-ttu-id="a48db-141">Daraufhin wird die Schatten Version angezeigt, wenn `shadowString` mit dem Schlüsselwort `MyBase` qualifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="a48db-141">It then displays the shadowed version when `shadowString` is qualified with the `MyBase` keyword.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="a48db-142">Robuste Programmierung</span><span class="sxs-lookup"><span data-stu-id="a48db-142">Robust Programming</span></span>

<span data-ttu-id="a48db-143">Mit shadowingwird mehr als eine Version einer Variablen mit demselben Namen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a48db-143">Shadowing introduces more than one version of a variable with the same name.</span></span> <span data-ttu-id="a48db-144">Wenn sich eine Code Anweisung auf den Variablennamen bezieht, hängt die Version, auf die der Compiler den Verweis auflöst, von Faktoren wie dem Speicherort der Code Anweisung und dem vorhanden sein einer qualifizierenden Zeichenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="a48db-144">When a code statement refers to the variable name, the version to which the compiler resolves the reference depends on factors such as the location of the code statement and the presence of a qualifying string.</span></span> <span data-ttu-id="a48db-145">Dadurch kann das Risiko erhöht werden, dass auf eine unbeabsichtigte Version einer schattiert-Variablen verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a48db-145">This can increase the risk of referring to an unintended version of a shadowed variable.</span></span> <span data-ttu-id="a48db-146">Sie können dieses Risiko verringern, indem Sie alle Verweise auf eine Schatten Variable vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="a48db-146">You can lower that risk by fully qualifying all references to a shadowed variable.</span></span>

## <a name="see-also"></a><span data-ttu-id="a48db-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a48db-147">See also</span></span>

- [<span data-ttu-id="a48db-148">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="a48db-148">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="a48db-149">Shadodown in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a48db-149">Shadowing in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="a48db-150">Unterschiede zwischen Shadowing und Überschreiben</span><span class="sxs-lookup"><span data-stu-id="a48db-150">Differences Between Shadowing and Overriding</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [<span data-ttu-id="a48db-151">Gewusst wie: Ausblenden einer geerbten Variablen</span><span class="sxs-lookup"><span data-stu-id="a48db-151">How to: Hide an Inherited Variable</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [<span data-ttu-id="a48db-152">Gewusst wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird</span><span class="sxs-lookup"><span data-stu-id="a48db-152">How to: Access a Variable Hidden by a Derived Class</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [<span data-ttu-id="a48db-153">Overrides</span><span class="sxs-lookup"><span data-stu-id="a48db-153">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="a48db-154">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="a48db-154">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="a48db-155">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="a48db-155">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
