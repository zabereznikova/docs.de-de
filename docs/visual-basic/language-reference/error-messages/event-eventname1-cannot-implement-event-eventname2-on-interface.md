---
title: "Ereignis &quot;&lt;eventname1&gt;&quot;kann nicht implementieren Ereignis&quot;&lt;eventname2&gt;&quot;auf der Schnittstelle&quot;&lt;Schnittstelle&gt;&quot; da ihre Delegattypen&lt;delegate1&gt;&quot;und&quot;&lt;delegate2&gt;&quot; stimmen nicht überein | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31423
- bc31423
dev_langs:
- VB
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
caps.latest.revision: 6
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
ms.openlocfilehash: 340547d3673b651e988a6c1167bf7043360b04e4
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="event-39lteventname1gt39-cannot-implement-event-39lteventname2gt39-on-interface-39ltinterfacegt39-because-their-delegate-types-39ltdelegate1gt39-and-39ltdelegate2gt39-do-not-match"></a><span data-ttu-id="282b8-102">Ereignis "&lt;eventname1&gt;"kann nicht implementieren Ereignis"&lt;eventname2&gt;"auf der Schnittstelle"&lt;Schnittstelle&gt;' da ihre Delegattypen&lt;delegate1&gt;"und"&lt;delegate2&gt;' stimmen nicht überein</span><span class="sxs-lookup"><span data-stu-id="282b8-102">Event &#39;&lt;eventname1&gt;&#39; cannot implement event &#39;&lt;eventname2&gt;&#39; on interface &#39;&lt;interface&gt;&#39; because their delegate types &#39;&lt;delegate1&gt;&#39; and &#39;&lt;delegate2&gt;&#39; do not match</span></span>
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="282b8-103">kann ein Ereignis nicht implementieren, da der Delegattyp des Ereignisses nicht dem Typ des Ereignisses in der Schnittstelle des Delegaten übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="282b8-103"> cannot implement an event because the delegate type of the event does not match the delegate type of the event in the interface.</span></span> <span data-ttu-id="282b8-104">Dieser Fehler kann auftreten, wenn Sie mehrere Ereignisse in einer Schnittstelle definieren und anschließend versuchen, sie mit demselben Ereignis zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="282b8-104">This error can occur when you define multiple events in an interface and then attempt to implement them together with the same event.</span></span> <span data-ttu-id="282b8-105">Ein Ereignis kann zwei oder mehrere Ereignisse nur implementieren, wenn alle implementierten Ereignisse mit der `As` -Syntax deklariert werden und denselben Delegattyp angeben.</span><span class="sxs-lookup"><span data-stu-id="282b8-105">An event can implement two or more events only if all implemented events are declared using the `As` syntax and specify the same delegate type.</span></span>  
  
 <span data-ttu-id="282b8-106">**Fehler-ID:** BC31423</span><span class="sxs-lookup"><span data-stu-id="282b8-106">**Error ID:** BC31423</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="282b8-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="282b8-107">To correct this error</span></span>  
  
-   <span data-ttu-id="282b8-108">Implementieren Sie die Ereignisse separat.</span><span class="sxs-lookup"><span data-stu-id="282b8-108">Implement the events separately.</span></span>  
  
     <span data-ttu-id="282b8-109">– oder –</span><span class="sxs-lookup"><span data-stu-id="282b8-109">—or—</span></span>  
  
-   <span data-ttu-id="282b8-110">Definieren Sie die Ereignisse in der Schnittstelle mithilfe der `As` Syntax und den gleichen Delegattyp angeben.</span><span class="sxs-lookup"><span data-stu-id="282b8-110">Define the events in the interface using the `As` syntax and specify the same delegate type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="282b8-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="282b8-111">See Also</span></span>  
 <span data-ttu-id="282b8-112">[Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="282b8-112">[Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="282b8-113"> [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="282b8-113"> [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="282b8-114"> [Ereignisse](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="282b8-114"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
