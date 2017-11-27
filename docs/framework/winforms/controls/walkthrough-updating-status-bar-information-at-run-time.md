---
title: 'Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], updating at run time
- status bars [Windows Forms], refreshing panels
- StatusBar control [Windows Forms], refreshing panels
- panels [Windows Forms], refreshing status bar
ms.assetid: cc2abb06-c082-49f7-a5a3-2fd1bbcb58d1
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6c67aa303f375734408201ce15d1c3db3dc32c8e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-updating-status-bar-information-at-run-time"></a>Exemplarische Vorgehensweise: Aktualisieren von Statusleisteninformationen zur Laufzeit
> [!IMPORTANT]
>  Die <xref:System.Windows.Forms.StatusStrip> und <xref:System.Windows.Forms.ToolStripStatusLabel> Steuerelemente ersetzen und Funktionen hinzufügen der <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> steuert; allerdings die <xref:System.Windows.Forms.StatusBar> und <xref:System.Windows.Forms.StatusBarPanel> Steuerelemente werden für die Abwärtskompatibilität und für zukünftige Verwendung beibehalten, wenn Sie Wählen Sie aus.  
  
 Ein Programm wird Sie häufig auffordern, die Inhalte von Bereichen der Statusleiste basierend auf Änderungen am Anwendungszustand oder anderen Benutzerinteraktionen dynamisch zur Laufzeit zu aktualisieren. Dies ist eine gängige Methode, Benutzern mitzuteilen, dass Tasten wie die FESTSTELLTASTE, NUM- oder ROLLEN-TASTE aktiviert sind oder um das Datum oder eine Uhr als praktische Referenz zur Verfügung zu stellen.  
  
 Im folgenden Beispiel verwenden Sie eine Instanz von der <xref:System.Windows.Forms.StatusBarPanel> -Klasse zum Hosten einer Uhr.  
  
### <a name="to-get-the-status-bar-ready-for-updating"></a>So bereiten Sie die Statusleiste für die Aktualisierung vor  
  
1.  Erstellen Sie ein neues Windows-Formular.  
  
2.  Fügen Sie Ihrem Formular ein <xref:System.Windows.Forms.StatusBar>-Steuerelement hinzu. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
3.  Hinzufügen einer Statusleistenbereichs auf Ihre <xref:System.Windows.Forms.StatusBar> Steuerelement. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Bereichen zu einem StatusBar-Steuerelement](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md).  
  
4.  Für die <xref:System.Windows.Forms.StatusBar> Steuerelementsatz, die Sie dem Formular hinzugefügt der <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> Eigenschaft `true`.  
  
5.  Hinzufügen einer Windows Forms <xref:System.Windows.Forms.Timer> -Komponente zum Formular.  
  
    > [!NOTE]
    >  Windows Forms <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> Komponente ist für eine Windows Forms-Umgebung entwickelt. Wenn Sie einen für eine Serverumgebung geeigneten Timer benötigen, lesen Sie die Informationen unter [Introduction to Server-Based Timers (Einführung in serverbasierte Timer)](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
6.  Legen Sie die <xref:System.Windows.Forms.Timer.Enabled%2A>-Eigenschaft auf `true` fest.  
  
7.  Festlegen der <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft von der <xref:System.Windows.Forms.Timer> auf 30000.  
  
    > [!NOTE]
    >  Die <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft von der <xref:System.Windows.Forms.Timer> Komponente auf 30 Sekunden (30.000 Millisekunden) festgelegt ist, um sicherzustellen, dass die genaue Uhrzeit in die angezeigte Uhrzeit wiedergegeben werden.  
  
### <a name="to-implement-the-timer-to-update-the-status-bar"></a>So Implementieren Sie den Zeitgeber zum Aktualisieren der Statusleiste  
  
1.  Legen Sie den folgenden Code in den Ereignishandler von dem <xref:System.Windows.Forms.Timer> Komponente zum Aktualisieren des Bereichs der der <xref:System.Windows.Forms.StatusBar> Steuerelement.  
  
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
  
     An diesem Punkt sind Sie bereit, die Anwendung auszuführen und zu sehen, wie die Uhr im Statusleistenbereich ausgeführt wird.  
  
### <a name="to-test-the-application"></a>So testen Sie die Anwendung  
  
1.  Debuggen Sie die Anwendung und drücken Sie F5, um die Anwendung auszuführen. Weitere Informationen zum Debugging finden Sie unter [Debuggen in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).  
  
    > [!NOTE]
    >  Es dauert ungefähr 30 Sekunden, bis die Uhr in der Statusleiste angezeigt wird. Dies ist die akkurateste mögliche Zeit. Umgekehrt, um die Uhr früher zu machen, können, verringern Sie den Wert von der <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft, die Sie in Schritt 7 in der vorherigen Prozedur festlegen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [Vorgehensweise: Hinzufügen von Bereichen zu einem StatusBar-Steuerelement](../../../../docs/framework/winforms/controls/how-to-add-panels-to-a-statusbar-control.md)  
 [Vorgehensweise: Bestimmen, auf welchen Bereich im StatusBar-Steuerelement in Windows Forms geklickt wurde](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)  
 [Übersicht über das StatusBar-Steuerelement](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
