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
# <a name="how-to-print-in-windows-forms-using-print-preview"></a>Vorgehensweise: Drucken in Windows Forms unter Verwendung der Seitenansicht
Es ist üblich, in Windows Forms-Programmen zusätzlich zu Druckdiensten eine Seitenansicht zur Verfügung zu stellen. Eine einfache Möglichkeit, Dienste für Seitenansichten zu Ihrer Anwendung hinzufügen, besteht darin, ein <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelement in Kombination mit der Behandlungslogik für <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignisse zu verwenden, um eine Datei zu drucken.  
  
### <a name="to-preview-a-text-document-with-a-printpreviewdialog-control"></a>So zeigen Sie eine Vorschau eines Textdokuments mit einem PrintPreviewDialog-Steuerelement an  
  
1. Fügen Sie Ihrem Formular eine <xref:System.Windows.Forms.PrintPreviewDialog>-Instanz, eine <xref:System.Drawing.Printing.PrintDocument>-Instanz und zwei Zeichenfolgen hinzu.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#1)]  
  
2. Legen Sie die <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> -Eigenschaft auf das zu druckende Dokument fest, öffnen Sie das Dokument, und lesen Sie dessen Inhalt in die Zeichenfolge, die Sie zuvor hinzugefügt haben.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#2)]  
  
3. Wie beim Drucken des Dokuments verwenden Sie im <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignishandler die <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> -Eigenschaft der <xref:System.Drawing.Printing.PrintPageEventArgs> -Klasse und den Dateiinhalt, um Zeilen pro Seite zu berechnen und den Dokumentinhalt zu rendern. Nachdem eine Seite gezeichnet ist, überprüfen Sie, ob sie die letzte Seite ist, und legen Sie die <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> -Eigenschaft von <xref:System.Drawing.Printing.PrintPageEventArgs> entsprechend fest. Das <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis wird solange ausgelöst, bis <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> den Wert `false`hat. Wenn das Dokument vollständig gerendert wurde, setzen Sie die zu rendernde Zeichenfolge zurück. Achten Sie außerdem darauf, dass das <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis mit seiner Ereignisbehandlungsmethode verknüpft ist.  
  
    > [!NOTE]
    > Die Schritte 2 und 3 haben Sie möglicherweise bereits abgeschlossen, wenn Sie Drucken in Ihrer Anwendung implementiert haben.  
  
     Im folgenden Codebeispiel wird der Ereignishandler verwendet, um die Datei "testPage.txt" mit der Schriftart zu drucken, die im Formular verwendet wird.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#3)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#3)]  
  
4. Legen Sie die <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> -Eigenschaft des <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelements auf die <xref:System.Drawing.Printing.PrintDocument> -Komponente im Formular fest.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#5)]  
  
5. Rufen Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> -Methode für das <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelement auf. In der Regel rufen Sie <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> aus der <xref:System.Windows.Forms.Control.Click> -Ereignisbehandlungsmethode einer Schaltfläche auf. Das Aufrufen von <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> löst das <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis aus und rendert die Ausgabe im <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelement. Klickt der Benutzer im Dialogfeld auf das Symbol für Drucken, wird das <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis erneut ausgelöst, und die Ausgabe wird an den Drucker anstatt an das Dialogfeld "Seitenansicht" gesendet. Aus diesem Grund wird die Zeichenfolge am Ende des Renderingprozesses in Schritt 3 zurückgesetzt.  
  
     Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.Control.Click> -Ereignisbehandlungsmethode für eine Schaltfläche auf dem Formular gezeigt. Diese Ereignisbehandlungsmethode ruft die Methoden auf, mit denen das Dokument gelesen und das Dialogfeld "Seitenansicht" angezeigt wird.  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#4)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#4)]  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Drawing.Printing.PrintPreviewExample#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintPreviewExample#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Verweise auf die Assemblys "System", "System.Windows.Forms" und "System.Drawing".  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [Druckunterstützung in Windows Forms](windows-forms-print-support.md)
- [Mehr Sicherheit beim Drucken in Windows Forms](../more-secure-printing-in-windows-forms.md)
