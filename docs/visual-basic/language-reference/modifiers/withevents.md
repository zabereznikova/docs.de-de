---
title: WithEvents
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 2309c675b50a2025d73841a47fe8e30e7cecd522
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350745"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="65079-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65079-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="65079-103">Gibt an, dass eine oder mehrere deklarierte Element Variablen auf eine Instanz einer Klasse verweisen, die Ereignisse hervorrufen kann.</span><span class="sxs-lookup"><span data-stu-id="65079-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="65079-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="65079-104">Remarks</span></span>

<span data-ttu-id="65079-105">Wenn eine Variable mithilfe von `WithEvents`definiert wird, können Sie deklarativ angeben, dass eine Methode die Ereignisse der Variablen mithilfe des Schlüssel Worts `Handles` behandelt.</span><span class="sxs-lookup"><span data-stu-id="65079-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="65079-106">Sie können `WithEvents` nur auf Klassen-oder Modulebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="65079-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="65079-107">Dies bedeutet, dass der Deklarations Kontext für eine `WithEvents` Variable eine Klasse oder ein Modul sein muss und weder eine Quelldatei noch ein Namespace, eine Struktur oder eine Prozedur sein darf.</span><span class="sxs-lookup"><span data-stu-id="65079-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="65079-108">Sie können `WithEvents` für einen Strukturmember nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="65079-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="65079-109">Sie können nur einzelne Variablen – keine Arrays – mit `WithEvents`deklarieren.</span><span class="sxs-lookup"><span data-stu-id="65079-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="65079-110">Regeln</span><span class="sxs-lookup"><span data-stu-id="65079-110">Rules</span></span>

<span data-ttu-id="65079-111">**Element Typen.**</span><span class="sxs-lookup"><span data-stu-id="65079-111">**Element Types.**</span></span> <span data-ttu-id="65079-112">Sie müssen `WithEvents` Variablen als Objektvariablen deklarieren, damit Sie Klassen Instanzen akzeptieren können.</span><span class="sxs-lookup"><span data-stu-id="65079-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="65079-113">Sie können Sie jedoch nicht als `Object`deklarieren.</span><span class="sxs-lookup"><span data-stu-id="65079-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="65079-114">Sie müssen Sie als eine bestimmte Klasse deklarieren, die die Ereignisse hervorrufen kann.</span><span class="sxs-lookup"><span data-stu-id="65079-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="65079-115">Der `WithEvents` Modifizierer kann in diesem Kontext verwendet werden: [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="65079-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="65079-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="65079-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="65079-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65079-117">See also</span></span>

- [<span data-ttu-id="65079-118">Handles</span><span class="sxs-lookup"><span data-stu-id="65079-118">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="65079-119">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="65079-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="65079-120">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="65079-120">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
