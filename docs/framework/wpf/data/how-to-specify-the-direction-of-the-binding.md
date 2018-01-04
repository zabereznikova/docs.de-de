---
title: 'Gewusst wie: Angeben der Bindungsrichtung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9944ff214a9dfe12b21e005c4e1998c249bf72b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="db852-102">Gewusst wie: Angeben der Bindungsrichtung</span><span class="sxs-lookup"><span data-stu-id="db852-102">How to: Specify the Direction of the Binding</span></span>
<span data-ttu-id="db852-103">In diesem Beispiel wird erläutert, wie sich angeben lässt, ob die Bindung nur die Eigenschaft „Bindungsziel (Ziel)“, „Bindungsquelle (Quelle)“ oder sowohl die Ziel- als auch die Quelleigenschaft aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="db852-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db852-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="db852-104">Example</span></span>  
 <span data-ttu-id="db852-105">Verwenden Sie die <xref:System.Windows.Data.Binding.Mode%2A> Eigenschaft, um die Richtung der Bindung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="db852-105">You use the <xref:System.Windows.Data.Binding.Mode%2A> property to specify the direction of the binding.</span></span> <span data-ttu-id="db852-106">In der folgenden Enumerationsliste werden die verfügbaren Optionen für Bindungsaktualisierungen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="db852-106">The following enumeration list shows the available options for binding updates:</span></span>  
  
-   <span data-ttu-id="db852-107"><xref:System.Windows.Data.BindingMode.TwoWay>Wenn die Zieleigenschaft oder die Quelleigenschaft ändert die Zieleigenschaft oder der Eigenschaft aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="db852-107"><xref:System.Windows.Data.BindingMode.TwoWay> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
-   <span data-ttu-id="db852-108"><xref:System.Windows.Data.BindingMode.OneWay>aktualisiert die Eigenschaft an, sobald sich die Quelleigenschaft ändert.</span><span class="sxs-lookup"><span data-stu-id="db852-108"><xref:System.Windows.Data.BindingMode.OneWay> updates the target property only when the source property changes.</span></span>  
  
-   <span data-ttu-id="db852-109"><xref:System.Windows.Data.BindingMode.OneTime>aktualisiert die Eigenschaft nur verwendet werden, wenn die Anwendung gestartet oder der <xref:System.Windows.FrameworkElement.DataContext%2A> eine Änderung vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="db852-109"><xref:System.Windows.Data.BindingMode.OneTime> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
-   <span data-ttu-id="db852-110"><xref:System.Windows.Data.BindingMode.OneWayToSource>aktualisiert die Quelleigenschaft, wenn die Zieleigenschaft geändert wird.</span><span class="sxs-lookup"><span data-stu-id="db852-110"><xref:System.Windows.Data.BindingMode.OneWayToSource> updates the source property when the target property changes.</span></span>  
  
-   <span data-ttu-id="db852-111"><xref:System.Windows.Data.BindingMode.Default>bewirkt, dass der <xref:System.Windows.Data.Binding.Mode%2A> Wert der Zieleigenschaft verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="db852-111"><xref:System.Windows.Data.BindingMode.Default> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="db852-112">Weitere Informationen finden Sie unter der <xref:System.Windows.Data.BindingMode>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="db852-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="db852-113">Im folgenden Beispiel wird das Festlegen der <xref:System.Windows.Data.Binding.Mode%2A>-Eigenschaft veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="db852-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="db852-114">Datenquellenänderungen erkannt (gilt für <xref:System.Windows.Data.BindingMode.OneWay> und <xref:System.Windows.Data.BindingMode.TwoWay> Bindungen), muss die Quelle einen Änderungsbenachrichtigungsmechanismus geeignete Eigenschaft z. B. implementieren <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="db852-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="db852-115">Finden Sie unter [implementieren Änderungsbenachrichtigung](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) ein Beispiel für eine <xref:System.ComponentModel.INotifyPropertyChanged> Implementierung.</span><span class="sxs-lookup"><span data-stu-id="db852-115">See [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="db852-116">Für <xref:System.Windows.Data.BindingMode.TwoWay> oder <xref:System.Windows.Data.BindingMode.OneWayToSource> Bindungen, Sie können die zeitliche Steuerung der Quelle Updates durch Festlegen der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="db852-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="db852-117">Weitere Informationen finden Sie unter <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.</span><span class="sxs-lookup"><span data-stu-id="db852-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db852-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db852-118">See Also</span></span>  
 <xref:System.Windows.Data.Binding>  
 [<span data-ttu-id="db852-119">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="db852-119">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="db852-120">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="db852-120">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
