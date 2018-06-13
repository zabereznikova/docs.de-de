---
title: Multithreading in Windows Forms-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- BackgroundWorker component
- threading [Windows Forms], controls
ms.assetid: c311d652-0f26-45fa-bdcc-b1615d73ce4e
ms.openlocfilehash: 68822c62a1a195ce3128d51c765cfeba2056955d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536356"
---
# <a name="multithreading-in-windows-forms-controls"></a><span data-ttu-id="3bebc-102">Multithreading in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="3bebc-102">Multithreading in Windows Forms Controls</span></span>
<span data-ttu-id="3bebc-103">In vielen Anwendungen können Sie Ihre Benutzeroberfläche (UI) anpassbar, indem zeitaufwändige Operationen in einem anderen Thread ausführen.</span><span class="sxs-lookup"><span data-stu-id="3bebc-103">In many applications, you can make your user interface (UI) more responsive by performing time-consuming operations on another thread.</span></span> <span data-ttu-id="3bebc-104">Eine Reihe von Tools stehen für multithreading Windows Forms-Steuerelemente, einschließlich der <xref:System.Threading> Namespace, der <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> -Methode, und die `BackgroundWorker` Komponente.</span><span class="sxs-lookup"><span data-stu-id="3bebc-104">A number of tools are available for multithreading your Windows Forms controls, including the <xref:System.Threading> namespace, the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method, and the `BackgroundWorker` component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3bebc-105">Die `BackgroundWorker` Komponente ersetzt und funktionell erweitert, um die <xref:System.Threading> Namespace und die <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> Methode; diese werden jedoch beibehalten für Abwärtskompatibilität und für zukünftige Verwendung, falls gewünscht.</span><span class="sxs-lookup"><span data-stu-id="3bebc-105">The `BackgroundWorker` component replaces and adds functionality to the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A?displayProperty=nameWithType> method; however, these are retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="3bebc-106">Weitere Informationen finden Sie unter [Übersicht über die BackgroundWorker-Komponente](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3bebc-106">For more information, see [BackgroundWorker Component Overview](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3bebc-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3bebc-107">In This Section</span></span>  
 [<span data-ttu-id="3bebc-108">Gewusst wie: Threadsicheres Aufrufen von Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="3bebc-108">How to: Make Thread-Safe Calls to Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-make-thread-safe-calls-to-windows-forms-controls.md)  
 <span data-ttu-id="3bebc-109">Zeigt, wie Sie threadsichere Aufrufe an Windows Forms-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="3bebc-109">Shows how to make thread-safe calls to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="3bebc-110">Gewusst wie: Verwenden eines Hintergrundthreads zur Dateisuche</span><span class="sxs-lookup"><span data-stu-id="3bebc-110">How to: Use a Background Thread to Search for Files</span></span>](../../../../docs/framework/winforms/controls/how-to-use-a-background-thread-to-search-for-files.md)  
 <span data-ttu-id="3bebc-111">Zeigt, wie die <xref:System.Threading> Namespace und die <xref:System.Windows.Forms.Control.BeginInvoke%2A> Methode zur Suche nach Dateien asynchron.</span><span class="sxs-lookup"><span data-stu-id="3bebc-111">Shows how to use the <xref:System.Threading> namespace and the <xref:System.Windows.Forms.Control.BeginInvoke%2A> method to search for files asynchronously.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="3bebc-112">Referenz</span><span class="sxs-lookup"><span data-stu-id="3bebc-112">Reference</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="3bebc-113">Die Dokumentation der Komponente, die einen Arbeitsthread für asynchrone Vorgänge kapselt.</span><span class="sxs-lookup"><span data-stu-id="3bebc-113">Documents a component that encapsulates a worker thread for asynchronous operations.</span></span>  
  
 <xref:System.Media.SoundPlayer.LoadAsync%2A>  
 <span data-ttu-id="3bebc-114">Dokumentiert, wie Sie einen Sound asynchron zu laden.</span><span class="sxs-lookup"><span data-stu-id="3bebc-114">Documents how to load a sound asynchronously.</span></span>  
  
 <xref:System.Windows.Forms.PictureBox.LoadAsync%2A>  
 <span data-ttu-id="3bebc-115">Dokumentiert, wie Sie ein Bild asynchron geladen werden.</span><span class="sxs-lookup"><span data-stu-id="3bebc-115">Documents how to load an image asynchronously.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3bebc-116">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="3bebc-116">Related Sections</span></span>  
 [<span data-ttu-id="3bebc-117">Gewusst wie: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="3bebc-117">How to: Run an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="3bebc-118">Zeigt die Vorgehensweise führen Sie einen zeitaufwändigen Vorgang mit der <xref:System.ComponentModel.BackgroundWorker> Komponente.</span><span class="sxs-lookup"><span data-stu-id="3bebc-118">Shows how to perform a time-consuming operation with the <xref:System.ComponentModel.BackgroundWorker> component.</span></span>  
  
 [<span data-ttu-id="3bebc-119">Übersicht über die BackgroundWorker-Komponente</span><span class="sxs-lookup"><span data-stu-id="3bebc-119">BackgroundWorker Component Overview</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component-overview.md)  
 <span data-ttu-id="3bebc-120">Enthält Themen, die beschreiben, wie Sie die <xref:System.ComponentModel.BackgroundWorker> -Komponente für asynchrone Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="3bebc-120">Provides topics that describe how to use the <xref:System.ComponentModel.BackgroundWorker> component for asynchronous operations.</span></span>
