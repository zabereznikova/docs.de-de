---
title: 'Vorgehensweise: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente'
description: Erfahren Sie, wie Sie die Grafik Flimmern mit doppelter Pufferung für Windows Forms reduzieren und mithilfe von Steuerelementen die Flimmer Probleme im Zusammenhang mit Paint-Vorgängen beheben.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: f7c0425729f8a1a780124621788a1c49e06e0c4e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618128"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a><span data-ttu-id="1bac2-103">Vorgehensweise: Reduzieren von Grafikflimmern mit doppelter Pufferung für Formulare und Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="1bac2-103">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>
<span data-ttu-id="1bac2-104">Bei der doppelten Pufferung werden Flimmerprobleme, die durch mehrere Zeichenoperationen entstehen, mithilfe eines Arbeitsspeicherpuffers behoben.</span><span class="sxs-lookup"><span data-stu-id="1bac2-104">Double buffering uses a memory buffer to address the flicker problems associated with multiple paint operations.</span></span> <span data-ttu-id="1bac2-105">Wenn die doppelte Pufferung aktiviert ist, werden alle Zeichenoperationen anstelle der Zeichenoberfläche auf dem Bildschirm zunächst in einen Arbeitsspeicherpuffer gerendert.</span><span class="sxs-lookup"><span data-stu-id="1bac2-105">When double buffering is enabled, all paint operations are first rendered to a memory buffer instead of the drawing surface on the screen.</span></span> <span data-ttu-id="1bac2-106">Nachdem alle Zeichenoperationen abgeschlossen sind, wird der Arbeitsspeicherpuffer direkt in die damit verbundene Zeichenoberfläche kopiert.</span><span class="sxs-lookup"><span data-stu-id="1bac2-106">After all paint operations are completed, the memory buffer is copied directly to the drawing surface associated with it.</span></span> <span data-ttu-id="1bac2-107">Da nur ein Grafik Vorgang auf dem Bildschirm ausgeführt wird, wird das Bild flimmern, das komplexen Zeichnungs Vorgängen zugeordnet ist, nicht mehr unterbunden. Bei den meisten Anwendungen bietet die standardmäßige doppelte Pufferung, die von der .NET Framework bereitgestellt wird, die besten Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="1bac2-107">Because only one graphics operation is performed on the screen, the image flickering associated with complex painting operations is eliminated.For most applications, the default double buffering provided by the .NET Framework will provide the best results.</span></span> <span data-ttu-id="1bac2-108">Standard Windows Forms-Steuerelemente werden standardmäßig doppelt gepuffert.</span><span class="sxs-lookup"><span data-stu-id="1bac2-108">Standard Windows Forms controls are double buffered by default.</span></span> <span data-ttu-id="1bac2-109">Sie können die standardmäßige doppelte Pufferung in Ihren Formularen und den erstellten Steuerelementen auf zwei Arten aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1bac2-109">You can enable default double buffering in your forms and authored controls in two ways.</span></span> <span data-ttu-id="1bac2-110">Sie können die- <xref:System.Windows.Forms.Control.DoubleBuffered%2A> Eigenschaft entweder auf festlegen `true` , oder Sie können die-Methode aufzurufen, um <xref:System.Windows.Forms.Control.SetStyle%2A> das- <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> Flag auf festzulegen `true` .</span><span class="sxs-lookup"><span data-stu-id="1bac2-110">You can either set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`, or you can call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span> <span data-ttu-id="1bac2-111">Beide Methoden ermöglichen die standardmäßige doppelte Pufferung für das Formular oder Steuerelement und bieten flimmerfreies Grafik Rendering.</span><span class="sxs-lookup"><span data-stu-id="1bac2-111">Both methods will enable default double buffering for your form or control and provide flicker-free graphics rendering.</span></span> <span data-ttu-id="1bac2-112">Das Aufrufen der- <xref:System.Windows.Forms.Control.SetStyle%2A> Methode wird nur für benutzerdefinierte Steuerelemente empfohlen, für die Sie den gesamten Renderingcode geschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="1bac2-112">Calling the <xref:System.Windows.Forms.Control.SetStyle%2A> method is recommended only for custom controls for which you have written all the rendering code.</span></span>  
  
 <span data-ttu-id="1bac2-113">Für erweiterte Szenarien mit doppelter Pufferung, wie z. b. Animation oder erweiterte Speicherverwaltung, können Sie eine eigene doppelte pufferlogik implementieren.</span><span class="sxs-lookup"><span data-stu-id="1bac2-113">For more advanced double buffering scenarios, such as animation or advanced memory management, you can implement your own double buffering logic.</span></span> <span data-ttu-id="1bac2-114">Weitere Informationen finden Sie unter Gewusst [wie: Manuelles Verwalten von gepufferten Grafiken](how-to-manually-manage-buffered-graphics.md).</span><span class="sxs-lookup"><span data-stu-id="1bac2-114">For more information, see [How to: Manually Manage Buffered Graphics](how-to-manually-manage-buffered-graphics.md).</span></span>  
  
### <a name="to-reduce-flicker"></a><span data-ttu-id="1bac2-115">So reduzieren Sie Flimmern</span><span class="sxs-lookup"><span data-stu-id="1bac2-115">To reduce flicker</span></span>  
  
- <span data-ttu-id="1bac2-116">Legen Sie die <xref:System.Windows.Forms.Control.DoubleBuffered%2A> -Eigenschaft auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="1bac2-116">Set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 <span data-ttu-id="1bac2-117">\- oder -</span><span class="sxs-lookup"><span data-stu-id="1bac2-117">\- or -</span></span>  
  
- <span data-ttu-id="1bac2-118">Ruft die- <xref:System.Windows.Forms.Control.SetStyle%2A> Methode auf, um das- <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> Flag auf festzulegen `true` .</span><span class="sxs-lookup"><span data-stu-id="1bac2-118">Call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="1bac2-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1bac2-119">See also</span></span>

- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [<span data-ttu-id="1bac2-120">Doppelt gepufferte Grafiken</span><span class="sxs-lookup"><span data-stu-id="1bac2-120">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="1bac2-121">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1bac2-121">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
