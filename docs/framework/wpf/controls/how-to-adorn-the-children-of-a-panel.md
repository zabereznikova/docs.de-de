---
title: 'Gewusst wie: Verzieren der untergeordneten Elemente eines Bereichs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], binding to children of Panels
- Panel control [WPF], binding adorners to children
ms.assetid: 4cc9b972-b472-4e5c-bdf3-3702d7fbb1f5
ms.openlocfilehash: 4babbf1df57f340a3f6be218f213ad1c868ec9f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550218"
---
# <a name="how-to-adorn-the-children-of-a-panel"></a><span data-ttu-id="8de1f-102">Gewusst wie: Verzieren der untergeordneten Elemente eines Bereichs</span><span class="sxs-lookup"><span data-stu-id="8de1f-102">How to: Adorn the Children of a Panel</span></span>
<span data-ttu-id="8de1f-103">Dieses Beispiel zeigt, wie Sie programmgesteuert einen Adorner an die untergeordneten Elemente eines angegebenen binden <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="8de1f-103">This example shows how to programmatically bind an adorner to the children of a specified <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8de1f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8de1f-104">Example</span></span>  
 <span data-ttu-id="8de1f-105">So binden Sie einen Adorner an die untergeordneten Elemente einer <xref:System.Windows.Controls.Panel>, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="8de1f-105">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>  
  
1.  <span data-ttu-id="8de1f-106">Deklarieren Sie ein neues <xref:System.Windows.Documents.AdornerLayer> Objekt, und rufen die `static` <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> Methode, um eine Adornerebene für das Element gesucht, deren untergeordnete Elemente sind, gestaltet werden.</span><span class="sxs-lookup"><span data-stu-id="8de1f-106">Declare a new <xref:System.Windows.Documents.AdornerLayer> object and call the `static`<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> method to find an adorner layer for the element whose children are to be adorned.</span></span>  
  
2.  <span data-ttu-id="8de1f-107">Durchlaufen der untergeordneten Elemente des übergeordneten Elements, und rufen die <xref:System.Windows.Documents.AdornerLayer.Add%2A> Methode, um einen Adorner an jedes untergeordnete Element binden.</span><span class="sxs-lookup"><span data-stu-id="8de1f-107">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>  
  
 <span data-ttu-id="8de1f-108">Im folgenden Beispiel bindet ein SimpleCircleAdorner (siehe oben) auf die untergeordneten eine <xref:System.Windows.Controls.StackPanel> mit dem Namen *MyStackPanel*.</span><span class="sxs-lookup"><span data-stu-id="8de1f-108">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*.</span></span>  
  
 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]  
  
> [!NOTE]
>  <span data-ttu-id="8de1f-109">Das Binden von Adornern an andere Elemente mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8de1f-109">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8de1f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8de1f-110">See Also</span></span>  
 [<span data-ttu-id="8de1f-111">Übersicht über Adorner</span><span class="sxs-lookup"><span data-stu-id="8de1f-111">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
