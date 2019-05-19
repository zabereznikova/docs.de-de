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
ms.openlocfilehash: e90e1d6643a30c1d2f4438e77317a2348b07fd71
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882424"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="b7ee7-102">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7ee7-102">Creating Event Handlers in Windows Forms</span></span>

<span data-ttu-id="b7ee7-103">Ein Ereignishandler stellt eine Prozedur in Ihrem Code dar, mit der festgelegt wird, welche Aktionen beim Eintreten eines bestimmten Ereignisses durchgeführt werden. Dies bezieht sich beispielsweise auf jene Fälle bei denen der Benutzer auf eine Schaltfläche klickt oder eine Meldungswarteschlange eine Meldung empfängt.</span><span class="sxs-lookup"><span data-stu-id="b7ee7-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="b7ee7-104">Wenn ein Ereignis ausgelöst wird, werden der Ereignishandler oder jene Handler ausgeführt, die das betreffende Ereignis empfangen.</span><span class="sxs-lookup"><span data-stu-id="b7ee7-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="b7ee7-105">Ereignisse lassen sich mehreren Handlern zuweisen. Außerdem können die Methoden, die besondere Ereignisse verwalten, dynamisch geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b7ee7-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="b7ee7-106">Sie können auch im Windows Forms-Designer in Visual Studio verwenden, um Ereignishandler zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7ee7-106">You can also use the Windows Forms Designer in Visual Studio to create event handlers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b7ee7-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b7ee7-107">In This Section</span></span>

 <span data-ttu-id="b7ee7-108">[Übersicht über Ereignisse](events-overview-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="b7ee7-108">[Events Overview](events-overview-windows-forms.md)\\</span></span>
 <span data-ttu-id="b7ee7-109">Erläutert das Ereignismodell und die Rolle der Delegaten.</span><span class="sxs-lookup"><span data-stu-id="b7ee7-109">Explains the event model and the role of delegates.</span></span>

 <span data-ttu-id="b7ee7-110">[Übersicht über Ereignishandler](event-handlers-overview-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="b7ee7-110">[Event Handlers Overview](event-handlers-overview-windows-forms.md)\\</span></span>
 <span data-ttu-id="b7ee7-111">Beschreibt, wie Ereignisse behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="b7ee7-111">Describes how to handle events.</span></span>

 <span data-ttu-id="b7ee7-112">[Vorgehensweise: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit](how-to-create-event-handlers-at-run-time-for-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="b7ee7-112">[How to: Create Event Handlers at Run Time for Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)\\</span></span>
 <span data-ttu-id="b7ee7-113">Gibt Richtungshinweise für eine dynamische Reaktion auf System- oder Benutzerereignisse an.</span><span class="sxs-lookup"><span data-stu-id="b7ee7-113">Gives directions for responding to system or user events dynamically.</span></span>

 <span data-ttu-id="b7ee7-114">[Vorgehensweise: Verbinden Sie mehrerer Ereignisse mit einem einzelnen Ereignishandler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="b7ee7-114">[How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)\\</span></span>
 <span data-ttu-id="b7ee7-115">Gibt Richtungshinweise zum Zuordnen derselben Funktionalität auf mehrere Steuerelemente bei Ereignissen an.</span><span class="sxs-lookup"><span data-stu-id="b7ee7-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>

 <span data-ttu-id="b7ee7-116">[Reihenfolge der Ereignisse in Windows Forms](order-of-events-in-windows-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="b7ee7-116">[Order of Events in Windows Forms](order-of-events-in-windows-forms.md)\\</span></span>
 <span data-ttu-id="b7ee7-117">Beschreibt die Reihenfolge, in der Ereignisse in den Windows Forms-Steuerelementen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="b7ee7-117">Describes the order in which events are raised in Windows Forms controls.</span></span>

 <span data-ttu-id="b7ee7-118">[Vorgehensweise: Erstellen von Ereignishandlern mithilfe der Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) wird beschrieben, wie der Windows Forms-Designer verwenden, um Ereignishandler zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b7ee7-118">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describes how to use the Windows Forms Designer to create event handlers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="b7ee7-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b7ee7-119">Related Sections</span></span>

 <span data-ttu-id="b7ee7-120">[Ereignisse](../../standard/events/index.md)\\</span><span class="sxs-lookup"><span data-stu-id="b7ee7-120">[Events](../../standard/events/index.md)\\</span></span>
 <span data-ttu-id="b7ee7-121">Enthält Links zu Themen bezüglich Behandlung und Auslösung von Ereignissen mit .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7ee7-121">Provides links to topics on handling and raising events using the .NET Framework.</span></span>

 <span data-ttu-id="b7ee7-122">[Problembehandlung für geerbte Ereignishandler in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)\\</span><span class="sxs-lookup"><span data-stu-id="b7ee7-122">[Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)\\</span></span>
 <span data-ttu-id="b7ee7-123">Listet häufige Probleme, die bei Ereignishandlern in vererbten Komponenten auftreten.</span><span class="sxs-lookup"><span data-stu-id="b7ee7-123">Lists common issues that occur with event handlers in inherited components.</span></span>
