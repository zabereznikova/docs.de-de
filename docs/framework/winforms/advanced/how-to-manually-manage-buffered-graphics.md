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
ms.openlocfilehash: 6010d52750b20c07db51917621f8643e9d9b47d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968601"
---
# <a name="how-to-manually-manage-buffered-graphics"></a><span data-ttu-id="7361b-102">Vorgehensweise: Manuelles Verwalten von gepufferten Grafiken</span><span class="sxs-lookup"><span data-stu-id="7361b-102">How to: Manually Manage Buffered Graphics</span></span>
<span data-ttu-id="7361b-103">Für erweiterte Szenarien mit doppelter Pufferung können Sie die .NET Framework-Klassen verwenden, um Ihre eigene, doppelte pufferinglogik zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="7361b-103">For more advanced double buffering scenarios, you can use the .NET Framework classes to implement your own double-buffering logic.</span></span> <span data-ttu-id="7361b-104">Die Klasse, die für das zuordnen und Verwalten einzelner Grafik Puffer <xref:System.Drawing.BufferedGraphicsContext> zuständig ist, ist die-Klasse.</span><span class="sxs-lookup"><span data-stu-id="7361b-104">The class responsible for allocating and managing individual graphics buffers is the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="7361b-105">Jede Anwendung verfügt über einen eigenen <xref:System.Drawing.BufferedGraphicsContext> Standard, der die standardmäßige doppelte Pufferung für diese Anwendung verwaltet.</span><span class="sxs-lookup"><span data-stu-id="7361b-105">Every application has its own default <xref:System.Drawing.BufferedGraphicsContext> that manages all of the default double buffering for that application.</span></span> <span data-ttu-id="7361b-106">Sie können einen Verweis auf diese Instanz abrufen, indem Sie <xref:System.Drawing.BufferedGraphicsManager.Current%2A>aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7361b-106">You can retrieve a reference to this instance by calling the <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span></span>  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a><span data-ttu-id="7361b-107">So rufen Sie einen Verweis auf den Standardwert von BufferedGraphicsContext ab</span><span class="sxs-lookup"><span data-stu-id="7361b-107">To obtain a reference to the default BufferedGraphicsContext</span></span>  
  
- <span data-ttu-id="7361b-108">Legen Sie <xref:System.Drawing.BufferedGraphicsManager.Current%2A> die-Eigenschaft fest, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7361b-108">Set the <xref:System.Drawing.BufferedGraphicsManager.Current%2A> property, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    > <span data-ttu-id="7361b-109">Sie müssen die `Dispose` -Methode für den <xref:System.Drawing.BufferedGraphicsContext> Verweis, den Sie von der <xref:System.Drawing.BufferedGraphicsManager> -Klasse empfangen, nicht aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="7361b-109">You do not need to call the `Dispose` method on the <xref:System.Drawing.BufferedGraphicsContext> reference that you receive from the <xref:System.Drawing.BufferedGraphicsManager> class.</span></span> <span data-ttu-id="7361b-110">Der <xref:System.Drawing.BufferedGraphicsManager> verarbeitet die gesamte Speicher Belegung und-Verteilung für Standard <xref:System.Drawing.BufferedGraphicsContext> Instanzen.</span><span class="sxs-lookup"><span data-stu-id="7361b-110">The <xref:System.Drawing.BufferedGraphicsManager> handles all of the memory allocation and distribution for default <xref:System.Drawing.BufferedGraphicsContext> instances.</span></span>  
  
     <span data-ttu-id="7361b-111">Für grafisch intensive Anwendungen, wie z. b. Animation, kann die <xref:System.Drawing.BufferedGraphicsContext> <xref:System.Drawing.BufferedGraphicsManager>Leistung manchmal verbessert werden, indem <xref:System.Drawing.BufferedGraphicsContext> ein dedizierter anstelle der von bereitgestellten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7361b-111">For graphically intensive applications such as animation, you can sometimes improve performance by using a dedicated <xref:System.Drawing.BufferedGraphicsContext> instead of the <xref:System.Drawing.BufferedGraphicsContext> provided by the <xref:System.Drawing.BufferedGraphicsManager>.</span></span> <span data-ttu-id="7361b-112">Dies ermöglicht es Ihnen, Grafik Puffer einzeln zu erstellen und zu verwalten, ohne dass der Aufwand für die Verwaltung aller anderen gepufferten Grafiken, die der Anwendung zugeordnet sind, entstehen soll, obwohl der von der Anwendung genutzte Arbeitsspeicher größer ist.</span><span class="sxs-lookup"><span data-stu-id="7361b-112">This enables you to create and manage graphics buffers individually, without incurring the performance overhead of managing all the other buffered graphics associated with your application, though the memory consumed by the application will be greater.</span></span>  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a><span data-ttu-id="7361b-113">So erstellen Sie einen dedizierten BufferedGraphicsContext</span><span class="sxs-lookup"><span data-stu-id="7361b-113">To create a dedicated BufferedGraphicsContext</span></span>  
  
- <span data-ttu-id="7361b-114">Deklarieren und erstellen Sie eine neue Instanz <xref:System.Drawing.BufferedGraphicsContext> der-Klasse, wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7361b-114">Declare and create a new instance of the <xref:System.Drawing.BufferedGraphicsContext> class, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="7361b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7361b-115">See also</span></span>

- <xref:System.Drawing.BufferedGraphicsContext>
- [<span data-ttu-id="7361b-116">Doppelt gepufferte Grafiken</span><span class="sxs-lookup"><span data-stu-id="7361b-116">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="7361b-117">Vorgehensweise: Manuelles renderdebuggergrafiken</span><span class="sxs-lookup"><span data-stu-id="7361b-117">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)
