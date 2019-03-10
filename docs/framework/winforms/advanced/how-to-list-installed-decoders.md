---
title: 'Vorgehensweise: Auflisten installierter Decoder'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
ms.openlocfilehash: c40bb79dde4a9baf8b84f3cda5fdabc6e30ad0b5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717530"
---
# <a name="how-to-list-installed-decoders"></a><span data-ttu-id="64e4b-102">Vorgehensweise: Auflisten installierter Decoder</span><span class="sxs-lookup"><span data-stu-id="64e4b-102">How to: List Installed Decoders</span></span>
<span data-ttu-id="64e4b-103">Möglicherweise möchten die Liste die auf einem Computer verfügbaren Bilddecoder, um festzustellen, ob Ihre Anwendung ein bestimmtes Bildformat Datei lesen kann.</span><span class="sxs-lookup"><span data-stu-id="64e4b-103">You may want to list the image decoders available on a computer, to determine whether your application can read a particular image file format.</span></span> <span data-ttu-id="64e4b-104">Die <xref:System.Drawing.Imaging.ImageCodecInfo> -Klasse stellt die <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> statische Methoden, damit Sie bestimmen können, welche Bilddecoder verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="64e4b-104">The <xref:System.Drawing.Imaging.ImageCodecInfo> class provides the <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> static methods so that you can determine which image decoders are available.</span></span> <span data-ttu-id="64e4b-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> Gibt ein Array von <xref:System.Drawing.Imaging.ImageCodecInfo> Objekte.</span><span class="sxs-lookup"><span data-stu-id="64e4b-105"><xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> returns an array of <xref:System.Drawing.Imaging.ImageCodecInfo> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64e4b-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="64e4b-106">Example</span></span>  
 <span data-ttu-id="64e4b-107">Das folgende Codebeispiel gibt die Liste der installierten Decoder und zugehörigen Eigenschaftswerte enthält.</span><span class="sxs-lookup"><span data-stu-id="64e4b-107">The following code example outputs the list of installed decoders and their property values.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#2](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="64e4b-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="64e4b-108">Compiling the Code</span></span>  
 <span data-ttu-id="64e4b-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="64e4b-109">This example requires:</span></span>  
  
-   <span data-ttu-id="64e4b-110">Eine Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="64e4b-110">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="64e4b-111">Ein <xref:System.Windows.Forms.PaintEventArgs>, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="64e4b-111">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64e4b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64e4b-112">See also</span></span>
- [<span data-ttu-id="64e4b-113">Vorgehensweise: Auflisten installierter Encoder</span><span class="sxs-lookup"><span data-stu-id="64e4b-113">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="64e4b-114">Verwenden von Bildencodern und -decodern in Managed GDI+</span><span class="sxs-lookup"><span data-stu-id="64e4b-114">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
