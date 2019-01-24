---
title: 'Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing [Windows Forms], printing multiple pages
- text [Windows Forms], printing Windows Forms
- Windows Forms, printing text
- printing [Windows Forms], text
ms.assetid: 362427f8-03d4-4826-b49f-60ab066ad322
ms.openlocfilehash: 149f0ca6df60931f8bb567ef5e4876c779825f1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54604368"
---
# <a name="how-to-print-a-multi-page-text-file-in-windows-forms"></a><span data-ttu-id="ef293-102">Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef293-102">How to: Print a Multi-Page Text File in Windows Forms</span></span>
<span data-ttu-id="ef293-103">Texte werden in Windows-basierten Anwendungen häufig gedruckt.</span><span class="sxs-lookup"><span data-stu-id="ef293-103">It is very common for Windows-based applications to print text.</span></span> <span data-ttu-id="ef293-104">Die <xref:System.Drawing.Graphics>-Klasse stellt Methoden bereit, mit denen Objekte (Grafik oder Text) auf einem Gerät, z. B. auf einem Bildschirm oder Drucker, gezeichnet werden können.</span><span class="sxs-lookup"><span data-stu-id="ef293-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects (graphics or text) to a device, such as a screen or printer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef293-105">Die <xref:System.Windows.Forms.TextRenderer.DrawText%2A>t-Methoden von <xref:System.Windows.Forms.TextRenderer> werden zum Drucken nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ef293-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of <xref:System.Windows.Forms.TextRenderer> are not supported for printing.</span></span> <span data-ttu-id="ef293-106">Sie sollten zu druckenden Text stets mit den <xref:System.Drawing.Graphics.DrawString%2A>-Methoden von <xref:System.Drawing.Graphics> zeichnen (siehe folgendes Codebeispiel).</span><span class="sxs-lookup"><span data-stu-id="ef293-106">You should always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of <xref:System.Drawing.Graphics>, as shown in the following code example, to draw text for printing purposes.</span></span>  
  
### <a name="to-print-text"></a><span data-ttu-id="ef293-107">So drucken Sie Text</span><span class="sxs-lookup"><span data-stu-id="ef293-107">To print text</span></span>  
  
1.  <span data-ttu-id="ef293-108">Fügen Sie dem Formular eine <xref:System.Drawing.Printing.PrintDocument>-Komponente und eine Zeichenfolge hinzu.</span><span class="sxs-lookup"><span data-stu-id="ef293-108">Add a <xref:System.Drawing.Printing.PrintDocument> component and a string to your form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#8)]
     [!code-vb[System.Drawing.Printing.PrintExamples#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#8)]  
  
2.  <span data-ttu-id="ef293-109">Zum Drucken eines Dokuments muss die <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A>-Eigenschaft auf das zu druckende Dokument festgelegt werden. Dann kann das Dokument geöffnet und dessen Inhalt in die von Ihnen hinzugefügte Zeichenfolge eingelesen werden.</span><span class="sxs-lookup"><span data-stu-id="ef293-109">If printing a document, set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property to the document you wish to print, and open and read the documents contents to the string you added previously.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintExamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#1)]  
  
3.  <span data-ttu-id="ef293-110">Verwenden Sie im <xref:System.Drawing.Printing.PrintDocument.PrintPage>-Ereignishandler die <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A>-Eigenschaft der <xref:System.Drawing.Printing.PrintPageEventArgs>-Klasse und den Inhalt des Dokuments zum Berechnen der Zeilenlänge und der Anzahl der Zeilen pro Seite.</span><span class="sxs-lookup"><span data-stu-id="ef293-110">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class and the document contents to calculate line length and lines per page.</span></span> <span data-ttu-id="ef293-111">Überprüfen Sie nach jeder Seitendarstellung, ob dies die letzte Seite war, und legen Sie die <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A>-Eigenschaft der <xref:System.Drawing.Printing.PrintPageEventArgs>-Klasse entsprechend fest.</span><span class="sxs-lookup"><span data-stu-id="ef293-111">After each page is drawn, check to see if it is the last page, and set the <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> accordingly.</span></span> <span data-ttu-id="ef293-112">Das <xref:System.Drawing.Printing.PrintDocument.PrintPage>-Ereignis wird so lange ausgelöst, bis <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> den Wert `false` erhält.</span><span class="sxs-lookup"><span data-stu-id="ef293-112">The <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised until <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> is `false`.</span></span> <span data-ttu-id="ef293-113">Stellen Sie außerdem sicher, dass das <xref:System.Drawing.Printing.PrintDocument.PrintPage>-Ereignis mit der zugehörigen Ereignisbehandlungsmethode verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="ef293-113">Also, make sure the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is associated with its event-handling method.</span></span>  
  
     <span data-ttu-id="ef293-114">Im folgenden Codebeispiel wird der Ereignishandler zum Drucken des Inhalts der Datei "testPage.txt" mit der im Formular verwendeten Schriftart verwendet.</span><span class="sxs-lookup"><span data-stu-id="ef293-114">In the following code example, the event handler is used to print the contents of the "testPage.txt" file in the same font as is used on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintExamples#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#2)]  
  
4.  <span data-ttu-id="ef293-115">Rufen Sie die <xref:System.Drawing.Printing.PrintDocument.Print%2A>-Methode auf, um das <xref:System.Drawing.Printing.PrintDocument.PrintPage>-Ereignis auszulösen.</span><span class="sxs-lookup"><span data-stu-id="ef293-115">Call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to raise the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintExamples#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="ef293-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef293-116">Example</span></span>  
 [!code-csharp[System.Drawing.Printing.PrintExamples#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintExamples#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ef293-117">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ef293-117">Compiling the Code</span></span>  
 <span data-ttu-id="ef293-118">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ef293-118">This example requires:</span></span>  
  
-   <span data-ttu-id="ef293-119">Eine Textdatei namens „testPage.txt“ im Stammverzeichnis von Laufwerk C:\\, die den zu druckenden Text enthält.</span><span class="sxs-lookup"><span data-stu-id="ef293-119">A text file named testPage.txt containing the text to print, located in the root of drive C:\\.</span></span> <span data-ttu-id="ef293-120">Bearbeiten Sie den Code entsprechend, um eine andere Datei zu drucken.</span><span class="sxs-lookup"><span data-stu-id="ef293-120">Edit the code to print a different file.</span></span>  
  
-   <span data-ttu-id="ef293-121">Verweise auf die Assemblys "System", "System.Windows.Forms" und "System.Drawing".</span><span class="sxs-lookup"><span data-stu-id="ef293-121">References to the System, System.Windows.Forms, System.Drawing assemblies.</span></span>  
  
-   <span data-ttu-id="ef293-122">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="ef293-122">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="ef293-123">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="ef293-123">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="ef293-124">Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Kompilieren und Ausführen einer vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="ef293-124">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef293-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef293-125">See also</span></span>
- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="ef293-126">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef293-126">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
