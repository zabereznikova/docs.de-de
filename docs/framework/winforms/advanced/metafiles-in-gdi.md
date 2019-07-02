---
title: Metadateien in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504588"
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="c0c63-102">Metadateien in GDI+</span><span class="sxs-lookup"><span data-stu-id="c0c63-102">Metafiles in GDI+</span></span>
<span data-ttu-id="c0c63-103">GDI + bietet die <xref:System.Drawing.Imaging.Metafile> Klasse, sodass Sie aufzeichnen und Anzeigen von Metadateien.</span><span class="sxs-lookup"><span data-stu-id="c0c63-103">GDI+ provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="c0c63-104">Eine Metadatei, auch einen Vektor Image bezeichnet, handelt es sich um ein Bild, das als eine Sequenz von Zeichnen-Befehle und Einstellungen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="c0c63-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="c0c63-105">Die Befehle und Einstellungen aufgezeichnet werden, einem <xref:System.Drawing.Imaging.Metafile> Objekt im Arbeitsspeicher gespeichert oder in einer Datei oder einem Stream gespeichert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c0c63-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="c0c63-106">Metadatei-Formaten</span><span class="sxs-lookup"><span data-stu-id="c0c63-106">Metafile Formats</span></span>  
 <span data-ttu-id="c0c63-107">GDI + kann Metadateien anzeigen, die in den folgenden Formaten gespeichert wurden:</span><span class="sxs-lookup"><span data-stu-id="c0c63-107">GDI+ can display metafiles that have been stored in the following formats:</span></span>  
  
- <span data-ttu-id="c0c63-108">Windows-Metadateien (WMF)</span><span class="sxs-lookup"><span data-stu-id="c0c63-108">Windows Metafile (WMF)</span></span>  
  
- <span data-ttu-id="c0c63-109">Erweiterte Metadatei (Enhanced Metafile, EMF)</span><span class="sxs-lookup"><span data-stu-id="c0c63-109">Enhanced Metafile (EMF)</span></span>  
  
- <span data-ttu-id="c0c63-110">EMF+</span><span class="sxs-lookup"><span data-stu-id="c0c63-110">EMF+</span></span>  
  
 <span data-ttu-id="c0c63-111">GDI + kann Metadateien im EMF und EMF +-Format, aber nicht in der WMF-Formats aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="c0c63-111">GDI+ can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="c0c63-112">EMF + ist eine Erweiterung, EMF, die von GDI +-Datensätze gespeichert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c0c63-112">EMF+ is an extension to EMF that allows GDI+ records to be stored.</span></span> <span data-ttu-id="c0c63-113">Es gibt zwei Variationen auf dem EMF +-Format: EMF + nur und duale EMF +.</span><span class="sxs-lookup"><span data-stu-id="c0c63-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="c0c63-114">EMF + nur Metadateien enthalten nur um GDI +-Datensätze.</span><span class="sxs-lookup"><span data-stu-id="c0c63-114">EMF+ Only metafiles contain only GDI+ records.</span></span> <span data-ttu-id="c0c63-115">Solche Metadateien können von GDI +, aber nicht von GDI angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c0c63-115">Such metafiles can be displayed by GDI+ but not by GDI.</span></span> <span data-ttu-id="c0c63-116">Duale EMF +-Metadateien enthalten GDI + und GDI-Datensätze.</span><span class="sxs-lookup"><span data-stu-id="c0c63-116">EMF+ Dual metafiles contain GDI+ and GDI records.</span></span> <span data-ttu-id="c0c63-117">Eine alternative GDI-Datensatz ist jeder GDI +-Datensatz in eine duale EMF +-Metadatei zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c0c63-117">Each GDI+ record in an EMF+ Dual metafile is paired with an alternate GDI record.</span></span> <span data-ttu-id="c0c63-118">Solche Metadateien können von GDI oder GDI angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c0c63-118">Such metafiles can be displayed by GDI+ or by GDI.</span></span>  
  
 <span data-ttu-id="c0c63-119">Das folgende Beispiel zeigt eine Metadatei, die zuvor als Datei gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="c0c63-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="c0c63-120">Die Metadatei wird angezeigt, mit der linken oberen Ecke an (100, 100).</span><span class="sxs-lookup"><span data-stu-id="c0c63-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="c0c63-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0c63-121">See also</span></span>

- [<span data-ttu-id="c0c63-122">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="c0c63-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
