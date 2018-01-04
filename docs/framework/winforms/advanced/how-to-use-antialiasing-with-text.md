---
title: "Gewusst wie: Verwenden der Bildkantenglättung mit Text"
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
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: edd31ec5b9d94ac1791fb0f2a73522fdf4178627
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="00b0e-102">Gewusst wie: Verwenden der Bildkantenglättung mit Text</span><span class="sxs-lookup"><span data-stu-id="00b0e-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="00b0e-103">*Antialiasing* bezieht sich auf das Glätten Flatterrändern von gezeichneten Grafiken und Text, um ihre Darstellung oder Lesbarkeit zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="00b0e-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="00b0e-104">Mit der verwalteten [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Klassen, können Sie qualitativ hochwertigen geglätteten Text als auch Text von geringer Qualität rendern.</span><span class="sxs-lookup"><span data-stu-id="00b0e-104">With the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="00b0e-105">In der Regel akzeptiert höherer Qualität rendern zeitaufwändiger als niedrigere Qualität rendern.</span><span class="sxs-lookup"><span data-stu-id="00b0e-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="00b0e-106">Legen Sie zum Festlegen der Qualitätsstufe Text der <xref:System.Drawing.Graphics.TextRenderingHint%2A> Eigenschaft eine <xref:System.Drawing.Graphics> in eines der Elemente des der <xref:System.Drawing.Text.TextRenderingHint> Enumeration</span><span class="sxs-lookup"><span data-stu-id="00b0e-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="00b0e-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00b0e-107">Example</span></span>  
 <span data-ttu-id="00b0e-108">Im folgenden Codebeispiel wird zeichnet Text mit zwei verschiedenen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="00b0e-108">The following code example draws text with two different quality settings.</span></span>  
  
 <span data-ttu-id="00b0e-109">Die folgende Abbildung zeigt die Ausgabe des Beispielcodes Beispielcode.</span><span class="sxs-lookup"><span data-stu-id="00b0e-109">The following illustration shows the output of the cod example code.</span></span>  
  
 <span data-ttu-id="00b0e-110">![Schriftartentext](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span><span class="sxs-lookup"><span data-stu-id="00b0e-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="00b0e-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="00b0e-111">Compiling the Code</span></span>  
 <span data-ttu-id="00b0e-112">Im vorangehenden Codebeispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="00b0e-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b0e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00b0e-113">See Also</span></span>  
 [<span data-ttu-id="00b0e-114">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="00b0e-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
