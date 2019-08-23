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
ms.openlocfilehash: 6b1d146dfd9d51641bc9eb5d8be4cd2508c223a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963477"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="d361b-102">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d361b-102">Creating Event Handlers in Windows Forms</span></span>

<span data-ttu-id="d361b-103">Ein Ereignishandler stellt eine Prozedur in Ihrem Code dar, mit der festgelegt wird, welche Aktionen beim Eintreten eines bestimmten Ereignisses durchgeführt werden. Dies bezieht sich beispielsweise auf jene Fälle bei denen der Benutzer auf eine Schaltfläche klickt oder eine Meldungswarteschlange eine Meldung empfängt.</span><span class="sxs-lookup"><span data-stu-id="d361b-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="d361b-104">Wenn ein Ereignis ausgelöst wird, werden der Ereignishandler oder jene Handler ausgeführt, die das betreffende Ereignis empfangen.</span><span class="sxs-lookup"><span data-stu-id="d361b-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="d361b-105">Ereignisse lassen sich mehreren Handlern zuweisen. Außerdem können die Methoden, die besondere Ereignisse verwalten, dynamisch geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d361b-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="d361b-106">Sie können auch die Windows Forms-Designer in Visual Studio verwenden, um Ereignishandler zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d361b-106">You can also use the Windows Forms Designer in Visual Studio to create event handlers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d361b-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d361b-107">In This Section</span></span>

 <span data-ttu-id="d361b-108">[Übersicht über Ereignisse](events-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="d361b-108">[Events Overview](events-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="d361b-109">Erläutert das Ereignismodell und die Rolle der Delegaten.</span><span class="sxs-lookup"><span data-stu-id="d361b-109">Explains the event model and the role of delegates.</span></span>

 <span data-ttu-id="d361b-110">[Übersicht über Ereignishandler](event-handlers-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="d361b-110">[Event Handlers Overview](event-handlers-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="d361b-111">Beschreibt, wie Ereignisse behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="d361b-111">Describes how to handle events.</span></span>

 <span data-ttu-id="d361b-112">[Vorgehensweise: Erstellen von Ereignis Handlern zur Laufzeit für Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="d361b-112">[How to: Create Event Handlers at Run Time for Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span></span>\
 <span data-ttu-id="d361b-113">Gibt Richtungshinweise für eine dynamische Reaktion auf System- oder Benutzerereignisse an.</span><span class="sxs-lookup"><span data-stu-id="d361b-113">Gives directions for responding to system or user events dynamically.</span></span>

 <span data-ttu-id="d361b-114">[Vorgehensweise: Verbinden mehrerer Ereignisse mit einem einzelnen Ereignis Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="d361b-114">[How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span></span>\
 <span data-ttu-id="d361b-115">Gibt Richtungshinweise zum Zuordnen derselben Funktionalität auf mehrere Steuerelemente bei Ereignissen an.</span><span class="sxs-lookup"><span data-stu-id="d361b-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>

 <span data-ttu-id="d361b-116">[Reihenfolge der Ereignisse in Windows Forms](order-of-events-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="d361b-116">[Order of Events in Windows Forms](order-of-events-in-windows-forms.md)</span></span>\
 <span data-ttu-id="d361b-117">Beschreibt die Reihenfolge, in der Ereignisse in den Windows Forms-Steuerelementen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="d361b-117">Describes the order in which events are raised in Windows Forms controls.</span></span>

 <span data-ttu-id="d361b-118">[Vorgehensweise: Erstellen von Ereignis Handlern mithilfe des](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Designers wird beschrieben, wie die Windows Forms-Designer zum Erstellen von Ereignis Handlern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d361b-118">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describes how to use the Windows Forms Designer to create event handlers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="d361b-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d361b-119">Related Sections</span></span>

 <span data-ttu-id="d361b-120">[Ereignisse](../../standard/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="d361b-120">[Events](../../standard/events/index.md)</span></span>\
 <span data-ttu-id="d361b-121">Enthält Links zu Themen über das behandeln und Auswerfen von Ereignissen mithilfe der .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d361b-121">Provides links to topics on handling and raising events using the .NET Framework.</span></span>

 <span data-ttu-id="d361b-122">[Problembehandlung für geerbte Ereignishandler in Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span><span class="sxs-lookup"><span data-stu-id="d361b-122">[Troubleshooting Inherited Event Handlers in Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span></span>\
 <span data-ttu-id="d361b-123">Listet häufige Probleme, die bei Ereignishandlern in vererbten Komponenten auftreten.</span><span class="sxs-lookup"><span data-stu-id="d361b-123">Lists common issues that occur with event handlers in inherited components.</span></span>
