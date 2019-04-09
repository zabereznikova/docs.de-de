---
title: 'Vorgehensweise: Verwenden einer Steuerelementwiedergabeklasse'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
ms.openlocfilehash: 7115c227cb24cf12a50073d0dc587524abf0cbb9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163571"
---
# <a name="how-to-use-a-control-rendering-class"></a><span data-ttu-id="31f8d-102">Vorgehensweise: Verwenden einer Steuerelementwiedergabeklasse</span><span class="sxs-lookup"><span data-stu-id="31f8d-102">How to: Use a Control Rendering Class</span></span>
<span data-ttu-id="31f8d-103">In diesem Beispiel wird veranschaulicht, wie die <xref:System.Windows.Forms.ComboBoxRenderer> Klasse auf den Dropdownpfeil neben einem Kombinationsfeld-Steuerelement zu rendern.</span><span class="sxs-lookup"><span data-stu-id="31f8d-103">This example demonstrates how to use the <xref:System.Windows.Forms.ComboBoxRenderer> class to render the drop-down arrow of a combo box control.</span></span> <span data-ttu-id="31f8d-104">Das Beispiel besteht aus den <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode der ein einfaches benutzerdefiniertes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="31f8d-104">The example consists of the <xref:System.Windows.Forms.Control.OnPaint%2A> method of a simple custom control.</span></span> <span data-ttu-id="31f8d-105">Die <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> Eigenschaft wird verwendet, um zu bestimmen, ob visuelle Stile im Clientbereich von Anwendungsfenstern aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="31f8d-105">The <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> property is used to determine whether visual styles are enabled in the client area of application windows.</span></span> <span data-ttu-id="31f8d-106">Wenn visuelle Stile aktiviert sind, gibt die <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> Methode rendert den Dropdown-Pfeil mit visuellen Stilen; andernfalls der <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> Methode rendert den Dropdown-Pfeil in der klassischen Windows-Stil.</span><span class="sxs-lookup"><span data-stu-id="31f8d-106">If visual styles are active, then the <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> method will render the drop-down arrow with visual styles; otherwise, the <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> method will render the drop-down arrow in the classic Windows style.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31f8d-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="31f8d-107">Example</span></span>  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="31f8d-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="31f8d-108">Compiling the Code</span></span>  
 <span data-ttu-id="31f8d-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="31f8d-109">This example requires:</span></span>  
  
-   <span data-ttu-id="31f8d-110">Ein benutzerdefiniertes Steuerelement abgeleitet wird, aus der <xref:System.Windows.Forms.Control> Klasse.</span><span class="sxs-lookup"><span data-stu-id="31f8d-110">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
-   <span data-ttu-id="31f8d-111">Ein <xref:System.Windows.Forms.Form> , die das benutzerdefinierte Steuerelement hostet.</span><span class="sxs-lookup"><span data-stu-id="31f8d-111">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
-   <span data-ttu-id="31f8d-112">Verweise auf die <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, und <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> Namespaces.</span><span class="sxs-lookup"><span data-stu-id="31f8d-112">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f8d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31f8d-113">See also</span></span>

- [<span data-ttu-id="31f8d-114">Rendering von Steuerelementen mit visuellen Stilen</span><span class="sxs-lookup"><span data-stu-id="31f8d-114">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)
