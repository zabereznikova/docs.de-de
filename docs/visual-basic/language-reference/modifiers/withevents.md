---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 50d5a768393e90d28d150b451405e35e6f4c7953
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583040"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="6db86-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6db86-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="6db86-103">Gibt an, dass eine oder mehrere deklarierte Element Variablen auf eine Instanz einer Klasse verweisen, die Ereignisse hervorrufen kann.</span><span class="sxs-lookup"><span data-stu-id="6db86-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="6db86-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6db86-104">Remarks</span></span>

<span data-ttu-id="6db86-105">Wenn eine Variable mithilfe von `WithEvents` definiert wird, können Sie deklarativ angeben, dass eine Methode die Ereignisse der Variablen mithilfe des Schlüssel Worts `Handles` behandelt.</span><span class="sxs-lookup"><span data-stu-id="6db86-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="6db86-106">Sie können `WithEvents` nur auf Klassen-oder Modulebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="6db86-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="6db86-107">Dies bedeutet, dass der Deklarations Kontext für eine `WithEvents` Variable eine Klasse oder ein Modul sein muss und weder eine Quelldatei noch ein Namespace, eine Struktur oder eine Prozedur sein darf.</span><span class="sxs-lookup"><span data-stu-id="6db86-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="6db86-108">Sie können `WithEvents` für einen Strukturmember nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="6db86-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="6db86-109">Sie können nur einzelne Variablen – keine Arrays – mit `WithEvents` deklarieren.</span><span class="sxs-lookup"><span data-stu-id="6db86-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="6db86-110">Regeln</span><span class="sxs-lookup"><span data-stu-id="6db86-110">Rules</span></span>

<span data-ttu-id="6db86-111">**Element Typen.**</span><span class="sxs-lookup"><span data-stu-id="6db86-111">**Element Types.**</span></span> <span data-ttu-id="6db86-112">Sie müssen `WithEvents` Variablen als Objektvariablen deklarieren, damit Sie Klassen Instanzen akzeptieren können.</span><span class="sxs-lookup"><span data-stu-id="6db86-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="6db86-113">Sie können Sie jedoch nicht als `Object` deklarieren.</span><span class="sxs-lookup"><span data-stu-id="6db86-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="6db86-114">Sie müssen Sie als eine bestimmte Klasse deklarieren, die die Ereignisse hervorrufen kann.</span><span class="sxs-lookup"><span data-stu-id="6db86-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="6db86-115">Der `WithEvents` Modifizierer kann in diesem Kontext verwendet werden: [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="6db86-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="6db86-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6db86-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="6db86-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6db86-117">See also</span></span>

- [<span data-ttu-id="6db86-118">Handles</span><span class="sxs-lookup"><span data-stu-id="6db86-118">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="6db86-119">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="6db86-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="6db86-120">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="6db86-120">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
