---
title: 'Gewusst wie: Festlegen von Tabstopps in gezeichnetem Text'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e561e8096780301230071e869dac482a6a908a5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a><span data-ttu-id="c581f-102">Gewusst wie: Festlegen von Tabstopps in gezeichnetem Text</span><span class="sxs-lookup"><span data-stu-id="c581f-102">How to: Set Tab Stops in Drawn Text</span></span>
<span data-ttu-id="c581f-103">Festlegen von Tabstopps für Text können durch Aufrufen der <xref:System.Drawing.StringFormat.SetTabStops%2A> Methode eine <xref:System.Drawing.StringFormat> Objekt und deren Übergabe, die <xref:System.Drawing.StringFormat> -Objekt an die <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> Klasse.</span><span class="sxs-lookup"><span data-stu-id="c581f-103">You can set tab stops for text by calling the <xref:System.Drawing.StringFormat.SetTabStops%2A> method of a <xref:System.Drawing.StringFormat> object and then passing that <xref:System.Drawing.StringFormat> object to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c581f-104">Die <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> verfügt, die nicht unterstützen das Hinzufügen von Tabstopps in gezeichnetem Text, obwohl Sie vorhandene Registerkarte erweitern können nicht verwendet mehr die <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> Flag.</span><span class="sxs-lookup"><span data-stu-id="c581f-104">The <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> does not support adding tab stops to drawn text, although you can expand existing tab stops using the <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c581f-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c581f-105">Example</span></span>  
 <span data-ttu-id="c581f-106">Im folgende Beispiel legt Tabstopps auf 150, 250 und 350 fest.</span><span class="sxs-lookup"><span data-stu-id="c581f-106">The following example sets tab stops at 150, 250, and 350.</span></span> <span data-ttu-id="c581f-107">Anschließend zeigt den Code eine im Registerkartenformat Liste mit Namen und Testergebnissen.</span><span class="sxs-lookup"><span data-stu-id="c581f-107">Then, the code displays a tabbed list of names and test scores.</span></span>  
  
 <span data-ttu-id="c581f-108">Die folgende Abbildung zeigt den Text im Registerkartenformat.</span><span class="sxs-lookup"><span data-stu-id="c581f-108">The following illustration shows the tabbed text.</span></span>  
  
 <span data-ttu-id="c581f-109">![Schriftartentext](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")</span><span class="sxs-lookup"><span data-stu-id="c581f-109">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")</span></span>  
  
 <span data-ttu-id="c581f-110">Folgender Code übergibt zwei Argumente an die <xref:System.Drawing.StringFormat.SetTabStops%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="c581f-110">The following code passes two arguments to the <xref:System.Drawing.StringFormat.SetTabStops%2A> method.</span></span> <span data-ttu-id="c581f-111">Das zweite Argument ist ein Array, Registerkarte Offsets enthält.</span><span class="sxs-lookup"><span data-stu-id="c581f-111">The second argument is an array that contains tab offsets.</span></span> <span data-ttu-id="c581f-112">Das erste Argument zu übergeben, um <xref:System.Drawing.StringFormat.SetTabStops%2A> ist-0 und bedeutet, dass es sich bei der erste Offset im Array an Position 0 (null) dem linken Rand des umschließenden Rechtecks gemessen wird.</span><span class="sxs-lookup"><span data-stu-id="c581f-112">The first argument passed to <xref:System.Drawing.StringFormat.SetTabStops%2A> is 0, which indicates that the first offset in the array is measured from position 0, the left edge of the bounding rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c581f-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c581f-113">Compiling the Code</span></span>  
  
-   <span data-ttu-id="c581f-114">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.</span><span class="sxs-lookup"><span data-stu-id="c581f-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c581f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c581f-115">See Also</span></span>  
 [<span data-ttu-id="c581f-116">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="c581f-116">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="c581f-117">Gewusst wie: Zeichnen von Text mit GDI</span><span class="sxs-lookup"><span data-stu-id="c581f-117">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
