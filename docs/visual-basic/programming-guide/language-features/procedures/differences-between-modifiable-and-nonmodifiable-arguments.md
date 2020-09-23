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
ms.openlocfilehash: 662ad3039bb3fd5c44847d5b2a97a033a18ad063
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071961"
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a><span data-ttu-id="9b4e4-102">Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b4e4-102">Differences Between Modifiable and Nonmodifiable Arguments (Visual Basic)</span></span>

<span data-ttu-id="9b4e4-103">Wenn Sie eine Prozedur aufzurufen, übergeben Sie in der Regel ein oder mehrere Argumente an Sie.</span><span class="sxs-lookup"><span data-stu-id="9b4e4-103">When you call a procedure, you typically pass one or more arguments to it.</span></span> <span data-ttu-id="9b4e4-104">Jedes Argument entspricht einem zugrunde liegenden Programmier Element.</span><span class="sxs-lookup"><span data-stu-id="9b4e4-104">Each argument corresponds to an underlying programming element.</span></span> <span data-ttu-id="9b4e4-105">Sowohl die zugrunde liegenden Elemente als auch die Argumente selbst können entweder änderbar oder nicht änderbar sein.</span><span class="sxs-lookup"><span data-stu-id="9b4e4-105">Both the underlying elements and the arguments themselves can be either modifiable or nonmodifiable.</span></span>  
  
## <a name="modifiable-and-nonmodifiable-elements"></a><span data-ttu-id="9b4e4-106">Änderbare und nicht änderbare Elemente</span><span class="sxs-lookup"><span data-stu-id="9b4e4-106">Modifiable and Nonmodifiable Elements</span></span>  

 <span data-ttu-id="9b4e4-107">Ein Programmier Element kann entweder ein *änderbares Element*sein, dessen Wert geändert werden kann, oder ein *nicht änderbares Element*, das nach seiner Erstellung einen festgelegten Wert aufweist.</span><span class="sxs-lookup"><span data-stu-id="9b4e4-107">A programming element can be either a *modifiable element*, which can have its value changed, or a *nonmodifiable element*, which has a fixed value once it has been created.</span></span>  
  
 <span data-ttu-id="9b4e4-108">In der folgenden Tabelle sind änderbare und nicht änderbare Programmier Elemente aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="9b4e4-108">The following table lists modifiable and nonmodifiable programming elements.</span></span>  
  
|<span data-ttu-id="9b4e4-109">Änderbare Elemente</span><span class="sxs-lookup"><span data-stu-id="9b4e4-109">Modifiable elements</span></span>|<span data-ttu-id="9b4e4-110">Nicht änderbare Elemente</span><span class="sxs-lookup"><span data-stu-id="9b4e4-110">Nonmodifiable elements</span></span>|  
|-------------------------|----------------------------|  
|<span data-ttu-id="9b4e4-111">Lokale Variablen (deklariert innerhalb von Prozeduren), einschließlich Objektvariablen, außer schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9b4e4-111">Local variables (declared inside procedures), including object variables, except for read-only</span></span>|<span data-ttu-id="9b4e4-112">Schreibgeschützte Variablen, Felder und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9b4e4-112">Read-only variables, fields, and properties</span></span>|  
|<span data-ttu-id="9b4e4-113">Felder (Element Variablen von Modulen, Klassen und Strukturen), mit Ausnahme von Schreib geschütztem</span><span class="sxs-lookup"><span data-stu-id="9b4e4-113">Fields (member variables of modules, classes, and structures), except for read-only</span></span>|<span data-ttu-id="9b4e4-114">Konstanten und Literale</span><span class="sxs-lookup"><span data-stu-id="9b4e4-114">Constants and literals</span></span>|  
|<span data-ttu-id="9b4e4-115">Eigenschaften, außer schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9b4e4-115">Properties, except for read-only</span></span>|<span data-ttu-id="9b4e4-116">Enumerationsmember</span><span class="sxs-lookup"><span data-stu-id="9b4e4-116">Enumeration members</span></span>|  
|<span data-ttu-id="9b4e4-117">Array Elemente</span><span class="sxs-lookup"><span data-stu-id="9b4e4-117">Array elements</span></span>|<span data-ttu-id="9b4e4-118">Ausdrücke (auch wenn ihre Elemente geändert werden können)</span><span class="sxs-lookup"><span data-stu-id="9b4e4-118">Expressions (even if their elements are modifiable)</span></span>|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a><span data-ttu-id="9b4e4-119">Änderbare und nicht änderbare Argumente</span><span class="sxs-lookup"><span data-stu-id="9b4e4-119">Modifiable and Nonmodifiable Arguments</span></span>  

 <span data-ttu-id="9b4e4-120">Ein *änderbares Argument* ist ein Element mit einem änderbaren zugrunde liegenden Element.</span><span class="sxs-lookup"><span data-stu-id="9b4e4-120">A *modifiable argument* is one with a modifiable underlying element.</span></span> <span data-ttu-id="9b4e4-121">Der Aufruf Code kann jederzeit einen neuen Wert speichern. Wenn Sie das [ByRef](../../../language-reference/modifiers/byref.md)-Argument übergeben, kann der Code in der Prozedur auch das zugrunde liegende Element im aufrufenden Code ändern.</span><span class="sxs-lookup"><span data-stu-id="9b4e4-121">The calling code can store a new value at any time, and if you pass the argument [ByRef](../../../language-reference/modifiers/byref.md), the code in the procedure can also modify the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="9b4e4-122">Ein *nicht änderbares Argument* weist entweder ein nicht änderbares zugrunde liegendes Element auf oder wird [ByVal](../../../language-reference/modifiers/byval.md)übermittelt.</span><span class="sxs-lookup"><span data-stu-id="9b4e4-122">A *nonmodifiable argument* either has a nonmodifiable underlying element or is passed [ByVal](../../../language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="9b4e4-123">Die Prozedur kann das zugrunde liegende Element im aufrufenden Code nicht ändern, selbst wenn es sich um ein änderbares Element handelt.</span><span class="sxs-lookup"><span data-stu-id="9b4e4-123">The procedure cannot modify the underlying element in the calling code, even if it is a modifiable element.</span></span> <span data-ttu-id="9b4e4-124">Wenn es sich um ein nicht änderbares Element handelt, kann der aufrufende Code es nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="9b4e4-124">If it is a nonmodifiable element, the calling code itself cannot modify it.</span></span>  
  
 <span data-ttu-id="9b4e4-125">Die aufgerufene Prozedur kann die lokale Kopie eines nicht änderbaren Arguments ändern, aber diese Änderung hat keine Auswirkung auf das zugrunde liegende Element im aufrufenden Code.</span><span class="sxs-lookup"><span data-stu-id="9b4e4-125">The called procedure might modify its local copy of a nonmodifiable argument, but that modification does not affect the underlying element in the calling code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b4e4-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b4e4-126">See also</span></span>

- [<span data-ttu-id="9b4e4-127">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="9b4e4-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="9b4e4-128">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="9b4e4-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="9b4e4-129">Vorgehensweise: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="9b4e4-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="9b4e4-130">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="9b4e4-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="9b4e4-131">Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="9b4e4-131">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="9b4e4-132">Vorgehensweise: Ändern des Werts eines Prozedurarguments</span><span class="sxs-lookup"><span data-stu-id="9b4e4-132">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="9b4e4-133">Vorgehensweise: Schützen eines Prozedurarguments gegen Wertänderungen</span><span class="sxs-lookup"><span data-stu-id="9b4e4-133">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="9b4e4-134">Vorgehensweise: Erzwingen, dass ein Argument als Wert übergeben wird</span><span class="sxs-lookup"><span data-stu-id="9b4e4-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="9b4e4-135">Übergeben von Argumenten nach Position und Name</span><span class="sxs-lookup"><span data-stu-id="9b4e4-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="9b4e4-136">Wert- und Verweistypen</span><span class="sxs-lookup"><span data-stu-id="9b4e4-136">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
