---
title: 'Vorgehensweise: Einrichten von Benachrichtigungen über Bindungsaktualisierungen'
ms.date: 03/30/2017
helpviewer_keywords:
- notifications [WPF], binding updates
- data binding [WPF], notification of binding updates
- binding [WPF], updates [WPF], notifications of
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
ms.openlocfilehash: 4185198312ed98f9aaa1388626600d9f21abae55
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213961"
---
# <a name="how-to-set-up-notification-of-binding-updates"></a><span data-ttu-id="7f490-102">Vorgehensweise: Einrichten von Benachrichtigungen über Bindungsaktualisierungen</span><span class="sxs-lookup"><span data-stu-id="7f490-102">How to: Set Up Notification of Binding Updates</span></span>
<span data-ttu-id="7f490-103">In diesem Beispiel wird erläutert, wie Sie Benachrichtigungen einrichten können, die Sie darüber informieren, wenn die Eigenschaft „Bindungsziel (Ziel)“ oder „Bindungsquelle (Quelle)“ einer Bindung aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7f490-103">This example shows how to set up to be notified when the binding target (target) or the binding source (source) property of a binding has been updated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f490-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7f490-104">Example</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="7f490-105">Löst ein jedes Mal, dass die Bindungsquelle oder das Ziel aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7f490-105">raises a data update event each time that the binding source or target has been updated.</span></span> <span data-ttu-id="7f490-106">Intern veranlasst dieses Ereignis die Benutzeroberfläche (User Interface, [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]), eine Aktualisierung durchzuführen, weil sich die gebundenen Daten geändert haben.</span><span class="sxs-lookup"><span data-stu-id="7f490-106">Internally, this event is used to inform the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] that it should update, because the bound data has changed.</span></span> <span data-ttu-id="7f490-107">Beachten Sie, dass für diese Ereignisse sowie für die unidirektionale oder bidirektionale Bindung ordnungsgemäß funktioniert, müssen Sie zum Implementieren der Klasse mit dem <xref:System.ComponentModel.INotifyPropertyChanged> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7f490-107">Note that for these events to work, and also for one-way or two-way binding to work properly, you need to implement your data class using the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="7f490-108">Weitere Informationen finden Sie unter [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](how-to-implement-property-change-notification.md).</span><span class="sxs-lookup"><span data-stu-id="7f490-108">For more information, see [Implement Property Change Notification](how-to-implement-property-change-notification.md).</span></span>  
  
 <span data-ttu-id="7f490-109">Legen Sie die <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> oder <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> -Eigenschaft (oder beides), `true` in der Bindung.</span><span class="sxs-lookup"><span data-stu-id="7f490-109">Set the <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> or <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> property (or both) to `true` in the binding.</span></span> <span data-ttu-id="7f490-110">Der Handler, den Sie zur Überwachung dieses Ereignisses bereitstellen, muss direkt an das Element angefügt werden, über dessen Änderungen Sie informiert werden möchten. Oder er muss an den Gesamtdatenkontext angefügt werden, wenn Sie über Änderungen am Kontext informiert werden möchten.</span><span class="sxs-lookup"><span data-stu-id="7f490-110">The handler you provide to listen for this event must be attached directly to the element where you want to be informed of changes, or to the overall data context if you want to be aware that anything in the context has changed.</span></span>  
  
 <span data-ttu-id="7f490-111">Im folgenden Beispiel wird erläutert, wie Sie Benachrichtigungen für die Aktualisierung einer Zieleigenschaft einrichten.</span><span class="sxs-lookup"><span data-stu-id="7f490-111">Here is an example that shows how to set up for notification when a target property has been updated.</span></span>  
  
 [!code-xaml[DirectionalBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 <span data-ttu-id="7f490-112">Anschließend können Sie zur Behandlung des Ereignisses einen Handler auf Grundlage des EventHandler\<T>-Delegaten einrichten, in diesem Beispiel *OnTargetUpdated*:</span><span class="sxs-lookup"><span data-stu-id="7f490-112">You can then assign a handler based on the EventHandler\<T> delegate, *OnTargetUpdated* in this example, to handle the event:</span></span>  
  
 [!code-csharp[DirectionalBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 <span data-ttu-id="7f490-113">Parameter des Ereignisses können zur Ermittlung von Details über die geänderte Eigenschaft (z. B. den Typ oder das jeweilige Element, wenn derselbe Handler an mehrere Elemente angefügt ist) verwendet werden. Diese Details können hilfreich sein, wenn es für ein einzelnes Element mehrere gebundene Eigenschaften gibt.</span><span class="sxs-lookup"><span data-stu-id="7f490-113">Parameters of the event can be used to determine details about the property that changed (such as the type or the specific element if the same handler is attached to more than one element), which can be useful if there are multiple bound properties on a single element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f490-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f490-114">See also</span></span>

- [<span data-ttu-id="7f490-115">Übersicht über die Datenbindung</span><span class="sxs-lookup"><span data-stu-id="7f490-115">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="7f490-116">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="7f490-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
