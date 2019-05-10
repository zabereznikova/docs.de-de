---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 41d38dcb3f44ccda19253adcd39401b0ac8dfb02
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647662"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="b8cf2-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8cf2-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="b8cf2-103">Gibt an, dass eine oder mehrere Membervariablen auf eine Instanz einer Klasse verweisen, die Ereignisse auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="b8cf2-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8cf2-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8cf2-104">Remarks</span></span>  
 <span data-ttu-id="b8cf2-105">Wenn eine Variable definiert ist, mithilfe von `WithEvents`, können Sie deklarativ angeben, dass eine Methode den Wert der Variablen-Ereignisse, die mit verarbeitet die `Handles` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="b8cf2-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="b8cf2-106">Sie können `WithEvents` nur auf Klassen-oder Modulebene.</span><span class="sxs-lookup"><span data-stu-id="b8cf2-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="b8cf2-107">Dies bedeutet, dass der Deklarationskontext für eine `WithEvents` Variable muss eine Klasse oder das Modul und eine Quelldatei, Namespace, Struktur oder Prozedur nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b8cf2-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="b8cf2-108">Sie können keine `WithEvents` auf einen Strukturmember.</span><span class="sxs-lookup"><span data-stu-id="b8cf2-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="b8cf2-109">Sie können nur einzelne Variablen deklarieren, nicht arrays – mit `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="b8cf2-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="b8cf2-110">Regeln</span><span class="sxs-lookup"><span data-stu-id="b8cf2-110">Rules</span></span>  
  
- <span data-ttu-id="b8cf2-111">**Elementtypen.**</span><span class="sxs-lookup"><span data-stu-id="b8cf2-111">**Element Types.**</span></span> <span data-ttu-id="b8cf2-112">Deklarieren Sie `WithEvents` Variablen so Objektvariablen, damit sie akzeptieren können-Klasseninstanzen.</span><span class="sxs-lookup"><span data-stu-id="b8cf2-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="b8cf2-113">Allerdings kann nicht deklariert werden sie als `Object`.</span><span class="sxs-lookup"><span data-stu-id="b8cf2-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="b8cf2-114">Sie müssen diese als spezifische Klasse deklarieren, die die Ereignisse auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="b8cf2-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="b8cf2-115">Die `WithEvents` Modifizierer kann in diesem Kontext verwendet werden: [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="b8cf2-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8cf2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8cf2-116">See also</span></span>

- [<span data-ttu-id="b8cf2-117">Handles</span><span class="sxs-lookup"><span data-stu-id="b8cf2-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="b8cf2-118">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b8cf2-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="b8cf2-119">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="b8cf2-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
