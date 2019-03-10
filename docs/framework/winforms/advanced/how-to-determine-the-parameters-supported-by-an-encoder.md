---
title: 'Vorgehensweise: Ermitteln der von einem Encoder unterstützten Parameter'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: f5af00833c8d8373444b475673709d902598d9d0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719701"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a><span data-ttu-id="0becb-102">Vorgehensweise: Ermitteln der von einem Encoder unterstützten Parameter</span><span class="sxs-lookup"><span data-stu-id="0becb-102">How to: Determine the Parameters Supported by an Encoder</span></span>
<span data-ttu-id="0becb-103">Sie können anpassen, Imageparameter, z. B. Qualität und der Komprimierung, jedoch müssen Sie wissen, welche Parameter von einem angegebenen Bildencoder unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="0becb-103">You can adjust image parameters, such as quality and compression level, but you must know which parameters are supported by a given image encoder.</span></span> <span data-ttu-id="0becb-104">Die <xref:System.Drawing.Image> -Klasse stellt die <xref:System.Drawing.Image.GetEncoderParameterList%2A> Methode, damit Sie bestimmen können, welche Parameter für einen bestimmten Encoder unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="0becb-104">The <xref:System.Drawing.Image> class provides the <xref:System.Drawing.Image.GetEncoderParameterList%2A> method so that you can determine which image parameters are supported for a particular encoder.</span></span> <span data-ttu-id="0becb-105">Sie geben den Encoder mit einer GUID.</span><span class="sxs-lookup"><span data-stu-id="0becb-105">You specify the encoder with a GUID.</span></span> <span data-ttu-id="0becb-106">Die <xref:System.Drawing.Image.GetEncoderParameterList%2A> Methode gibt ein Array von <xref:System.Drawing.Imaging.EncoderParameter> Objekte.</span><span class="sxs-lookup"><span data-stu-id="0becb-106">The <xref:System.Drawing.Image.GetEncoderParameterList%2A> method returns an array of <xref:System.Drawing.Imaging.EncoderParameter> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0becb-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0becb-107">Example</span></span>  
 <span data-ttu-id="0becb-108">Der folgende Beispielcode gibt die unterstützten Parameter für den JPEG-Encoder.</span><span class="sxs-lookup"><span data-stu-id="0becb-108">The following example code outputs the supported parameters for the JPEG encoder.</span></span> <span data-ttu-id="0becb-109">Verwenden Sie die Liste der Parameterkategorien und zugehörigen GUIDs in der <xref:System.Drawing.Imaging.Encoder> Übersicht über die Klasse aus, um die Kategorie für jeden Parameter zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="0becb-109">Use the list of parameter categories and associated GUIDs in the <xref:System.Drawing.Imaging.Encoder> class overview to determine the category for each parameter.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0becb-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0becb-110">Compiling the Code</span></span>  
 <span data-ttu-id="0becb-111">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0becb-111">This example requires:</span></span>  
  
-   <span data-ttu-id="0becb-112">Eine Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="0becb-112">A Windows Forms application.</span></span>  
  
-   <span data-ttu-id="0becb-113">Ein <xref:System.Windows.Forms.PaintEventArgs>, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="0becb-113">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0becb-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0becb-114">See also</span></span>
- [<span data-ttu-id="0becb-115">Vorgehensweise: Auflisten installierter Encoder</span><span class="sxs-lookup"><span data-stu-id="0becb-115">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="0becb-116">Typen von Bitmaps</span><span class="sxs-lookup"><span data-stu-id="0becb-116">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="0becb-117">Verwenden von Bildencodern und -decodern in Managed GDI+</span><span class="sxs-lookup"><span data-stu-id="0becb-117">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
