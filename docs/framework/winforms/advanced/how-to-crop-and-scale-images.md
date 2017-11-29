---
title: 'Gewusst wie: Zuschneiden und Skalieren von Bildern'
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
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8fb5d527cd1047197f370c4a9a9b1f8f33461653
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-crop-and-scale-images"></a><span data-ttu-id="32c1f-102">Gewusst wie: Zuschneiden und Skalieren von Bildern</span><span class="sxs-lookup"><span data-stu-id="32c1f-102">How to: Crop and Scale Images</span></span>
<span data-ttu-id="32c1f-103">Die <xref:System.Drawing.Graphics> Klasse stellt mehrere <xref:System.Drawing.Graphics.DrawImage%2A> Methoden, von denen einige Quell- und Zielschemas Rechteck Parameter haben, die zum Zuschneiden und Skalieren von Bildern verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="32c1f-103">The <xref:System.Drawing.Graphics> class provides several <xref:System.Drawing.Graphics.DrawImage%2A> methods, some of which have source and destination rectangle parameters that you can use to crop and scale images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32c1f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="32c1f-104">Example</span></span>  
 <span data-ttu-id="32c1f-105">Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus der Datenträgerdatei Apple.gif.</span><span class="sxs-lookup"><span data-stu-id="32c1f-105">The following example constructs an <xref:System.Drawing.Image> object from the disk file Apple.gif.</span></span> <span data-ttu-id="32c1f-106">Der Code zeichnet das gesamte Apple-Bild in seiner ursprünglichen Größe an.</span><span class="sxs-lookup"><span data-stu-id="32c1f-106">The code draws the entire apple image in its original size.</span></span> <span data-ttu-id="32c1f-107">Der Code ruft dann die <xref:System.Drawing.Graphics.DrawImage%2A> Methode von einer <xref:System.Drawing.Graphics> Objekt, das einen Teil der Apple-Bildes in ein Zielrechteck zu zeichnen, die größer als das ursprüngliche Apple-Image ist.</span><span class="sxs-lookup"><span data-stu-id="32c1f-107">The code then calls the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object to draw a portion of the apple image in a destination rectangle that is larger than the original apple image.</span></span>  
  
 <span data-ttu-id="32c1f-108">Die <xref:System.Drawing.Graphics.DrawImage%2A> Methode bestimmt, welcher Teil der Apple gezogen werden unter Verwendung des fünften und sechsten Argumente suchen soll.</span><span class="sxs-lookup"><span data-stu-id="32c1f-108">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines which portion of the apple to draw by looking at the source rectangle, which is specified by the third, fourth, fifth, and sixth arguments.</span></span> <span data-ttu-id="32c1f-109">In diesem Fall wird die Apple 75 Prozent der Breite und 75 Prozent der Höhe zugeschnitten.</span><span class="sxs-lookup"><span data-stu-id="32c1f-109">In this case, the apple is cropped to 75 percent of its width and 75 percent of its height.</span></span>  
  
 <span data-ttu-id="32c1f-110">Die <xref:System.Drawing.Graphics.DrawImage%2A> Methode bestimmt, wo Sie zugeschnittene Apple gezeichnet werden soll und wie groß die zugeschnittenen Apfels anhand des Zielrechtecks, dies ist durch das zweite Argument angegeben.</span><span class="sxs-lookup"><span data-stu-id="32c1f-110">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines where to draw the cropped apple and how big to make the cropped apple by looking at the destination rectangle, which is specified by the second argument.</span></span> <span data-ttu-id="32c1f-111">In diesem Fall ist das Zielrechteck 30 Prozent breiter und 30 Prozent höher als das ursprüngliche Image.</span><span class="sxs-lookup"><span data-stu-id="32c1f-111">In this case, the destination rectangle is 30 percent wider and 30 percent taller than the original image.</span></span>  
  
 <span data-ttu-id="32c1f-112">Die folgende Abbildung zeigt die ursprüngliche Apple und die skalierte Apple zugeschnitten.</span><span class="sxs-lookup"><span data-stu-id="32c1f-112">The following illustration shows the original apple and the scaled, cropped apple.</span></span>  
  
 <span data-ttu-id="32c1f-113">![Zuschneiden und skalieren](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")</span><span class="sxs-lookup"><span data-stu-id="32c1f-113">![Crop & Scale](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="32c1f-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="32c1f-114">Compiling the Code</span></span>  
 <span data-ttu-id="32c1f-115">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="32c1f-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="32c1f-116">Achten Sie darauf, ersetzen Sie `Apple.gif` mit einem Dateinamen und Pfad, die auf Ihrem System gültig sind.</span><span class="sxs-lookup"><span data-stu-id="32c1f-116">Make sure to replace `Apple.gif` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32c1f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32c1f-117">See Also</span></span>  
 [<span data-ttu-id="32c1f-118">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="32c1f-118">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="32c1f-119">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="32c1f-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
