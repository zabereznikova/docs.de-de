---
title: Nicht genügend Stapelspeicher (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: 29dbdf74808fc98bb856483c3fd8e3a09a72113b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59318792"
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="fa9c9-102">Nicht genügend Stapelspeicher (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa9c9-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="fa9c9-103">Der Stapel ist ein Arbeitsbereich des Arbeitsspeichers, der wächst oder schrumpft dynamisch mit den Anforderungen des ausgeführten Programms an.</span><span class="sxs-lookup"><span data-stu-id="fa9c9-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="fa9c9-104">Seine Grenzen wurden überschritten.</span><span class="sxs-lookup"><span data-stu-id="fa9c9-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fa9c9-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fa9c9-105">To correct this error</span></span>  
  
1. <span data-ttu-id="fa9c9-106">Überprüfen Sie, dass die Prozeduren nicht zu tief geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="fa9c9-106">Check that procedures are not nested too deeply.</span></span>  
  
2. <span data-ttu-id="fa9c9-107">Stellen Sie sicher, dass rekursive Prozeduren ordnungsgemäß zu beenden.</span><span class="sxs-lookup"><span data-stu-id="fa9c9-107">Make sure recursive procedures terminate properly.</span></span>  
  
3. <span data-ttu-id="fa9c9-108">Wenn lokale Variablen mehr Speicherplatz als verfügbar ist erforderlich, versuchen Sie es deklarieren einige Variablen auf Modulebene.</span><span class="sxs-lookup"><span data-stu-id="fa9c9-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="fa9c9-109">Sie können alle Variablen in der Prozedur auch statische deklarieren, abgrenzen, indem Sie die `Property`, `Sub`, oder `Function` Schlüsselwort mit `Static`.</span><span class="sxs-lookup"><span data-stu-id="fa9c9-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="fa9c9-110">Sie können auch die `Static` Anweisung, um einzelne statische Variablen innerhalb von Prozeduren deklarieren.</span><span class="sxs-lookup"><span data-stu-id="fa9c9-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4. <span data-ttu-id="fa9c9-111">Definieren Sie einige Ihrer Zeichenfolgen fester Länge, als Zeichenfolgen variabler Länge aus, wie Zeichenfolgen mit fester Länge mehr Stapelspeicher als Zeichenfolgen variabler Länge verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa9c9-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="fa9c9-112">Sie können auch die Zeichenfolge auf Modulebene definieren, in denen es keine Stapelspeicher erfordert.</span><span class="sxs-lookup"><span data-stu-id="fa9c9-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5. <span data-ttu-id="fa9c9-113">Überprüfen Sie die Anzahl der geschachtelten `DoEvents` Funktionsaufrufe, mit der `Calls` Dialogfeld anzeigen, welche Prozeduren auf dem Stapel aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="fa9c9-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6. <span data-ttu-id="fa9c9-114">Stellen Sie sicher, dass Sie nicht "Ereignisfolge" dazu führte, durch Auslösen eines Ereignisses, das eine Ereignisprozedur bereits auf dem Stapel aufruft.</span><span class="sxs-lookup"><span data-stu-id="fa9c9-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="fa9c9-115">Eine Ereigniskette ist vergleichbar mit einer nicht abgeschlossenen rekursiven Prozeduraufruf, aber es ist weniger offensichtlich, da der Aufruf von Visual Basic, anstatt einen expliziten Aufruf im Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fa9c9-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by Visual Basic rather than an explicit call in the code.</span></span> <span data-ttu-id="fa9c9-116">Verwenden der `Calls` Dialogfeld anzeigen, welche Prozeduren auf dem Stapel aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="fa9c9-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa9c9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa9c9-117">See also</span></span>

- [<span data-ttu-id="fa9c9-118">Fenster "Arbeitsspeicher"</span><span class="sxs-lookup"><span data-stu-id="fa9c9-118">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
