---
title: 'Vorgehensweise: Laden und Anzeigen von Metadateien'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 39b7251b2789c7410e1d59b4aa7990a2f73055fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229354"
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="ec253-102">Vorgehensweise: Laden und Anzeigen von Metadateien</span><span class="sxs-lookup"><span data-stu-id="ec253-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="ec253-103">Die <xref:System.Drawing.Imaging.Metafile> -Klasse, die erbt die <xref:System.Drawing.Image> Klasse, stellt Methoden zum Aufzeichnen, anzeigen und Überprüfen von Rasterbildern.</span><span class="sxs-lookup"><span data-stu-id="ec253-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec253-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec253-104">Example</span></span>  
 <span data-ttu-id="ec253-105">Um einen Vektorbild (Metafile) auf dem Bildschirm anzuzeigen, müssen Sie eine <xref:System.Drawing.Imaging.Metafile> Objekt und ein <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="ec253-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="ec253-106">Übergeben Sie den Namen einer Datei (oder einen Stream) zu einem <xref:System.Drawing.Imaging.Metafile> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="ec253-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="ec253-107">Nach der Erstellung einer <xref:System.Drawing.Imaging.Metafile> Objekt, und übergeben, die <xref:System.Drawing.Imaging.Metafile> -Objekt an die <xref:System.Drawing.Graphics.DrawImage%2A> -Methode der ein <xref:System.Drawing.Graphics> Objekt.</span><span class="sxs-lookup"><span data-stu-id="ec253-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="ec253-108">Das Beispiel erstellt eine <xref:System.Drawing.Imaging.Metafile> Objekt aus einer Datei EMF (Erweiterte Metadatei) und anschließend zeichnet das Bild mit der linken oberen Ecke auf ("60", "10").</span><span class="sxs-lookup"><span data-stu-id="ec253-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="ec253-109">Die folgende Abbildung zeigt die Metadatei an der angegebenen Position gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ec253-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="ec253-110">![Abbildung Position](./media/imageposition2.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="ec253-110">![Image Position](./media/imageposition2.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ec253-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ec253-111">Compiling the Code</span></span>  
 <span data-ttu-id="ec253-112">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, ein Parameter von der <xref:System.Windows.Forms.Control.Paint> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="ec253-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec253-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec253-113">See also</span></span>

- [<span data-ttu-id="ec253-114">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="ec253-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
