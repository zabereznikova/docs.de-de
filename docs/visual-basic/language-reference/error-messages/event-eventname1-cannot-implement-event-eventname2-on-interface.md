---
title: Ereignis &#39; &lt;ereignisname1&gt; &#39; kann Ereignis nicht implementieren, &#39; &lt;ereignisname2&gt; &#39; Schnittstelle &#39; &lt;Schnittstelle&gt; &#39; da Ihre Delegattypen &#39; &lt;delegate1&gt; &#39; und &#39; &lt;delegate2&gt; &#39; stimmen nicht überein
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 41f5984458eb17db04f20b292a0d80783093dcb4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="event-39lteventname1gt39-cannot-implement-event-39lteventname2gt39-on-interface-39ltinterfacegt39-because-their-delegate-types-39ltdelegate1gt39-and-39ltdelegate2gt39-do-not-match"></a><span data-ttu-id="af90b-102">Ereignis &#39; &lt;ereignisname1&gt; &#39; kann Ereignis nicht implementieren, &#39; &lt;ereignisname2&gt; &#39; Schnittstelle &#39; &lt;Schnittstelle&gt; &#39; da Ihre Delegattypen &#39; &lt;delegate1&gt; &#39; und &#39; &lt;delegate2&gt; &#39; stimmen nicht überein</span><span class="sxs-lookup"><span data-stu-id="af90b-102">Event &#39;&lt;eventname1&gt;&#39; cannot implement event &#39;&lt;eventname2&gt;&#39; on interface &#39;&lt;interface&gt;&#39; because their delegate types &#39;&lt;delegate1&gt;&#39; and &#39;&lt;delegate2&gt;&#39; do not match</span></span>
<span data-ttu-id="af90b-103">Visual Basic kann kein Ereignis implementiert werden, weil der Delegattyp des Ereignisses nicht mit den Delegattyp des Ereignisses in der Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="af90b-103">Visual Basic cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="af90b-104">Dieser Fehler kann auftreten, wenn Sie mehrere Ereignisse in einer Schnittstelle definieren und anschließend versuchen, sie mit demselben Ereignis zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="af90b-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="af90b-105">Ein Ereignis kann zwei oder mehrere Ereignisse nur implementieren, wenn alle implementierten Ereignisse mit der `As` -Syntax deklariert werden und denselben Delegattyp angeben.</span><span class="sxs-lookup"><span data-stu-id="af90b-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="af90b-106">**Fehler-ID:** BC31423</span><span class="sxs-lookup"><span data-stu-id="af90b-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="af90b-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="af90b-107">To correct this error</span></span>  
  
-   <span data-ttu-id="af90b-108">Implementieren Sie die Ereignisse separat.</span><span class="sxs-lookup"><span data-stu-id="af90b-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="af90b-109">– oder –</span><span class="sxs-lookup"><span data-stu-id="af90b-109">—or—</span></span>  
  
-   <span data-ttu-id="af90b-110">Definieren Sie die Ereignisse in der Schnittstelle mithilfe der `As` Syntax und den gleichen Delegattyp angeben.</span><span class="sxs-lookup"><span data-stu-id="af90b-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af90b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af90b-111">See Also</span></span>  
 [<span data-ttu-id="af90b-112">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="af90b-112">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
 [<span data-ttu-id="af90b-113">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="af90b-113">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="af90b-114">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="af90b-114">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
