---
title: "Vorgehensweise: erstellen eine Windows Forms-Anwendung über die Befehlszeile"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-winforms
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, application development from command line
- Windows Forms, getting started
- Windows Forms, creating basic form
ms.assetid: 45ad3f8b-1c26-4c9f-91a9-3bb0759a47a4
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e6ddb27f724e30071be339ac753cfd85599ccd86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-windows-forms-application-from-the-command-line"></a>Vorgehensweise: erstellen eine Windows Forms-Anwendung über die Befehlszeile
In den folgenden Verfahren werden die grundlegenden Schritte beschrieben, die Sie zum Erstellen einer Windows Forms-Anwendung und Ausführen dieser Anwendung über die Befehlszeile abschließen müssen. Visual Studio bietet umfassende Unterstützung für diese Verfahren.  Siehe auch [Exemplarische Vorgehensweise: Erstellen eines einfachen Windows Forms](http://msdn.microsoft.com/library/z9w2f38k\(v=vs.100\)).  
  
## <a name="procedure"></a>Prozedur  
  
#### <a name="to-create-the-form"></a>So erstellen Sie das Formular  
  
1.  Geben Sie in einer leeren Codedatei die folgende Imports- bzw. using-Anweisungen ein:  
  
     [!code-csharp[System.Windows.Forms.BasicForm#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BasicForm#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#2)]  
  
2.  Deklarieren Sie eine Klasse namens `Form1`, die von der Form-Klasse erbt.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BasicForm#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#3)]  
  
3.  Erstellen Sie einen Standardkonstruktor für `Form1`.  
  
     In einem späteren Verfahren fügen Sie dem Konstruktor weiteren Code hinzu.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.BasicForm#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#4)]  
  
4.  Fügen Sie der Klasse eine `Main`-Method hinzu.  
  
    1.  Wenden Sie <xref:System.STAThreadAttribute> auf die `Main`-Methode an, um anzugeben, dass es sich bei der Windows Forms-Anwendung um ein Singlethread-Apartment handelt.  
  
    2.  Rufen Sie <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> auf, um Ihre Anwendung im Stil von Windows XP anzuzeigen.  
  
    3.  Erstellen Sie eine Instanz des Formulars, und führen Sie diese aus.  
  
     [!code-csharp[System.Windows.Forms.BasicForm#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.BasicForm#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BasicForm/VB/Form1.vb#5)]  
  
#### <a name="to-compile-and-run-the-application"></a>So kompilieren Sie die Anwendung und führen sie aus  
  
1.  Navigieren Sie an der .NET Framework-Eingabeaufforderung zu dem Verzeichnis, in dem Sie die `Form1`-Klasse erstellt haben.  
  
2.  Kompilieren Sie das Formular.  
  
    -   Wenn Sie c# verwenden, geben Sie ein:`csc form1.cs`  
  
         `-or-`  
  
    -   Wenn Sie Visual Basic verwenden, geben Sie:`vbc form1.vb /r:system.dll,system.drawing.dll,system.windows.forms.dll`  
  
3.  Geben Sie an der Eingabeaufforderung:`Form1.exe`  
  
## <a name="adding-a-control-and-handling-an-event"></a>Hinzufügen eines Steuerelements und Behandeln eines Ereignisses  
 Anhand der vorherigen Schritte wurde veranschaulicht, wie Sie ein einfaches Windows Form erstellen, das kompiliert und ausgeführt wird. Im nächsten Verfahren wird erläutert, wie Sie ein Steuerelement erstellen und es dem Formular hinzufügen und wie Sie ein Ereignis für das Steuerelement behandeln. Weitere Informationen zu den Steuerelementen, die Sie zu Windows Forms hinzufügen können, finden Sie unter [Windows Forms-Steuerelementen](../../../docs/framework/winforms/controls/index.md).  
  
 Zusätzlich zu dem Wissen, wie Windows Forms-Anwendungen erstellt werden, sollten Sie auch wissen, wie ereignisbasierte Programmierung geht und wie Benutzereingaben behandelt werden. Weitere Informationen finden Sie unter [Erstellen von Ereignishandlern in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md), und [Behandeln von Benutzereingaben](../../../docs/framework/winforms/controls/handling-user-input.md)  
  
#### <a name="to-declare-a-button-control-and-handle-its-click-event"></a>So deklarieren Sie ein Button-Steuerelement und behandeln sein Click-Ereignis  
  
1.  Deklarieren Sie ein Button-Steuerelement namens `button1`.  
  
2.  Erstellen Sie im Konstruktor die Schaltfläche, und legen Sie deren Eigenschaften <xref:System.Windows.Forms.Control.Size%2A>, <xref:System.Windows.Forms.Control.Location%2A> und <xref:System.Windows.Forms.Control.Text%2A> fest.  
  
3.  Fügen Sie die Schaltfläche dem Formular hinzu.  
  
     Im folgenden Codebeispiel wird die Deklaration des Button-Steuerelements veranschaulicht.  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.FormWithButton#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#2)]  
  
4.  Erstellen Sie eine Methode, um das <xref:System.Windows.Forms.Control.Click>-Ereignis für die Schaltfläche zu behandeln.  
  
5.  Zeigen Sie im Click-Ereignishandler eine <xref:System.Windows.Forms.MessageBox>-Instanz mit der Meldung "Hello World" an.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie das Click-Ereignis des Button-Steuerelements behandelt wird.  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.FormWithButton#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#3)]  
  
6.  Ordnen Sie das <xref:System.Windows.Forms.Control.Click>-Ereignis der Methode zu, die Sie erstellt haben.  
  
     Im folgenden Codebeispiel wird veranschaulicht, wie der Methode das Ereignis zugeordnet wird.  
  
     [!code-csharp[System.Windows.Forms.FormWithButton#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.FormWithButton#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#4)]  
  
7.  Kompilieren Sie die Anwendung, und führen Sie sie aus, wie im vorherigen Verfahren beschrieben.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel entspricht dem vollständigen Beispiel aus den vorherigen Verfahren.  
  
 [!code-csharp[System.Windows.Forms.FormWithButton#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.FormWithButton#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FormWithButton/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
-   Um den Code zu kompilieren, führen Sie die Anweisungen aus dem vorangehenden Verfahren aus, in denen beschrieben ist, wie die Anwendung zu kompilieren und auszuführen ist.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.Form>  
 <xref:System.Windows.Forms.Control>  
 [Ändern der Darstellung von Windows Forms](../../../docs/framework/winforms/changing-the-appearance-of-windows-forms.md)  
 [Erweitern von Windows Forms-Anwendungen](../../../docs/framework/winforms/advanced/index.md)  
 [Erste Schritte mit Windows Forms](../../../docs/framework/winforms/getting-started-with-windows-forms.md)
