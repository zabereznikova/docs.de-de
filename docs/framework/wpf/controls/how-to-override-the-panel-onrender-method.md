---
title: 'Vorgehensweise: Überschreiben der Panel.OnRender-Methode'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- overriding OnRender method
- Panel control, overriding OnRender method
- OnRender method
- controls, Panel, overriding OnRender method
helpviewer_keywords:
- overriding OnRender method of Panel control [WPF]
- OnRender method [WPF], overriding
- Panel control [WPF], overriding OnRender method
ms.assetid: 57397834-a085-4e36-90ab-416fad98f341
ms.openlocfilehash: 23c3353e130585ed83726816a467ca73f6aa9152
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666715"
---
# <a name="how-to-override-the-panel-onrender-method"></a><span data-ttu-id="b1561-102">Vorgehensweise: Überschreiben der Panel.OnRender-Methode</span><span class="sxs-lookup"><span data-stu-id="b1561-102">How to: Override the Panel OnRender Method</span></span>
<span data-ttu-id="b1561-103">In diesem Beispiel wird gezeigt, wie <xref:System.Windows.Controls.Panel.OnRender%2A> die- <xref:System.Windows.Controls.Panel> Methode von überschrieben wird, um einem Layout-Element benutzerdefinierte grafische Effekte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b1561-103">This example shows how to override the <xref:System.Windows.Controls.Panel.OnRender%2A> method of <xref:System.Windows.Controls.Panel> in order to add custom graphical effects to a layout element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1561-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1561-104">Example</span></span>  
 <span data-ttu-id="b1561-105">Verwenden Sie <xref:System.Windows.Controls.Panel.OnRender%2A> die-Methode, um einem gerenderten Panel-Element grafische Effekte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b1561-105">Use the <xref:System.Windows.Controls.Panel.OnRender%2A> method in order to add graphical effects to a rendered panel element.</span></span> <span data-ttu-id="b1561-106">Beispielsweise können Sie mit dieser Methode benutzerdefinierte Rahmen-oder Hintergrundeffekte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b1561-106">For example, you can use this method to add custom border or background effects.</span></span> <span data-ttu-id="b1561-107">Ein <xref:System.Windows.Media.DrawingContext> -Objekt wird als Argument übermittelt, das Methoden zum Zeichnen von Formen, Text, Bildern oder Videos bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b1561-107">A <xref:System.Windows.Media.DrawingContext> object is passed as an argument, which provides methods for drawing shapes, text, images, or videos.</span></span> <span data-ttu-id="b1561-108">Folglich ist diese Methode nützlich für die Anpassung eines Panel-Objekts.</span><span class="sxs-lookup"><span data-stu-id="b1561-108">As a result, this method is useful for customization of a panel object.</span></span>  
  
 [!code-csharp[LightWeightCustomPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LightWeightCustomPanel/CSharp/OffsetPanel.cs#1)]
 [!code-vb[LightWeightCustomPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LightWeightCustomPanel/visualbasic/offsetpanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b1561-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1561-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="b1561-110">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="b1561-110">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="b1561-111">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="b1561-111">How-to Topics</span></span>](panel-how-to-topics.md)
