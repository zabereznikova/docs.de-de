---
title: 'Vorgehensweise: Binden eines Adorners an ein Element'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UIElements [WPF], binding adorners to
- adorners [WPF], binding to specified UIElements
ms.assetid: b2101611-a0ee-4137-bdb8-9b3673d2e6b9
ms.openlocfilehash: e8c7eb929042bfe1455bfc9bf459fc466de5c397
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923496"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a><span data-ttu-id="39cb2-102">Vorgehensweise: Binden eines Adorners an ein Element</span><span class="sxs-lookup"><span data-stu-id="39cb2-102">How to: Bind an Adorner to an Element</span></span>
<span data-ttu-id="39cb2-103">In diesem Beispiel wird gezeigt, wie ein Funktions Indikator Programm gesteuert an eine <xref:System.Windows.UIElement>angegebene gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="39cb2-103">This example shows how to programmatically bind an adorner to a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39cb2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39cb2-104">Example</span></span>  
 <span data-ttu-id="39cb2-105">Führen Sie die folgenden Schritte aus, um <xref:System.Windows.UIElement>einen Funktions Indikator an einen bestimmten zu binden:</span><span class="sxs-lookup"><span data-stu-id="39cb2-105">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1. <span data-ttu-id="39cb2-106">Ruft die `static` - <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> Methode auf, <xref:System.Windows.Documents.AdornerLayer> um ein- <xref:System.Windows.UIElement> Objekt zu erhalten, das zu schmücken ist.</span><span class="sxs-lookup"><span data-stu-id="39cb2-106">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="39cb2-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>durchläuft die visuelle Struktur, beginnend beim angegebenen **UIElement**, und gibt die erste gefundene Adornerebene zurück.</span><span class="sxs-lookup"><span data-stu-id="39cb2-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified **UIElement**, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="39cb2-108">(Falls keine Adorner-Ebenen gefunden werden, gibt die Methode NULL zurück.)</span><span class="sxs-lookup"><span data-stu-id="39cb2-108">(If no adorner layers are found, the method returns null.)</span></span>  
  
2. <span data-ttu-id="39cb2-109">Ruft die <xref:System.Windows.Documents.AdornerLayer.Add%2A> -Methode auf, um den Funktions Indikator an das **UIElement**-Ziel zu binden.</span><span class="sxs-lookup"><span data-stu-id="39cb2-109">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target **UIElement**.</span></span>  
  
 <span data-ttu-id="39cb2-110">Im folgenden Beispiel wird ein SimpleCircleAdorner (siehe oben) an ein <xref:System.Windows.Controls.TextBox> benanntes *MyTextBox*-Element gebunden.</span><span class="sxs-lookup"><span data-stu-id="39cb2-110">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
> <span data-ttu-id="39cb2-111">Das Binden von Adornern an andere Elemente mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="39cb2-111">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39cb2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39cb2-112">See also</span></span>

- [<span data-ttu-id="39cb2-113">Übersicht über Adorner</span><span class="sxs-lookup"><span data-stu-id="39cb2-113">Adorners Overview</span></span>](adorners-overview.md)
