---
title: 'Vorgehensweise: Angeben der Bindungsrichtung'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 4334ed178e7f2ed90928db6b434eb8c9fee77bf7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206433"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="e115e-102">Vorgehensweise: Angeben der Bindungsrichtung</span><span class="sxs-lookup"><span data-stu-id="e115e-102">How to: Specify the Direction of the Binding</span></span>
<span data-ttu-id="e115e-103">In diesem Beispiel wird erläutert, wie sich angeben lässt, ob die Bindung nur die Eigenschaft „Bindungsziel (Ziel)“, „Bindungsquelle (Quelle)“ oder sowohl die Ziel- als auch die Quelleigenschaft aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="e115e-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e115e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e115e-104">Example</span></span>  
 <span data-ttu-id="e115e-105">Sie verwenden die <xref:System.Windows.Data.Binding.Mode%2A> Eigenschaft, um die Richtung der Bindung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e115e-105">You use the <xref:System.Windows.Data.Binding.Mode%2A> property to specify the direction of the binding.</span></span> <span data-ttu-id="e115e-106">In der folgenden Enumerationsliste werden die verfügbaren Optionen für Bindungsaktualisierungen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e115e-106">The following enumeration list shows the available options for binding updates:</span></span>  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay> <span data-ttu-id="e115e-107">aktualisiert die Zieleigenschaft bzw. die Eigenschaft, wenn sich die Zieleigenschaft oder die Quelleigenschaft ändert.</span><span class="sxs-lookup"><span data-stu-id="e115e-107">updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
-   <xref:System.Windows.Data.BindingMode.OneWay> <span data-ttu-id="e115e-108">aktualisiert die Zieleigenschaft, nur, wenn die Quelleigenschaft ändert.</span><span class="sxs-lookup"><span data-stu-id="e115e-108">updates the target property only when the source property changes.</span></span>  
  
-   <xref:System.Windows.Data.BindingMode.OneTime> <span data-ttu-id="e115e-109">aktualisiert die Zieleigenschaft, nur, wenn die Anwendung gestartet wird oder wenn die <xref:System.Windows.FrameworkElement.DataContext%2A> wird eine Änderung vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="e115e-109">updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource> <span data-ttu-id="e115e-110">Aktualisiert die Quelleigenschaft, wenn die Zieleigenschaft ändert.</span><span class="sxs-lookup"><span data-stu-id="e115e-110">updates the source property when the target property changes.</span></span>  
  
-   <xref:System.Windows.Data.BindingMode.Default> <span data-ttu-id="e115e-111">bewirkt, dass der <xref:System.Windows.Data.Binding.Mode%2A> Wert der Zieleigenschaft verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e115e-111">causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="e115e-112">Weitere Informationen finden Sie unter der <xref:System.Windows.Data.BindingMode>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e115e-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="e115e-113">Im folgenden Beispiel wird das Festlegen der <xref:System.Windows.Data.Binding.Mode%2A>-Eigenschaft veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e115e-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="e115e-114">Zum Erkennen von quelländerungen (gilt für <xref:System.Windows.Data.BindingMode.OneWay> und <xref:System.Windows.Data.BindingMode.TwoWay> Bindungen), muss die Quelle einen Änderungsbenachrichtigungsmechanismus von geeigneten wie z. B. implementieren <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="e115e-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="e115e-115">Finden Sie unter [bei Eigenschaftenänderungen implementieren](how-to-implement-property-change-notification.md) ein Beispiel für eine <xref:System.ComponentModel.INotifyPropertyChanged> Implementierung.</span><span class="sxs-lookup"><span data-stu-id="e115e-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="e115e-116">Für <xref:System.Windows.Data.BindingMode.TwoWay> oder <xref:System.Windows.Data.BindingMode.OneWayToSource> Bindungen können Sie die zeitplanung für die Quelle aktualisiert steuern, durch Festlegen der <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e115e-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="e115e-117">Weitere Informationen finden Sie unter <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.</span><span class="sxs-lookup"><span data-stu-id="e115e-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e115e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e115e-118">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="e115e-119">Übersicht über die Datenbindung</span><span class="sxs-lookup"><span data-stu-id="e115e-119">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="e115e-120">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="e115e-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
