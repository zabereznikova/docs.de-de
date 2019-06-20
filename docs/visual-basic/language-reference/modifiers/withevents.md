---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: e8a8fb571fa65228f3a0acec1f902d21eb9bfe04
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268307"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="02f44-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02f44-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="02f44-103">Gibt an, dass eine oder mehrere Membervariablen auf eine Instanz einer Klasse verweisen, die Ereignisse auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="02f44-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02f44-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="02f44-104">Remarks</span></span>  
 <span data-ttu-id="02f44-105">Wenn eine Variable definiert ist, mithilfe von `WithEvents`, können Sie deklarativ angeben, dass eine Methode den Wert der Variablen-Ereignisse, die mit verarbeitet die `Handles` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="02f44-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="02f44-106">Sie können `WithEvents` nur auf Klassen-oder Modulebene.</span><span class="sxs-lookup"><span data-stu-id="02f44-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="02f44-107">Dies bedeutet, dass der Deklarationskontext für eine `WithEvents` Variable muss eine Klasse oder das Modul und eine Quelldatei, Namespace, Struktur oder Prozedur nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="02f44-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="02f44-108">Sie können keine `WithEvents` auf einen Strukturmember.</span><span class="sxs-lookup"><span data-stu-id="02f44-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="02f44-109">Sie können nur einzelne Variablen deklarieren, nicht arrays – mit `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="02f44-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="02f44-110">Regeln</span><span class="sxs-lookup"><span data-stu-id="02f44-110">Rules</span></span>  
  
- <span data-ttu-id="02f44-111">**Elementtypen.**</span><span class="sxs-lookup"><span data-stu-id="02f44-111">**Element Types.**</span></span> <span data-ttu-id="02f44-112">Deklarieren Sie `WithEvents` Variablen so Objektvariablen, damit sie akzeptieren können-Klasseninstanzen.</span><span class="sxs-lookup"><span data-stu-id="02f44-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="02f44-113">Allerdings kann nicht deklariert werden sie als `Object`.</span><span class="sxs-lookup"><span data-stu-id="02f44-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="02f44-114">Sie müssen diese als spezifische Klasse deklarieren, die die Ereignisse auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="02f44-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="02f44-115">Die `WithEvents` Modifizierer kann in diesem Kontext verwendet werden: [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="02f44-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
 
## <a name="example"></a><span data-ttu-id="02f44-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="02f44-116">Example</span></span>

```VB
Dim WithEvents app As Application
```
  
## <a name="see-also"></a><span data-ttu-id="02f44-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02f44-117">See also</span></span>

- [<span data-ttu-id="02f44-118">Handles</span><span class="sxs-lookup"><span data-stu-id="02f44-118">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="02f44-119">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="02f44-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="02f44-120">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="02f44-120">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
