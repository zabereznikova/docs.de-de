---
title: WithEvents (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.WithEvents
- WithEvents
dev_langs:
- VB
helpviewer_keywords:
- WithEvents keyword
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: 17
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
ms.openlocfilehash: b956f8f0d6f0a2fd9f41c5df6d6c82b43fa09018
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="withevents-visual-basic"></a><span data-ttu-id="fd968-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd968-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="fd968-103">Gibt an, dass eine oder mehrere Membervariablen auf eine Instanz einer Klasse verweisen, die Ereignisse auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="fd968-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd968-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd968-104">Remarks</span></span>  
 <span data-ttu-id="fd968-105">Wenn eine Variable mit definiert wird `WithEvents`, können Sie deklarativ angeben, dass eine Methode die Ereignisse der Variablen mit behandelt die `Handles` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="fd968-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="fd968-106">Sie können `WithEvents` nur auf Klassen-oder Modulebene.</span><span class="sxs-lookup"><span data-stu-id="fd968-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="fd968-107">Dies bedeutet, dass der Deklarationskontext für eine `WithEvents` Variable muss eine Klasse oder ein Modul und eine Quelldatei, Namespace, Struktur oder Prozedur nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="fd968-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="fd968-108">Sie können keine `WithEvents` auf einen Member einer Struktur.</span><span class="sxs-lookup"><span data-stu-id="fd968-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="fd968-109">Sie können nur einzelne Variablen deklarieren, keine arrays – mit `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="fd968-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="fd968-110">Regeln</span><span class="sxs-lookup"><span data-stu-id="fd968-110">Rules</span></span>  
  
-   <span data-ttu-id="fd968-111">**Elementtypen.**</span><span class="sxs-lookup"><span data-stu-id="fd968-111">**Element Types.**</span></span> <span data-ttu-id="fd968-112">Deklarieren Sie `WithEvents` Variablen als Objektvariablen, damit sie akzeptieren können Klasseninstanzen.</span><span class="sxs-lookup"><span data-stu-id="fd968-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="fd968-113">Jedoch nicht Sie deklarieren diese als `Object`.</span><span class="sxs-lookup"><span data-stu-id="fd968-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="fd968-114">Sie müssen diese als spezifische Klasse deklarieren, die Ereignisse auslösen kann.</span><span class="sxs-lookup"><span data-stu-id="fd968-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="fd968-115">Die `WithEvents` Modifizierer kann in diesem Kontext verwendet werden: [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="fd968-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd968-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd968-116">See Also</span></span>  
 <span data-ttu-id="fd968-117">[Handles](../../../visual-basic/language-reference/statements/handles-clause.md) </span><span class="sxs-lookup"><span data-stu-id="fd968-117">[Handles](../../../visual-basic/language-reference/statements/handles-clause.md) </span></span>  
<span data-ttu-id="fd968-118"> [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="fd968-118"> [Keywords](../../../visual-basic/language-reference/keywords/index.md) </span></span>  
<span data-ttu-id="fd968-119"> [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="fd968-119"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
