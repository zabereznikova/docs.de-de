---
title: 'Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen zum Einsparen von Arbeitsspeicher (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: e4132f51f4dd85ad964042d05f7c5bc0a2e6e3cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973159"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="ade90-102">Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen zum Einsparen von Arbeitsspeicher (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ade90-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="ade90-103">Es gibt verschiedenen Fällen beim ist es wichtig, dass eine Anwendung die arbeitsspeicherauslastung gering halten.</span><span class="sxs-lookup"><span data-stu-id="ade90-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="ade90-104">Benutzerdefinierte Ereignisse ermöglichen die Anwendung zur Verwendung von Speicher nur für die Ereignisse, die ihn verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="ade90-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="ade90-105">Wenn eine Klasse ein Ereignis deklariert, weist der Compiler standardmäßig Speicher für ein Feld aus, um die Ereignisinformationen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ade90-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="ade90-106">Verfügt eine Klasse über viele nicht verwendeten Ereignisse, beanspruchen diese unnötigerweise Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="ade90-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="ade90-107">Statt die standardmäßige Implementierung von Ereignissen, die Visual Basic bietet, können Sie benutzerdefinierte Ereignisse genau die speicherauslastung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="ade90-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ade90-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ade90-108">Example</span></span>  
 <span data-ttu-id="ade90-109">In diesem Beispiel verwendet die Klasse eine Instanz der dem <xref:System.ComponentModel.EventHandlerList> Klasse, die gespeichert, der `Events` Feld zum Speichern von Informationen zu den Ereignissen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ade90-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="ade90-110">Die <xref:System.ComponentModel.EventHandlerList> -Klasse ist eine optimierte Listenklasse zum Speichern von Delegaten.</span><span class="sxs-lookup"><span data-stu-id="ade90-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="ade90-111">Alle Ereignisse in der Klasse verwenden die `Events` Feld zum Nachverfolgen jedes Ereignis welche Methoden behandeln.</span><span class="sxs-lookup"><span data-stu-id="ade90-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a><span data-ttu-id="ade90-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ade90-112">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList>
- [<span data-ttu-id="ade90-113">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="ade90-113">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [<span data-ttu-id="ade90-114">Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen, um die Blockierung zu vermeiden</span><span class="sxs-lookup"><span data-stu-id="ade90-114">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)
