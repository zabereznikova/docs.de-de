---
title: Windows Forms-Koordinaten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f4b42fd71dacb0071013067dc3c14add96c8aca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-coordinates"></a><span data-ttu-id="2fd6f-102">Windows Forms-Koordinaten</span><span class="sxs-lookup"><span data-stu-id="2fd6f-102">Windows Forms Coordinates</span></span>
<span data-ttu-id="2fd6f-103">Das Koordinatensystem für ein Windows Form basiert auf dem Gerätekoordinaten und die grundlegende Maßeinheit beim Zeichnen in Windows Forms ist die Einheit (in der Regel das Pixel) des Geräts.</span><span class="sxs-lookup"><span data-stu-id="2fd6f-103">The coordinate system for a Windows Form is based on device coordinates, and the basic unit of measure when drawing in Windows Forms is the device unit (typically, the pixel).</span></span> <span data-ttu-id="2fd6f-104">Punkte auf dem Bildschirm werden vom x- und y-Koordinate-Paaren mit den X-Koordinaten, erhöhen das Recht und die y-Koordinaten erhöhen von oben nach unten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2fd6f-104">Points on the screen are described by x- and y-coordinate pairs, with the x-coordinates increasing to the right and the y-coordinates increasing from top to bottom.</span></span> <span data-ttu-id="2fd6f-105">Die Position des Ursprungs, relativ zu dem Bildschirm "" variiert abhängig davon, ob Sie Bildschirm- oder Clientkoordinaten angeben.</span><span class="sxs-lookup"><span data-stu-id="2fd6f-105">The location of the origin, relative to the screen, will vary depending on whether you are specifying screen or client coordinates.</span></span>  
  
## <a name="screen-coordinates"></a><span data-ttu-id="2fd6f-106">Bildschirmkoordinaten</span><span class="sxs-lookup"><span data-stu-id="2fd6f-106">Screen Coordinates</span></span>  
 <span data-ttu-id="2fd6f-107">Eine Windows Forms-Anwendung gibt die Position eines Fensters auf dem Bildschirm in Bildschirmkoordinaten.</span><span class="sxs-lookup"><span data-stu-id="2fd6f-107">A Windows Forms application specifies the position of a window on the screen in screen coordinates.</span></span> <span data-ttu-id="2fd6f-108">Für Bildschirmkoordinaten ist der Ursprung die linke obere Ecke des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="2fd6f-108">For screen coordinates, the origin is the upper-left corner of the screen.</span></span> <span data-ttu-id="2fd6f-109">Die vollständige Position eines Fensters wird häufig durch beschrieben eine <xref:System.Drawing.Rectangle> Struktur, die die Bildschirmkoordinaten von zwei Punkten, die die linken, oberen und unteren rechten Ecke des Fensters definieren enthält.</span><span class="sxs-lookup"><span data-stu-id="2fd6f-109">The full position of a window is often described by a <xref:System.Drawing.Rectangle> structure containing the screen coordinates of two points that define the upper-left and lower-right corners of the window.</span></span>  
  
## <a name="client-coordinates"></a><span data-ttu-id="2fd6f-110">Clientkoordinaten</span><span class="sxs-lookup"><span data-stu-id="2fd6f-110">Client Coordinates</span></span>  
 <span data-ttu-id="2fd6f-111">Eine Windows Forms-Anwendung gibt die Position der Punkte in einem Formular oder Steuerelement mit dem Clientkoordinaten.</span><span class="sxs-lookup"><span data-stu-id="2fd6f-111">A Windows Forms application specifies the position of points in a form or control using client coordinates.</span></span> <span data-ttu-id="2fd6f-112">Der Ursprung für Clientkoordinaten ist der oberen linken Ecke des Clientbereichs des Steuerelements oder Formulars.</span><span class="sxs-lookup"><span data-stu-id="2fd6f-112">The origin for client coordinates is the upper-left corner of the client area of the control or form.</span></span> <span data-ttu-id="2fd6f-113">Clientkoordinaten stellen Sie sicher, dass eine Anwendung konsistent Koordinatenwerte beim Zeichnen in einem Formular oder Steuerelement, unabhängig von der Position des Formulars oder Steuerelements auf dem Bildschirm verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="2fd6f-113">Client coordinates ensure that an application can use consistent coordinate values while drawing in a form or control, regardless of the position of the form or control on the screen.</span></span>  
  
 <span data-ttu-id="2fd6f-114">Darüber hinaus werden die Abmessungen des Clientbereichs beschrieben durch einen <xref:System.Drawing.Rectangle> Struktur, die Clientkoordinaten für den Bereich enthält.</span><span class="sxs-lookup"><span data-stu-id="2fd6f-114">The dimensions of the client area are also described by a <xref:System.Drawing.Rectangle> structure that contains client coordinates for the area.</span></span> <span data-ttu-id="2fd6f-115">In allen Fällen ist die linke obere Koordinate des Rechtecks in den Clientbereich enthalten, während die untere rechte Koordinate ausgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="2fd6f-115">In all cases, the upper-left coordinate of the rectangle is included in the client area, while the lower-right coordinate is excluded.</span></span> <span data-ttu-id="2fd6f-116">Grafikoperationen enthalten nicht den rechten und unteren Rand eines Client-Bereichs.</span><span class="sxs-lookup"><span data-stu-id="2fd6f-116">Graphics operations do not include the right and lower edges of a client area.</span></span> <span data-ttu-id="2fd6f-117">Zum Beispiel die <xref:System.Drawing.Graphics.FillRectangle%2A> Methode an den rechten und unteren Rand des angegebenen Rechtecks voll, aber diese Kanten werden nicht eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2fd6f-117">For example the <xref:System.Drawing.Graphics.FillRectangle%2A> method will fill up to the right and lower edge of the specified rectangle, but will not include these edges.</span></span>  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a><span data-ttu-id="2fd6f-118">Zuordnung von einem Typ von Koordinate in eine andere</span><span class="sxs-lookup"><span data-stu-id="2fd6f-118">Mapping From One Type of Coordinate to Another</span></span>  
 <span data-ttu-id="2fd6f-119">In einigen Fällen müssen Sie möglicherweise von Bildschirmkoordinaten in Clientkoordinaten zuordnen.</span><span class="sxs-lookup"><span data-stu-id="2fd6f-119">Occasionally, you may need to map from screen coordinates to client coordinates.</span></span> <span data-ttu-id="2fd6f-120">Sie können problemlos zu diesem Zweck verwenden der <xref:System.Windows.Forms.Control.PointToClient%2A> und <xref:System.Windows.Forms.Control.PointToScreen%2A> in verfügbaren Methoden der <xref:System.Windows.Forms.Control> Klasse.</span><span class="sxs-lookup"><span data-stu-id="2fd6f-120">You can easily accomplish this by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available in the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="2fd6f-121">Z. B. die <xref:System.Windows.Forms.Control.MousePosition%2A> Eigenschaft <xref:System.Windows.Forms.Control> wird gemeldet, in Bildschirmkoordinaten, aber möglicherweise möchten Sie diese kostenlos in Clientkoordinaten konvertieren.</span><span class="sxs-lookup"><span data-stu-id="2fd6f-121">For example, the <xref:System.Windows.Forms.Control.MousePosition%2A> property of <xref:System.Windows.Forms.Control> is reported in screen coordinates, but you may want to convert these to client coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fd6f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fd6f-122">See Also</span></span>  
 <xref:System.Windows.Forms.Control.PointToClient%2A>  
 <xref:System.Windows.Forms.Control.PointToScreen%2A>
