---
title: 'Vorgehensweise: Manuelles Verwalten von gepufferten Grafiken'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: 965e3225f8cf1af6d61b81434089ebacac8ad13a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138670"
---
# <a name="how-to-manually-manage-buffered-graphics"></a><span data-ttu-id="19c6c-102">Vorgehensweise: Manuelles Verwalten von gepufferten Grafiken</span><span class="sxs-lookup"><span data-stu-id="19c6c-102">How to: Manually Manage Buffered Graphics</span></span>
<span data-ttu-id="19c6c-103">Für erweiterte Szenarien mit doppelter Pufferung, können Sie die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Klassen Ihre eigene doppelte Pufferungslogik implementieren.</span><span class="sxs-lookup"><span data-stu-id="19c6c-103">For more advanced double buffering scenarios, you can use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] classes to implement your own double-buffering logic.</span></span> <span data-ttu-id="19c6c-104">Die Klasse, die für das zuordnen und Verwalten einzelner Grafikpuffer verantwortlich ist die <xref:System.Drawing.BufferedGraphicsContext> Klasse.</span><span class="sxs-lookup"><span data-stu-id="19c6c-104">The class responsible for allocating and managing individual graphics buffers is the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="19c6c-105">Jede Anwendung verfügt über einen standardmäßigen <xref:System.Drawing.BufferedGraphicsContext> , die die gesamte standardmäßige doppelte Pufferung für die Anwendung verwaltet.</span><span class="sxs-lookup"><span data-stu-id="19c6c-105">Every application has its own default <xref:System.Drawing.BufferedGraphicsContext> that manages all of the default double buffering for that application.</span></span> <span data-ttu-id="19c6c-106">Sie können einen Verweis auf diese Instanz abrufen, durch den Aufruf der <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="19c6c-106">You can retrieve a reference to this instance by calling the <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span></span>  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a><span data-ttu-id="19c6c-107">Um einen Verweis auf den Standardwert BufferedGraphicsContext erhalten</span><span class="sxs-lookup"><span data-stu-id="19c6c-107">To obtain a reference to the default BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="19c6c-108">Legen Sie die <xref:System.Drawing.BufferedGraphicsManager.Current%2A> -Eigenschaft, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="19c6c-108">Set the <xref:System.Drawing.BufferedGraphicsManager.Current%2A> property, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  <span data-ttu-id="19c6c-109">Sie müssen nicht aufrufen, die `Dispose` Methode für die <xref:System.Drawing.BufferedGraphicsContext> -Verweis, der erhalten Sie von der <xref:System.Drawing.BufferedGraphicsManager> Klasse.</span><span class="sxs-lookup"><span data-stu-id="19c6c-109">You do not need to call the `Dispose` method on the <xref:System.Drawing.BufferedGraphicsContext> reference that you receive from the <xref:System.Drawing.BufferedGraphicsManager> class.</span></span> <span data-ttu-id="19c6c-110">Die <xref:System.Drawing.BufferedGraphicsManager> behandelt die gesamte die speicherbelegung und die Verteilung für standardmäßige <xref:System.Drawing.BufferedGraphicsContext> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="19c6c-110">The <xref:System.Drawing.BufferedGraphicsManager> handles all of the memory allocation and distribution for default <xref:System.Drawing.BufferedGraphicsContext> instances.</span></span>  
  
     <span data-ttu-id="19c6c-111">Von grafisch anspruchsvollen Anwendungen wie z. B. Animationen, Sie können manchmal Leistung verbessern, indem eine dedizierte <xref:System.Drawing.BufferedGraphicsContext> statt der <xref:System.Drawing.BufferedGraphicsContext> gebotenen die <xref:System.Drawing.BufferedGraphicsManager>.</span><span class="sxs-lookup"><span data-stu-id="19c6c-111">For graphically intensive applications such as animation, you can sometimes improve performance by using a dedicated <xref:System.Drawing.BufferedGraphicsContext> instead of the <xref:System.Drawing.BufferedGraphicsContext> provided by the <xref:System.Drawing.BufferedGraphicsManager>.</span></span> <span data-ttu-id="19c6c-112">Dadurch können Sie zum Erstellen und verwalten Grafikpuffer einzeln, ohne dass der Mehraufwand an Leistung verwalten Sie alle anderen gepufferte Grafiken Ihrer Anwendung zugeordnet, jedoch von der Anwendung belegt größer werden.</span><span class="sxs-lookup"><span data-stu-id="19c6c-112">This enables you to create and manage graphics buffers individually, without incurring the performance overhead of managing all the other buffered graphics associated with your application, though the memory consumed by the application will be greater.</span></span>  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a><span data-ttu-id="19c6c-113">Erstellen Sie einen dedizierte BufferedGraphicsContext</span><span class="sxs-lookup"><span data-stu-id="19c6c-113">To create a dedicated BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="19c6c-114">Deklarieren und erstellen Sie eine neue Instanz der dem <xref:System.Drawing.BufferedGraphicsContext> Klasse, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="19c6c-114">Declare and create a new instance of the <xref:System.Drawing.BufferedGraphicsContext> class, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="19c6c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19c6c-115">See also</span></span>

- <xref:System.Drawing.BufferedGraphicsContext>
- [<span data-ttu-id="19c6c-116">Doppelt gepufferte Grafiken</span><span class="sxs-lookup"><span data-stu-id="19c6c-116">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="19c6c-117">Vorgehensweise: Manuelles Rendern von gepufferten Grafiken</span><span class="sxs-lookup"><span data-stu-id="19c6c-117">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)
