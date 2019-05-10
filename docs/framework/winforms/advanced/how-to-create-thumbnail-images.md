---
title: 'Vorgehensweise: Erstellen von Miniaturbildern'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thumbnail images [Windows Forms], creating
- images [Windows Forms], creating thumbnails
ms.assetid: e956242a-1e5b-4217-a3cf-5f3fb45d00ba
ms.openlocfilehash: 275041372bd5e7da5dd0b32dc0a3d70a38bd0dcd
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063772"
---
# <a name="how-to-create-thumbnail-images"></a><span data-ttu-id="38145-102">Vorgehensweise: Erstellen von Miniaturbildern</span><span class="sxs-lookup"><span data-stu-id="38145-102">How to: Create Thumbnail Images</span></span>
<span data-ttu-id="38145-103">Eine Miniaturansicht ist eine kleine Version eines Bilds.</span><span class="sxs-lookup"><span data-stu-id="38145-103">A thumbnail image is a small version of an image.</span></span> <span data-ttu-id="38145-104">Sie können ein Miniaturbild erstellen, durch den Aufruf der <xref:System.Drawing.Image.GetThumbnailImage%2A> Methode eine <xref:System.Drawing.Image> Objekt.</span><span class="sxs-lookup"><span data-stu-id="38145-104">You can create a thumbnail image by calling the <xref:System.Drawing.Image.GetThumbnailImage%2A> method of an <xref:System.Drawing.Image> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38145-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="38145-105">Example</span></span>  
 <span data-ttu-id="38145-106">Das folgende Beispiel erstellt eine <xref:System.Drawing.Image> Objekt aus einer JPG-Datei.</span><span class="sxs-lookup"><span data-stu-id="38145-106">The following example constructs an <xref:System.Drawing.Image> object from a JPG file.</span></span> <span data-ttu-id="38145-107">Das ursprüngliche Image verfügt über eine Breite von 640 Pixel und eine Höhe von 479 Pixel.</span><span class="sxs-lookup"><span data-stu-id="38145-107">The original image has a width of 640 pixels and a height of 479 pixels.</span></span> <span data-ttu-id="38145-108">Der Code erstellt ein Miniaturbild, die eine Breite von 100 Pixel und eine Höhe von 100 Pixel aufweist.</span><span class="sxs-lookup"><span data-stu-id="38145-108">The code creates a thumbnail image that has a width of 100 pixels and a height of 100 pixels.</span></span>  
  
 <span data-ttu-id="38145-109">Die folgende Abbildung zeigt das Miniaturbild an:</span><span class="sxs-lookup"><span data-stu-id="38145-109">The following illustration shows the thumbnail image:</span></span>  
  
 ![Screenshot mit der Ausgabe-Miniaturansicht.](./media/how-to-create-thumbnail-images/construct-thumbnail-image.png)  
  
> [!NOTE]
>  <span data-ttu-id="38145-111">In diesem Beispiel wird eine Callback-Methode deklariert, aber nie verwendet.</span><span class="sxs-lookup"><span data-stu-id="38145-111">In this example, a callback method is declared, but never used.</span></span> <span data-ttu-id="38145-112">Alle Versionen von GDI + unterstützt.</span><span class="sxs-lookup"><span data-stu-id="38145-112">This supports all versions of GDI+.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="38145-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="38145-113">Compiling the Code</span></span>  
 <span data-ttu-id="38145-114">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="38145-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="38145-115">Um das Beispiel auszuführen, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="38145-115">To run the example, follow these steps:</span></span>  
  
1. <span data-ttu-id="38145-116">Erstellen Sie eine neue Windows Forms-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="38145-116">Create a new Windows Forms application.</span></span>  
  
2. <span data-ttu-id="38145-117">Fügen Sie den Beispielcode, in das Formular.</span><span class="sxs-lookup"><span data-stu-id="38145-117">Add the example code to the form.</span></span>  
  
3. <span data-ttu-id="38145-118">Erstellen Sie einen Ereignishandler für des Formulars des <xref:System.Windows.Forms.Control.Paint> Ereignis</span><span class="sxs-lookup"><span data-stu-id="38145-118">Create a handler for the form's <xref:System.Windows.Forms.Control.Paint> event</span></span>  
  
4. <span data-ttu-id="38145-119">In der <xref:System.Windows.Forms.Control.Paint> Handler, rufen die `GetThumbnail` Methode und übergeben Sie `e` für <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="38145-119">In the <xref:System.Windows.Forms.Control.Paint> handler, call the `GetThumbnail` method and pass `e` for <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
5. <span data-ttu-id="38145-120">Finden Sie eine Bilddatei, der Sie eine Miniaturansicht erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="38145-120">Find an image file that you want to make a thumbnail of.</span></span>  
  
6. <span data-ttu-id="38145-121">In der `GetThumbnail` Methode, geben Sie den Pfad und Dateinamen an, in Ihrem Image.</span><span class="sxs-lookup"><span data-stu-id="38145-121">In the `GetThumbnail` method, specify the path and file name to your image.</span></span>  
  
7. <span data-ttu-id="38145-122">Drücken Sie F5, um das Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="38145-122">Press F5 to run the example.</span></span>  
  
     <span data-ttu-id="38145-123">Eine Miniaturansicht 100 x 100 wird im Formular angezeigt.</span><span class="sxs-lookup"><span data-stu-id="38145-123">A 100 by 100 thumbnail image appears on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38145-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38145-124">See also</span></span>

- [<span data-ttu-id="38145-125">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="38145-125">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="38145-126">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="38145-126">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
