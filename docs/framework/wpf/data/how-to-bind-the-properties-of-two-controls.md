---
title: 'Vorgehensweise: Binden der Eigenschaften von zwei Steuerelementen'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 332e8e0dfa30ff7aff27c95652f07446baf6511a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754050"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="e7ef9-102">Vorgehensweise: Binden der Eigenschaften von zwei Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="e7ef9-102">How to: Bind the Properties of Two Controls</span></span>
<span data-ttu-id="e7ef9-103">Dieses Beispiel zeigt, wie Sie die Eigenschaft eines instanziierten Steuerelements an, die von einem anderen mit binden die <xref:System.Windows.Data.Binding.ElementName%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e7ef9-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7ef9-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7ef9-104">Example</span></span>  
 <span data-ttu-id="e7ef9-105">Das folgende Beispiel zeigt, wie Sie binden die <xref:System.Windows.Controls.Panel.Background%2A> Eigenschaft eine <xref:System.Windows.Controls.Canvas> auf die <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span><span class="sxs-lookup"><span data-stu-id="e7ef9-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the <xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A>.<xref:System.Windows.Controls.ContentControl.Content%2A></span></span> <span data-ttu-id="e7ef9-106">-Eigenschaft einer <xref:System.Windows.Controls.ComboBox>:</span><span class="sxs-lookup"><span data-stu-id="e7ef9-106">property of a <xref:System.Windows.Controls.ComboBox>:</span></span>  
  
 [!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="e7ef9-107">Bei Rendern dieses Beispiels sieht es folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="e7ef9-107">When this example is rendered it looks like the following:</span></span>  
  
![Screenshot, der ein Kombinationsfeld anzeigt, das mit dem Wert, der grüne aktiviert und ein grünes Quadrat.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="e7ef9-109">Die Bindungsziel-Eigenschaft (in diesem Beispiel die <xref:System.Windows.Controls.Panel.Background%2A> Eigenschaft) muss eine Abhängigkeitseigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="e7ef9-109">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="e7ef9-110">Weitere Informationen finden Sie unter [Übersicht über Datenbindung](data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e7ef9-110">For more information, see [Data Binding Overview](data-binding-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7ef9-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7ef9-111">See also</span></span>

- [<span data-ttu-id="e7ef9-112">Angeben der Bindungsquelle</span><span class="sxs-lookup"><span data-stu-id="e7ef9-112">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="e7ef9-113">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="e7ef9-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
