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
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="1854e-102">Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1854e-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>
<span data-ttu-id="1854e-103">Wenn Sie eine Prozedur aufzurufen, übergeben Sie in der Regel ein oder mehrere Argumente an Sie.</span><span class="sxs-lookup"><span data-stu-id="1854e-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="1854e-104">Jedes Argument entspricht einem zugrunde liegenden Programmier Element.</span><span class="sxs-lookup"><span data-stu-id="1854e-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="1854e-105">Sowohl die zugrunde liegenden Elemente als auch die Argumente selbst können entweder änderbar oder nicht änderbar sein.</span><span class="sxs-lookup"><span data-stu-id="1854e-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="1854e-106">Änderbare und nicht änderbare Elemente</span><span class="sxs-lookup"><span data-stu-id="1854e-106">Modifiable and Nonmodifiable Elements</span></span>  
 <span data-ttu-id="1854e-107">Ein Programmier Element kann entweder ein *änderbares Element*sein, dessen Wert geändert werden kann, oder ein *nicht änderbares Element*, das nach seiner Erstellung einen festgelegten Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="1854e-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="1854e-108">In der folgenden Tabelle sind änderbare und nicht änderbare Programmier Elemente aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="1854e-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="1854e-109">Änderbare Elemente</span><span class="sxs-lookup"><span data-stu-id="1854e-109">Modifiable elements</span></span>|<span data-ttu-id="1854e-110">Nicht änderbare Elemente</span><span class="sxs-lookup"><span data-stu-id="1854e-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="1854e-111">Lokale Variablen (deklariert innerhalb von Prozeduren), einschließlich Objektvariablen, außer schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1854e-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="1854e-112">Schreibgeschützte Variablen, Felder und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1854e-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="1854e-113">Felder (Element Variablen von Modulen, Klassen und Strukturen), mit Ausnahme von Schreib geschütztem</span><span class="sxs-lookup"><span data-stu-id="1854e-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="1854e-114">Konstanten und Literale</span><span class="sxs-lookup"><span data-stu-id="1854e-114">Constants and literals</span></span>|  
|<span data-ttu-id="1854e-115">Eigenschaften, außer schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="1854e-115">Properties, except for read-only</span></span>|<span data-ttu-id="1854e-116">Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="1854e-116">Enumeration members</span></span>|  
|<span data-ttu-id="1854e-117">Array Elemente</span><span class="sxs-lookup"><span data-stu-id="1854e-117">Array elements</span></span>|<span data-ttu-id="1854e-118">Ausdrücke (auch wenn ihre Elemente geändert werden können)</span><span class="sxs-lookup"><span data-stu-id="1854e-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="1854e-119">Änderbare und nicht änderbare Argumente</span><span class="sxs-lookup"><span data-stu-id="1854e-119">Modifiable and Nonmodifiable Arguments</span></span>  
 <span data-ttu-id="1854e-120">Ein *änderbares Argument* ist ein Element mit einem änderbaren zugrunde liegenden Element.</span><span class="sxs-lookup"><span data-stu-id="1854e-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="1854e-121">Der Aufruf Code kann jederzeit einen neuen Wert speichern. Wenn Sie das [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)-Argument übergeben, kann der Code in der Prozedur auch das zugrunde liegende Element im aufrufenden Code ändern.</span><span class="sxs-lookup"><span data-stu-id="1854e-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="1854e-122">Ein *nicht änderbares Argument* weist entweder ein nicht änderbares zugrunde liegendes Element auf oder wird [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)übermittelt.</span><span class="sxs-lookup"><span data-stu-id="1854e-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="1854e-123">Die Prozedur kann das zugrunde liegende Element im aufrufenden Code nicht ändern, selbst wenn es sich um ein änderbares Element handelt.</span><span class="sxs-lookup"><span data-stu-id="1854e-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="1854e-124">Wenn es sich um ein nicht änderbares Element handelt, kann der aufrufende Code es nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="1854e-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="1854e-125">Die aufgerufene Prozedur kann die lokale Kopie eines nicht änderbaren Arguments ändern, aber diese Änderung hat keine Auswirkung auf das zugrunde liegende Element im aufrufenden Code.</span><span class="sxs-lookup"><span data-stu-id="1854e-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1854e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1854e-126">See also</span></span>

- [<span data-ttu-id="1854e-127">Verfahren</span><span class="sxs-lookup"><span data-stu-id="1854e-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="1854e-128">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="1854e-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="1854e-129">Gewusst wie: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="1854e-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="1854e-130">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="1854e-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="1854e-131">Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="1854e-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="1854e-132">Gewusst wie: Ändern des Werts eines Prozedurarguments</span><span class="sxs-lookup"><span data-stu-id="1854e-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="1854e-133">Gewusst wie: Schützen eines Prozedurarguments gegen Wertänderungen</span><span class="sxs-lookup"><span data-stu-id="1854e-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="1854e-134">Gewusst wie: Erzwingen, dass ein Argument als Wert übergeben wird</span><span class="sxs-lookup"><span data-stu-id="1854e-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="1854e-135">Übergeben von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="1854e-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="1854e-136">Werttypen und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="1854e-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
