---
title: 'Vorgehensweise: Verwenden der Bildkantenglättung mit Text'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 64b1c27b9e8b7d405dde5add105ff2e682f8ad87
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534103"
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="77aa4-102">Vorgehensweise: Verwenden der Bildkantenglättung mit Text</span><span class="sxs-lookup"><span data-stu-id="77aa4-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="77aa4-103">*Antialiasing* bezieht sich auf das Glätten der gezackten Kanten des gezeichneten Grafiken und Text, um ihre Darstellung oder die Lesbarkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="77aa4-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="77aa4-104">Mit den verwalteten [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Klassen, können Sie qualitativ hochwertige geglätteten Text als auch vom niedrigere Qualität Text rendern.</span><span class="sxs-lookup"><span data-stu-id="77aa4-104">With the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="77aa4-105">Höhere Qualität Rendering dauert in der Regel mehr Verarbeitungszeit als vom niedrigere Qualität Rendering.</span><span class="sxs-lookup"><span data-stu-id="77aa4-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="77aa4-106">Um die Qualität der Text festzulegen, legen Sie die <xref:System.Drawing.Graphics.TextRenderingHint%2A> Eigenschaft eine <xref:System.Drawing.Graphics> auf eines der Elemente von der <xref:System.Drawing.Text.TextRenderingHint> Enumeration</span><span class="sxs-lookup"><span data-stu-id="77aa4-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="77aa4-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="77aa4-107">Example</span></span>  
 <span data-ttu-id="77aa4-108">Im folgenden Codebeispiel wird zeichnet Text mit zwei Einstellungen für unterschiedliche Qualität.</span><span class="sxs-lookup"><span data-stu-id="77aa4-108">The following code example draws text with two different quality settings.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
 
 <span data-ttu-id="77aa4-109">Die folgende Abbildung zeigt die Ausgabe des Beispielcodes:</span><span class="sxs-lookup"><span data-stu-id="77aa4-109">The following illustration shows the output of the example code:</span></span>  
  
 <span data-ttu-id="77aa4-110">![Schriftartentext](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span><span class="sxs-lookup"><span data-stu-id="77aa4-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="77aa4-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="77aa4-111">Compiling the Code</span></span>  
 <span data-ttu-id="77aa4-112">Das vorherige Codebeispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="77aa4-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77aa4-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77aa4-113">See also</span></span>
- [<span data-ttu-id="77aa4-114">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="77aa4-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
