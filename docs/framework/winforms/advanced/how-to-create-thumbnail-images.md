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
ms.openlocfilehash: 786a92d99f5e7a0c27f502efa9a5fe617ac4d4d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923756"
---
# <a name="how-to-create-thumbnail-images"></a><span data-ttu-id="f116f-102">Vorgehensweise: Erstellen von Miniaturbildern</span><span class="sxs-lookup"><span data-stu-id="f116f-102">How to: Create Thumbnail Images</span></span>
<span data-ttu-id="f116f-103">Bei einem Miniaturbild handelt es sich um eine kleine Version eines Bilds.</span><span class="sxs-lookup"><span data-stu-id="f116f-103">A thumbnail image is a small version of an image.</span></span> <span data-ttu-id="f116f-104">Sie können ein Miniaturbild erstellen, indem Sie <xref:System.Drawing.Image.GetThumbnailImage%2A> die-Methode <xref:System.Drawing.Image> eines-Objekts aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f116f-104">You can create a thumbnail image by calling the <xref:System.Drawing.Image.GetThumbnailImage%2A> method of an <xref:System.Drawing.Image> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f116f-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f116f-105">Example</span></span>  
 <span data-ttu-id="f116f-106">Im folgenden Beispiel wird ein <xref:System.Drawing.Image> -Objekt aus einer JPG-Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="f116f-106">The following example constructs an <xref:System.Drawing.Image> object from a JPG file.</span></span> <span data-ttu-id="f116f-107">Das ursprüngliche Bild hat eine Breite von 640 Pixeln und eine Höhe von 479 Pixel.</span><span class="sxs-lookup"><span data-stu-id="f116f-107">The original image has a width of 640 pixels and a height of 479 pixels.</span></span> <span data-ttu-id="f116f-108">Der Code erstellt ein Miniaturbild mit einer Breite von 100 Pixeln und einer Höhe von 100 Pixeln.</span><span class="sxs-lookup"><span data-stu-id="f116f-108">The code creates a thumbnail image that has a width of 100 pixels and a height of 100 pixels.</span></span>  
  
 <span data-ttu-id="f116f-109">Die folgende Abbildung zeigt das Miniaturbild:</span><span class="sxs-lookup"><span data-stu-id="f116f-109">The following illustration shows the thumbnail image:</span></span>  
  
 ![Screenshot, der die Miniaturansicht der Ausgabe anzeigt.](./media/how-to-create-thumbnail-images/construct-thumbnail-image.png)  
  
> [!NOTE]
> <span data-ttu-id="f116f-111">In diesem Beispiel wird eine Rückruf Methode deklariert, aber nie verwendet.</span><span class="sxs-lookup"><span data-stu-id="f116f-111">In this example, a callback method is declared, but never used.</span></span> <span data-ttu-id="f116f-112">Dies unterstützt alle Versionen von GDI+.</span><span class="sxs-lookup"><span data-stu-id="f116f-112">This supports all versions of GDI+.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.WorkingWithImages#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f116f-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="f116f-113">Compiling the Code</span></span>  
 <span data-ttu-id="f116f-114">Das vorherige Beispiel wurde für die Verwendung mit Windows Forms entwickelt und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, was ein Parameter des- <xref:System.Windows.Forms.Control.Paint> Ereignis Handlers ist.</span><span class="sxs-lookup"><span data-stu-id="f116f-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="f116f-115">Um das Beispiel auszuführen, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f116f-115">To run the example, follow these steps:</span></span>  
  
1. <span data-ttu-id="f116f-116">Erstellen Sie eine neue Windows Forms-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f116f-116">Create a new Windows Forms application.</span></span>  
  
2. <span data-ttu-id="f116f-117">Fügen Sie dem Formular den Beispielcode hinzu.</span><span class="sxs-lookup"><span data-stu-id="f116f-117">Add the example code to the form.</span></span>  
  
3. <span data-ttu-id="f116f-118">Erstellen eines Handlers für das <xref:System.Windows.Forms.Control.Paint> Ereignis des Formulars</span><span class="sxs-lookup"><span data-stu-id="f116f-118">Create a handler for the form's <xref:System.Windows.Forms.Control.Paint> event</span></span>  
  
4. <span data-ttu-id="f116f-119">Nennen Sie im- `GetThumbnail` `e` <xref:System.Windows.Forms.PaintEventArgs>Handler die-Methode, und übergeben Sie für. <xref:System.Windows.Forms.Control.Paint></span><span class="sxs-lookup"><span data-stu-id="f116f-119">In the <xref:System.Windows.Forms.Control.Paint> handler, call the `GetThumbnail` method and pass `e` for <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
5. <span data-ttu-id="f116f-120">Suchen Sie nach einer Bilddatei, für die Sie eine Miniaturansicht erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="f116f-120">Find an image file that you want to make a thumbnail of.</span></span>  
  
6. <span data-ttu-id="f116f-121">Geben Sie `GetThumbnail` in der-Methode den Pfad und den Dateinamen für das Image an.</span><span class="sxs-lookup"><span data-stu-id="f116f-121">In the `GetThumbnail` method, specify the path and file name to your image.</span></span>  
  
7. <span data-ttu-id="f116f-122">Drücken Sie F5, um das Beispiel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f116f-122">Press F5 to run the example.</span></span>  
  
     <span data-ttu-id="f116f-123">Im Formular wird ein Miniaturbild von 100 nach 100 angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f116f-123">A 100 by 100 thumbnail image appears on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f116f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f116f-124">See also</span></span>

- [<span data-ttu-id="f116f-125">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="f116f-125">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="f116f-126">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="f116f-126">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
