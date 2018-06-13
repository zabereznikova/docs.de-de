---
title: 'Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: d19c91d66e458ca2317dc049d517b92fa7406ef6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647180"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="c862e-102">Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c862e-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="c862e-103">Es gibt mehrere Situationen können, ist es wichtig, dass eine Anwendung die speicherauslastung gering halten.</span><span class="sxs-lookup"><span data-stu-id="c862e-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="c862e-104">Benutzerdefinierte Ereignisse können die Anwendung Speicher nur für die Ereignisse zu nutzen, die ihn verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="c862e-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="c862e-105">Wenn eine Klasse ein Ereignis deklariert, reserviert der Compiler standardmäßig Speicher für ein Feld, um die Ereignisinformationen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c862e-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="c862e-106">Wenn eine Klasse viele nicht verwendete Ereignisse aufweist, beanspruchen diese unnötigerweise Speicher.</span><span class="sxs-lookup"><span data-stu-id="c862e-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="c862e-107">Statt die standardmäßige Implementierung von Ereignissen, die Visual Basic bietet können Sie benutzerdefinierte Ereignisse verwenden, um die Auslastung des Speichers mehr sorgfältig verwalten.</span><span class="sxs-lookup"><span data-stu-id="c862e-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c862e-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c862e-108">Example</span></span>  
 <span data-ttu-id="c862e-109">In diesem Beispiel verwendet die Klasse eine Instanz von der <xref:System.ComponentModel.EventHandlerList> Klasse, die gespeichert, der `Events` Feld zum Speichern von Informationen zu den Ereignissen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c862e-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="c862e-110">Die <xref:System.ComponentModel.EventHandlerList> -Klasse ist eine optimierte Listenklasse zum Speichern von Delegaten.</span><span class="sxs-lookup"><span data-stu-id="c862e-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="c862e-111">Alle Ereignisse in der Klasse verwenden die `Events` Feld zum Nachverfolgen von welche Methoden jedes Ereignis behandeln.</span><span class="sxs-lookup"><span data-stu-id="c862e-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c862e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c862e-112">See Also</span></span>  
 <xref:System.ComponentModel.EventHandlerList>  
 [<span data-ttu-id="c862e-113">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="c862e-113">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="c862e-114">Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden</span><span class="sxs-lookup"><span data-stu-id="c862e-114">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
