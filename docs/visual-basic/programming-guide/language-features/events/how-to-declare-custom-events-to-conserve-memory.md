---
title: 'Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen zum Einsparen von Arbeitsspeicher'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring events [Visual Basic], custom
- events [Visual Basic], custom
- custom events [Visual Basic]
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
ms.openlocfilehash: 78934e3e5ae7d5a3f5867c99a9f1db760c65ecbf
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075121"
---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="12bb5-102">Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12bb5-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>

<span data-ttu-id="12bb5-103">Es gibt verschiedene Situationen, in denen es wichtig ist, dass eine Anwendung die Speicherauslastung niedrig hält.</span><span class="sxs-lookup"><span data-stu-id="12bb5-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="12bb5-104">Benutzerdefinierte Ereignisse ermöglichen es der Anwendung, Arbeitsspeicher nur für die Ereignisse zu verwenden, die Sie verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="12bb5-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="12bb5-105">Wenn eine Klasse ein Ereignis deklariert, ordnet der Compiler standardmäßig Speicher für ein Feld zu, um die Ereignis Informationen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="12bb5-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="12bb5-106">Wenn eine Klasse über viele nicht verwendete Ereignisse verfügt, nehmen Sie unnötigerweise Speicherplatz in Anspruch.</span><span class="sxs-lookup"><span data-stu-id="12bb5-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="12bb5-107">Anstatt die Standard Implementierung von Ereignissen zu verwenden, die Visual Basic bereitstellt, können Sie benutzerdefinierte Ereignisse verwenden, um die Speicherauslastung sorgfältiger zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="12bb5-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12bb5-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="12bb5-108">Example</span></span>  

 <span data-ttu-id="12bb5-109">In diesem Beispiel verwendet die-Klasse eine Instanz der- <xref:System.ComponentModel.EventHandlerList> Klasse, die im- `Events` Feld gespeichert ist, um Informationen über die verwendeten Ereignisse zu speichern.</span><span class="sxs-lookup"><span data-stu-id="12bb5-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="12bb5-110">Die- <xref:System.ComponentModel.EventHandlerList> Klasse ist eine optimierte Listen Klasse, die Delegaten enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="12bb5-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="12bb5-111">Alle Ereignisse in der-Klasse verwenden das- `Events` Feld, um nachzuverfolgen, welche Methoden die einzelnen Ereignisse verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="12bb5-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 [!code-vb[VbVbalrEvents#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#22)]  
  
## <a name="see-also"></a><span data-ttu-id="12bb5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12bb5-112">See also</span></span>

- <xref:System.ComponentModel.EventHandlerList>
- [<span data-ttu-id="12bb5-113">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="12bb5-113">Events</span></span>](index.md)
- [<span data-ttu-id="12bb5-114">Vorgehensweise: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden</span><span class="sxs-lookup"><span data-stu-id="12bb5-114">How to: Declare Custom Events To Avoid Blocking</span></span>](how-to-declare-custom-events-to-avoid-blocking.md)
