---
title: "Ereignisse freigegebener WithEvents-Variablen können nicht von freigegebenen Methoden behandelt werden."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords: BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53372927b88df3946583564492df42170f302739
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a><span data-ttu-id="c8e97-102">Ereignisse freigegebener WithEvents-Variablen können nicht von freigegebenen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="c8e97-102">Events of shared WithEvents variables cannot be handled by non-shared methods</span></span>
<span data-ttu-id="c8e97-103">Eine Variable mit dem `Shared` Modifizierer ist eine freigegebene Variable.</span><span class="sxs-lookup"><span data-stu-id="c8e97-103">A variable declared with the `Shared` modifier is a shared variable.</span></span> <span data-ttu-id="c8e97-104">Eine freigegebene Variable gibt genau einen Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="c8e97-104">A shared variable identifies exactly one storage location.</span></span> <span data-ttu-id="c8e97-105">Eine Variable mit dem `WithEvents` Modifizierer bestätigt, dass der Typ, der die Variable angehört, den Satz von Ereignissen verarbeitet die Variable löst.</span><span class="sxs-lookup"><span data-stu-id="c8e97-105">A variable declared with the `WithEvents` modifier asserts that the type to which the variable belongs handles the set of events the variable raises.</span></span> <span data-ttu-id="c8e97-106">Wenn die Variable ein Wert zugewiesen wird, wird die Eigenschaft erstellt, indem die `WithEvents` Deklaration hebt alle vorhandenen Ereignishandler und verknüpft die neuen Ereignishandler über die `Add` Methode.</span><span class="sxs-lookup"><span data-stu-id="c8e97-106">When a value is assigned to the variable, the property created by the `WithEvents` declaration unhooks any existing event handler and hooks up the new event handler via the `Add` method.</span></span>  
  
 <span data-ttu-id="c8e97-107">**Fehler-ID:** BC30594</span><span class="sxs-lookup"><span data-stu-id="c8e97-107">**Error ID:** BC30594</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c8e97-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c8e97-108">To correct this error</span></span>  
  
-   <span data-ttu-id="c8e97-109">Deklarieren Sie den Ereignishandler `Shared`.</span><span class="sxs-lookup"><span data-stu-id="c8e97-109">Declare your event handler `Shared`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8e97-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8e97-110">See Also</span></span>  
 [<span data-ttu-id="c8e97-111">Shared</span><span class="sxs-lookup"><span data-stu-id="c8e97-111">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="c8e97-112">WithEvents</span><span class="sxs-lookup"><span data-stu-id="c8e97-112">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
