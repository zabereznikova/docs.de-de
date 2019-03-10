---
title: 'Vorgehensweise: Drehen, spiegeln und Zerren von Bildern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 3e539f41667edb505269fe420396c79b68f34e8f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711498"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a><span data-ttu-id="d70c2-102">Vorgehensweise: Drehen, spiegeln und Zerren von Bildern</span><span class="sxs-lookup"><span data-stu-id="d70c2-102">How to: Rotate, Reflect, and Skew Images</span></span>
<span data-ttu-id="d70c2-103">Sie können zu drehen, spiegeln und neigen ein Image, indem Zielpunkte für die oberen linken, oberen rechten und unteren linken Ecke des ursprünglichen Bilds.</span><span class="sxs-lookup"><span data-stu-id="d70c2-103">You can rotate, reflect, and skew an image by specifying destination points for the upper-left, upper-right, and lower-left corners of the original image.</span></span> <span data-ttu-id="d70c2-104">Die drei Zielpunkte bestimmen eine affine Transformation, die ein Parallelogramm das Originalbild rechteckige zuordnet.</span><span class="sxs-lookup"><span data-stu-id="d70c2-104">The three destination points determine an affine transformation that maps the original rectangular image to a parallelogram.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d70c2-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d70c2-105">Example</span></span>  
 <span data-ttu-id="d70c2-106">Nehmen wir beispielsweise an, die das ursprüngliche Bild ist ein Rechteck mit der linken oberen Ecke auf (0, 0) oben rechts auf (100, 0), und der unteren linken Ecke an ("0", "50").</span><span class="sxs-lookup"><span data-stu-id="d70c2-106">For example, suppose the original image is a rectangle with upper-left corner at (0, 0), upper-right corner at (100, 0), and lower-left corner at (0, 50).</span></span> <span data-ttu-id="d70c2-107">Jetzt angenommen, das Sie zuordnen, die Punkte drei Zielpunkte wie folgt.</span><span class="sxs-lookup"><span data-stu-id="d70c2-107">Now suppose you map those three points to destination points as follows.</span></span>  
  
|<span data-ttu-id="d70c2-108">Ursprüngliche Punkt</span><span class="sxs-lookup"><span data-stu-id="d70c2-108">Original point</span></span>|<span data-ttu-id="d70c2-109">Ziel</span><span class="sxs-lookup"><span data-stu-id="d70c2-109">Destination point</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="d70c2-110">Linke obere (0, 0)</span><span class="sxs-lookup"><span data-stu-id="d70c2-110">Upper-left (0, 0)</span></span>|<span data-ttu-id="d70c2-111">(200, 20)</span><span class="sxs-lookup"><span data-stu-id="d70c2-111">(200, 20)</span></span>|  
|<span data-ttu-id="d70c2-112">Rechts ("100", "0")</span><span class="sxs-lookup"><span data-stu-id="d70c2-112">Upper-right (100, 0)</span></span>|<span data-ttu-id="d70c2-113">(110, 100)</span><span class="sxs-lookup"><span data-stu-id="d70c2-113">(110, 100)</span></span>|  
|<span data-ttu-id="d70c2-114">Unteren linken ("0", "50")</span><span class="sxs-lookup"><span data-stu-id="d70c2-114">Lower-left (0, 50)</span></span>|<span data-ttu-id="d70c2-115">(250, 30)</span><span class="sxs-lookup"><span data-stu-id="d70c2-115">(250, 30)</span></span>|  
  
 <span data-ttu-id="d70c2-116">Die folgende Abbildung zeigt das ursprüngliche Bild und das Bild, das dem Parallelogramm zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d70c2-116">The following illustration shows the original image and the image mapped to the parallelogram.</span></span> <span data-ttu-id="d70c2-117">Das ursprüngliche Bild hat verzerrt, wiedergegeben, gedreht, übersetzt und.</span><span class="sxs-lookup"><span data-stu-id="d70c2-117">The original image has been skewed, reflected, rotated, and translated.</span></span> <span data-ttu-id="d70c2-118">Die Zeile, die ausgeführt, über wird die x-Achse entlang des oberen Randes des ursprünglichen Bilds zugeordnet ist ("200", "20") und (110, 100).</span><span class="sxs-lookup"><span data-stu-id="d70c2-118">The x-axis along the top edge of the original image is mapped to the line that runs through (200, 20) and (110, 100).</span></span> <span data-ttu-id="d70c2-119">Die Zeile, die ausgeführt, über wird die y-Achse entlang des linken Randes des ursprünglichen Bilds zugeordnet ist ("200", "20") und (250, 30).</span><span class="sxs-lookup"><span data-stu-id="d70c2-119">The y-axis along the left edge of the original image is mapped to the line that runs through (200, 20) and (250, 30).</span></span>  
  
 <span data-ttu-id="d70c2-120">![Streifen](./media/stripes1.gif "Stripes1")</span><span class="sxs-lookup"><span data-stu-id="d70c2-120">![Stripes](./media/stripes1.gif "Stripes1")</span></span>  
  
 <span data-ttu-id="d70c2-121">Die folgende Abbildung zeigt eine ähnliche Transformation angewendet auf ein Foto.</span><span class="sxs-lookup"><span data-stu-id="d70c2-121">The following illustration shows a similar transformation applied to a photographic image.</span></span>  
  
 <span data-ttu-id="d70c2-122">![Transformiert Anstieg](./media/transformedclimber.png "TransformedClimber")</span><span class="sxs-lookup"><span data-stu-id="d70c2-122">![Transformed Climber](./media/transformedclimber.png "TransformedClimber")</span></span>  
  
 <span data-ttu-id="d70c2-123">Die folgende Abbildung zeigt eine ähnliche Transformation angewendet auf einer Metadatei an.</span><span class="sxs-lookup"><span data-stu-id="d70c2-123">The following illustration shows a similar transformation applied to a metafile.</span></span>  
  
 <span data-ttu-id="d70c2-124">![Transformiert die Metadatei](./media/transformedmetafile.png "TransformedMetafile")</span><span class="sxs-lookup"><span data-stu-id="d70c2-124">![Transformed Metafile](./media/transformedmetafile.png "TransformedMetafile")</span></span>  
  
 <span data-ttu-id="d70c2-125">Im folgenden Beispiel wird die Bilder in der ersten Abbildung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d70c2-125">The following example produces the images shown in the first illustration.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d70c2-126">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d70c2-126">Compiling the Code</span></span>  
 <span data-ttu-id="d70c2-127">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs>`e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="d70c2-127">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="d70c2-128">Achten Sie darauf, ersetzen Sie dies `Stripes.bmp` durch den Pfad zu einem Bild, das auf Ihrem System gültig ist.</span><span class="sxs-lookup"><span data-stu-id="d70c2-128">Make sure to replace `Stripes.bmp` with the path to an image that is valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d70c2-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d70c2-129">See also</span></span>
- [<span data-ttu-id="d70c2-130">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="d70c2-130">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
