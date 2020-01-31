---
title: Drucken mithilfe der Seitenansicht
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing [Windows Forms], using print preview
- printing [Windows Forms], with print preview
- print preview
ms.assetid: 4a16f7e2-ae10-4485-b0ae-3d558334d0fe
ms.openlocfilehash: 1975c902fdb56326c763f2e2fc11e381ffc7fbd3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740605"
---
# <a name="how-to-print-in-windows-forms-using-print-preview"></a><span data-ttu-id="0e534-102">Gewusst wie: Drucken in Windows Forms unter Verwendung der Seitenansicht</span><span class="sxs-lookup"><span data-stu-id="0e534-102">How to: Print in Windows Forms Using Print Preview</span></span>
<span data-ttu-id="0e534-103">Es ist üblich, in Windows Forms-Programmen zusätzlich zu Druckdiensten eine Seitenansicht zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="0e534-103">It is very common in Windows Forms programming to offer print preview in addition to printing services.</span></span> <span data-ttu-id="0e534-104">Eine einfache Möglichkeit, Dienste für Seitenansichten zu Ihrer Anwendung hinzufügen, besteht darin, ein <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelement in Kombination mit der Behandlungslogik für <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignisse zu verwenden, um eine Datei zu drucken.</span><span class="sxs-lookup"><span data-stu-id="0e534-104">An easy way to add print preview services to your application is to use a <xref:System.Windows.Forms.PrintPreviewDialog> control in combination with the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event-handling logic for printing a file.</span></span>  
  
### <a name="to-preview-a-text-document-with-a-printpreviewdialog-control"></a><span data-ttu-id="0e534-105">So zeigen Sie eine Vorschau eines Textdokuments mit einem PrintPreviewDialog-Steuerelement an</span><span class="sxs-lookup"><span data-stu-id="0e534-105">To preview a text document with a PrintPreviewDialog control</span></span>  
  
1. <span data-ttu-id="0e534-106">Fügen Sie Ihrem Formular eine <xref:System.Windows.Forms.PrintPreviewDialog>-Instanz, eine <xref:System.Drawing.Printing.PrintDocument>-Instanz und zwei Zeichenfolgen hinzu.</span><span class="sxs-lookup"><span data-stu-id="0e534-106">Add a <xref:System.Windows.Forms.PrintPreviewDialog>, <xref:System.Drawing.Printing.PrintDocument>, and two strings to your form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#1)]  
  
2. <span data-ttu-id="0e534-107">Legen Sie die <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> -Eigenschaft auf das zu druckende Dokument fest, öffnen Sie das Dokument, und lesen Sie dessen Inhalt in die Zeichenfolge, die Sie zuvor hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="0e534-107">Set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property to the document you wish to print, and open and read the document's contents to the string you added previously.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="0e534-108">Wie beim Drucken des Dokuments verwenden Sie im <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignishandler die <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> -Eigenschaft der <xref:System.Drawing.Printing.PrintPageEventArgs> -Klasse und den Dateiinhalt, um Zeilen pro Seite zu berechnen und den Dokumentinhalt zu rendern.</span><span class="sxs-lookup"><span data-stu-id="0e534-108">As you would for printing the document, in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class and the file contents to calculate lines per page and render the document's contents.</span></span> <span data-ttu-id="0e534-109">Nachdem eine Seite gezeichnet ist, überprüfen Sie, ob sie die letzte Seite ist, und legen Sie die <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> -Eigenschaft von <xref:System.Drawing.Printing.PrintPageEventArgs> entsprechend fest.</span><span class="sxs-lookup"><span data-stu-id="0e534-109">After each page is drawn, check to see if it is the last page, and set the <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> accordingly.</span></span> <span data-ttu-id="0e534-110">Das <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis wird solange ausgelöst, bis <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> den Wert `false`hat.</span><span class="sxs-lookup"><span data-stu-id="0e534-110">The <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised until <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> is `false`.</span></span> <span data-ttu-id="0e534-111">Wenn das Dokument vollständig gerendert wurde, setzen Sie die zu rendernde Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="0e534-111">When the document has finished rendering, reset the string to be rendered.</span></span> <span data-ttu-id="0e534-112">Achten Sie außerdem darauf, dass das <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis mit seiner Ereignisbehandlungsmethode verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="0e534-112">Also, make sure the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is associated with its event-handling method.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0e534-113">Die Schritte 2 und 3 haben Sie möglicherweise bereits abgeschlossen, wenn Sie Drucken in Ihrer Anwendung implementiert haben.</span><span class="sxs-lookup"><span data-stu-id="0e534-113">You may have already completed steps 2 and 3 if you have implemented printing in your application.</span></span>  
  
     <span data-ttu-id="0e534-114">Im folgenden Codebeispiel wird der Ereignishandler verwendet, um die Datei "testPage.txt" mit der Schriftart zu drucken, die im Formular verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e534-114">In the following code example, the event handler is used to print the "testPage.txt" file in the same font used on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#3)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#3)]  
  
4. <span data-ttu-id="0e534-115">Legen Sie die <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> -Eigenschaft des <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelements auf die <xref:System.Drawing.Printing.PrintDocument> -Komponente im Formular fest.</span><span class="sxs-lookup"><span data-stu-id="0e534-115">Set the <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintPreviewDialog> control to the <xref:System.Drawing.Printing.PrintDocument> component on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#5)]  
  
5. <span data-ttu-id="0e534-116">Rufen Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> -Methode für das <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelement auf.</span><span class="sxs-lookup"><span data-stu-id="0e534-116">Call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method on the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="0e534-117">In der Regel rufen Sie <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> aus der <xref:System.Windows.Forms.Control.Click> -Ereignisbehandlungsmethode einer Schaltfläche auf.</span><span class="sxs-lookup"><span data-stu-id="0e534-117">You would typically call <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> from the <xref:System.Windows.Forms.Control.Click> event-handling method of a button.</span></span> <span data-ttu-id="0e534-118">Das Aufrufen von <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> löst das <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis aus und rendert die Ausgabe im <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0e534-118">Calling <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> raises the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event and renders the output to the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="0e534-119">Klickt der Benutzer im Dialogfeld auf das Symbol für Drucken, wird das <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis erneut ausgelöst, und die Ausgabe wird an den Drucker anstatt an das Dialogfeld "Seitenansicht" gesendet.</span><span class="sxs-lookup"><span data-stu-id="0e534-119">When the user clicks the print icon on the dialog, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised again, sending the output to the printer instead of the preview dialog.</span></span> <span data-ttu-id="0e534-120">Aus diesem Grund wird die Zeichenfolge am Ende des Renderingprozesses in Schritt 3 zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="0e534-120">This is why the string is reset at the end of the rendering process in step 3.</span></span>  
  
     <span data-ttu-id="0e534-121">Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.Control.Click> -Ereignisbehandlungsmethode für eine Schaltfläche auf dem Formular gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e534-121">The following code example shows the <xref:System.Windows.Forms.Control.Click> event-handling method for a button on the form.</span></span> <span data-ttu-id="0e534-122">Diese Ereignisbehandlungsmethode ruft die Methoden auf, mit denen das Dokument gelesen und das Dialogfeld "Seitenansicht" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0e534-122">This event-handling method calls the methods to read the document and show the print preview dialog.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#4)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="0e534-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e534-123">Example</span></span>  
 [!code-csharp[System.Drawing.Printing.PrintPreviewExample#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintPreviewExample#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0e534-124">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0e534-124">Compiling the Code</span></span>  
 <span data-ttu-id="0e534-125">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0e534-125">This example requires:</span></span>  
  
- <span data-ttu-id="0e534-126">Verweise auf die Assemblys "System", "System.Windows.Forms" und "System.Drawing".</span><span class="sxs-lookup"><span data-stu-id="0e534-126">References to the System, System.Windows.Forms, System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e534-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e534-127">See also</span></span>

- [<span data-ttu-id="0e534-128">Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0e534-128">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [<span data-ttu-id="0e534-129">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0e534-129">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
- [<span data-ttu-id="0e534-130">Mehr Sicherheit beim Drucken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0e534-130">More Secure Printing in Windows Forms</span></span>](../more-secure-printing-in-windows-forms.md)
