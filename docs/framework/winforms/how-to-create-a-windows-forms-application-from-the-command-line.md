---
title: Erstellen einer Windows Forms-Anwendung über die Befehlszeile
titleSuffix: ''
description: Erfahren Sie, wie Sie die grundlegenden Schritte zum Erstellen und Ausführen einer Windows Forms-Anwendung über die Befehlszeile ausführen.
ms.date: 03/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
ms.openlocfilehash: b63bf884b9fd03a0510c7f240f19d7a14196971a
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903453"
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a>Vorgehensweise: Erstellen einer Windows Forms-Anwendung über die Befehlszeile

In den folgenden Verfahren werden die grundlegenden Schritte beschrieben, die Sie zum Erstellen einer Windows Forms-Anwendung und Ausführen dieser Anwendung über die Befehlszeile abschließen müssen. Visual Studio bietet umfassende Unterstützung für diese Verfahren.  Siehe auch Exemplarische Vorgehensweise [: Hosting eines Windows Forms-Steuer Elements in WPF](../wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).
  
## <a name="procedure"></a>Vorgehensweise  
  
#### <a name="to-create-the-form"></a>So erstellen Sie das Formular  
  
1. Geben Sie in einer leeren Codedatei die folgenden- `Imports` oder- `using` Anweisungen ein:  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2. Deklarieren Sie eine Klasse mit `Form1` dem Namen, die von der Formular Klasse erbt:
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3. Erstellen Sie einen Parameter losen Konstruktor für `Form1` .
  
     In einem späteren Verfahren fügen Sie dem Konstruktor weiteren Code hinzu.
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4. Fügen Sie der Klasse eine `Main`-Method hinzu.
  
    1. Wenden Sie das <xref:System.STAThreadAttribute> auf die c#- `Main` Methode an, um anzugeben, dass Windows Forms Anwendung ein Single Thread-Apartment ist. (Das-Attribut ist in Visual Basic nicht erforderlich, da Windows Forms-Anwendungen, die mit Visual Basic entwickelt wurden, standardmäßig ein Single Thread-Apartment Modell verwenden.)  
  
    2. <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>Wenden Sie an, um Betriebssystem Stile auf Ihre Anwendung anzuwenden.  
  
    3. Erstellen Sie eine Instanz des Formulars, und führen Sie diese aus.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a>So kompilieren Sie die Anwendung und führen sie aus  
  
1. Navigieren Sie an der .NET Framework-Eingabeaufforderung zu dem Verzeichnis, in dem Sie die `Form1`-Klasse erstellt haben.  
  
2. Kompilieren Sie das Formular.  
  
    - Wenn Sie c# verwenden, geben Sie Folgendes ein:`csc form1.cs`  
  
         `-or-`  
  
    - Wenn Sie Visual Basic verwenden, geben Sie Folgendes ein:`vbc form1.vb`  
  
3. Geben Sie an der Eingabeaufforderung Folgendes ein: `Form1.exe`  
  
## <a name="adding-a-control-and-handling-an-event"></a>Hinzufügen eines Steuer Elements und behandeln eines Ereignisses

Anhand der vorherigen Schritte wurde veranschaulicht, wie Sie ein einfaches Windows Form erstellen, das kompiliert und ausgeführt wird. Im nächsten Verfahren wird erläutert, wie Sie ein Steuerelement erstellen und es dem Formular hinzufügen und wie Sie ein Ereignis für das Steuerelement behandeln. Weitere Informationen zu den Steuerelementen, die Sie Windows Forms hinzufügen können, finden Sie unter Windows Forms-Steuer [Elemente](./controls/index.md).
  
 Zusätzlich zu dem Wissen, wie Windows Forms-Anwendungen erstellt werden, sollten Sie auch wissen, wie ereignisbasierte Programmierung geht und wie Benutzereingaben behandelt werden. Weitere Informationen finden Sie unter [Erstellen von Ereignis Handlern in Windows Forms](creating-event-handlers-in-windows-forms.md)und [Behandeln von Benutzereingaben](./controls/handling-user-input.md) .  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a>So deklarieren Sie ein Button-Steuerelement und behandeln sein Click-Ereignis  
  
1. Deklarieren Sie ein Button-Steuerelement namens `button1`.  
  
2. Erstellen Sie im Konstruktor die Schaltfläche, und legen Sie deren Eigenschaften <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> und <xref:System.Windows.Forms.Control.Text%2A> fest.  
  
3. Fügen Sie die Schaltfläche dem Formular hinzu.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie Sie das Schaltflächen-Steuerelement deklarieren:
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4. Erstellen Sie eine Methode, um das <xref:System.Windows.Forms.Control.Click>-Ereignis für die Schaltfläche zu behandeln.  
  
5. Zeigen Sie im Click-Ereignishandler eine <xref:System.Windows.Forms.MessageBox>-Instanz mit der Meldung "Hello World" an.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie das Click-Ereignis des Button-Steuer Elements behandelt wird:
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6. Ordnen Sie das <xref:System.Windows.Forms.Control.Click>-Ereignis der Methode zu, die Sie erstellt haben.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie der Methode das Ereignis zugeordnet wird.  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7. Kompilieren Sie die Anwendung, und führen Sie sie aus, wie im vorherigen Verfahren beschrieben.  
  
## <a name="example"></a>Beispiel  

Das folgende Codebeispiel ist das komplette Beispiel aus den vorherigen Prozeduren:
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Control>
- [Ändern der Darstellung von Windows Forms](changing-the-appearance-of-windows-forms.md)
- [Erweitern von Windows Forms-Anwendungen](./advanced/index.md)
- [Ersten Schritte mit Windows Forms](getting-started-with-windows-forms.md)
