---
title: Metadateien in GDI+
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
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b75ceb08df0454172a000d5d1ad15445f685ddf
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="cd082-102">Metadateien in GDI+</span><span class="sxs-lookup"><span data-stu-id="cd082-102">Metafiles in GDI+</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="cd082-103">Stellt die <xref:System.Drawing.Imaging.Metafile> Klasse, damit Sie aufzeichnen und Anzeigen von Metadateien.</span><span class="sxs-lookup"><span data-stu-id="cd082-103"> provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="cd082-104">Eine Metadatei, die so genannte ein Vektor-Image ist ein Bild, das als eine Sequenz von Zeichnen-Befehle und Einstellungen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="cd082-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="cd082-105">Die Befehle und Einstellungen aufgezeichnet werden, einem <xref:System.Drawing.Imaging.Metafile> Objekt im Arbeitsspeicher gespeichert oder in eine Datei oder den Stream gespeichert werden kann.</span><span class="sxs-lookup"><span data-stu-id="cd082-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="cd082-106">Metadatei-Formate</span><span class="sxs-lookup"><span data-stu-id="cd082-106">Metafile Formats</span></span>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="cd082-107">Metadateien, die in den folgenden Formaten gespeichert wurden, können angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="cd082-107"> can display metafiles that have been stored in the following formats:</span></span>  
  
-   <span data-ttu-id="cd082-108">Windows-Metadatei (WMF)</span><span class="sxs-lookup"><span data-stu-id="cd082-108">Windows Metafile (WMF)</span></span>  
  
-   <span data-ttu-id="cd082-109">Erweiterte Metadatei (Enhanced Metafile, EMF)</span><span class="sxs-lookup"><span data-stu-id="cd082-109">Enhanced Metafile (EMF)</span></span>  
  
-   <span data-ttu-id="cd082-110">EMF +</span><span class="sxs-lookup"><span data-stu-id="cd082-110">EMF+</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="cd082-111">kann Metadateien in den Formaten EMF und EMF +, jedoch nicht in der WMF-Format aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="cd082-111"> can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="cd082-112">EMF + ist eine Erweiterung, EMF, der ermöglicht [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Datensätze gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="cd082-112">EMF+ is an extension to EMF that allows [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] records to be stored.</span></span> <span data-ttu-id="cd082-113">Es gibt zwei Variationen auf dem EMF-Format: EMF + Only und EMF + Dual.</span><span class="sxs-lookup"><span data-stu-id="cd082-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="cd082-114">EMF + nur Metadateien enthalten nur [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Datensätze.</span><span class="sxs-lookup"><span data-stu-id="cd082-114">EMF+ Only metafiles contain only [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] records.</span></span> <span data-ttu-id="cd082-115">Solche Metadateien können angezeigt werden, indem [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] jedoch nicht von [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd082-115">Such metafiles can be displayed by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] but not by [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span> <span data-ttu-id="cd082-116">EMF + Dual Metadateien enthalten [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Datensätze.</span><span class="sxs-lookup"><span data-stu-id="cd082-116">EMF+ Dual metafiles contain [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] records.</span></span> <span data-ttu-id="cd082-117">Jede [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Datensatz in einer EMF + Dual Metadatei wird zusammen mit einer alternativen [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Datensatz.</span><span class="sxs-lookup"><span data-stu-id="cd082-117">Each [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record in an EMF+ Dual metafile is paired with an alternate [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] record.</span></span> <span data-ttu-id="cd082-118">Solche Metadateien können angezeigt werden, indem [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] oder [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd082-118">Such metafiles can be displayed by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] or by [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 <span data-ttu-id="cd082-119">Das folgende Beispiel zeigt eine Metadatei, die zuvor als Datei gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="cd082-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="cd082-120">Die Metadatei wird angezeigt, mit der linken oberen Ecke an (100, 100).</span><span class="sxs-lookup"><span data-stu-id="cd082-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="cd082-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd082-121">See Also</span></span>  
 [<span data-ttu-id="cd082-122">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="cd082-122">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
