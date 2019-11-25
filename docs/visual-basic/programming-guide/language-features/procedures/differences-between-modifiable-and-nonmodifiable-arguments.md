---
title: Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
ms.openlocfilehash: 989795ee2cdd3a78b71bad4d95cf9b384c2719bd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341392"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="60030-102">Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60030-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>
<span data-ttu-id="60030-103">When you call a procedure, you typically pass one or more arguments to it.</span><span class="sxs-lookup"><span data-stu-id="60030-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="60030-104">Each argument corresponds to an underlying programming element.</span><span class="sxs-lookup"><span data-stu-id="60030-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="60030-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span><span class="sxs-lookup"><span data-stu-id="60030-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="60030-106">Modifiable and Nonmodifiable Elements</span><span class="sxs-lookup"><span data-stu-id="60030-106">Modifiable and Nonmodifiable Elements</span></span>  
 <span data-ttu-id="60030-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span><span class="sxs-lookup"><span data-stu-id="60030-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="60030-108">The following table lists modifiable and nonmodifiable programming elements.</span><span class="sxs-lookup"><span data-stu-id="60030-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="60030-109">Modifiable elements</span><span class="sxs-lookup"><span data-stu-id="60030-109">Modifiable elements</span></span>|<span data-ttu-id="60030-110">Nonmodifiable elements</span><span class="sxs-lookup"><span data-stu-id="60030-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="60030-111">Local variables (declared inside procedures), including object variables, except for read-only</span><span class="sxs-lookup"><span data-stu-id="60030-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="60030-112">Read-only variables, fields, and properties</span><span class="sxs-lookup"><span data-stu-id="60030-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="60030-113">Fields (member variables of modules, classes, and structures), except for read-only</span><span class="sxs-lookup"><span data-stu-id="60030-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="60030-114">Constants and literals</span><span class="sxs-lookup"><span data-stu-id="60030-114">Constants and literals</span></span>|  
|<span data-ttu-id="60030-115">Properties, except for read-only</span><span class="sxs-lookup"><span data-stu-id="60030-115">Properties, except for read-only</span></span>|<span data-ttu-id="60030-116">Enumeration members</span><span class="sxs-lookup"><span data-stu-id="60030-116">Enumeration members</span></span>|  
|<span data-ttu-id="60030-117">Array elements</span><span class="sxs-lookup"><span data-stu-id="60030-117">Array elements</span></span>|<span data-ttu-id="60030-118">Expressions (even if their elements are modifiable)</span><span class="sxs-lookup"><span data-stu-id="60030-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="60030-119">Modifiable and Nonmodifiable Arguments</span><span class="sxs-lookup"><span data-stu-id="60030-119">Modifiable and Nonmodifiable Arguments</span></span>  
 <span data-ttu-id="60030-120">A *modifiable argument* is one with a modifiable underlying element.</span><span class="sxs-lookup"><span data-stu-id="60030-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="60030-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span><span class="sxs-lookup"><span data-stu-id="60030-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="60030-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span><span class="sxs-lookup"><span data-stu-id="60030-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="60030-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span><span class="sxs-lookup"><span data-stu-id="60030-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="60030-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span><span class="sxs-lookup"><span data-stu-id="60030-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="60030-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span><span class="sxs-lookup"><span data-stu-id="60030-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60030-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60030-126">See also</span></span>

- [<span data-ttu-id="60030-127">Verfahren</span><span class="sxs-lookup"><span data-stu-id="60030-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="60030-128">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="60030-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="60030-129">Gewusst wie: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="60030-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="60030-130">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="60030-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="60030-131">Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="60030-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="60030-132">Gewusst wie: Ändern des Werts eines Prozedurarguments</span><span class="sxs-lookup"><span data-stu-id="60030-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="60030-133">Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen</span><span class="sxs-lookup"><span data-stu-id="60030-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="60030-134">Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird</span><span class="sxs-lookup"><span data-stu-id="60030-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="60030-135">Übergeben von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="60030-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="60030-136">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="60030-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
