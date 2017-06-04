---
title: "Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Bereiche, Aktualisieren der Statusleiste"
  - "Statusleisten, Aktualisieren von Bereichen"
  - "Statusleisten, Aktualisieren zur Laufzeit"
  - "StatusBar-Steuerelement [Windows Forms], Aktualisieren von Bereichen"
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit
> [!IMPORTANT]
>  Obwohl die Steuerelemente <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> durch die Steuerelemente <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> ersetzt und funktionell erweitert werden, werden die Steuerelemente <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 In vielen Fällen werden Sie in einem Programm aufgefordert, den Inhalt der Statusleistenbereiche zur Laufzeit dynamisch zu aktualisieren, sofern Änderungen des Anwendungszustands oder andere Benutzerinteraktionen erfolgt sind.  Dies ist eine häufige Methode, Benutzern mitzuteilen, dass Tasten wie die FESTSTELLTASTE, NUM oder ROLLEN aktiviert sind, oder um das Datum oder die Uhrzeit als Bezugsgröße bereitzustellen.  
  
 Im folgenden Beispiel verwenden Sie eine Instanz der <xref:System.Windows.Forms.StatusBarPanel>\-Klasse als Host für eine Uhr.  
  
### So bereiten Sie die Statusleiste für die Aktualisierung vor  
  
1.  Erstellen Sie ein neues Windows Form.  
  
2.  Fügen Sie dem Formular ein <xref:System.Windows.Forms.StatusBar>\-Steuerelement hinzu.  Ausführliche Informationen finden Sie unter [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
3.  Fügen Sie dem <xref:System.Windows.Forms.StatusBar>\-Steuerelement einen Statusleistenbereich hinzu.  Ausführliche Informationen finden Sie unter [Gewusst wie: Hinzufügen von Bereichen zu einem StatusBar\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md).  
  
4.  Legen Sie die <xref:System.Windows.Forms.StatusBar.ShowPanels%2A>\-Eigenschaft für das <xref:System.Windows.Forms.StatusBar>\-Steuerelement, das Sie dem Formular hinzugefügt haben, auf `true` fest.  
  
5.  Fügen Sie dem Formular eine <xref:System.Windows.Forms.Timer>\-Komponente von Windows Forms hinzu.  
  
    > [!NOTE]
    >  Die Windows Forms\-<xref:System.Windows.Forms.Timer?displayProperty=fullName>\-Komponente ist für eine Windows Forms\-Umgebung vorgesehen.  Wenn Sie einen Zeitgeber benötigen, der für eine Serverumgebung geeignet ist, informieren Sie sich unter [Introduction to Server\-Based Timers](http://msdn.microsoft.com/de-de/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
6.  Legen Sie die <xref:System.Windows.Forms.Timer.Enabled%2A>\-Eigenschaft auf `true` fest.  
  
7.  Legen Sie die <xref:System.Windows.Forms.Timer.Interval%2A>\-Eigenschaft von <xref:System.Windows.Forms.Timer> auf 30000 fest.  
  
    > [!NOTE]
    >  Die <xref:System.Windows.Forms.Timer.Interval%2A>\-Eigenschaft der <xref:System.Windows.Forms.Timer>\-Komponente wird auf 30 Sekunden \(30.000 Millisekunden\) festgelegt, um sicherzustellen, dass die angezeigte Zeit die wirkliche Zeit genau wiedergibt.  
  
### So implementieren Sie den Zeitgeber zum Aktualisierne der Statusleiste  
  
1.  Fügen Sie im Ereignishandler der <xref:System.Windows.Forms.Timer>\-Komponente zum Aktualisieren des Bereichs des <xref:System.Windows.Forms.StatusBar>\-Steuerelements folgenden Code ein.  
  
    ```vb  
    Private Sub Timer1_Tick(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Timer1.Tick  
       StatusBar1.Panels(0).Text = Now.ToShortTimeString  
    End Sub  
  
    ```  
  
    ```csharp  
    private void timer1_Tick(object sender, System.EventArgs e)  
    {  
       statusBar1.Panels[0].Text = DateTime.Now.ToShortTimeString();  
    }  
  
    ```  
  
    ```cpp  
    private:  
      System::Void timer1_Tick(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        statusBar1->Panels[0]->Text =  
          DateTime::Now.ToShortTimeString();  
      }  
    ```  
  
     Nun können Sie die Anwendung ausführen und die im Statusleistenbereich angezeigte Uhr beobachten.  
  
### So testen Sie die Anwendung  
  
1.  Debuggen Sie die Anwendung, und drücken Sie F5, um sie auszuführen.  Details über das Debuggen finden Sie unter [Debuggen in Visual Studio](../Topic/Debugging%20in%20Visual%20Studio.md).  
  
    > [!NOTE]
    >  Nach etwa 30 Sekunden wird die Uhr in der Statusleiste angezeigt.  Dadurch kann eine möglichst genaue Zeit abgerufen werden.  Um die Uhr hingegen früher einzublenden, müssen Sie den zuvor in Schritt 7 festgelegten Wert der <xref:System.Windows.Forms.Timer.Interval%2A>\-Eigenschaft verringern.  
  
## Siehe auch  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [Gewusst wie: Hinzufügen von Bereichen zu einem StatusBar\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)   
 [Gewusst wie: Bestimmen, auf welchen Bereich im StatusBar\-Steuerelement in Windows Forms geklickt wurde](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)   
 [Übersicht über das StatusBar\-Steuerelement](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)