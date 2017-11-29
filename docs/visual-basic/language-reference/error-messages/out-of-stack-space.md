---
title: "Nicht genügend Stapelspeicher (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3959c24aa4e95204e156a9863ef0ce237af1fcda
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="47c5a-102">Nicht genügend Stapelspeicher (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47c5a-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="47c5a-103">Der Stapel ist ein Arbeitsbereich des Arbeitsspeichers, der vergrößert bzw. verkleinert sich dynamisch mit den Anforderungen an das ausgeführte Programm.</span><span class="sxs-lookup"><span data-stu-id="47c5a-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="47c5a-104">Seine Grenzen wurden überschritten.</span><span class="sxs-lookup"><span data-stu-id="47c5a-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="47c5a-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="47c5a-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="47c5a-106">Überprüfen Sie, dass die Prozeduren nicht zu tief geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="47c5a-106">Check that procedures are not nested too deeply.</span></span>  
  
2.  <span data-ttu-id="47c5a-107">Stellen Sie sicher, dass rekursive Prozeduren ordnungsgemäß beendet.</span><span class="sxs-lookup"><span data-stu-id="47c5a-107">Make sure recursive procedures terminate properly.</span></span>  
  
3.  <span data-ttu-id="47c5a-108">Wenn lokale Variablen mehr Speicherplatz als die verfügbare erforderlich ist, versuchen Sie, einige Variablen auf Modulebene deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="47c5a-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="47c5a-109">Sie können alle Variablen in der Prozedur auch statische deklarieren, abgrenzen, indem Sie die `Property`, `Sub`, oder `Function` Schlüsselwort mit `Static`.</span><span class="sxs-lookup"><span data-stu-id="47c5a-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="47c5a-110">Oder Sie können die `Static` Anweisung, um einzelne statische Variablen innerhalb von Prozeduren deklarieren.</span><span class="sxs-lookup"><span data-stu-id="47c5a-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4.  <span data-ttu-id="47c5a-111">Definieren Sie einige Zeichenfolgen fester Länge als Zeichenfolgen mit variabler Länge, wie Zeichenfolgen mit fester Länge mehr Stapelspeicher als Zeichenfolgen variabler Länge verwendet.</span><span class="sxs-lookup"><span data-stu-id="47c5a-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="47c5a-112">Sie können auch die Zeichenfolge auf Modulebene definieren, in denen es keine Stapelspeicher erfordert.</span><span class="sxs-lookup"><span data-stu-id="47c5a-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5.  <span data-ttu-id="47c5a-113">Überprüfen Sie die Anzahl der geschachtelten `DoEvents` Funktionsaufrufe mithilfe der `Calls` im Dialogfeld anzeigen, welche Prozeduren auf dem Stapel aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="47c5a-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6.  <span data-ttu-id="47c5a-114">Stellen Sie sicher, dass Sie nicht "Ereigniskette" verursacht haben, durch das Auslösen eines Ereignisses, das eine Ereignisprozedur bereits auf dem Stapel aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="47c5a-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="47c5a-115">Eine Ereigniskette ist ein nicht abgeschlossenes rekursiven Prozeduraufruf ähnelt, jedoch ist weniger offensichtlich, da der Aufruf erfolgt [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] statt eines expliziten Aufrufs im Code.</span><span class="sxs-lookup"><span data-stu-id="47c5a-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] rather than an explicit call in the code.</span></span> <span data-ttu-id="47c5a-116">Verwenden der `Calls` im Dialogfeld anzeigen, welche Prozeduren auf dem Stapel aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="47c5a-116">Use the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47c5a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47c5a-117">See Also</span></span>  
 [<span data-ttu-id="47c5a-118">Fenster "Arbeitsspeicher"</span><span class="sxs-lookup"><span data-stu-id="47c5a-118">Memory Windows</span></span>](/visualstudio/debugger/memory-windows)
