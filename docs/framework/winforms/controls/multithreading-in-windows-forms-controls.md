---
title: Multithreading in Windows Forms-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cf6790172b7445ad154eead5d17f8efddd78ffee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952681"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="87f6c-102">Multithreading in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="87f6c-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="87f6c-103">In vielen Anwendungen können Sie die Benutzeroberfläche (UI) reaktionsfähiger machen, indem Sie zeitaufwändige Vorgänge in einem anderen Thread ausführen.</span><span class="sxs-lookup"><span data-stu-id="87f6c-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="87f6c-104">Zum Multithreading Ihrer Windows Forms-Steuerelemente stehen eine Reihe von Tools zur Verfügung <xref:System.Threading> , einschließlich des- <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> Namespace, der `BackgroundWorker` -Methode und der-Komponente.</span><span class="sxs-lookup"><span data-stu-id="87f6c-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="87f6c-105">Die `BackgroundWorker` Komponente ersetzt und fügt Funktionen <xref:System.Threading> zum-Namespace und zur <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> -Methode hinzu. Diese werden jedoch sowohl für die Abwärtskompatibilität als auch für die zukünftige Verwendung beibehalten, wenn Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="87f6c-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="87f6c-106">Weitere Informationen finden Sie unter [Übersicht über die BackgroundWorker-Komponente](backgroundworker-component-overview.md).</span><span class="sxs-lookup"><span data-stu-id="87f6c-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="87f6c-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="87f6c-107">In This Section</span></span>  
 [<span data-ttu-id="87f6c-108">Vorgehensweise: Thread sichere Aufrufe an Windows Forms Steuerelemente erstellen</span><span class="sxs-lookup"><span data-stu-id="87f6c-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="87f6c-109">Zeigt, wie Thread sichere Aufrufe an Windows Forms-Steuerelemente durchführen werden.</span><span class="sxs-lookup"><span data-stu-id="87f6c-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="87f6c-110">Vorgehensweise: Verwenden Sie einen Hintergrund Thread, um nach Dateien zu suchen.</span><span class="sxs-lookup"><span data-stu-id="87f6c-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="87f6c-111">Zeigt, wie Sie mit <xref:System.Threading> dem-Namespace <xref:System.Windows.Forms.Control.BeginInvoke%2A> und der-Methode asynchron nach Dateien suchen.</span><span class="sxs-lookup"><span data-stu-id="87f6c-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="87f6c-112">Referenz</span><span class="sxs-lookup"><span data-stu-id="87f6c-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="87f6c-113">Dokumentiert eine Komponente, die einen Arbeits Thread für asynchrone Vorgänge kapselt.</span><span class="sxs-lookup"><span data-stu-id="87f6c-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="87f6c-114">Dokumente zum asynchronen Laden eines Sounds.</span><span class="sxs-lookup"><span data-stu-id="87f6c-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="87f6c-115">Dokumente zum asynchronen Laden eines Bilds.</span><span class="sxs-lookup"><span data-stu-id="87f6c-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="87f6c-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="87f6c-116">Related Sections</span></span>  
 [<span data-ttu-id="87f6c-117">Vorgehensweise: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="87f6c-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="87f6c-118">Zeigt, wie ein zeitaufwendiger Vorgang mit der <xref:System.ComponentModel.BackgroundWorker> -Komponente durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="87f6c-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="87f6c-119">Übersicht über die BackgroundWorker-Komponente</span><span class="sxs-lookup"><span data-stu-id="87f6c-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="87f6c-120">Enthält Themen, in denen beschrieben wird, <xref:System.ComponentModel.BackgroundWorker> wie die-Komponente für asynchrone Vorgänge verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="87f6c-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
