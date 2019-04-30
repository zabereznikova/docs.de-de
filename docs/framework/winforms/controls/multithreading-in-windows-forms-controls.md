---
title: Multithreading in Windows Forms-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: cc7f358a62c8057abb77e1f5a28544bb6c858d98
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012723"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="119b6-102">Multithreading in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="119b6-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="119b6-103">In vielen Anwendungen können Sie Ihre Benutzeroberfläche (UI) Steigern der Reaktionsfähigkeit, indem zeitaufwändige Vorgänge in einem anderen Thread.</span><span class="sxs-lookup"><span data-stu-id="119b6-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="119b6-104">Eine Reihe von Tools stehen für multithreading Ihrer Windows Forms-Steuerelemente, einschließlich der <xref:System.Threading> -Namespace, der <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> -Methode, und die `BackgroundWorker` Komponente.</span><span class="sxs-lookup"><span data-stu-id="119b6-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="119b6-105">Die `BackgroundWorker` Komponente ersetzt und funktionell erweitert die <xref:System.Threading> Namespace und die <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> Methode; diese werden jedoch beibehalten für die Abwärtskompatibilität und zur zukünftigen Verwendung, wenn Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="119b6-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="119b6-106">Weitere Informationen finden Sie unter [Übersicht über die BackgroundWorker-Komponente](backgroundworker-component-overview.md).</span><span class="sxs-lookup"><span data-stu-id="119b6-106">For more information, see [BackgroundWorker Component Overview](backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="119b6-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="119b6-107">In This Section</span></span>  
 [<span data-ttu-id="119b6-108">Vorgehensweise: Threadsichere Aufrufe von Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="119b6-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="119b6-109">Zeigt, wie für threadsichere Aufrufe von Windows Forms-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="119b6-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="119b6-110">Vorgehensweise: Verwenden eines Hintergrundthreads zur Dateisuche</span><span class="sxs-lookup"><span data-stu-id="119b6-110">How to: Use a Background Thread to Search for Files</span></span>](how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="119b6-111">Zeigt, wie die <xref:System.Threading> Namespace und die <xref:System.Windows.Forms.Control.BeginInvoke%2A> Methode, um nach Dateien suchen, asynchron.</span><span class="sxs-lookup"><span data-stu-id="119b6-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="119b6-112">Referenz</span><span class="sxs-lookup"><span data-stu-id="119b6-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="119b6-113">Dokumentation der Komponente, die einen Arbeitsthread für asynchrone Vorgänge kapselt.</span><span class="sxs-lookup"><span data-stu-id="119b6-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="119b6-114">Dokumentiert, wie Sie einen Sound asynchron zu laden.</span><span class="sxs-lookup"><span data-stu-id="119b6-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="119b6-115">Dokumentation zum asynchronen Laden eines Bilds.</span><span class="sxs-lookup"><span data-stu-id="119b6-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="119b6-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="119b6-116">Related Sections</span></span>  
 [<span data-ttu-id="119b6-117">Vorgehensweise: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="119b6-117">How to: Run an Operation in the Background</span></span>](how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="119b6-118">Zeigt, wie einen zeitaufwändigen Vorgang mit führen die <xref:System.ComponentModel.BackgroundWorker> Komponente.</span><span class="sxs-lookup"><span data-stu-id="119b6-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="119b6-119">Übersicht über die BackgroundWorker-Komponente</span><span class="sxs-lookup"><span data-stu-id="119b6-119">BackgroundWorker Component Overview</span></span>](backgroundworker-component-overview.md)  
 <span data-ttu-id="119b6-120">Enthält Themen, die beschreiben, wie Sie mit der <xref:System.ComponentModel.BackgroundWorker> -Komponente für asynchrone Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="119b6-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
