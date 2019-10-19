---
title: 'Gewusst wie: Steuern des Gültigkeitsbereichs einer Variablen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
ms.openlocfilehash: 23a10bd2d6c0c9f3a13bff864559460c48927e01
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582599"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a><span data-ttu-id="ed840-102">Gewusst wie: Steuern des Gültigkeitsbereichs einer Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed840-102">How to: Control the Scope of a Variable (Visual Basic)</span></span>
<span data-ttu-id="ed840-103">Normalerweise befindet sich eine Variable im Gültigkeits *Bereich*oder in der Region, in der Sie Sie deklarieren, als Verweis sichtbar.</span><span class="sxs-lookup"><span data-stu-id="ed840-103">Normally, a variable is in *scope*, or visible for reference, throughout the region in which you declare it.</span></span> <span data-ttu-id="ed840-104">In einigen Fällen kann sich die *Zugriffsebene* der Variablen auf den Gültigkeitsbereich auswirken.</span><span class="sxs-lookup"><span data-stu-id="ed840-104">In some cases, the variable's *access level* can influence its scope.</span></span>  
  
 <span data-ttu-id="ed840-105">Weitere Informationen finden Sie unter [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="ed840-105">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="scope-at-block-or-procedure-level"></a><span data-ttu-id="ed840-106">Bereich auf Block-oder Prozedur Ebene</span><span class="sxs-lookup"><span data-stu-id="ed840-106">Scope at Block or Procedure Level</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a><span data-ttu-id="ed840-107">So machen Sie eine Variable nur innerhalb eines Blocks sichtbar</span><span class="sxs-lookup"><span data-stu-id="ed840-107">To make a variable visible only within a block</span></span>  
  
- <span data-ttu-id="ed840-108">Platzieren Sie die [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) für die Variable zwischen den initiierenden und abschließenden Deklarations Anweisungen dieses Blocks, z. b. zwischen den Anweisungen `For` und `Next` einer `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="ed840-108">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable between the initiating and terminating declaration statements of that block, for example between the `For` and `Next` statements of a `For` loop.</span></span>  
  
     <span data-ttu-id="ed840-109">Sie können nur innerhalb des-Blocks auf die-Variable verweisen.</span><span class="sxs-lookup"><span data-stu-id="ed840-109">You can refer to the variable only from within the block.</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a><span data-ttu-id="ed840-110">So machen Sie eine Variable nur innerhalb einer Prozedur sichtbar</span><span class="sxs-lookup"><span data-stu-id="ed840-110">To make a variable visible only within a procedure</span></span>  
  
- <span data-ttu-id="ed840-111">Platzieren Sie die `Dim`-Anweisung für die Variable innerhalb der Prozedur, aber außerhalb eines Blocks (z. b. eines `With`... `End With`-Blocks).</span><span class="sxs-lookup"><span data-stu-id="ed840-111">Place the `Dim` statement for the variable inside the procedure but outside any block (such as a `With`...`End With` block).</span></span>  
  
     <span data-ttu-id="ed840-112">Sie können auf die Variable nur innerhalb der Prozedur verweisen, einschließlich der in der Prozedur enthaltenen Blöcke.</span><span class="sxs-lookup"><span data-stu-id="ed840-112">You can refer to the variable only from within the procedure, including inside any block contained in the procedure.</span></span>  
  
## <a name="scope-at-module-or-namespace-level"></a><span data-ttu-id="ed840-113">Bereich auf Modul-oder Namespace Ebene</span><span class="sxs-lookup"><span data-stu-id="ed840-113">Scope at Module or Namespace Level</span></span>  
 <span data-ttu-id="ed840-114">Der Vorteil ist, dass die einzelne Begriffs *Modulebene* gleichermaßen auf Module, Klassen und Strukturen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ed840-114">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="ed840-115">Die Zugriffsebene einer Variablen auf Modulebene bestimmt ihren Bereich.</span><span class="sxs-lookup"><span data-stu-id="ed840-115">The access level of a module level variable determines its scope.</span></span> <span data-ttu-id="ed840-116">Der Namespace, der das Modul, die Klasse oder die Struktur enthält, wirkt sich auch auf den Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="ed840-116">The namespace that contains the module, class, or structure also influences the scope.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a><span data-ttu-id="ed840-117">So machen Sie eine Variable in einem Modul, einer Klasse oder einer Struktur sichtbar</span><span class="sxs-lookup"><span data-stu-id="ed840-117">To make a variable visible throughout a module, class, or structure</span></span>  
  
1. <span data-ttu-id="ed840-118">Platzieren Sie die `Dim`-Anweisung für die Variable innerhalb des Moduls, der Klasse oder der Struktur, aber außerhalb der Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="ed840-118">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="ed840-119">Fügen Sie das [private](../../../../visual-basic/language-reference/modifiers/private.md) -Schlüsselwort in die `Dim`-Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="ed840-119">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="ed840-120">Sie können auf die Variable von einer beliebigen Stelle innerhalb des Moduls, der Klasse oder Struktur verweisen, jedoch nicht von außerhalb.</span><span class="sxs-lookup"><span data-stu-id="ed840-120">You can refer to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a><span data-ttu-id="ed840-121">So machen Sie eine Variable in einem Namespace sichtbar</span><span class="sxs-lookup"><span data-stu-id="ed840-121">To make a variable visible throughout a namespace</span></span>  
  
1. <span data-ttu-id="ed840-122">Platzieren Sie die `Dim`-Anweisung für die Variable innerhalb des Moduls, der Klasse oder der Struktur, aber außerhalb der Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="ed840-122">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="ed840-123">Fügen Sie das [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) -oder [Public](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort in die `Dim` Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="ed840-123">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="ed840-124">Sie können innerhalb des Namespace, der das Modul, die Klasse oder Struktur enthält, auf die Variable verweisen.</span><span class="sxs-lookup"><span data-stu-id="ed840-124">You can refer to the variable from anywhere within the namespace containing the module, class, or structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed840-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed840-125">Example</span></span>  
 <span data-ttu-id="ed840-126">Im folgenden Beispiel wird eine Variable auf Modulebene deklariert und deren Sichtbarkeit auf den Code im Modul beschränkt.</span><span class="sxs-lookup"><span data-stu-id="ed840-126">The following example declares a variable at module level and limits its visibility to code within the module.</span></span>  
  
```vb  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="ed840-127">Im vorherigen Beispiel können alle in Modul `demonstrateScope` definierten Prozeduren auf die `String` Variable `strMsg` verweisen.</span><span class="sxs-lookup"><span data-stu-id="ed840-127">In the preceding example, all the procedures defined in module `demonstrateScope` can refer to the `String` variable `strMsg`.</span></span> <span data-ttu-id="ed840-128">Wenn die `usePrivateVariable` Prozedur aufgerufen wird, wird der Inhalt der Zeichen folgen Variablen `strMsg` in einem Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ed840-128">When the `usePrivateVariable` procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
 <span data-ttu-id="ed840-129">Mit der folgenden Änderung am vorangehenden Beispiel kann auf die Zeichen folgen Variable `strMsg` von Code an beliebiger Stelle im Namespace der zugehörigen Deklaration verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="ed840-129">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```vb  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a><span data-ttu-id="ed840-130">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="ed840-130">Robust Programming</span></span>  
 <span data-ttu-id="ed840-131">Je geringer der Gültigkeitsbereich einer Variablen ist, desto weniger Möglichkeiten haben Sie, um versehentlich auf diese anstelle einer anderen Variablen mit demselben Namen zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="ed840-131">The narrower the scope of a variable, the fewer opportunities you have for accidentally referring to it in place of another variable with the same name.</span></span> <span data-ttu-id="ed840-132">Sie können auch Probleme bei der Verweis Übereinstimmung minimieren.</span><span class="sxs-lookup"><span data-stu-id="ed840-132">You can also minimize problems of reference matching.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ed840-133">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ed840-133">.NET Framework Security</span></span>  
 <span data-ttu-id="ed840-134">Je geringer der Gültigkeitsbereich einer Variablen ist, desto geringer ist die Wahrscheinlichkeit, dass böswilliger Code diese nicht ordnungsgemäß verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="ed840-134">The narrower the scope of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed840-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed840-135">See also</span></span>

- [<span data-ttu-id="ed840-136">Bereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ed840-136">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="ed840-137">Lebensdauer in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ed840-137">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="ed840-138">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ed840-138">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="ed840-139">Variablen</span><span class="sxs-lookup"><span data-stu-id="ed840-139">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="ed840-140">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="ed840-140">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="ed840-141">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ed840-141">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
