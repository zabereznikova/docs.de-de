---
title: 'Vorgehensweise: Implementieren einer benutzerdefinierten Layout-Engine'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- layout engines [Windows Forms], custom
- TableLayoutPanel control [Windows Forms], layout engine
- layout engines [Windows Forms], implementing
- FlowLayoutPanel control [Windows Forms], layout engine
ms.assetid: f91aa91c-29f4-4089-95ca-5d48b774b00e
ms.openlocfilehash: 8e5043e2b42b1e7449c6dab51691b6d57e28cd53
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083373"
---
# <a name="how-to-implement-a-custom-layout-engine"></a><span data-ttu-id="39663-102">Vorgehensweise: Implementieren einer benutzerdefinierten Layout-Engine</span><span class="sxs-lookup"><span data-stu-id="39663-102">How to: Implement a Custom Layout Engine</span></span>
<span data-ttu-id="39663-103">Im folgenden Codebeispiel wird veranschaulicht, wie eine benutzerdefiniertes Layout-Engine zu erstellen, die ein einfache Flusslayout ausführt, wird.</span><span class="sxs-lookup"><span data-stu-id="39663-103">The following code example demonstrates how to create a custom layout engine that performs a simple flow layout.</span></span> <span data-ttu-id="39663-104">Implementiert ein Bereichssteuerelement namens `DemoFlowPanel`, welche Außerkraftsetzungen der <xref:System.Windows.Forms.Control.LayoutEngine%2A> Eigenschaft zu einer Instanz von der `DemoFlowLayout` Klasse.</span><span class="sxs-lookup"><span data-stu-id="39663-104">It implements a panel control named `DemoFlowPanel`, which overrides the <xref:System.Windows.Forms.Control.LayoutEngine%2A> property to provide an instance of the `DemoFlowLayout` class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39663-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39663-105">Example</span></span>  
 [!code-cpp[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/cpp/DemoFlowLayout.cpp#1)]
 [!code-csharp[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/CS/DemoFlowLayout.cs#1)]
 [!code-vb[System.Windows.Forms.Layout.LayoutEngine#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/VB/DemoFlowLayout.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="39663-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39663-106">See also</span></span>

- <xref:System.Windows.Forms.Layout.LayoutEngine>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A?displayProperty=nameWithType>
