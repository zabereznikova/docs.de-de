---
title: 'Gewusst wie: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET], asynchronous features
- components [.NET], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
ms.openlocfilehash: 94bd79bab1e7982ea39b5aa5872a6674033f9ccf
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830362"
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a><span data-ttu-id="225d6-102">Gewusst wie: Verwenden von Komponenten, die das ereignisbasierte asynchrone Muster unterstützen</span><span class="sxs-lookup"><span data-stu-id="225d6-102">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="225d6-103">Viele Komponenten bieten Ihnen die Möglichkeit, ihre Arbeit asynchron auszuführen.</span><span class="sxs-lookup"><span data-stu-id="225d6-103">Many components provide you with the option of performing their work asynchronously.</span></span> <span data-ttu-id="225d6-104">Mit den Komponenten <xref:System.Media.SoundPlayer> und <xref:System.Windows.Forms.PictureBox> können Sie beispielsweise Sounds und Bilder „im Hintergrund“ laden, während Ihr Hauptthread ohne Unterbrechung weiterläuft.</span><span class="sxs-lookup"><span data-stu-id="225d6-104">The <xref:System.Media.SoundPlayer> and <xref:System.Windows.Forms.PictureBox> components, for example, enable you to load sounds and images "in the background" while your main thread continues running without interruption.</span></span>  
  
 <span data-ttu-id="225d6-105">Die Verwendung von asynchronen Methoden in einer Klasse, die die [Übersicht für ereignisbasierte asynchrone Muster](event-based-asynchronous-pattern-overview.md) unterstützt, kann so einfach sein, indem Sie einen Ereignishandler an das Ereignis _MethodName_**Completed** der Komponente wie bei jedem anderen Ereignis anhängen.</span><span class="sxs-lookup"><span data-stu-id="225d6-105">Using asynchronous methods on a class that supports the [Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md) can be as simple as attaching an event handler to the component's _MethodName_**Completed** event, just as you would for any other event.</span></span> <span data-ttu-id="225d6-106">Beim Aufrufen der _MethodName_**Async**-Methode wird Ihre Anwendung weiterhin ohne Unterbrechung ausgeführt, bis das _MethodName_**Completed**-Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="225d6-106">When you call the _MethodName_**Async** method, your application will continue running without interruption until the _MethodName_**Completed** event is raised.</span></span> <span data-ttu-id="225d6-107">In Ihrem Ereignishandler können Sie anhand des Parameters <xref:System.ComponentModel.AsyncCompletedEventArgs> festzustellen, ob der asynchrone Vorgang erfolgreich beendet oder abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="225d6-107">In your event handler, you can examine the <xref:System.ComponentModel.AsyncCompletedEventArgs> parameter to determine if the asynchronous operation successfully completed or if it was canceled.</span></span>  
  
 <span data-ttu-id="225d6-108">Weitere Informationen zur Verwendung von Ereignishandlern finden Sie unter [Übersicht über Ereignishandler](/dotnet/desktop/winforms/event-handlers-overview-windows-forms).</span><span class="sxs-lookup"><span data-stu-id="225d6-108">For more information about using event handlers, see [Event Handlers Overview](/dotnet/desktop/winforms/event-handlers-overview-windows-forms).</span></span>  
  
 <span data-ttu-id="225d6-109">Die folgende Prozedur zeigt, wie die Funktion zum asynchronen Laden von Images eines <xref:System.Windows.Forms.PictureBox>-Steuerelements verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="225d6-109">The following procedure shows how to use the asynchronous image-loading capability of a <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a><span data-ttu-id="225d6-110">So aktivieren Sie ein PictureBox-Steuerelement zum asynchronen Laden eines Images</span><span class="sxs-lookup"><span data-stu-id="225d6-110">To enable a PictureBox control to asynchronously load an image</span></span>  
  
1. <span data-ttu-id="225d6-111">Erstellen Sie eine Instanz der <xref:System.Windows.Forms.PictureBox>-Komponente in Ihrem Formular.</span><span class="sxs-lookup"><span data-stu-id="225d6-111">Create an instance of the <xref:System.Windows.Forms.PictureBox> component in your form.</span></span>  
  
2. <span data-ttu-id="225d6-112">Weisen Sie dem <xref:System.Windows.Forms.PictureBox.LoadCompleted>-Ereignis einen Ereignishandler zu.</span><span class="sxs-lookup"><span data-stu-id="225d6-112">Assign an event handler to the <xref:System.Windows.Forms.PictureBox.LoadCompleted> event.</span></span>  
  
     <span data-ttu-id="225d6-113">Ob während des asynchronen Downloads Fehler aufgetreten sind, prüfen Sie hier.</span><span class="sxs-lookup"><span data-stu-id="225d6-113">Check for any errors that may have occurred during the asynchronous download here.</span></span> <span data-ttu-id="225d6-114">Hier sehen Sie auch, falls es zu einem Abbruch kam.</span><span class="sxs-lookup"><span data-stu-id="225d6-114">This is also where you check for cancellation.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#5)]  
  
3. <span data-ttu-id="225d6-115">Fügen Sie zwei Schaltflächen, `loadButton` und `cancelLoadButton`, zu Ihrem Formular hinzu.</span><span class="sxs-lookup"><span data-stu-id="225d6-115">Add two buttons, called `loadButton` and `cancelLoadButton`, to your form.</span></span> <span data-ttu-id="225d6-116">Fügen Sie <xref:System.Windows.Forms.Control.Click>-Ereignishandler zum Starten und Abbrechen des Downloads hinzu.</span><span class="sxs-lookup"><span data-stu-id="225d6-116">Add <xref:System.Windows.Forms.Control.Click> event handlers to start and cancel the download.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#4)]  
  
4. <span data-ttu-id="225d6-117">Führen Sie die Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="225d6-117">Run your application.</span></span>  
  
     <span data-ttu-id="225d6-118">Während der Imagedownload voranschreitet, können Sie das Formular frei verschieben, minimieren und maximieren.</span><span class="sxs-lookup"><span data-stu-id="225d6-118">As the image download proceeds, you can move the form freely, minimize it, and maximize it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="225d6-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="225d6-119">See also</span></span>

- [<span data-ttu-id="225d6-120">Gewusst wie: Ausführen eines Vorgangs im Hintergrund</span><span class="sxs-lookup"><span data-stu-id="225d6-120">How to: Run an Operation in the Background</span></span>](/dotnet/desktop/winforms/controls/how-to-run-an-operation-in-the-background)
- [<span data-ttu-id="225d6-121">Event-based Asynchronous Pattern Overview (Übersicht über ereignisbasierte asynchrone Muster)</span><span class="sxs-lookup"><span data-stu-id="225d6-121">Event-based Asynchronous Pattern Overview</span></span>](event-based-asynchronous-pattern-overview.md)
