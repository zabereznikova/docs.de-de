---
title: 'Vorgehensweise: Festlegen von Tabstopps in gezeichnetem Text'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 8e8f1bf193a41530a19e1046e3907b4c926b779f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64637034"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a><span data-ttu-id="8b46a-102">Vorgehensweise: Festlegen von Tabstopps in gezeichnetem Text</span><span class="sxs-lookup"><span data-stu-id="8b46a-102">How to: Set Tab Stops in Drawn Text</span></span>
<span data-ttu-id="8b46a-103">Sie können die Tabstopps für Text festlegen, durch den Aufruf der <xref:System.Drawing.StringFormat.SetTabStops%2A> -Methode der eine <xref:System.Drawing.StringFormat> -Objekt, und klicken Sie dann übergebe <xref:System.Drawing.StringFormat> -Objekt an die <xref:System.Drawing.Graphics.DrawString%2A> -Methode der der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="8b46a-103">You can set tab stops for text by calling the <xref:System.Drawing.StringFormat.SetTabStops%2A> method of a <xref:System.Drawing.StringFormat> object and then passing that <xref:System.Drawing.StringFormat> object to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b46a-104">Die <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> wird nicht unterstützt, Hinzufügen von Tabstopps in gezeichnetem Text, obwohl Sie vorhandene Registerkarte erweitern können nicht mehr die <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> Flag.</span><span class="sxs-lookup"><span data-stu-id="8b46a-104">The <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> does not support adding tab stops to drawn text, although you can expand existing tab stops using the <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b46a-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b46a-105">Example</span></span>  
 <span data-ttu-id="8b46a-106">Im folgende Beispiel legt Tabstopps auf 150, 250 und 350 fest.</span><span class="sxs-lookup"><span data-stu-id="8b46a-106">The following example sets tab stops at 150, 250, and 350.</span></span> <span data-ttu-id="8b46a-107">Anschließend zeigt der Code eine tabulatorgetrennte Liste der Namen und Testergebnisse.</span><span class="sxs-lookup"><span data-stu-id="8b46a-107">Then, the code displays a tabbed list of names and test scores.</span></span>  
  
 <span data-ttu-id="8b46a-108">Die folgende Abbildung zeigt den Text im Registerkartenformat an:</span><span class="sxs-lookup"><span data-stu-id="8b46a-108">The following illustration shows the tabbed text:</span></span>  
  
 ![Screenshot, der eine tabulatorgetrennte Liste der Namen und Ergebnisse anzeigt.](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 <span data-ttu-id="8b46a-110">Der folgende Code übergibt zwei Argumente an die <xref:System.Drawing.StringFormat.SetTabStops%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="8b46a-110">The following code passes two arguments to the <xref:System.Drawing.StringFormat.SetTabStops%2A> method.</span></span> <span data-ttu-id="8b46a-111">Das zweite Argument ist ein Array, Registerkarte Offsets enthält.</span><span class="sxs-lookup"><span data-stu-id="8b46a-111">The second argument is an array that contains tab offsets.</span></span> <span data-ttu-id="8b46a-112">Das erste Argument zu übergeben, um <xref:System.Drawing.StringFormat.SetTabStops%2A> ist 0. Dies gibt an, dass es sich bei der erste Offset im Array an Position 0 (null) dem linken Rand des umschließenden Rechtecks gemessen wird.</span><span class="sxs-lookup"><span data-stu-id="8b46a-112">The first argument passed to <xref:System.Drawing.StringFormat.SetTabStops%2A> is 0, which indicates that the first offset in the array is measured from position 0, the left edge of the bounding rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8b46a-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8b46a-113">Compiling the Code</span></span>  
  
- <span data-ttu-id="8b46a-114">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="8b46a-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b46a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b46a-115">See also</span></span>

- [<span data-ttu-id="8b46a-116">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="8b46a-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="8b46a-117">Vorgehensweise: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="8b46a-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
