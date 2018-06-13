---
title: 'Gewusst wie: Erstellen von Miniaturbildern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 870ea223698e48438bd4dd08597d0a6ab79cec27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521484"
---
# <a name="how-to-create-thumbnail-images"></a><span data-ttu-id="93e05-102">Gewusst wie: Erstellen von Miniaturbildern</span><span class="sxs-lookup"><span data-stu-id="93e05-102">How to: Create Thumbnail Images</span></span>
<span data-ttu-id="93e05-103">Ein Miniaturbild ist eine kleine Version eines Bilds.</span><span class="sxs-lookup"><span data-stu-id="93e05-103">A thumbnail image is a small version of an image.</span></span> <span data-ttu-id="93e05-104">Sie können ein Miniaturbild erstellen, durch Aufrufen der <xref:System.Drawing.Image.GetThumbnailImage%2A> Methode ein <xref:System.Drawing.Image> Objekt.</span><span class="sxs-lookup"><span data-stu-id="93e05-104">You can create a thumbnail image by calling the <xref:System.Drawing.Image.GetThumbnailImage%2A> method of an <xref:System.Drawing.Image> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93e05-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93e05-105">Example</span></span>  
 <span data-ttu-id="93e05-106">Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus einer JPG-Datei.</span><span class="sxs-lookup"><span data-stu-id="93e05-106">The following example constructs an <xref:System.Drawing.Image> object from a JPG file.</span></span> <span data-ttu-id="93e05-107">Das ursprüngliche Bild verfügt über eine Breite von 640 Pixel und eine Höhe von 479 Pixel.</span><span class="sxs-lookup"><span data-stu-id="93e05-107">The original image has a width of 640 pixels and a height of 479 pixels.</span></span> <span data-ttu-id="93e05-108">Der Code erstellt eine Miniaturansicht Image mit einer Breite von 100 Pixeln und eine Höhe von 100 Pixel.</span><span class="sxs-lookup"><span data-stu-id="93e05-108">The code creates a thumbnail image that has a width of 100 pixels and a height of 100 pixels.</span></span>  
  
 <span data-ttu-id="93e05-109">Die folgende Abbildung zeigt die Miniaturansicht.</span><span class="sxs-lookup"><span data-stu-id="93e05-109">The following illustration shows the thumbnail image.</span></span>  
  
 <span data-ttu-id="93e05-110">![Miniaturansicht](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")</span><span class="sxs-lookup"><span data-stu-id="93e05-110">![Thumbnail Image](../../../../docs/framework/winforms/advanced/media/thumbnail1.png "Thumbnail1")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93e05-111">In diesem Beispiel ist eine Rückrufmethode deklariert, aber nie verwendet.</span><span class="sxs-lookup"><span data-stu-id="93e05-111">In this example, a callback method is declared, but never used.</span></span> <span data-ttu-id="93e05-112">Alle Versionen von GDI + unterstützt.</span><span class="sxs-lookup"><span data-stu-id="93e05-112">This supports all versions of GDI+.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="93e05-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="93e05-113">Compiling the Code</span></span>  
 <span data-ttu-id="93e05-114">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, einen Parameter des <xref:System.Windows.Forms.Control.Paint>-Ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="93e05-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="93e05-115">Um das Beispiel auszuführen, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="93e05-115">To run the example, follow these steps:</span></span>  
  
1.  <span data-ttu-id="93e05-116">Erstellen Sie eine neue Windows Forms-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="93e05-116">Create a new Windows Forms application.</span></span>  
  
2.  <span data-ttu-id="93e05-117">Fügen Sie den Beispielcode, in das Formular.</span><span class="sxs-lookup"><span data-stu-id="93e05-117">Add the example code to the form.</span></span>  
  
3.  <span data-ttu-id="93e05-118">Erstellen Sie einen Ereignishandler für des Formulars <xref:System.Windows.Forms.Control.Paint> Ereignis</span><span class="sxs-lookup"><span data-stu-id="93e05-118">Create a handler for the form's <xref:System.Windows.Forms.Control.Paint> event</span></span>  
  
4.  <span data-ttu-id="93e05-119">In der <xref:System.Windows.Forms.Control.Paint> Handler, rufen die `GetThumbnail` Methode und übergeben Sie `e` für <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="93e05-119">In the <xref:System.Windows.Forms.Control.Paint> handler, call the `GetThumbnail` method and pass `e` for <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
5.  <span data-ttu-id="93e05-120">Suchen von Abbilddateien, die eine Miniaturansicht der machen möchten.</span><span class="sxs-lookup"><span data-stu-id="93e05-120">Find an image file that you want to make a thumbnail of.</span></span>  
  
6.  <span data-ttu-id="93e05-121">In der `GetThumbnail` -Methode, geben Sie den Pfad und Dateinamen an, in das Abbild.</span><span class="sxs-lookup"><span data-stu-id="93e05-121">In the `GetThumbnail` method, specify the path and file name to your image.</span></span>  
  
7.  <span data-ttu-id="93e05-122">Drücken Sie F5, um das Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="93e05-122">Press F5 to run the example.</span></span>  
  
     <span data-ttu-id="93e05-123">Ein Miniaturbild Maßen 100 x 100 wird auf dem Formular angezeigt.</span><span class="sxs-lookup"><span data-stu-id="93e05-123">A 100 by 100 thumbnail image appears on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93e05-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93e05-124">See Also</span></span>  
 [<span data-ttu-id="93e05-125">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="93e05-125">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="93e05-126">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="93e05-126">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
