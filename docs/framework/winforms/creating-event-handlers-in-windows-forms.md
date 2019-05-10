---
title: Erstellen von Ereignishandlern in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- event handling [Windows Forms]
- Windows Forms controls, event handling
- Windows Forms, event handling
- events [Windows Forms], event handlers
- event handlers [Windows Forms]
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
ms.openlocfilehash: 329060e0c53178a9320be9a7cdff492d69917782
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211244"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="e21fb-102">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e21fb-102">Creating Event Handlers in Windows Forms</span></span>

<span data-ttu-id="e21fb-103">Ein Ereignishandler stellt eine Prozedur in Ihrem Code dar, mit der festgelegt wird, welche Aktionen beim Eintreten eines bestimmten Ereignisses durchgeführt werden. Dies bezieht sich beispielsweise auf jene Fälle bei denen der Benutzer auf eine Schaltfläche klickt oder eine Meldungswarteschlange eine Meldung empfängt.</span><span class="sxs-lookup"><span data-stu-id="e21fb-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="e21fb-104">Wenn ein Ereignis ausgelöst wird, werden der Ereignishandler oder jene Handler ausgeführt, die das betreffende Ereignis empfangen.</span><span class="sxs-lookup"><span data-stu-id="e21fb-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="e21fb-105">Ereignisse lassen sich mehreren Handlern zuweisen. Außerdem können die Methoden, die besondere Ereignisse verwalten, dynamisch geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e21fb-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="e21fb-106">Sie können auch im Windows Forms-Designer in Visual Studio verwenden, um Ereignishandler zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e21fb-106">You can also use the Windows Forms Designer in Visual Studio to create event handlers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e21fb-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e21fb-107">In This Section</span></span>

 <span data-ttu-id="e21fb-108">[Übersicht über Ereignisse](events-overview-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="e21fb-108">[Events Overview](events-overview-windows-forms.md)\\</span></span>
 <span data-ttu-id="e21fb-109">Erläutert das Ereignismodell und die Rolle der Delegaten.</span><span class="sxs-lookup"><span data-stu-id="e21fb-109">Explains the event model and the role of delegates.</span></span>

 <span data-ttu-id="e21fb-110">[Übersicht über Ereignishandler](event-handlers-overview-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="e21fb-110">[Event Handlers Overview](event-handlers-overview-windows-forms.md)\\</span></span>
 <span data-ttu-id="e21fb-111">Beschreibt, wie Ereignisse behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e21fb-111">Describes how to handle events.</span></span>

 <span data-ttu-id="e21fb-112">[Vorgehensweise: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit](how-to-create-event-handlers-at-run-time-for-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="e21fb-112">[How to: Create Event Handlers at Run Time for Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)\\</span></span>
 <span data-ttu-id="e21fb-113">Gibt Richtungshinweise für eine dynamische Reaktion auf System- oder Benutzerereignisse an.</span><span class="sxs-lookup"><span data-stu-id="e21fb-113">Gives directions for responding to system or user events dynamically.</span></span>

 <span data-ttu-id="e21fb-114">[Vorgehensweise: Verbinden Sie mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="e21fb-114">[How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)\\</span></span>
 <span data-ttu-id="e21fb-115">Gibt Richtungshinweise zum Zuordnen derselben Funktionalität auf mehrere Steuerelemente bei Ereignissen an.</span><span class="sxs-lookup"><span data-stu-id="e21fb-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>

 <span data-ttu-id="e21fb-116">[Reihenfolge der Ereignisse in Windows Forms](order-of-events-in-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="e21fb-116">[Order of Events in Windows Forms](order-of-events-in-windows-forms.md)\\</span></span>
 <span data-ttu-id="e21fb-117">Beschreibt die Reihenfolge, in der Ereignisse in den Windows Forms-Steuerelementen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e21fb-117">Describes the order in which events are raised in Windows Forms controls.</span></span>

 <span data-ttu-id="e21fb-118">[Vorgehensweise: Erstellen von Ereignishandlern mithilfe der Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) wird beschrieben, wie der Windows Forms-Designer verwenden, um Ereignishandler zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e21fb-118">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describes how to use the Windows Forms Designer to create event handlers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="e21fb-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="e21fb-119">Related Sections</span></span>

 <span data-ttu-id="e21fb-120">[Ereignisse](../../standard/events/index.md)\\</span><span class="sxs-lookup"><span data-stu-id="e21fb-120">[Events](../../standard/events/index.md)\\</span></span>
 <span data-ttu-id="e21fb-121">Enthält Links zu Themen bezüglich Behandlung und Auslösung von Ereignissen mit der [!INCLUDE [dnprdnshort](../../../includes/dnprdnshort-md.md)\].</span><span class="sxs-lookup"><span data-stu-id="e21fb-121">Provides links to topics on handling and raising events using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)\].</span></span>

 <span data-ttu-id="e21fb-122">[Problembehandlung für geerbte Ereignishandler in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)\\</span><span class="sxs-lookup"><span data-stu-id="e21fb-122">[Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)\\</span></span>
 <span data-ttu-id="e21fb-123">Listet häufige Probleme, die bei Ereignishandlern in vererbten Komponenten auftreten.</span><span class="sxs-lookup"><span data-stu-id="e21fb-123">Lists common issues that occur with event handlers in inherited components.</span></span>
