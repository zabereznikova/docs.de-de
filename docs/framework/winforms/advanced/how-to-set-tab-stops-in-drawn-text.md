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
ms.openlocfilehash: 4bf9328b63be88f487995f7b9691683167271c46
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635805"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a><span data-ttu-id="ecc4b-102">Vorgehensweise: Festlegen von Tabstopps in gezeichnetem Text</span><span class="sxs-lookup"><span data-stu-id="ecc4b-102">How to: Set Tab Stops in Drawn Text</span></span>
<span data-ttu-id="ecc4b-103">Sie können die Tabstopps für Text festlegen, durch den Aufruf der <xref:System.Drawing.StringFormat.SetTabStops%2A> -Methode der eine <xref:System.Drawing.StringFormat> -Objekt, und klicken Sie dann übergebe <xref:System.Drawing.StringFormat> -Objekt an die <xref:System.Drawing.Graphics.DrawString%2A> -Methode der der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="ecc4b-103">You can set tab stops for text by calling the <xref:System.Drawing.StringFormat.SetTabStops%2A> method of a <xref:System.Drawing.StringFormat> object and then passing that <xref:System.Drawing.StringFormat> object to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ecc4b-104">Die <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> wird nicht unterstützt, Hinzufügen von Tabstopps in gezeichnetem Text, obwohl Sie vorhandene Registerkarte erweitern können nicht mehr die <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> Flag.</span><span class="sxs-lookup"><span data-stu-id="ecc4b-104">The <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> does not support adding tab stops to drawn text, although you can expand existing tab stops using the <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecc4b-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ecc4b-105">Example</span></span>  
 <span data-ttu-id="ecc4b-106">Im folgende Beispiel legt Tabstopps auf 150, 250 und 350 fest.</span><span class="sxs-lookup"><span data-stu-id="ecc4b-106">The following example sets tab stops at 150, 250, and 350.</span></span> <span data-ttu-id="ecc4b-107">Anschließend zeigt der Code eine tabulatorgetrennte Liste der Namen und Testergebnisse.</span><span class="sxs-lookup"><span data-stu-id="ecc4b-107">Then, the code displays a tabbed list of names and test scores.</span></span>  
  
 <span data-ttu-id="ecc4b-108">Die folgende Abbildung zeigt den Text im Registerkartenformat.</span><span class="sxs-lookup"><span data-stu-id="ecc4b-108">The following illustration shows the tabbed text.</span></span>  
  
 <span data-ttu-id="ecc4b-109">![Schriftartentext](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")</span><span class="sxs-lookup"><span data-stu-id="ecc4b-109">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")</span></span>  
  
 <span data-ttu-id="ecc4b-110">Der folgende Code übergibt zwei Argumente an die <xref:System.Drawing.StringFormat.SetTabStops%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="ecc4b-110">The following code passes two arguments to the <xref:System.Drawing.StringFormat.SetTabStops%2A> method.</span></span> <span data-ttu-id="ecc4b-111">Das zweite Argument ist ein Array, Registerkarte Offsets enthält.</span><span class="sxs-lookup"><span data-stu-id="ecc4b-111">The second argument is an array that contains tab offsets.</span></span> <span data-ttu-id="ecc4b-112">Das erste Argument zu übergeben, um <xref:System.Drawing.StringFormat.SetTabStops%2A> ist 0. Dies gibt an, dass es sich bei der erste Offset im Array an Position 0 (null) dem linken Rand des umschließenden Rechtecks gemessen wird.</span><span class="sxs-lookup"><span data-stu-id="ecc4b-112">The first argument passed to <xref:System.Drawing.StringFormat.SetTabStops%2A> is 0, which indicates that the first offset in the array is measured from position 0, the left edge of the bounding rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ecc4b-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ecc4b-113">Compiling the Code</span></span>  
  
-   <span data-ttu-id="ecc4b-114">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.</span><span class="sxs-lookup"><span data-stu-id="ecc4b-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecc4b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecc4b-115">See also</span></span>
- [<span data-ttu-id="ecc4b-116">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="ecc4b-116">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [<span data-ttu-id="ecc4b-117">Vorgehensweise: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="ecc4b-117">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
