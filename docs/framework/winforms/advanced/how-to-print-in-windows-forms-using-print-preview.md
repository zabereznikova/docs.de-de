---
title: Drucken mithilfe der Seitenansicht
description: Erfahren Sie, wie Sie der Anwendung mit dem Windows Forms PrintPreviewDialog-Steuerelement Druckvorschau Dienste hinzufügen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing [Windows Forms], using print preview
- printing [Windows Forms], with print preview
- print preview
ms.assetid: 4a16f7e2-ae10-4485-b0ae-3d558334d0fe
ms.openlocfilehash: abcf77db40f648df1a0cd49922bb49e5c9407811
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621612"
---
# <a name="how-to-print-in-windows-forms-using-print-preview"></a><span data-ttu-id="cb585-103">Vorgehensweise: Drucken in Windows Forms unter Verwendung der Seitenansicht</span><span class="sxs-lookup"><span data-stu-id="cb585-103">How to: Print in Windows Forms Using Print Preview</span></span>
<span data-ttu-id="cb585-104">Es ist üblich, in Windows Forms-Programmen zusätzlich zu Druckdiensten eine Seitenansicht zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="cb585-104">It is very common in Windows Forms programming to offer print preview in addition to printing services.</span></span> <span data-ttu-id="cb585-105">Eine einfache Möglichkeit, Dienste für Seitenansichten zu Ihrer Anwendung hinzufügen, besteht darin, ein <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelement in Kombination mit der Behandlungslogik für <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignisse zu verwenden, um eine Datei zu drucken.</span><span class="sxs-lookup"><span data-stu-id="cb585-105">An easy way to add print preview services to your application is to use a <xref:System.Windows.Forms.PrintPreviewDialog> control in combination with the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event-handling logic for printing a file.</span></span>  
  
### <a name="to-preview-a-text-document-with-a-printpreviewdialog-control"></a><span data-ttu-id="cb585-106">So zeigen Sie eine Vorschau eines Textdokuments mit einem PrintPreviewDialog-Steuerelement an</span><span class="sxs-lookup"><span data-stu-id="cb585-106">To preview a text document with a PrintPreviewDialog control</span></span>  
  
1. <span data-ttu-id="cb585-107">Fügen Sie Ihrem Formular eine <xref:System.Windows.Forms.PrintPreviewDialog>-Instanz, eine <xref:System.Drawing.Printing.PrintDocument>-Instanz und zwei Zeichenfolgen hinzu.</span><span class="sxs-lookup"><span data-stu-id="cb585-107">Add a <xref:System.Windows.Forms.PrintPreviewDialog>, <xref:System.Drawing.Printing.PrintDocument>, and two strings to your form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#1)]  
  
2. <span data-ttu-id="cb585-108">Legen Sie die <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> -Eigenschaft auf das zu druckende Dokument fest, öffnen Sie das Dokument, und lesen Sie dessen Inhalt in die Zeichenfolge, die Sie zuvor hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="cb585-108">Set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property to the document you wish to print, and open and read the document's contents to the string you added previously.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="cb585-109">Wie beim Drucken des Dokuments verwenden Sie im <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignishandler die <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> -Eigenschaft der <xref:System.Drawing.Printing.PrintPageEventArgs> -Klasse und den Dateiinhalt, um Zeilen pro Seite zu berechnen und den Dokumentinhalt zu rendern.</span><span class="sxs-lookup"><span data-stu-id="cb585-109">As you would for printing the document, in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class and the file contents to calculate lines per page and render the document's contents.</span></span> <span data-ttu-id="cb585-110">Nachdem eine Seite gezeichnet ist, überprüfen Sie, ob sie die letzte Seite ist, und legen Sie die <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> -Eigenschaft von <xref:System.Drawing.Printing.PrintPageEventArgs> entsprechend fest.</span><span class="sxs-lookup"><span data-stu-id="cb585-110">After each page is drawn, check to see if it is the last page, and set the <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> accordingly.</span></span> <span data-ttu-id="cb585-111">Das <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis wird solange ausgelöst, bis <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> den Wert `false`hat.</span><span class="sxs-lookup"><span data-stu-id="cb585-111">The <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised until <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> is `false`.</span></span> <span data-ttu-id="cb585-112">Wenn das Dokument vollständig gerendert wurde, setzen Sie die zu rendernde Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="cb585-112">When the document has finished rendering, reset the string to be rendered.</span></span> <span data-ttu-id="cb585-113">Achten Sie außerdem darauf, dass das <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis mit seiner Ereignisbehandlungsmethode verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="cb585-113">Also, make sure the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is associated with its event-handling method.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="cb585-114">Die Schritte 2 und 3 haben Sie möglicherweise bereits abgeschlossen, wenn Sie Drucken in Ihrer Anwendung implementiert haben.</span><span class="sxs-lookup"><span data-stu-id="cb585-114">You may have already completed steps 2 and 3 if you have implemented printing in your application.</span></span>  
  
     <span data-ttu-id="cb585-115">Im folgenden Codebeispiel wird der Ereignishandler verwendet, um die Datei "testPage.txt" mit der Schriftart zu drucken, die im Formular verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cb585-115">In the following code example, the event handler is used to print the "testPage.txt" file in the same font used on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#3)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#3)]  
  
4. <span data-ttu-id="cb585-116">Legen Sie die <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> -Eigenschaft des <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelements auf die <xref:System.Drawing.Printing.PrintDocument> -Komponente im Formular fest.</span><span class="sxs-lookup"><span data-stu-id="cb585-116">Set the <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintPreviewDialog> control to the <xref:System.Drawing.Printing.PrintDocument> component on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#5)]  
  
5. <span data-ttu-id="cb585-117">Rufen Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> -Methode für das <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelement auf.</span><span class="sxs-lookup"><span data-stu-id="cb585-117">Call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method on the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="cb585-118">In der Regel rufen Sie <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> aus der <xref:System.Windows.Forms.Control.Click> -Ereignisbehandlungsmethode einer Schaltfläche auf.</span><span class="sxs-lookup"><span data-stu-id="cb585-118">You would typically call <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> from the <xref:System.Windows.Forms.Control.Click> event-handling method of a button.</span></span> <span data-ttu-id="cb585-119">Das Aufrufen von <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> löst das <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis aus und rendert die Ausgabe im <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="cb585-119">Calling <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> raises the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event and renders the output to the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="cb585-120">Klickt der Benutzer im Dialogfeld auf das Symbol für Drucken, wird das <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis erneut ausgelöst, und die Ausgabe wird an den Drucker anstatt an das Dialogfeld "Seitenansicht" gesendet.</span><span class="sxs-lookup"><span data-stu-id="cb585-120">When the user clicks the print icon on the dialog, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised again, sending the output to the printer instead of the preview dialog.</span></span> <span data-ttu-id="cb585-121">Aus diesem Grund wird die Zeichenfolge am Ende des Renderingprozesses in Schritt 3 zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="cb585-121">This is why the string is reset at the end of the rendering process in step 3.</span></span>  
  
     <span data-ttu-id="cb585-122">Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.Control.Click> -Ereignisbehandlungsmethode für eine Schaltfläche auf dem Formular gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb585-122">The following code example shows the <xref:System.Windows.Forms.Control.Click> event-handling method for a button on the form.</span></span> <span data-ttu-id="cb585-123">Diese Ereignisbehandlungsmethode ruft die Methoden auf, mit denen das Dokument gelesen und das Dialogfeld "Seitenansicht" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cb585-123">This event-handling method calls the methods to read the document and show the print preview dialog.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#4)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="cb585-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb585-124">Example</span></span>  
 [!code-csharp[System.Drawing.Printing.PrintPreviewExample#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintPreviewExample#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cb585-125">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="cb585-125">Compiling the Code</span></span>  
 <span data-ttu-id="cb585-126">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="cb585-126">This example requires:</span></span>  
  
- <span data-ttu-id="cb585-127">Verweise auf die Assemblys "System", "System.Windows.Forms" und "System.Drawing".</span><span class="sxs-lookup"><span data-stu-id="cb585-127">References to the System, System.Windows.Forms, System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb585-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb585-128">See also</span></span>

- [<span data-ttu-id="cb585-129">Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb585-129">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [<span data-ttu-id="cb585-130">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb585-130">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
- [<span data-ttu-id="cb585-131">Mehr Sicherheit beim Drucken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cb585-131">More Secure Printing in Windows Forms</span></span>](../more-secure-printing-in-windows-forms.md)
