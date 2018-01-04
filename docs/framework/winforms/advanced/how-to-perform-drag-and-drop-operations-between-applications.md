---
title: "Gewusst wie: Ausführen von Drag & Drop-Operationen zwischen Anwendungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: drag and drop [Windows Forms], between applications
ms.assetid: fa347436-2b12-4dd6-8507-59d7241f6a06
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 514c283575ca54e74d23ae31d3590979be2c3ef0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-perform-drag-and-drop-operations-between-applications"></a><span data-ttu-id="a6cdf-102">Gewusst wie: Ausführen von Drag & Drop-Operationen zwischen Anwendungen</span><span class="sxs-lookup"><span data-stu-id="a6cdf-102">How to: Perform Drag-and-Drop Operations Between Applications</span></span>
<span data-ttu-id="a6cdf-103">Das Ausführen von Drag & Drop-Vorgängen zwischen Anwendungen unterscheidet sich nicht vom Aktivieren dieser Aktion innerhalb einer Anwendung, so lange sich die beiden betroffenen Anwendungen gemäß dem "Vertrag" verhalten, der zwischen den Eigenschaften <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> und <xref:System.Windows.Forms.DragEventArgs.Effect%2A> eingerichtet wurde.</span><span class="sxs-lookup"><span data-stu-id="a6cdf-103">Performing drag-and-drop operations between applications is no different than enabling this action within an application, as long as both applications involved behave according to the "contract" established between the <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> and <xref:System.Windows.Forms.DragEventArgs.Effect%2A> properties.</span></span>  
  
 <span data-ttu-id="a6cdf-104">Im folgenden Verfahren verwenden Sie eine von Ihnen erstellte Windows-basierte Anwendung und das im Windows-Betriebssystem enthaltene Textverarbeitungsprogramm WordPad, um Drag & Drop-Vorgänge zwischen Anwendungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a6cdf-104">In the following procedure, you will use a Windows-based application you create and the WordPad word processor that is included with the Windows operating system to perform drag-and-drop operations between applications.</span></span> <span data-ttu-id="a6cdf-105">WordPad verfügt über einen bestimmten Satz an zulässigen Effekte für Drag & Drop-Text. Die Windows-basierte Anwendung, für die Sie Code schreiben, arbeitet mit diesen Effekten, damit die Drag & Drop-Vorgänge erfolgreich ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="a6cdf-105">WordPad has a certain set of allowed effects for text being dragged and dropped; the Windows-based application you will write code for will work with these effects so that drag-and-drop operations may be completed successfully.</span></span>  
  
### <a name="to-perform-a-drag-and-drop-procedure-between-applications"></a><span data-ttu-id="a6cdf-106">So führen Sie ein Drag & Drop-Verfahren zwischen Anwendungen aus</span><span class="sxs-lookup"><span data-stu-id="a6cdf-106">To perform a drag-and-drop procedure between applications</span></span>  
  
1.  <span data-ttu-id="a6cdf-107">Erstellen Sie eine neue Windows Forms-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a6cdf-107">Create a new Windows Forms application.</span></span>  
  
2.  <span data-ttu-id="a6cdf-108">Fügen Sie Ihrem Formular ein <xref:System.Windows.Forms.TextBox>-Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="a6cdf-108">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
3.  <span data-ttu-id="a6cdf-109">Konfigurieren Sie das <xref:System.Windows.Forms.TextBox>-Steuerelement, um abgelegte Daten zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="a6cdf-109">Configure the <xref:System.Windows.Forms.TextBox> control to receive dropped data.</span></span>  
  
     <span data-ttu-id="a6cdf-110">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Ausführen eines Drag & Drop-Vorgangs in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a6cdf-110">For more information, see [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span></span>  
  
4.  <span data-ttu-id="a6cdf-111">Führen Sie die Windows-basierte Anwendung aus. Während die Anwendung aktiv ist, führen Sie WordPad aus.</span><span class="sxs-lookup"><span data-stu-id="a6cdf-111">Run your Windows-based application, and while the application is running, run WordPad.</span></span>  
  
     <span data-ttu-id="a6cdf-112">WordPad ist ein Text-Editor von Windows, der Drag & Drop-Vorgänge ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a6cdf-112">WordPad is a text editor installed by Windows that allows drag-and-drop operations.</span></span> <span data-ttu-id="a6cdf-113">Ist verfügbar durch Drücken der **starten** Schaltfläche auswählen **ausführen**, und geben dann `WordPad` in das Textfeld der **ausführen** Dialogfeld und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6cdf-113">It is accessible by pressing the **Start** button, selecting **Run**, and then typing `WordPad` into the text box of the **Run** dialog box and clicking **OK**.</span></span>  
  
5.  <span data-ttu-id="a6cdf-114">Sobald WordPad geöffnet ist, geben Sie eine Textzeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="a6cdf-114">Once WordPad is open, type a string of text into it.</span></span>  
  
6.  <span data-ttu-id="a6cdf-115">Mit der Maus markieren Sie den Text, und ziehen Sie den markierten Text dann zum <xref:System.Windows.Forms.TextBox>-Steuerelement in der Windows-basierten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a6cdf-115">Using the mouse, select the text, and then drag the selected text over to the <xref:System.Windows.Forms.TextBox> control in your Windows-based application.</span></span>  
  
     <span data-ttu-id="a6cdf-116">Wenn sich die Maus über dem <xref:System.Windows.Forms.TextBox>-Steuerelement befindet (und damit folglich das <xref:System.Windows.Forms.Control.DragEnter>-Ereignis ausgelöst wird), können Sie erkennen, dass sich der Cursor geändert hat. Sie können den markierten Text dann im <xref:System.Windows.Forms.TextBox>-Steuerelement ablegen.</span><span class="sxs-lookup"><span data-stu-id="a6cdf-116">Observe that when you mouse over the <xref:System.Windows.Forms.TextBox> control (and, consequently, raise the <xref:System.Windows.Forms.Control.DragEnter> event), the cursor changes, and you can drop the selected text into the <xref:System.Windows.Forms.TextBox> control.</span></span>  
  
     <span data-ttu-id="a6cdf-117">Darüber hinaus können Sie das <xref:System.Windows.Forms.TextBox>-Steuerelement konfigurieren, damit Textzeichenfolgen per Drag & Drop in WordPad eingefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="a6cdf-117">Additionally, you can configure your <xref:System.Windows.Forms.TextBox> control to allow text strings to be dragged and dropped into WordPad.</span></span> <span data-ttu-id="a6cdf-118">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Ausführen eines Drag & Drop-Vorgangs in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a6cdf-118">For more information, see [Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6cdf-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6cdf-119">See Also</span></span>  
 [<span data-ttu-id="a6cdf-120">Gewusst wie: Hinzufügen von Daten zur Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="a6cdf-120">How to: Add Data to the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 [<span data-ttu-id="a6cdf-121">Gewusst wie: Abrufen von Daten aus der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="a6cdf-121">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 [<span data-ttu-id="a6cdf-122">Drag & Drop-Vorgänge und Unterstützung der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="a6cdf-122">Drag-and-Drop Operations and Clipboard Support</span></span>](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)
