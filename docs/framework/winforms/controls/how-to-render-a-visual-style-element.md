---
title: 'Vorgehensweise: Rendern eines visuellen Stilelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- visual themes [Windows Forms], applying to elements of Windows Forms applications
- professional appearance [Windows Forms], applying to elements of Windows Forms applications
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
ms.openlocfilehash: a2b9524b6a3e3c77d3c68c4d9e138b8c0e2a9373
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662288"
---
# <a name="how-to-render-a-visual-style-element"></a><span data-ttu-id="61a76-102">Vorgehensweise: Rendern eines visuellen Stilelements</span><span class="sxs-lookup"><span data-stu-id="61a76-102">How to: Render a Visual Style Element</span></span>
<span data-ttu-id="61a76-103">Die <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> Namespace weist <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> den Windows-Benutzer darstellende – Objekte Schnittstellenelemente (UI) von visuellen Stilen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="61a76-103">The <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespace exposes <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> objects that represent the Windows user interface (UI) elements supported by visual styles.</span></span> <span data-ttu-id="61a76-104">In diesem Thema wird veranschaulicht, wie Sie mit der <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> -Klasse zum Rendern der <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> darstellt, die die **Abmelden** und **Herunterfahren** Schaltflächen des Startmenüs auf.</span><span class="sxs-lookup"><span data-stu-id="61a76-104">This topic demonstrates how to use the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> class to render the <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> that represents the **Log Off** and **Shut Down** buttons of the Start menu.</span></span>  
  
### <a name="to-render-a-visual-style-element"></a><span data-ttu-id="61a76-105">Um ein visuelles Stilelement zu rendern.</span><span class="sxs-lookup"><span data-stu-id="61a76-105">To render a visual style element</span></span>  
  
1. <span data-ttu-id="61a76-106">Erstellen Sie eine <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> und legen Sie es auf das Element, das Sie zeichnen möchten.</span><span class="sxs-lookup"><span data-stu-id="61a76-106">Create a <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> and set it to the element you want to draw.</span></span> <span data-ttu-id="61a76-107">Beachten Sie die Verwendung der <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> Eigenschaft und die <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> Methode; die <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> Konstruktor wird eine Ausnahme ausgelöst, wenn visuelle Stile deaktiviert sind, oder ein Element nicht definiert ist.</span><span class="sxs-lookup"><span data-stu-id="61a76-107">Note the use of the <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> property and the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> method; the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> constructor will throw an exception if visual styles are disabled or an element is undefined.</span></span>  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2. <span data-ttu-id="61a76-108">Rufen Sie die <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> Methode, um dem Element gerendert werden, die die <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> darstellt.</span><span class="sxs-lookup"><span data-stu-id="61a76-108">Call the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> method to render the element that the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> currently represents.</span></span>  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="61a76-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="61a76-109">Compiling the Code</span></span>  
 <span data-ttu-id="61a76-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="61a76-110">This example requires:</span></span>  
  
- <span data-ttu-id="61a76-111">Ein benutzerdefiniertes Steuerelement abgeleitet wird, aus der <xref:System.Windows.Forms.Control> Klasse.</span><span class="sxs-lookup"><span data-stu-id="61a76-111">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
- <span data-ttu-id="61a76-112">Ein <xref:System.Windows.Forms.Form> , die das benutzerdefinierte Steuerelement hostet.</span><span class="sxs-lookup"><span data-stu-id="61a76-112">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
- <span data-ttu-id="61a76-113">Verweise auf die <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, und <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> Namespaces.</span><span class="sxs-lookup"><span data-stu-id="61a76-113">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a76-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61a76-114">See also</span></span>

- [<span data-ttu-id="61a76-115">Rendering von Steuerelementen mit visuellen Stilen</span><span class="sxs-lookup"><span data-stu-id="61a76-115">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)
