---
title: "Gewusst wie: Einrichten von Benachrichtigungen über Bindungsaktualisierungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- notifications [WPF], binding updates
- data binding [WPF], notification of binding updates
- binding [WPF], updates [WPF], notifications of
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a07337e99e985bfbc0a5dbc5f2d231ee36cf1422
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-up-notification-of-binding-updates"></a><span data-ttu-id="6f73c-102">Gewusst wie: Einrichten von Benachrichtigungen über Bindungsaktualisierungen</span><span class="sxs-lookup"><span data-stu-id="6f73c-102">How to: Set Up Notification of Binding Updates</span></span>
<span data-ttu-id="6f73c-103">In diesem Beispiel wird erläutert, wie Sie Benachrichtigungen einrichten können, die Sie darüber informieren, wenn die Eigenschaft „Bindungsziel (Ziel)“ oder „Bindungsquelle (Quelle)“ einer Bindung aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="6f73c-103">This example shows how to set up to be notified when the binding target (target) or the binding source (source) property of a binding has been updated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f73c-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6f73c-104">Example</span></span>  
 <span data-ttu-id="6f73c-105">Bei jeder Aktualisierung der Bindungsquelle oder des Bindungsziels löst [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ein Datenaktualisierungsereignis aus.</span><span class="sxs-lookup"><span data-stu-id="6f73c-105">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] raises a data update event each time that the binding source or target has been updated.</span></span> <span data-ttu-id="6f73c-106">Intern veranlasst dieses Ereignis die Benutzeroberfläche (User Interface, [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]), eine Aktualisierung durchzuführen, weil sich die gebundenen Daten geändert haben.</span><span class="sxs-lookup"><span data-stu-id="6f73c-106">Internally, this event is used to inform the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] that it should update, because the bound data has changed.</span></span> <span data-ttu-id="6f73c-107">Beachten Sie, dass für diese Ereignisse zu arbeiten, und auch für die unidirektionale oder bidirektionale Bindung ordnungsgemäß funktioniert, Sie der Klasse mit implementieren müssen die <xref:System.ComponentModel.INotifyPropertyChanged> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6f73c-107">Note that for these events to work, and also for one-way or two-way binding to work properly, you need to implement your data class using the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="6f73c-108">Weitere Informationen finden Sie unter [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span><span class="sxs-lookup"><span data-stu-id="6f73c-108">For more information, see [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
 <span data-ttu-id="6f73c-109">Legen Sie die <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> oder <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> -Eigenschaft (oder beides), `true` in der Bindung.</span><span class="sxs-lookup"><span data-stu-id="6f73c-109">Set the <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> or <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> property (or both) to `true` in the binding.</span></span> <span data-ttu-id="6f73c-110">Der Handler, den Sie zur Überwachung dieses Ereignisses bereitstellen, muss direkt an das Element angefügt werden, über dessen Änderungen Sie informiert werden möchten. Oder er muss an den Gesamtdatenkontext angefügt werden, wenn Sie über Änderungen am Kontext informiert werden möchten.</span><span class="sxs-lookup"><span data-stu-id="6f73c-110">The handler you provide to listen for this event must be attached directly to the element where you want to be informed of changes, or to the overall data context if you want to be aware that anything in the context has changed.</span></span>  
  
 <span data-ttu-id="6f73c-111">Im folgenden Beispiel wird erläutert, wie Sie Benachrichtigungen für die Aktualisierung einer Zieleigenschaft einrichten.</span><span class="sxs-lookup"><span data-stu-id="6f73c-111">Here is an example that shows how to set up for notification when a target property has been updated.</span></span>  
  
 [!code-xaml[DirectionalBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 <span data-ttu-id="6f73c-112">Anschließend können Sie zur Behandlung des Ereignisses einen Handler auf Grundlage des EventHandler\<T>-Delegaten einrichten, in diesem Beispiel *OnTargetUpdated*:</span><span class="sxs-lookup"><span data-stu-id="6f73c-112">You can then assign a handler based on the EventHandler\<T> delegate, *OnTargetUpdated* in this example, to handle the event:</span></span>  
  
 [!code-csharp[DirectionalBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 <span data-ttu-id="6f73c-113">Parameter des Ereignisses können zur Ermittlung von Details über die geänderte Eigenschaft (z. B. den Typ oder das jeweilige Element, wenn derselbe Handler an mehrere Elemente angefügt ist) verwendet werden. Diese Details können hilfreich sein, wenn es für ein einzelnes Element mehrere gebundene Eigenschaften gibt.</span><span class="sxs-lookup"><span data-stu-id="6f73c-113">Parameters of the event can be used to determine details about the property that changed (such as the type or the specific element if the same handler is attached to more than one element), which can be useful if there are multiple bound properties on a single element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f73c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f73c-114">See Also</span></span>  
 [<span data-ttu-id="6f73c-115">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="6f73c-115">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="6f73c-116">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="6f73c-116">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
