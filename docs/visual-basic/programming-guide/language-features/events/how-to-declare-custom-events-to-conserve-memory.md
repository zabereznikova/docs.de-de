---
title: 'Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declaring events, custom
- events [Visual Basic], custom
- custom events
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: 11
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
ms.openlocfilehash: 130cbda875d6a56f826aefea341d233ea4b3731d
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="how-to-declare-custom-events-to-conserve-memory-visual-basic"></a><span data-ttu-id="b62b8-102">Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b62b8-102">How to: Declare Custom Events To Conserve Memory (Visual Basic)</span></span>
<span data-ttu-id="b62b8-103">Es gibt mehrere Situationen, wenn es wichtig ist, dass eine Anwendung die Speicherverwendung gering halten.</span><span class="sxs-lookup"><span data-stu-id="b62b8-103">There are several circumstances when it is important that an application keep its memory usage low.</span></span> <span data-ttu-id="b62b8-104">Benutzerdefinierte Ereignisse ermöglichen die Anwendung Speicher nur für die Ereignisse verwenden, die sie behandelt.</span><span class="sxs-lookup"><span data-stu-id="b62b8-104">Custom events allow the application to use memory only for the events that it handles.</span></span>  
  
 <span data-ttu-id="b62b8-105">Wenn eine Klasse ein Ereignis deklariert, reserviert der Compiler standardmäßig Speicher für ein Feld zum Speichern von Informationen für das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b62b8-105">By default, when a class declares an event, the compiler allocates memory for a field to store the event information.</span></span> <span data-ttu-id="b62b8-106">Wenn eine Klasse viele nicht verwendete Ereignisse aufweist, beanspruchen diese unnötigerweise Speicher.</span><span class="sxs-lookup"><span data-stu-id="b62b8-106">If a class has many unused events, they needlessly take up memory.</span></span>  
  
 <span data-ttu-id="b62b8-107">Statt die standardmäßige Implementierung der Ereignisse, die Visual Basic bietet, können Sie benutzerdefinierte Ereignisse die Speicherverwendung sorgfältiger verwalten.</span><span class="sxs-lookup"><span data-stu-id="b62b8-107">Instead of using the default implementation of events that Visual Basic provides, you can use custom events to manage the memory usage more carefully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b62b8-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b62b8-108">Example</span></span>  
 <span data-ttu-id="b62b8-109">In diesem Beispiel verwendet die Klasse eine Instanz der <xref:System.ComponentModel.EventHandlerList>Klasse, die in gespeicherten der `Events` Feld zum Speichern von Informationen zu den Ereignissen verwendet.</xref:System.ComponentModel.EventHandlerList></span><span class="sxs-lookup"><span data-stu-id="b62b8-109">In this example, the class uses one instance of the <xref:System.ComponentModel.EventHandlerList> class, stored in the `Events` field, to store information about the events in use.</span></span> <span data-ttu-id="b62b8-110">Die <xref:System.ComponentModel.EventHandlerList>-Klasse ist eine optimierte Listenklasse zum Speichern von Delegaten.</xref:System.ComponentModel.EventHandlerList></span><span class="sxs-lookup"><span data-stu-id="b62b8-110">The <xref:System.ComponentModel.EventHandlerList> class is an optimized list class designed to hold delegates.</span></span>  
  
 <span data-ttu-id="b62b8-111">Alle Ereignisse in der Klasse verwenden das `Events` Feld zum Nachverfolgen von welche Methoden jedes Ereignis behandeln.</span><span class="sxs-lookup"><span data-stu-id="b62b8-111">All events in the class use the `Events` field to keep track of what methods are handling each event.</span></span>  
  
 <span data-ttu-id="b62b8-112">[!code-vb[VbVbalrEvents&#22;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b62b8-112">[!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b62b8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b62b8-113">See Also</span></span>  
 <span data-ttu-id="b62b8-114"><xref:System.ComponentModel.EventHandlerList></xref:System.ComponentModel.EventHandlerList></span><span class="sxs-lookup"><span data-stu-id="b62b8-114"><xref:System.ComponentModel.EventHandlerList></span></span>   
<span data-ttu-id="b62b8-115"> [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="b62b8-115"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="b62b8-116"> [Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um eine Blockierung zu vermeiden](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="b62b8-116"> [How to: Declare Custom Events To Avoid Blocking](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)</span></span>
