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
ms.openlocfilehash: 91dd047e65af8791f8e558a9a3b622ef05e2cb77
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606321"
---
# <a name="how-to-bind-an-adorner-to-an-element"></a><span data-ttu-id="1b385-102">Vorgehensweise: Binden eines Adorners an ein Element</span><span class="sxs-lookup"><span data-stu-id="1b385-102">How to: Bind an Adorner to an Element</span></span>
<span data-ttu-id="1b385-103">Dieses Beispiel zeigt, wie Sie programmgesteuert einen Adorner an einem angegebenen binden <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="1b385-103">This example shows how to programmatically bind an adorner to a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b385-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b385-104">Example</span></span>  
 <span data-ttu-id="1b385-105">Zum Binden eines Adorners an ein bestimmtes <xref:System.Windows.UIElement>, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="1b385-105">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="1b385-106">Aufrufen der `static` Methode <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> zum Abrufen einer <xref:System.Windows.Documents.AdornerLayer> -Objekt für die <xref:System.Windows.UIElement> verziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1b385-106">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="1b385-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> durchläuft die visuelle Struktur, beginnend am angegebenen **"UIElement"**, und gibt die erste Adornerebene gefundenen zurück.</span><span class="sxs-lookup"><span data-stu-id="1b385-107"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified **UIElement**, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="1b385-108">(Falls keine Adorner-Ebenen gefunden werden, gibt die Methode NULL zurück.)</span><span class="sxs-lookup"><span data-stu-id="1b385-108">(If no adorner layers are found, the method returns null.)</span></span>  
  
2.  <span data-ttu-id="1b385-109">Rufen Sie die <xref:System.Windows.Documents.AdornerLayer.Add%2A> Methode, um den Adorner an das Ziel binden **"UIElement"**.</span><span class="sxs-lookup"><span data-stu-id="1b385-109">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target **UIElement**.</span></span>  
  
 <span data-ttu-id="1b385-110">Im folgende Beispiel wird ein SimpleCircleAdorner, die (siehe oben), um eine <xref:System.Windows.Controls.TextBox> mit dem Namen *MyTextBox*.</span><span class="sxs-lookup"><span data-stu-id="1b385-110">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]  
  
> [!NOTE]
>  <span data-ttu-id="1b385-111">Das Binden von Adornern an andere Elemente mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1b385-111">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b385-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b385-112">See also</span></span>
- [<span data-ttu-id="1b385-113">Übersicht über Adorner</span><span class="sxs-lookup"><span data-stu-id="1b385-113">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
