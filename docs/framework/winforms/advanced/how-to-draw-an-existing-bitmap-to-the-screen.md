---
title: 'Gewusst wie: Zeichnen einer vorhandenen Bitmap auf dem Bildschirm'
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
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f435c397832e8f64b2bf911a59aae7578ffd3bdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a><span data-ttu-id="d7912-102">Gewusst wie: Zeichnen einer vorhandenen Bitmap auf dem Bildschirm</span><span class="sxs-lookup"><span data-stu-id="d7912-102">How to: Draw an Existing Bitmap to the Screen</span></span>
<span data-ttu-id="d7912-103">Sie können ein vorhandenes Image einfach auf dem Bildschirm zeichnen.</span><span class="sxs-lookup"><span data-stu-id="d7912-103">You can easily draw an existing image on the screen.</span></span> <span data-ttu-id="d7912-104">Zunächst müssen Sie erstellen eine <xref:System.Drawing.Bitmap> Objekt mithilfe der Bitmapkonstruktor, der einen Dateinamen akzeptiert <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="d7912-104">First you need to create a <xref:System.Drawing.Bitmap> object by using the bitmap constructor that takes a file name, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.</span></span> <span data-ttu-id="d7912-105">Dieser Konstruktor akzeptiert Bilder mit unterschiedlichen Dateiformaten, z. B. BMP, GIF, JPEG, PNG und TIFF.</span><span class="sxs-lookup"><span data-stu-id="d7912-105">This constructor accepts images with several different file formats, including BMP, GIF, JPEG, PNG, and TIFF.</span></span> <span data-ttu-id="d7912-106">Nach der Erstellung der <xref:System.Drawing.Bitmap> Objekt, und übergeben, die <xref:System.Drawing.Bitmap> -Objekt an die <xref:System.Drawing.Graphics.DrawImage%2A> Methode von einer <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="d7912-106">After you have created the <xref:System.Drawing.Bitmap> object, pass that <xref:System.Drawing.Bitmap> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7912-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7912-107">Example</span></span>  
 <span data-ttu-id="d7912-108">In diesem Beispiel wird ein <xref:System.Drawing.Bitmap> Objekt aus einer JPEG-Datei, und klicken Sie dann zeichnet die Bitmap mit der linken oberen Ecke an (60, 10).</span><span class="sxs-lookup"><span data-stu-id="d7912-108">This example creates a <xref:System.Drawing.Bitmap> object from a JPEG file and then draws the bitmap with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="d7912-109">Die folgende Abbildung zeigt die Bitmap gezeichnet, die an der angegebenen Position.</span><span class="sxs-lookup"><span data-stu-id="d7912-109">The following illustration shows the bitmap drawn at the specified location.</span></span>  
  
 <span data-ttu-id="d7912-110">![Abbildung Position](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")</span><span class="sxs-lookup"><span data-stu-id="d7912-110">![Image Position](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7912-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="d7912-111">Compiling the Code</span></span>  
 <span data-ttu-id="d7912-112">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="d7912-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7912-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7912-113">See Also</span></span>  
 [<span data-ttu-id="d7912-114">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d7912-114">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="d7912-115">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="d7912-115">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
