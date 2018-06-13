---
title: 'Gewusst wie: Manuelles Verwalten von gepufferten Grafiken'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: f8675582fe6bafefd94d6a740c3263e407dfd4e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523954"
---
# <a name="how-to-manually-manage-buffered-graphics"></a><span data-ttu-id="180b4-102">Gewusst wie: Manuelles Verwalten von gepufferten Grafiken</span><span class="sxs-lookup"><span data-stu-id="180b4-102">How to: Manually Manage Buffered Graphics</span></span>
<span data-ttu-id="180b4-103">Für erweiterte Szenarien mit doppelter Pufferung können Sie die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Klassen, Ihre eigene Logik Doppelpufferung implementieren.</span><span class="sxs-lookup"><span data-stu-id="180b4-103">For more advanced double buffering scenarios, you can use the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] classes to implement your own double-buffering logic.</span></span> <span data-ttu-id="180b4-104">Die Klasse, die verantwortlich für das zuordnen und Verwalten einzelner Grafikpuffer ist die <xref:System.Drawing.BufferedGraphicsContext> Klasse.</span><span class="sxs-lookup"><span data-stu-id="180b4-104">The class responsible for allocating and managing individual graphics buffers is the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="180b4-105">Jede Anwendung verfügt über einen eigenen Standard <xref:System.Drawing.BufferedGraphicsContext> , verwaltet alle Standardeinstellungen, die doppelte Pufferung für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="180b4-105">Every application has its own default <xref:System.Drawing.BufferedGraphicsContext> that manages all of the default double buffering for that application.</span></span> <span data-ttu-id="180b4-106">Sie können einen Verweis auf diese Instanz abrufen, durch Aufrufen der <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span><span class="sxs-lookup"><span data-stu-id="180b4-106">You can retrieve a reference to this instance by calling the <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span></span>  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a><span data-ttu-id="180b4-107">Abrufen eines Verweises auf den standardmäßigen BufferedGraphicsContext</span><span class="sxs-lookup"><span data-stu-id="180b4-107">To obtain a reference to the default BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="180b4-108">Legen Sie die <xref:System.Drawing.BufferedGraphicsManager.Current%2A> Eigenschaft, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="180b4-108">Set the <xref:System.Drawing.BufferedGraphicsManager.Current%2A> property, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  <span data-ttu-id="180b4-109">Sie müssen nicht Aufrufen der `Dispose` Methode auf die <xref:System.Drawing.BufferedGraphicsContext> -Referenz, die Sie von erhalten die <xref:System.Drawing.BufferedGraphicsManager> Klasse.</span><span class="sxs-lookup"><span data-stu-id="180b4-109">You do not need to call the `Dispose` method on the <xref:System.Drawing.BufferedGraphicsContext> reference that you receive from the <xref:System.Drawing.BufferedGraphicsManager> class.</span></span> <span data-ttu-id="180b4-110">Die <xref:System.Drawing.BufferedGraphicsManager> behandelt die speicherbelegung und die Verteilung für standardmäßige <xref:System.Drawing.BufferedGraphicsContext> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="180b4-110">The <xref:System.Drawing.BufferedGraphicsManager> handles all of the memory allocation and distribution for default <xref:System.Drawing.BufferedGraphicsContext> instances.</span></span>  
  
     <span data-ttu-id="180b4-111">Für grafisch anspruchsvolle Anwendungen z. B. Animation, Sie können in einigen Fällen verbessern, indem mithilfe einer dedizierten <xref:System.Drawing.BufferedGraphicsContext> statt der <xref:System.Drawing.BufferedGraphicsContext> gebotenen der <xref:System.Drawing.BufferedGraphicsManager>.</span><span class="sxs-lookup"><span data-stu-id="180b4-111">For graphically intensive applications such as animation, you can sometimes improve performance by using a dedicated <xref:System.Drawing.BufferedGraphicsContext> instead of the <xref:System.Drawing.BufferedGraphicsContext> provided by the <xref:System.Drawing.BufferedGraphicsManager>.</span></span> <span data-ttu-id="180b4-112">Dadurch können Sie zum Erstellen und verwalten Grafikpuffer einzeln ohne Beeinträchtigung der Systemleistung, verwalten Sie alle anderen gepufferten Grafiken Ihrer Anwendung zugeordnet, obwohl die von der Anwendung belegten Arbeitsspeichers größer werden.</span><span class="sxs-lookup"><span data-stu-id="180b4-112">This enables you to create and manage graphics buffers individually, without incurring the performance overhead of managing all the other buffered graphics associated with your application, though the memory consumed by the application will be greater.</span></span>  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a><span data-ttu-id="180b4-113">So erstellen einen dedizierten BufferedGraphicsContext</span><span class="sxs-lookup"><span data-stu-id="180b4-113">To create a dedicated BufferedGraphicsContext</span></span>  
  
-   <span data-ttu-id="180b4-114">Deklarieren und erstellen Sie eine neue Instanz der dem <xref:System.Drawing.BufferedGraphicsContext> Klasse, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="180b4-114">Declare and create a new instance of the <xref:System.Drawing.BufferedGraphicsContext> class, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="180b4-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="180b4-115">See Also</span></span>  
 <xref:System.Drawing.BufferedGraphicsContext>  
 [<span data-ttu-id="180b4-116">Doppelt gepufferte Grafiken</span><span class="sxs-lookup"><span data-stu-id="180b4-116">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 [<span data-ttu-id="180b4-117">Gewusst wie: Manuelles Rendern von gepufferten Grafiken</span><span class="sxs-lookup"><span data-stu-id="180b4-117">How to: Manually Render Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)
