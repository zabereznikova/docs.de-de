---
title: "Gewusst wie: Hinzufügen einer Klassenbehandlung für ein Routingereignis"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abbbdce0ca12c4d8bdd12f616bf49c3d6f66f441
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a><span data-ttu-id="61557-102">Gewusst wie: Hinzufügen einer Klassenbehandlung für ein Routingereignis</span><span class="sxs-lookup"><span data-stu-id="61557-102">How to: Add Class Handling for a Routed Event</span></span>
<span data-ttu-id="61557-103">Routingereignisse können entweder durch die Klasse oder Instanzhandler auf einen beliebigen Knoten in der Route behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="61557-103">Routed events can be handled either by class handlers or instance handlers on any given node in the route.</span></span> <span data-ttu-id="61557-104">Klassenhandler werden zuerst aufgerufen und können von Klasse-Implementierungen verwendet werden, um Ereignisse aus der Instanz Behandlung zu unterdrücken, oder dass Sie andere Ereignis spezifische Verhalten auf Ereignisse, die im Besitz von Basisklassen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="61557-104">Class handlers are invoked first, and can be used by class implementations to suppress events from instance handling or introduce other event specific behaviors on events that are owned by base classes.</span></span> <span data-ttu-id="61557-105">Dieses Beispiel veranschaulicht zwei eng verwandte Techniken zum Implementieren von Klassenhandler.</span><span class="sxs-lookup"><span data-stu-id="61557-105">This example illustrates two closely related techniques for implementing class handlers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61557-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="61557-106">Example</span></span>  
 <span data-ttu-id="61557-107">Dieses Beispiel verwendet eine benutzerdefinierte Klasse, die auf der Grundlage der <xref:System.Windows.Controls.Canvas> Bereich.</span><span class="sxs-lookup"><span data-stu-id="61557-107">This example uses a custom class based on the <xref:System.Windows.Controls.Canvas> panel.</span></span> <span data-ttu-id="61557-108">Die grundlegende Prämisse der Anwendung ist, dass die benutzerdefinierte Klasse Verhaltensweisen auf seine untergeordneten Elemente einschließlich abfangen, die linken Maustaste drückt, und behandelt führt, bevor die Klasse des untergeordneten Elements oder beliebige Instanzhandler aufgerufen werden, markieren.</span><span class="sxs-lookup"><span data-stu-id="61557-108">The basic premise of the application is that the custom class introduces behaviors on its child elements, including intercepting any left mouse button clicks and marking them handled, before the child element class or any instance handlers on it will be invoked.</span></span>  
  
 <span data-ttu-id="61557-109">Die <xref:System.Windows.UIElement> Klasse bereitstellt, eine virtuelle Methode, die ermöglicht eine Klassenbehandlung für das <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> Ereignis, indem das Ereignis einfach überschrieben.</span><span class="sxs-lookup"><span data-stu-id="61557-109">The <xref:System.Windows.UIElement> class exposes a virtual method that enables class handling on the <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> event, by simply overriding the event.</span></span> <span data-ttu-id="61557-110">Dies ist die einfachste Methode zum Klassenbehandlung implementieren, wenn eine solche virtuelle Methode an einer beliebigen Stelle in der Klassenhierarchie verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="61557-110">This is the simplest way to implement class handling if such a virtual method is available somewhere in your class' hierarchy.</span></span> <span data-ttu-id="61557-111">Der folgende code zeigt die <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> Implementierung in "MyEditContainer", die abgeleitet ist <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="61557-111">The following code shows the <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> implementation in the "MyEditContainer" that is derived from <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="61557-112">Die Implementierung kennzeichnet das Ereignis in den Argumenten behandelt, und fügt dann Code für dem Quellelement eine grundlegende sichtbare Änderung erteilen.</span><span class="sxs-lookup"><span data-stu-id="61557-112">The implementation marks the event as handled in the arguments, and then adds some code to give the source element a basic visible change.</span></span>  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 <span data-ttu-id="61557-113">Wenn kein virtuelles auf Basisklassen oder für die jeweilige Methode verfügbar ist, Klassenbehandlung kann hinzugefügt werden direkt über eine Hilfsprogrammmethode, die von der <xref:System.Windows.EventManager> Klasse <xref:System.Windows.EventManager.RegisterClassHandler%2A>.</span><span class="sxs-lookup"><span data-stu-id="61557-113">If no virtual is available on base classes or for that particular method, class handling can be added directly using a utility method of the <xref:System.Windows.EventManager> class, <xref:System.Windows.EventManager.RegisterClassHandler%2A>.</span></span> <span data-ttu-id="61557-114">Diese Methode sollte nur innerhalb der statischen Initialisierung von Klassen aufgerufen werden, die Klassenbehandlung hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="61557-114">This method should only be called within the static initialization of classes that are adding class handling.</span></span> <span data-ttu-id="61557-115">In diesem Beispiel fügt einen anderen Handler für <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , und die registrierte Klasse wird in diesem Fall die benutzerdefinierte Klasse.</span><span class="sxs-lookup"><span data-stu-id="61557-115">This example adds another handler for <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , and in this case the registered class is the custom class.</span></span> <span data-ttu-id="61557-116">Im Gegensatz dazu bei Verwendung die registrierte Klasse wird tatsächlich die <xref:System.Windows.UIElement> Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="61557-116">In contrast, when using the virtuals, the registered class is really the <xref:System.Windows.UIElement> base class.</span></span> <span data-ttu-id="61557-117">In Fällen, wo Basisklassen und -Unterklasse Klassenbehandlung registrieren, werden die Unterklassenhandler zuerst aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="61557-117">In cases where base classes and subclass each register class handling, the subclass handlers are invoked first.</span></span> <span data-ttu-id="61557-118">Das Verhalten in einer Anwendung wäre, dass dieser Handler diese zuerst den Posteingang anzeigen würde und dann die visuelle Änderung im Handler für die virtuelle Methode angezeigt werden würden.</span><span class="sxs-lookup"><span data-stu-id="61557-118">The behavior in an application would be that first this handler would show its message box and then the visual change in the virtual method's handler would be shown.</span></span>  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a><span data-ttu-id="61557-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61557-119">See Also</span></span>  
 <xref:System.Windows.EventManager>  
 [<span data-ttu-id="61557-120">Markieren von Routingereignissen als behandelt und Klassenbehandlung</span><span class="sxs-lookup"><span data-stu-id="61557-120">Marking Routed Events as Handled, and Class Handling</span></span>](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [<span data-ttu-id="61557-121">Behandeln eines Routingereignisses</span><span class="sxs-lookup"><span data-stu-id="61557-121">Handle a Routed Event</span></span>](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)  
 [<span data-ttu-id="61557-122">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="61557-122">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
