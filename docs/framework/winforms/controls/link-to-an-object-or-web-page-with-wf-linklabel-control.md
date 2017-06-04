---
title: "Gewusst wie: Verkn&#252;pfen eines Objekts oder einer Webseite mit dem LinkLabel-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "Beispiele [Windows Forms], LinkLabel-Steuerelement"
  - "Verknüpfen, Für andere Formulare"
  - "LinkLabel-Steuerelement [Windows Forms], Beispiele"
  - "LinkLabel-Steuerelement [Windows Forms], Verknüpfen mit Objekt oder Webseite"
  - "Verknüpfungen, Für andere Formulare"
  - "Link-Steuerelement für Webseiten"
  - "Windows Forms, Verknüpfen mit Objekten"
  - "Windows Forms, Verknüpfen mit Webseiten"
ms.assetid: 6c91c975-3cb7-4504-82f0-fc6255f8fb85
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: Verkn&#252;pfen eines Objekts oder einer Webseite mit dem LinkLabel-Steuerelement in Windows&#160;Forms
Mit dem <xref:System.Windows.Forms.LinkLabel>\-Steuerelement in Windows Forms können Sie in einem Formular Webhyperlinks erstellen.  Die Farbe des Links kann, nachdem darauf geklickt wurde, geändert werden, um zu signalisieren, dass er bereits besucht wurde.  Weitere Informationen über das Ändern der Farbe finden Sie unter [Gewusst wie: Ändern der Darstellung des LinkLabel\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).  
  
## Verknüpfen mit einem anderen Formular  
  
#### So stellen Sie mit einem LinkLabel\-Steuerelement einen Link mit einem anderen Steuerelement her  
  
1.  Legen Sie für die <xref:System.Windows.Forms.LinkLabel.Text%2A>\-Eigenschaft eine geeignete Beschriftung fest.  
  
2.  Definieren Sie die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>\-Eigenschaft, um festzulegen, welcher Teil der Beschriftung als Link gekennzeichnet wird.  Wie der Link gekennzeichnet wird, hängt von den Darstellungseigenschaften der Linkbezeichnung ab.  Der <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>\-Wert wird durch ein <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>\-Objekt mit zwei Zahlen dargestellt. Diese stehen für die Position des ersten Zeichens und die Anzahl der Zeichen.  Die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>\-Eigenschaft kann im Eigenschaftenfenster oder in Code ähnlich wie folgt festgelegt werden:  
  
    ```vb  
    ' In this code example, the link area has been set to begin  
    ' at the first character and extend for eight characters.  
    ' You may need to modify this based on the text entered in Step 1.  
    LinkLabel1.LinkArea = New LinkArea(0, 8)  
  
    ```  
  
    ```csharp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1.LinkArea = new LinkArea(0,8);  
  
    ```  
  
    ```cpp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1->LinkArea = LinkArea(0,8);  
    ```  
  
3.  Rufen Sie im <xref:System.Windows.Forms.LinkLabel.LinkClicked>\-Ereignishandler die <xref:System.Windows.Forms.Form.Show%2A>\-Methode auf, um ein weiteres Formular im Projekt zu öffnen, und legen Sie die <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>\-Eigenschaft auf `true` fest.  
  
    > [!NOTE]
    >  Eine Instanz der <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs>\-Klasse enthält einen Verweis auf das <xref:System.Windows.Forms.LinkLabel>\-Steuerelement, auf das geklickt wurde, sodass eine Umwandlung des `sender` \-Objekts nicht erforderlich ist.  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked(ByVal Sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       ' Show another form.  
       Dim f2 As New Form()  
       f2.Show  
       LinkLabel1.LinkVisited = True  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void linkLabel1_LinkClicked(object sender, System. Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       // Show another form.  
       Form f2 = new Form();  
       f2.Show();  
       linkLabel1.LinkVisited = true;  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Show another form.  
          Form ^ f2 = new Form();  
          f2->Show();  
          linkLabel1->LinkVisited = true;  
       }  
    ```  
  
## Verknüpfen zu einer Webseite  
 Darüber hinaus kann mithilfe des <xref:System.Windows.Forms.LinkLabel>\-Steuerelements eine Webseite in einem Standardbrowser angezeigt werden.  
  
#### So starten Sie Internet Explorer und stellen einen Link mit einer Webseite mit einem LinkLabel\-Steuerelement her  
  
1.  Legen Sie für die <xref:System.Windows.Forms.LinkLabel.Text%2A>\-Eigenschaft eine geeignete Beschriftung fest.  
  
2.  Definieren Sie die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>\-Eigenschaft, um festzulegen, welcher Teil der Beschriftung als Link gekennzeichnet wird.  
  
3.  Rufen Sie im <xref:System.Windows.Forms.LinkLabel.LinkClicked>\-Ereignishandler in einem Ausnahmebehandlungsblock eine zweite Prozedur auf, die für die <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>\-Eigenschaft `true` festlegt und die <xref:System.Diagnostics.Process.Start%2A>\-Methode verwendet, um den Standardbrowser mit einer URL zu starten.  Um die <xref:System.Diagnostics.Process.Start%2A>\-Methode zu verwenden, müssen Sie einen Verweis auf den <xref:System.Diagnostics?displayProperty=fullName>\-Namespace hinzufügen.  
  
    > [!IMPORTANT]
    >  Wenn der unten stehende Code in einer teilweise vertrauenswürdigen Umgebung ausgeführt wird \(z. B. auf einem freigegebenen Laufwerk\), schlägt die Umwandlung durch den JIT\-Compiler fehl, wenn die `VisitLink`\-Methode aufgerufen wird.  Die Anweisung`System.Diagnostics.Process.Start` verursacht einen Linkaufruf, der fehlschlägt.  Bei einem Fehlschlag des JIT\-Compilers stellt der unten stehende Code die erfolgreiche Behandlung des Fehlers sicher, indem die Ausnahme abgefangen wird, wenn die `VisitLink`\-Methode aufgerufen wird.  
  
    ```vb  
    Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       Try  
          VisitLink()  
       Catch ex As Exception  
          ' The error message  
          MessageBox.Show("Unable to open link that was clicked.")  
       End Try  
    End Sub  
  
    Sub VisitLink()  
       ' Change the color of the link text by setting LinkVisited   
       ' to True.  
       LinkLabel1.LinkVisited = True  
       ' Call the Process.Start method to open the default browser   
       ' with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com")  
    End Sub  
  
    ```  
  
    ```csharp  
    private void linkLabel1_LinkClicked(object sender, System.Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       try  
       {  
          VisitLink();  
       }  
       catch (Exception ex )  
       {  
          MessageBox.Show("Unable to open link that was clicked.");  
       }  
    }  
  
    private void VisitLink()  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to true.  
       linkLabel1.LinkVisited = true;  
       //Call the Process.Start method to open the default browser   
       //with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com");  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          try  
          {  
             VisitLink();  
          }  
          catch (Exception ^ ex)  
          {  
             MessageBox::Show("Unable to open link that was clicked.");  
          }  
       }  
    private:  
       void VisitLink()  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to true.  
          linkLabel1->LinkVisited = true;  
          // Call the Process.Start method to open the default browser   
          // with a URL:  
          System::Diagnostics::Process::Start("http://www.microsoft.com");  
       }  
    ```  
  
## Siehe auch  
 <xref:System.Diagnostics.Process.Start%2A?displayProperty=fullName>   
 [Übersicht über das LinkLabel\-Steuerelement](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)   
 [Gewusst wie: Ändern der Darstellung des LinkLabel\-Steuerelements in Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)   
 [LinkLabel\-Steuerelement](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)