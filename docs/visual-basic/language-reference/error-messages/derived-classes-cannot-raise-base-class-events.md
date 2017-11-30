---
title: "Abgeleitete Klassen können keine Basisklassenereignisse auslösen."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords: BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 70dde8b96980adfd618e38b9ce142cdec56a6b13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="6cbec-102">Abgeleitete Klassen können keine Basisklassenereignisse auslösen.</span><span class="sxs-lookup"><span data-stu-id="6cbec-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="6cbec-103">Ein Ereignis kann nur vom Deklarationsabschnitt ausgelöst werden, in der sie deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="6cbec-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="6cbec-104">Aus diesem Grund kann keine Klasse von einer anderen Klasse, eine Auslösen von Ereignissen von der sie abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="6cbec-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="6cbec-105">**Fehler-ID:** BC30029</span><span class="sxs-lookup"><span data-stu-id="6cbec-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6cbec-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="6cbec-106">To correct this error</span></span>  
  
-   <span data-ttu-id="6cbec-107">Verschieben der `Event` Anweisung oder der `RaiseEvent` Anweisung, sodass sie sich in derselben Klasse befinden.</span><span class="sxs-lookup"><span data-stu-id="6cbec-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cbec-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6cbec-108">See Also</span></span>  
 [<span data-ttu-id="6cbec-109">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6cbec-109">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="6cbec-110">RaiseEvent-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6cbec-110">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
