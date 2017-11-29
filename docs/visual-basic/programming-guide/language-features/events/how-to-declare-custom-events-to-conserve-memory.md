---
title: 'Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eec9a2fc687f481ab40313e35cbde81c25b81ae8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="a81a3-102">Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a81a3-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="a81a3-103">Es gibt mehrere Situationen können, ist es wichtig, dass eine Anwendung die speicherauslastung gering halten.</span><span class="sxs-lookup"><span data-stu-id="a81a3-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="a81a3-104">Benutzerdefinierte Ereignisse können die Anwendung Speicher nur für die Ereignisse zu nutzen, die ihn verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a81a3-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="a81a3-105">Wenn eine Klasse ein Ereignis deklariert, reserviert der Compiler standardmäßig Speicher für ein Feld, um die Ereignisinformationen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a81a3-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="a81a3-106">Wenn eine Klasse viele nicht verwendete Ereignisse aufweist, beanspruchen diese unnötigerweise Speicher.</span><span class="sxs-lookup"><span data-stu-id="a81a3-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="a81a3-107">Statt die standardmäßige Implementierung von Ereignissen, die Visual Basic bietet können Sie benutzerdefinierte Ereignisse verwenden, um die Auslastung des Speichers mehr sorgfältig verwalten.</span><span class="sxs-lookup"><span data-stu-id="a81a3-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a81a3-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a81a3-108">Example</span></span>  
 <span data-ttu-id="a81a3-109">In diesem Beispiel verwendet die Klasse eine Instanz von der <xref:System.ComponentModel.EventHandlerList> Klasse, die gespeichert, der `Events` Feld zum Speichern von Informationen zu den Ereignissen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a81a3-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="a81a3-110">Die <xref:System.ComponentModel.EventHandlerList> -Klasse ist eine optimierte Listenklasse zum Speichern von Delegaten.</span><span class="sxs-lookup"><span data-stu-id="a81a3-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="a81a3-111">Alle Ereignisse in der Klasse verwenden die `Events` Feld zum Nachverfolgen von welche Methoden jedes Ereignis behandeln.</span><span class="sxs-lookup"><span data-stu-id="a81a3-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a81a3-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a81a3-112">See Also</span></span>  
 <xref:System.ComponentModel.EventHandlerList>  
 [<span data-ttu-id="a81a3-113">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="a81a3-113">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="a81a3-114">Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden</span><span class="sxs-lookup"><span data-stu-id="a81a3-114">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
