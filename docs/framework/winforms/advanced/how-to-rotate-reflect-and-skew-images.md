---
title: 'Gewusst wie: Drehen, Spiegeln und Zerren von Bildern'
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
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 163af74d27adcb7ec720a54bfd969bd704f7b1e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-rotate-reflect-and-skew-images"></a><span data-ttu-id="22365-102">Gewusst wie: Drehen, Spiegeln und Zerren von Bildern</span><span class="sxs-lookup"><span data-stu-id="22365-102">How to: Rotate, Reflect, and Skew Images</span></span>
<span data-ttu-id="22365-103">Sie können drehen, wider und ein Bild von Zielpunkte für die oberen linken, oberen rechten und unteren linken Ecke des ursprünglichen Bilds verzerren.</span><span class="sxs-lookup"><span data-stu-id="22365-103">You can rotate, reflect, and skew an image by specifying destination points for the upper-left, upper-right, and lower-left corners of the original image.</span></span> <span data-ttu-id="22365-104">Die drei Zielpunkte bestimmen eine affine Transformation, die ein Parallelogramm dem ursprungsabbild rechteckigen zuordnet.</span><span class="sxs-lookup"><span data-stu-id="22365-104">The three destination points determine an affine transformation that maps the original rectangular image to a parallelogram.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22365-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="22365-105">Example</span></span>  
 <span data-ttu-id="22365-106">Nehmen wir beispielsweise an, die das ursprüngliche Bild ist ein Rechteck mit der linken oberen Ecke an (0, 0), rechten oberen Ecke an (100, 0), und der unteren linken Ecke auf (0, 50).</span><span class="sxs-lookup"><span data-stu-id="22365-106">For example, suppose the original image is a rectangle with upper-left corner at (0, 0), upper-right corner at (100, 0), and lower-left corner at (0, 50).</span></span> <span data-ttu-id="22365-107">Jetzt angenommen, Sie ordnen Sie die Punkte drei Zielpunkte wie folgt.</span><span class="sxs-lookup"><span data-stu-id="22365-107">Now suppose you map those three points to destination points as follows.</span></span>  
  
|<span data-ttu-id="22365-108">Ursprüngliche Punkt</span><span class="sxs-lookup"><span data-stu-id="22365-108">Original point</span></span>|<span data-ttu-id="22365-109">Zielpunkt</span><span class="sxs-lookup"><span data-stu-id="22365-109">Destination point</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="22365-110">Linke (0, 0)</span><span class="sxs-lookup"><span data-stu-id="22365-110">Upper-left (0, 0)</span></span>|<span data-ttu-id="22365-111">(200, 20)</span><span class="sxs-lookup"><span data-stu-id="22365-111">(200, 20)</span></span>|  
|<span data-ttu-id="22365-112">Rechts (100, 0)</span><span class="sxs-lookup"><span data-stu-id="22365-112">Upper-right (100, 0)</span></span>|<span data-ttu-id="22365-113">(110, 100)</span><span class="sxs-lookup"><span data-stu-id="22365-113">(110, 100)</span></span>|  
|<span data-ttu-id="22365-114">Unten links (0, 50)</span><span class="sxs-lookup"><span data-stu-id="22365-114">Lower-left (0, 50)</span></span>|<span data-ttu-id="22365-115">(250, 30)</span><span class="sxs-lookup"><span data-stu-id="22365-115">(250, 30)</span></span>|  
  
 <span data-ttu-id="22365-116">Die folgende Abbildung zeigt das ursprüngliche Image und das Bild, das Parallelogramm zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="22365-116">The following illustration shows the original image and the image mapped to the parallelogram.</span></span> <span data-ttu-id="22365-117">Das ursprüngliche Image wurde verzerrt wiedergegeben, gedreht übersetzt und wurden.</span><span class="sxs-lookup"><span data-stu-id="22365-117">The original image has been skewed, reflected, rotated, and translated.</span></span> <span data-ttu-id="22365-118">Die Zeile, die ausgeführt, über wird die x-Achse entlang des oberen Randes des ursprünglichen Bilds zugeordnet ist (200, 20) und (110, 100).</span><span class="sxs-lookup"><span data-stu-id="22365-118">The x-axis along the top edge of the original image is mapped to the line that runs through (200, 20) and (110, 100).</span></span> <span data-ttu-id="22365-119">Die Zeile, die ausgeführt, über wird die y-Achse entlang des linken Randes des ursprünglichen Bilds zugeordnet ist (200, 20) und (250, 30).</span><span class="sxs-lookup"><span data-stu-id="22365-119">The y-axis along the left edge of the original image is mapped to the line that runs through (200, 20) and (250, 30).</span></span>  
  
 <span data-ttu-id="22365-120">![Streifen](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")</span><span class="sxs-lookup"><span data-stu-id="22365-120">![Stripes](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")</span></span>  
  
 <span data-ttu-id="22365-121">Die folgende Abbildung zeigt eine ähnliche Transformation auf ein Foto angewendet.</span><span class="sxs-lookup"><span data-stu-id="22365-121">The following illustration shows a similar transformation applied to a photographic image.</span></span>  
  
 <span data-ttu-id="22365-122">![Transformiert Anstieg](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")</span><span class="sxs-lookup"><span data-stu-id="22365-122">![Transformed Climber](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")</span></span>  
  
 <span data-ttu-id="22365-123">Die folgende Abbildung zeigt eine ähnliche Transformation, die auf eine Metadatei angewendet.</span><span class="sxs-lookup"><span data-stu-id="22365-123">The following illustration shows a similar transformation applied to a metafile.</span></span>  
  
 <span data-ttu-id="22365-124">![Transformiert Metadatei](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")</span><span class="sxs-lookup"><span data-stu-id="22365-124">![Transformed Metafile](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")</span></span>  
  
 <span data-ttu-id="22365-125">Im folgenden Beispiel wird die Bilder, die in der ersten Abbildung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="22365-125">The following example produces the images shown in the first illustration.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="22365-126">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="22365-126">Compiling the Code</span></span>  
 <span data-ttu-id="22365-127">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="22365-127">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="22365-128">Achten Sie darauf, ersetzen Sie `Stripes.bmp` durch den Pfad zu einem Bild, das auf Ihrem System gültig ist.</span><span class="sxs-lookup"><span data-stu-id="22365-128">Make sure to replace `Stripes.bmp` with the path to an image that is valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22365-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22365-129">See Also</span></span>  
 [<span data-ttu-id="22365-130">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="22365-130">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
