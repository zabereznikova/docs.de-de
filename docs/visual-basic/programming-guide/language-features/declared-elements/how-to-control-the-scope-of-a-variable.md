---
title: 'Vorgehensweise: Steuern des Gültigkeitsbereichs einer Variablen (Visual Basic)'
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
ms.openlocfilehash: 24a7ae3b8f3400beeaedb20ea6352ea44bdb7597
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794731"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a><span data-ttu-id="31eff-102">Vorgehensweise: Steuern des Gültigkeitsbereichs einer Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31eff-102">How to: Control the Scope of a Variable (Visual Basic)</span></span>
<span data-ttu-id="31eff-103">In der Regel wird eine Variable *Bereich*, oder als Referenz in der Region, in dem Sie wurde deklariert, sichtbar.</span><span class="sxs-lookup"><span data-stu-id="31eff-103">Normally, a variable is in *scope*, or visible for reference, throughout the region in which you declare it.</span></span> <span data-ttu-id="31eff-104">In einigen Fällen die Variable des *Zugriffsebene* können ihren Bereich beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="31eff-104">In some cases, the variable's *access level* can influence its scope.</span></span>  
  
 <span data-ttu-id="31eff-105">Weitere Informationen finden Sie unter [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="31eff-105">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
## <a name="scope-at-block-or-procedure-level"></a><span data-ttu-id="31eff-106">Gültigkeitsbereich der Block- oder Prozedurebene</span><span class="sxs-lookup"><span data-stu-id="31eff-106">Scope at Block or Procedure Level</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a><span data-ttu-id="31eff-107">Um eine Variable nur innerhalb eines Blocks sichtbar zu machen</span><span class="sxs-lookup"><span data-stu-id="31eff-107">To make a variable visible only within a block</span></span>  
  
- <span data-ttu-id="31eff-108">Ort der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) für die Variable zwischen der initiiert und beendet die deklarationsanweisungen dieses Blocks, z. B. zwischen den `For` und `Next` Anweisungen eine `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="31eff-108">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable between the initiating and terminating declaration statements of that block, for example between the `For` and `Next` statements of a `For` loop.</span></span>  
  
     <span data-ttu-id="31eff-109">Sie können auf die Variable nur von innerhalb des Blocks verweisen.</span><span class="sxs-lookup"><span data-stu-id="31eff-109">You can refer to the variable only from within the block.</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a><span data-ttu-id="31eff-110">Um eine Variable nur innerhalb einer Prozedur sichtbar zu machen</span><span class="sxs-lookup"><span data-stu-id="31eff-110">To make a variable visible only within a procedure</span></span>  
  
- <span data-ttu-id="31eff-111">Ort der `Dim` -Anweisung für die Variable in der Prozedur, aber außerhalb aller Blöcke (z. B. eine `With`... `End With` Block).</span><span class="sxs-lookup"><span data-stu-id="31eff-111">Place the `Dim` statement for the variable inside the procedure but outside any block (such as a `With`...`End With` block).</span></span>  
  
     <span data-ttu-id="31eff-112">Sie können auf die Variable nur von innerhalb der Prozedur, einschließlich innerhalb eines beliebigen Blocks enthalten sind, in der Prozedur verweisen.</span><span class="sxs-lookup"><span data-stu-id="31eff-112">You can refer to the variable only from within the procedure, including inside any block contained in the procedure.</span></span>  
  
## <a name="scope-at-module-or-namespace-level"></a><span data-ttu-id="31eff-113">Bereich auf Namespace-Ebene oder Moduls</span><span class="sxs-lookup"><span data-stu-id="31eff-113">Scope at Module or Namespace Level</span></span>  
 <span data-ttu-id="31eff-114">Der Einfachheit halber einen einzelnen Ausdruck *auf Modulebene* gilt gleichermaßen für Module, Klassen und Strukturen.</span><span class="sxs-lookup"><span data-stu-id="31eff-114">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="31eff-115">Die Zugriffsebene der einer Modulvariablen Ebene bestimmt den Gültigkeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="31eff-115">The access level of a module level variable determines its scope.</span></span> <span data-ttu-id="31eff-116">Der Namespace, der das Modul, Klasse oder Struktur enthält, wirkt sich auch auf den Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="31eff-116">The namespace that contains the module, class, or structure also influences the scope.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a><span data-ttu-id="31eff-117">Um eine Variable in einem Modul, Klasse oder Struktur sichtbar zu machen</span><span class="sxs-lookup"><span data-stu-id="31eff-117">To make a variable visible throughout a module, class, or structure</span></span>  
  
1. <span data-ttu-id="31eff-118">Ort der `Dim` -Anweisung für die Variable in das Modul, Klasse oder Struktur, aber außerhalb einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="31eff-118">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="31eff-119">Enthalten die [Private](../../../../visual-basic/language-reference/modifiers/private.md) -Schlüsselwort in der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="31eff-119">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="31eff-120">Sehen Sie sich die Variable aus einer beliebigen Position innerhalb der Module, Klasse oder Struktur, jedoch nicht von außerhalb davon.</span><span class="sxs-lookup"><span data-stu-id="31eff-120">You can refer to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a><span data-ttu-id="31eff-121">Um eine Variable in einem Namespace sichtbar zu machen</span><span class="sxs-lookup"><span data-stu-id="31eff-121">To make a variable visible throughout a namespace</span></span>  
  
1. <span data-ttu-id="31eff-122">Ort der `Dim` -Anweisung für die Variable in das Modul, Klasse oder Struktur, aber außerhalb einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="31eff-122">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="31eff-123">Enthalten die [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) oder [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort in der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="31eff-123">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) or [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="31eff-124">Sie können auf die Variable verweisen, von überall aus innerhalb des Namespaces, die das Modul, Klasse oder Struktur enthält.</span><span class="sxs-lookup"><span data-stu-id="31eff-124">You can refer to the variable from anywhere within the namespace containing the module, class, or structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31eff-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="31eff-125">Example</span></span>  
 <span data-ttu-id="31eff-126">Das folgende Beispiel deklariert eine Variable auf Modulebene und schränkt die Sichtbarkeit für Code innerhalb des Moduls.</span><span class="sxs-lookup"><span data-stu-id="31eff-126">The following example declares a variable at module level and limits its visibility to code within the module.</span></span>  
  
```  
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
  
 <span data-ttu-id="31eff-127">Im vorherigen Beispiel werden alle Prozeduren in Modul definierten `demonstrateScope` können, finden Sie in der `String` Variable `strMsg`.</span><span class="sxs-lookup"><span data-stu-id="31eff-127">In the preceding example, all the procedures defined in module `demonstrateScope` can refer to the `String` variable `strMsg`.</span></span> <span data-ttu-id="31eff-128">Wenn die `usePrivateVariable` Prozedur aufgerufen wird, wird es zeigt den Inhalt der Zeichenfolgenvariablen `strMsg` in einem Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="31eff-128">When the `usePrivateVariable` procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
 <span data-ttu-id="31eff-129">Durch die folgende Änderung zum vorherigen Beispiel die Zeichenfolgenvariable `strMsg` kann vom Code an einer beliebigen Stelle in den Namespace der Deklaration verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="31eff-129">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a><span data-ttu-id="31eff-130">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="31eff-130">Robust Programming</span></span>  
 <span data-ttu-id="31eff-131">Je schmaler der Gültigkeitsbereich einer Variablen, die weniger Möglichkeiten haben Sie bei der es versehentlich anstelle einer anderen Variablen mit dem gleichen Namen auf.</span><span class="sxs-lookup"><span data-stu-id="31eff-131">The narrower the scope of a variable, the fewer opportunities you have for accidentally referring to it in place of another variable with the same name.</span></span> <span data-ttu-id="31eff-132">Sie können auch Probleme mit übereinstimmenden verweisen minimieren.</span><span class="sxs-lookup"><span data-stu-id="31eff-132">You can also minimize problems of reference matching.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="31eff-133">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="31eff-133">.NET Framework Security</span></span>  
 <span data-ttu-id="31eff-134">Je schmaler des Gültigkeitsbereichs einer Variablen, verwendet der geringer ist die Wahrscheinlichkeit, die bösartiger Code eine ungültige vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="31eff-134">The narrower the scope of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31eff-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31eff-135">See also</span></span>

- [<span data-ttu-id="31eff-136">Gültigkeitsbereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31eff-136">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="31eff-137">Lebensdauer in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31eff-137">Lifetime in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="31eff-138">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="31eff-138">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="31eff-139">Variablen</span><span class="sxs-lookup"><span data-stu-id="31eff-139">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="31eff-140">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="31eff-140">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="31eff-141">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="31eff-141">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
