---
title: 'Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms'
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
ms.openlocfilehash: 07e1bb4bcdcaa99635db293f23e5ecb689b6063e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621331"
---
# <a name="how-to-print-a-multi-page-text-file-in-windows-forms"></a>Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms
Texte werden in Windows-basierten Anwendungen häufig gedruckt. Die <xref:System.Drawing.Graphics>-Klasse stellt Methoden bereit, mit denen Objekte (Grafik oder Text) auf einem Gerät, z. B. auf einem Bildschirm oder Drucker, gezeichnet werden können.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.TextRenderer.DrawText%2A>t-Methoden von <xref:System.Windows.Forms.TextRenderer> werden zum Drucken nicht unterstützt. Sie sollten zu druckenden Text stets mit den <xref:System.Drawing.Graphics.DrawString%2A>-Methoden von <xref:System.Drawing.Graphics> zeichnen (siehe folgendes Codebeispiel).  
  
### <a name="to-print-text"></a>So drucken Sie Text  
  
1. Fügen Sie dem Formular eine <xref:System.Drawing.Printing.PrintDocument>-Komponente und eine Zeichenfolge hinzu.  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#8)]
     [!code-vb[System.Drawing.Printing.PrintExamples#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#8)]  
  
2. Zum Drucken eines Dokuments muss die <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A>-Eigenschaft auf das zu druckende Dokument festgelegt werden. Dann kann das Dokument geöffnet und dessen Inhalt in die von Ihnen hinzugefügte Zeichenfolge eingelesen werden.  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintExamples#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#1)]  
  
3. Verwenden Sie im <xref:System.Drawing.Printing.PrintDocument.PrintPage>-Ereignishandler die <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A>-Eigenschaft der <xref:System.Drawing.Printing.PrintPageEventArgs>-Klasse und den Inhalt des Dokuments zum Berechnen der Zeilenlänge und der Anzahl der Zeilen pro Seite. Überprüfen Sie nach jeder Seitendarstellung, ob dies die letzte Seite war, und legen Sie die <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A>-Eigenschaft der <xref:System.Drawing.Printing.PrintPageEventArgs>-Klasse entsprechend fest. Das <xref:System.Drawing.Printing.PrintDocument.PrintPage>-Ereignis wird so lange ausgelöst, bis <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> den Wert `false` erhält. Stellen Sie außerdem sicher, dass das <xref:System.Drawing.Printing.PrintDocument.PrintPage>-Ereignis mit der zugehörigen Ereignisbehandlungsmethode verknüpft ist.  
  
     Im folgenden Codebeispiel wird der Ereignishandler zum Drucken des Inhalts der Datei "testPage.txt" mit der im Formular verwendeten Schriftart verwendet.  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintExamples#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#2)]  
  
4. Rufen Sie die <xref:System.Drawing.Printing.PrintDocument.Print%2A>-Methode auf, um das <xref:System.Drawing.Printing.PrintDocument.PrintPage>-Ereignis auszulösen.  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintExamples#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#5)]  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Drawing.Printing.PrintExamples#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintExamples#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Eine Textdatei namens „testPage.txt“ im Stammverzeichnis von Laufwerk C:\\, die den zu druckenden Text enthält. Bearbeiten Sie den Code entsprechend, um eine andere Datei zu drucken.  
  
- Verweise auf die Assemblys "System", "System.Windows.Forms" und "System.Drawing".  
  
- Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [Druckunterstützung in Windows Forms](windows-forms-print-support.md)
