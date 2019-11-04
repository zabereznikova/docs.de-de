---
title: 'Gewusst wie: Laden und Anzeigen von Metadateien'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 6c17e0b2d023ccf80b0d32301b7ee6765edcae9f
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424822"
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="9b42e-102">Gewusst wie: Laden und Anzeigen von Metadateien</span><span class="sxs-lookup"><span data-stu-id="9b42e-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="9b42e-103">Die <xref:System.Drawing.Imaging.Metafile>-Klasse, die von der <xref:System.Drawing.Image>-Klasse erbt, stellt Methoden zum Aufzeichnen, anzeigen und untersuchen von Vektorbildern bereit.</span><span class="sxs-lookup"><span data-stu-id="9b42e-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b42e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b42e-104">Example</span></span>  
 <span data-ttu-id="9b42e-105">Zum Anzeigen eines Vektor Bilds (Metadatei) auf dem Bildschirm benötigen Sie ein <xref:System.Drawing.Imaging.Metafile>-Objekt und ein <xref:System.Drawing.Graphics>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="9b42e-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="9b42e-106">Übergeben Sie den Namen einer Datei (oder eines Datenstroms) an einen <xref:System.Drawing.Imaging.Metafile> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="9b42e-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="9b42e-107">Nachdem Sie ein <xref:System.Drawing.Imaging.Metafile>-Objekt erstellt haben, übergeben Sie das <xref:System.Drawing.Imaging.Metafile>-Objekt an die <xref:System.Drawing.Graphics.DrawImage%2A>-Methode eines <xref:System.Drawing.Graphics> Objekts.</span><span class="sxs-lookup"><span data-stu-id="9b42e-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="9b42e-108">Im Beispiel wird ein <xref:System.Drawing.Imaging.Metafile> Objekt aus einer EMF-Datei (Enhanced Metafile) erstellt und dann mit der linken oberen Ecke bei (60, 10) gezeichnet.</span><span class="sxs-lookup"><span data-stu-id="9b42e-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="9b42e-109">In der folgenden Abbildung ist die an der angegebenen Position gezeichnete Metadatendatei dargestellt.</span><span class="sxs-lookup"><span data-stu-id="9b42e-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="9b42e-110">![Screenshot der Bildposition](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="9b42e-110">![Screenshot showing image position.](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9b42e-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9b42e-111">Compiling the Code</span></span>  
 <span data-ttu-id="9b42e-112">Das vorherige Beispiel wurde für die Verwendung mit Windows Forms entwickelt und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, bei dem es sich um einen Parameter des <xref:System.Windows.Forms.Control.Paint> Ereignis Handlers handelt.</span><span class="sxs-lookup"><span data-stu-id="9b42e-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b42e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b42e-113">See also</span></span>

- [<span data-ttu-id="9b42e-114">Arbeiten mit Bildern, Bitmaps, Symbolen und Metadateien</span><span class="sxs-lookup"><span data-stu-id="9b42e-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
