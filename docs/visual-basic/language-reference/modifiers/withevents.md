---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords: WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 68a58fd130c04f2ed0cb1f2e5b9250f6c85f120d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="f2062-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f2062-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="f2062-103">Gibt an, dass eine oder mehrere deklarierten Member-Variablen mit einer Instanz einer Klasse verweisen, die Ereignisse auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="f2062-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2062-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f2062-104">Remarks</span></span>  
 <span data-ttu-id="f2062-105">Wenn eine Variable definiert ist mit `WithEvents`, können Sie deklarativ angeben, dass eine Methode Ereignisse der Variablen mit verarbeitet die `Handles` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="f2062-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="f2062-106">Sie können `WithEvents` nur auf Klassen-oder Modulebene.</span><span class="sxs-lookup"><span data-stu-id="f2062-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="f2062-107">Dies bedeutet, dass der Deklarationskontext für eine `WithEvents` Variable muss eine Klasse oder ein Modul sein und darf keine Quelldatei, Namespace, Struktur oder Prozedur.</span><span class="sxs-lookup"><span data-stu-id="f2062-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="f2062-108">Sie können keine `WithEvents` auf einen Member einer Struktur.</span><span class="sxs-lookup"><span data-stu-id="f2062-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="f2062-109">Sie können nur einzelne Variablen deklarieren – keine arrays – mit `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="f2062-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="f2062-110">Regeln</span><span class="sxs-lookup"><span data-stu-id="f2062-110">Rules</span></span>  
  
-   <span data-ttu-id="f2062-111">**Elementtypen.**</span><span class="sxs-lookup"><span data-stu-id="f2062-111">**Element Types.**</span></span> <span data-ttu-id="f2062-112">Sie müssen deklarieren `WithEvents` -Klasseninstanzen für Variablen Objektvariablen sein, damit sie akzeptieren können.</span><span class="sxs-lookup"><span data-stu-id="f2062-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="f2062-113">Allerdings kann nicht deklariert werden als `Object`.</span><span class="sxs-lookup"><span data-stu-id="f2062-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="f2062-114">Sie müssen diese als spezifische Klasse deklarieren, die die Ereignisse auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="f2062-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="f2062-115">Die `WithEvents` Modifizierer kann in diesem Kontext verwendet werden: [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="f2062-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2062-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2062-116">See Also</span></span>  
 [<span data-ttu-id="f2062-117">Handles</span><span class="sxs-lookup"><span data-stu-id="f2062-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="f2062-118">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f2062-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="f2062-119">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="f2062-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
