---
title: 'Gewusst wie: Positionieren von untergeordneten Elementen mithilfe der angefügten Eigenschaften von Canvas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
ms.openlocfilehash: 89327b834dfd71c0a7420eb42a598b98cdb5e9d8
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208490"
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a><span data-ttu-id="1088e-102">Gewusst wie: Positionieren von untergeordneten Elementen mithilfe der angefügten Eigenschaften von Canvas</span><span class="sxs-lookup"><span data-stu-id="1088e-102">How to: Use the Attached Properties of Canvas to Position Child Elements</span></span>
<span data-ttu-id="1088e-103">Dieses Beispiel zeigt, wie Sie mit der angefügten Eigenschaften von <xref:System.Windows.Controls.Canvas> zum Positionieren der untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="1088e-103">This example shows how to use the attached properties of <xref:System.Windows.Controls.Canvas> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1088e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1088e-104">Example</span></span>  
 <span data-ttu-id="1088e-105">Das folgende Beispiel fügt vier <xref:System.Windows.Controls.Button> -Elemente als untergeordnete Elemente eines übergeordneten Elements <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="1088e-105">The following example adds four <xref:System.Windows.Controls.Button> elements as child elements of a parent <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="1088e-106">Jedes Element wird dargestellt, indem eine <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, und <xref:System.Windows.Controls.Canvas.Top%2A>.</span><span class="sxs-lookup"><span data-stu-id="1088e-106">Each element is represented by a <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, and <xref:System.Windows.Controls.Canvas.Top%2A>.</span></span>
<span data-ttu-id="1088e-107">Jede <xref:System.Windows.Controls.Button> befindet sich relativ zum übergeordneten <xref:System.Windows.Controls.Canvas> und entsprechend des zugeordneten Eigenschaftswerts.</span><span class="sxs-lookup"><span data-stu-id="1088e-107">Each <xref:System.Windows.Controls.Button> is positioned relative to the parent <xref:System.Windows.Controls.Canvas> and according to its assigned property value.</span></span>  
  
 [!code-cpp[CanvasAttachedProperties#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1088e-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1088e-108">See Also</span></span>  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.Canvas.Bottom%2A>  
 <xref:System.Windows.Controls.Canvas.Left%2A>  
 <xref:System.Windows.Controls.Canvas.Right%2A>  
 <xref:System.Windows.Controls.Canvas.Top%2A>  
 <xref:System.Windows.Controls.Button>  
 [<span data-ttu-id="1088e-109">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="1088e-109">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="1088e-110">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="1088e-110">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)  
 [<span data-ttu-id="1088e-111">Übersicht über angefügte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1088e-111">Attached Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)
