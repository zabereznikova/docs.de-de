---
title: "Nicht genügend Stapelspeicher (Visual Basic) | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID28
dev_langs:
- VB
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 256ef0c7fcb3632e0c13d12737d438225343884f
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="d5517-102">Nicht genügend Stapelspeicher (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5517-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="d5517-103">Der Stapel ist ein Arbeitsbereich des Arbeitsspeichers, der vergrößert bzw. verkleinert dynamisch mit der Auslastung des ausgeführten Programms an.</span><span class="sxs-lookup"><span data-stu-id="d5517-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="d5517-104">Die Grenzen wurden überschritten.</span><span class="sxs-lookup"><span data-stu-id="d5517-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d5517-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d5517-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="d5517-106">Überprüfen Sie, dass Prozeduren nicht zu tief geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="d5517-106">Check that procedures are not nested too deeply.</span></span>  
  
2.  <span data-ttu-id="d5517-107">Stellen Sie sicher, dass rekursive Prozeduren ordnungsgemäß zu beenden.</span><span class="sxs-lookup"><span data-stu-id="d5517-107">Make sure recursive procedures terminate properly.</span></span>  
  
3.  <span data-ttu-id="d5517-108">Wenn lokale Variablen mehr Speicherplatz als erforderlich ist, versuchen Sie, einige Variablen auf Modulebene zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="d5517-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="d5517-109">Sie können alle Variablen in der Prozedur auch statische deklarieren, indem Sie vor der `Property`, `Sub`, oder `Function` Schlüsselwort mit `Static`.</span><span class="sxs-lookup"><span data-stu-id="d5517-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="d5517-110">Sie können auch die `Static` Anweisung, um einzelne statische Variablen innerhalb von Prozeduren zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="d5517-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4.  <span data-ttu-id="d5517-111">Definieren Sie einige Zeichenfolgen fester Länge als Zeichenfolgen variabler Länge, wie Zeichenfolgen mit fester Länge als Zeichenfolgen variabler Länge mehr Stapelspeicher verwenden.</span><span class="sxs-lookup"><span data-stu-id="d5517-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="d5517-112">Sie können auch die Zeichenfolge auf Modulebene definieren, in denen es keine Stapelspeicher erfordert.</span><span class="sxs-lookup"><span data-stu-id="d5517-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5.  <span data-ttu-id="d5517-113">Überprüfen Sie die Anzahl der geschachtelten `DoEvents` Funktionsaufrufe, mithilfe der `Calls` Dialogfeld, welche Prozeduren aktiv auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="d5517-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6.  <span data-ttu-id="d5517-114">Stellen Sie sicher, dass Sie nicht "Ereignisfolge" durch das Auslösen eines Ereignisses, das eine Ereignisprozedur bereits auf dem Stapel aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d5517-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="d5517-115">Eine Ereigniskette ist mit einem nicht abgeschlossenen rekursiven Prozeduraufruf, aber es ist weniger offensichtlich, da der Aufruf erfolgt [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] anstatt explizit im Code.</span><span class="sxs-lookup"><span data-stu-id="d5517-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] rather than an explicit call in the code.</span></span> <span data-ttu-id="d5517-116">Verwenden der `Calls`Dialogfeld, welche Prozeduren aktiv auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="d5517-116">Use the `Calls`dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5517-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5517-117">See Also</span></span>  
 [<span data-ttu-id="d5517-118">Fenster "Arbeitsspeicher"</span><span class="sxs-lookup"><span data-stu-id="d5517-118">Memory Windows</span></span>](https://docs.microsoft.com/visualstudio/debugger/memory-windows)
