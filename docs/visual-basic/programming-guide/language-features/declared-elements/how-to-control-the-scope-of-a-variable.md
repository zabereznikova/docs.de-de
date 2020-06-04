---
title: 'Vorgehensweise: Steuern des Gültigkeitsbereichs einer Variablen'
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
ms.openlocfilehash: 8b21f22edea84448e3f2969c3e4b07c08a17a338
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357347"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a><span data-ttu-id="d737a-102">Gewusst wie: Steuern des Gültigkeitsbereichs einer Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d737a-102">How to: Control the Scope of a Variable (Visual Basic)</span></span>
<span data-ttu-id="d737a-103">Normalerweise befindet sich eine Variable im Gültigkeits *Bereich*oder in der Region, in der Sie Sie deklarieren, als Verweis sichtbar.</span><span class="sxs-lookup"><span data-stu-id="d737a-103">Normally, a variable is in *scope*, or visible for reference, throughout the region in which you declare it.</span></span> <span data-ttu-id="d737a-104">In einigen Fällen kann sich die *Zugriffsebene* der Variablen auf den Gültigkeitsbereich auswirken.</span><span class="sxs-lookup"><span data-stu-id="d737a-104">In some cases, the variable's *access level* can influence its scope.</span></span>  
  
 <span data-ttu-id="d737a-105">Weitere Informationen finden Sie unter [Scope in Visual Basic](scope.md).</span><span class="sxs-lookup"><span data-stu-id="d737a-105">For more information, see [Scope in Visual Basic](scope.md).</span></span>  
  
## <a name="scope-at-block-or-procedure-level"></a><span data-ttu-id="d737a-106">Bereich auf Block-oder Prozedur Ebene</span><span class="sxs-lookup"><span data-stu-id="d737a-106">Scope at Block or Procedure Level</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a><span data-ttu-id="d737a-107">So machen Sie eine Variable nur innerhalb eines Blocks sichtbar</span><span class="sxs-lookup"><span data-stu-id="d737a-107">To make a variable visible only within a block</span></span>  
  
- <span data-ttu-id="d737a-108">Platzieren Sie die [Dim-Anweisung](../../../language-reference/statements/dim-statement.md) für die Variable zwischen den initiierenden und abschließenden Deklarations Anweisungen dieses Blocks, z. b. zwischen der-Anweisung `For` und der-Anweisung `Next` einer- `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="d737a-108">Place the [Dim Statement](../../../language-reference/statements/dim-statement.md) for the variable between the initiating and terminating declaration statements of that block, for example between the `For` and `Next` statements of a `For` loop.</span></span>  
  
     <span data-ttu-id="d737a-109">Sie können nur innerhalb des-Blocks auf die-Variable verweisen.</span><span class="sxs-lookup"><span data-stu-id="d737a-109">You can refer to the variable only from within the block.</span></span>  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a><span data-ttu-id="d737a-110">So machen Sie eine Variable nur innerhalb einer Prozedur sichtbar</span><span class="sxs-lookup"><span data-stu-id="d737a-110">To make a variable visible only within a procedure</span></span>  
  
- <span data-ttu-id="d737a-111">Platzieren Sie die- `Dim` Anweisung für die Variable innerhalb der Prozedur, aber außerhalb eines Blocks (z `With` . b. eines...- `End With` Blocks).</span><span class="sxs-lookup"><span data-stu-id="d737a-111">Place the `Dim` statement for the variable inside the procedure but outside any block (such as a `With`...`End With` block).</span></span>  
  
     <span data-ttu-id="d737a-112">Sie können auf die Variable nur innerhalb der Prozedur verweisen, einschließlich der in der Prozedur enthaltenen Blöcke.</span><span class="sxs-lookup"><span data-stu-id="d737a-112">You can refer to the variable only from within the procedure, including inside any block contained in the procedure.</span></span>  
  
## <a name="scope-at-module-or-namespace-level"></a><span data-ttu-id="d737a-113">Bereich auf Modul-oder Namespace Ebene</span><span class="sxs-lookup"><span data-stu-id="d737a-113">Scope at Module or Namespace Level</span></span>  
 <span data-ttu-id="d737a-114">Der Vorteil ist, dass die einzelne Begriffs *Modulebene* gleichermaßen auf Module, Klassen und Strukturen angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d737a-114">For convenience, the single term *module level* applies equally to modules, classes, and structures.</span></span> <span data-ttu-id="d737a-115">Die Zugriffsebene einer Variablen auf Modulebene bestimmt ihren Bereich.</span><span class="sxs-lookup"><span data-stu-id="d737a-115">The access level of a module level variable determines its scope.</span></span> <span data-ttu-id="d737a-116">Der Namespace, der das Modul, die Klasse oder die Struktur enthält, wirkt sich auch auf den Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="d737a-116">The namespace that contains the module, class, or structure also influences the scope.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a><span data-ttu-id="d737a-117">So machen Sie eine Variable in einem Modul, einer Klasse oder einer Struktur sichtbar</span><span class="sxs-lookup"><span data-stu-id="d737a-117">To make a variable visible throughout a module, class, or structure</span></span>  
  
1. <span data-ttu-id="d737a-118">Platzieren Sie die- `Dim` Anweisung für die Variable innerhalb des Moduls, der Klasse oder der Struktur, aber außerhalb der Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="d737a-118">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="d737a-119">Fügen Sie das [private](../../../language-reference/modifiers/private.md) -Schlüsselwort in die `Dim` Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="d737a-119">Include the [Private](../../../language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="d737a-120">Sie können auf die Variable von einer beliebigen Stelle innerhalb des Moduls, der Klasse oder Struktur verweisen, jedoch nicht von außerhalb.</span><span class="sxs-lookup"><span data-stu-id="d737a-120">You can refer to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a><span data-ttu-id="d737a-121">So machen Sie eine Variable in einem Namespace sichtbar</span><span class="sxs-lookup"><span data-stu-id="d737a-121">To make a variable visible throughout a namespace</span></span>  
  
1. <span data-ttu-id="d737a-122">Platzieren Sie die- `Dim` Anweisung für die Variable innerhalb des Moduls, der Klasse oder der Struktur, aber außerhalb der Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="d737a-122">Place the `Dim` statement for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="d737a-123">Fügen Sie das [Friend](../../../language-reference/modifiers/friend.md) -oder [Public](../../../language-reference/modifiers/public.md) -Schlüsselwort in die `Dim` Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="d737a-123">Include the [Friend](../../../language-reference/modifiers/friend.md) or [Public](../../../language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
3. <span data-ttu-id="d737a-124">Sie können innerhalb des Namespace, der das Modul, die Klasse oder Struktur enthält, auf die Variable verweisen.</span><span class="sxs-lookup"><span data-stu-id="d737a-124">You can refer to the variable from anywhere within the namespace containing the module, class, or structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d737a-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d737a-125">Example</span></span>  
 <span data-ttu-id="d737a-126">Im folgenden Beispiel wird eine Variable auf Modulebene deklariert und deren Sichtbarkeit auf den Code im Modul beschränkt.</span><span class="sxs-lookup"><span data-stu-id="d737a-126">The following example declares a variable at module level and limits its visibility to code within the module.</span></span>  
  
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
  
 <span data-ttu-id="d737a-127">Im vorherigen Beispiel können alle im Modul definierten Prozeduren `demonstrateScope` auf die Variable verweisen `String` `strMsg` .</span><span class="sxs-lookup"><span data-stu-id="d737a-127">In the preceding example, all the procedures defined in module `demonstrateScope` can refer to the `String` variable `strMsg`.</span></span> <span data-ttu-id="d737a-128">Wenn die `usePrivateVariable` Prozedur aufgerufen wird, wird der Inhalt der Zeichen folgen Variablen `strMsg` in einem Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d737a-128">When the `usePrivateVariable` procedure is called, it displays the contents of the string variable `strMsg` in a dialog box.</span></span>  
  
 <span data-ttu-id="d737a-129">Mit der folgenden Änderung am vorangehenden Beispiel kann auf die Zeichen folgen Variable an `strMsg` beliebiger Stelle im Namespace der zugehörigen Deklaration verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="d737a-129">With the following alteration to the preceding example, the string variable `strMsg` can be referred to by code anywhere in the namespace of its declaration.</span></span>  
  
```vb  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a><span data-ttu-id="d737a-130">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="d737a-130">Robust Programming</span></span>  
 <span data-ttu-id="d737a-131">Je geringer der Gültigkeitsbereich einer Variablen ist, desto weniger Möglichkeiten haben Sie, um versehentlich auf diese anstelle einer anderen Variablen mit demselben Namen zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="d737a-131">The narrower the scope of a variable, the fewer opportunities you have for accidentally referring to it in place of another variable with the same name.</span></span> <span data-ttu-id="d737a-132">Sie können auch Probleme bei der Verweis Übereinstimmung minimieren.</span><span class="sxs-lookup"><span data-stu-id="d737a-132">You can also minimize problems of reference matching.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d737a-133">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d737a-133">.NET Framework Security</span></span>  
 <span data-ttu-id="d737a-134">Je geringer der Gültigkeitsbereich einer Variablen ist, desto geringer ist die Wahrscheinlichkeit, dass böswilliger Code diese nicht ordnungsgemäß verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="d737a-134">The narrower the scope of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d737a-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d737a-135">See also</span></span>

- [<span data-ttu-id="d737a-136">Gültigkeitsbereich in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d737a-136">Scope in Visual Basic</span></span>](scope.md)
- [<span data-ttu-id="d737a-137">Lebensdauer in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d737a-137">Lifetime in Visual Basic</span></span>](lifetime.md)
- [<span data-ttu-id="d737a-138">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d737a-138">Access levels in Visual Basic</span></span>](access-levels.md)
- [<span data-ttu-id="d737a-139">Variablen</span><span class="sxs-lookup"><span data-stu-id="d737a-139">Variables</span></span>](../variables/index.md)
- [<span data-ttu-id="d737a-140">Variablen Deklaration</span><span class="sxs-lookup"><span data-stu-id="d737a-140">Variable Declaration</span></span>](../variables/variable-declaration.md)
- [<span data-ttu-id="d737a-141">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d737a-141">Dim Statement</span></span>](../../../language-reference/statements/dim-statement.md)
