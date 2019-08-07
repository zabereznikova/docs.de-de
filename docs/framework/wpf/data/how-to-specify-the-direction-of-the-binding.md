---
title: 'Vorgehensweise: Angeben der Bindungsrichtung'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 023cd42ad5fb321e7ffa65f08673cb4145f49af4
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817913"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="4b9b9-102">Vorgehensweise: Angeben der Bindungs Richtung</span><span class="sxs-lookup"><span data-stu-id="4b9b9-102">How to: Specify the direction of the binding</span></span>

<span data-ttu-id="4b9b9-103">In diesem Beispiel wird erläutert, wie sich angeben lässt, ob die Bindung nur die Eigenschaft „Bindungsziel (Ziel)“, „Bindungsquelle (Quelle)“ oder sowohl die Ziel- als auch die Quelleigenschaft aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="4b9b9-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b9b9-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4b9b9-104">Example</span></span>  
 <span data-ttu-id="4b9b9-105">Verwenden Sie die <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> -Eigenschaft, um die Bindungs Richtung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4b9b9-105">You use the <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> property to specify the direction of the binding.</span></span> <span data-ttu-id="4b9b9-106">Im folgenden finden Sie die verfügbaren Optionen für das Binden von Updates:</span><span class="sxs-lookup"><span data-stu-id="4b9b9-106">The following are the available options for binding updates:</span></span>  
  
- <span data-ttu-id="4b9b9-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>Aktualisiert die Ziel Eigenschaft oder die-Eigenschaft, wenn sich entweder die Ziel Eigenschaft oder die Quell Eigenschaft ändert.</span><span class="sxs-lookup"><span data-stu-id="4b9b9-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
- <span data-ttu-id="4b9b9-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType>Aktualisiert die Ziel Eigenschaft nur, wenn sich die Quell Eigenschaft ändert.</span><span class="sxs-lookup"><span data-stu-id="4b9b9-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> updates the target property only when the source property changes.</span></span>  
  
- <span data-ttu-id="4b9b9-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType>Aktualisiert die Ziel Eigenschaft nur, wenn die Anwendung gestartet wird oder <xref:System.Windows.FrameworkElement.DataContext%2A> wenn eine Änderung durchläuft.</span><span class="sxs-lookup"><span data-stu-id="4b9b9-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
- <span data-ttu-id="4b9b9-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType>Aktualisiert die Quell Eigenschaft, wenn die Ziel Eigenschaft geändert wird.</span><span class="sxs-lookup"><span data-stu-id="4b9b9-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> updates the source property when the target property changes.</span></span>  
  
- <span data-ttu-id="4b9b9-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType>bewirkt, dass <xref:System.Windows.Data.Binding.Mode%2A> der Standardwert der Ziel Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4b9b9-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="4b9b9-112">Weitere Informationen finden Sie unter der <xref:System.Windows.Data.BindingMode>-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="4b9b9-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="4b9b9-113">Im folgenden Beispiel wird das Festlegen der <xref:System.Windows.Data.Binding.Mode%2A>-Eigenschaft veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4b9b9-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="4b9b9-114">Zum Erkennen von Quell Änderungen (anwendbar <xref:System.Windows.Data.BindingMode.OneWay> auf <xref:System.Windows.Data.BindingMode.TwoWay> -und-Bindungen) muss die Quelle einen geeigneten Mechanismus für die Eigenschafts <xref:System.ComponentModel.INotifyPropertyChanged>Änderungs Benachrichtigung implementieren, z. b.</span><span class="sxs-lookup"><span data-stu-id="4b9b9-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="4b9b9-115">Ein Beispiel für eine <xref:System.ComponentModel.INotifyPropertyChanged> -Implementierung finden Sie unter Implementieren von Benachrichtigungen über [Eigenschafts Änderungen](how-to-implement-property-change-notification.md) .</span><span class="sxs-lookup"><span data-stu-id="4b9b9-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="4b9b9-116">Für <xref:System.Windows.Data.BindingMode.TwoWay> - <xref:System.Windows.Data.BindingMode.OneWayToSource> oder-Bindungen können Sie die zeitliche Steuerung der Quell Aktualisierungen steuern, indem <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Sie die-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="4b9b9-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="4b9b9-117">Weitere Informationen finden Sie unter <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b9b9-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b9b9-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b9b9-118">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="4b9b9-119">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="4b9b9-119">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="4b9b9-120">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="4b9b9-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
