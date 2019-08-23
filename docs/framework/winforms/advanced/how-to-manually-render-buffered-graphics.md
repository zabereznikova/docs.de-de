---
title: 'Vorgehensweise: Manuelles Rendern von gepufferten Grafiken'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually rendering graphics
- graphics [Windows Forms], rendering
ms.assetid: 5192295e-bd8e-45f7-8bd6-5c4f6bd21e61
ms.openlocfilehash: a6655652a7c5dedb8e183356688972c07a705cbc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931837"
---
# <a name="how-to-manually-render-buffered-graphics"></a><span data-ttu-id="5f763-102">Vorgehensweise: Manuelles Rendern von gepufferten Grafiken</span><span class="sxs-lookup"><span data-stu-id="5f763-102">How to: Manually Render Buffered Graphics</span></span>
<span data-ttu-id="5f763-103">Wenn Sie Ihre eigenen gepufferten Grafiken verwalten, müssen Sie Grafikpuffer erstellen und rendern können.</span><span class="sxs-lookup"><span data-stu-id="5f763-103">If you are managing your own buffered graphics, you will need to be able to create and render graphics buffers.</span></span> <span data-ttu-id="5f763-104">Sie können Instanzen der <xref:System.Drawing.BufferedGraphics>-Klasse erstellen, die mit Zeichenflächen auf dem Bildschirm verknüpft ist. Dazu rufen Sie die <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="5f763-104">You can create instances of the <xref:System.Drawing.BufferedGraphics> class that is associated with drawing surfaces on your screen by calling the <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> method.</span></span> <span data-ttu-id="5f763-105">Diese Methode erstellt eine <xref:System.Drawing.BufferedGraphics>-Instanz, die mit einer bestimmten Darstellungsoberfläche verknüpft ist, beispielsweise mit einem Formular oder Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="5f763-105">This method creates a <xref:System.Drawing.BufferedGraphics> instance that is associated with a particular rendering surface, such as a form or control.</span></span> <span data-ttu-id="5f763-106">Nachdem Sie eine <xref:System.Drawing.BufferedGraphics>-Instanz erstellt haben, können Sie mit der<xref:System.Drawing.BufferedGraphics.Graphics%2A>-Eigenschaft Grafiken in den Puffer schreiben, dem die Instanz entspricht.</span><span class="sxs-lookup"><span data-stu-id="5f763-106">After you have created a <xref:System.Drawing.BufferedGraphics> instance, you can draw graphics to the buffer it represents through the <xref:System.Drawing.BufferedGraphics.Graphics%2A> property.</span></span> <span data-ttu-id="5f763-107">Nachdem Sie alle Grafikvorgänge ausgeführt haben, können Sie den Inhalt des Puffers auf den Bildschirm kopieren, indem Sie die <xref:System.Drawing.BufferedGraphics.Render%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5f763-107">After you have performed all graphics operations, you can copy the contents of the buffer to the screen by calling the <xref:System.Drawing.BufferedGraphics.Render%2A> method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f763-108">Wenn Sie Ihr eigenes Rendering ausführen, erhöht sich die Arbeitsspeichernutzung, allerdings wahrscheinlich nur geringfügig.</span><span class="sxs-lookup"><span data-stu-id="5f763-108">If you perform your own rendering, memory consumption will increase, though the increase may only be slight.</span></span>  
  
### <a name="to-manually-display-buffered-graphics"></a><span data-ttu-id="5f763-109">So zeigen Sie gepufferte Grafiken manuell an</span><span class="sxs-lookup"><span data-stu-id="5f763-109">To manually display buffered graphics</span></span>  
  
1. <span data-ttu-id="5f763-110">Rufen Sie einen Verweis auf eine Instanz der <xref:System.Drawing.BufferedGraphicsContext>-Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="5f763-110">Obtain a reference to an instance of the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="5f763-111">Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Verwalten von gepufferten Grafiken](how-to-manually-manage-buffered-graphics.md).</span><span class="sxs-lookup"><span data-stu-id="5f763-111">For more information, see [How to: Manually Manage Buffered Graphics](how-to-manually-manage-buffered-graphics.md).</span></span>  
  
2. <span data-ttu-id="5f763-112">Erstellen Sie eine Instanz der <xref:System.Drawing.BufferedGraphics>-Klasse, indem Sie die <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A>-Methode wie im folgenden Codebeispiel gezeigt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5f763-112">Create an instance of the <xref:System.Drawing.BufferedGraphics> class by calling the <xref:System.Drawing.BufferedGraphicsContext.Allocate%2A> method, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#21)]  
  
3. <span data-ttu-id="5f763-113">Zeichnen Sie Grafiken in den Grafikpuffer, indem Sie die <xref:System.Drawing.BufferedGraphics.Graphics%2A>-Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="5f763-113">Draw graphics to the graphics buffer by setting the <xref:System.Drawing.BufferedGraphics.Graphics%2A> property.</span></span> <span data-ttu-id="5f763-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5f763-114">For example:</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#22)]  
  
4. <span data-ttu-id="5f763-115">Wenn Sie Ihre Zeichenvorgänge für den Grafikpuffer abgeschlossen haben, rufen Sie die <xref:System.Drawing.BufferedGraphics.Render%2A>-Methode auf, um den Puffer, wie im folgenden Codebeispiel gezeigt, entweder auf der Zeichenfläche, die mit diesem Puffer verknüpft ist, oder auf einer angegebenen Zeichenfläche zu rendern.</span><span class="sxs-lookup"><span data-stu-id="5f763-115">When you have completed all of your drawing operations to the graphics buffer, call the <xref:System.Drawing.BufferedGraphics.Render%2A> method to render the buffer, either to the drawing surface associated with that buffer, or to a specified drawing surface, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#23)]  
  
5. <span data-ttu-id="5f763-116">Wenn Sie das Rendern der Grafiken abgeschlossen haben, rufen Sie die `Dispose`-Methode für die <xref:System.Drawing.BufferedGraphics>-Instanz auf, um Systemressourcen freizugeben.</span><span class="sxs-lookup"><span data-stu-id="5f763-116">After you are finished rendering graphics, call the `Dispose` method on the <xref:System.Drawing.BufferedGraphics> instance to free system resources.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#24)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#24)]  
  
## <a name="see-also"></a><span data-ttu-id="5f763-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f763-117">See also</span></span>

- <xref:System.Drawing.BufferedGraphicsContext>
- <xref:System.Drawing.BufferedGraphics>
- [<span data-ttu-id="5f763-118">Doppelt gepufferte Grafiken</span><span class="sxs-lookup"><span data-stu-id="5f763-118">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="5f763-119">Vorgehensweise: Manuelles Verwalten gepufferter Grafiken</span><span class="sxs-lookup"><span data-stu-id="5f763-119">How to: Manually Manage Buffered Graphics</span></span>](how-to-manually-manage-buffered-graphics.md)
