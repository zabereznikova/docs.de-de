---
title: 'Vorgehensweise: Verknüpfen eines Objekts oder einer Webseite mit dem LinkLabel-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Windows Forms, linking to objects
- Web page link control
- linking [Windows Forms], to other forms
- Windows Forms, linking to Web pages
- links [Windows Forms], to other forms
- LinkLabel control [Windows Forms], linking to object or Web page
- LinkLabel control [Windows Forms], examples
ms.assetid: 6c91c975-3cb7-4504-82f0-fc6255f8fb85
ms.openlocfilehash: edebfaee6f0da6826f4b757568408662f3208d41
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012859"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a>Vorgehensweise: Verknüpfen eines Objekts oder einer Webseite mit dem LinkLabel-Steuerelement in Windows Forms
Die Windows-Formulare <xref:System.Windows.Forms.LinkLabel> Steuerelement ermöglicht es Ihnen die Erstellung von Weblinks in Ihrem Formular. Wenn auf der Link geklickt wird, können Sie ändern die Farbe, um anzugeben, dass der Link bereits besucht wurde. Weitere Informationen zum Ändern der Farbe finden Sie unter [Vorgehensweise: Ändern der Darstellung des LinkLabel-Steuerelement von Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).  
  
## <a name="linking-to-another-form"></a>Verknüpfen mit einer anderen Form  
  
#### <a name="to-link-to-another-form-with-a-linklabel-control"></a>So verknüpfen Sie mit einem anderen Formular mit einem LinkLabel-Steuerelement  
  
1. Legen Sie die <xref:System.Windows.Forms.LinkLabel.Text%2A> Eigenschaft eine geeignete Beschriftung.  
  
2. Legen Sie die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Eigenschaft, um zu bestimmen, welcher Teil der Beschriftung als Link gekennzeichnet wird. Wie es angegeben wird, hängt von der Darstellungseigenschaften für die Link-Beschriftung ab. Die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Wert wird durch dargestellt eine <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Objekt, das zwei Zahlen, die Position des ersten Zeichens und die Anzahl der Zeichen enthält. Die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Eigenschaft kann festgelegt werden, in dem Fenster "Eigenschaften" oder im Code ähnlich dem folgenden:  
  
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
  
3. In der <xref:System.Windows.Forms.LinkLabel.LinkClicked> -Ereignishandler Aufrufen der <xref:System.Windows.Forms.Form.Show%2A> Methode, um eine andere Form im Projekt öffnen, und legen die <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> Eigenschaft `true`.  
  
    > [!NOTE]
    >  Eine Instanz von der <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> Klasse enthält einen Verweis auf die <xref:System.Windows.Forms.LinkLabel> -Steuerelement, das geklickt wurde, daher keine Notwendigkeit besteht, umgewandelt, die `sender` Objekt.  
  
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
  
## <a name="linking-to-a-web-page"></a>Verknüpfen mit einer Webseite  
 Die <xref:System.Windows.Forms.LinkLabel> -Steuerelement kann auch verwendet werden, um eine Webseite mit den Standardbrowser anzuzeigen.  
  
#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a>Starten Sie Internet Explorer "und" Link zu einer Webseite mit einem LinkLabel-Steuerelement  
  
1. Legen Sie die <xref:System.Windows.Forms.LinkLabel.Text%2A> Eigenschaft eine geeignete Beschriftung.  
  
2. Legen Sie die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Eigenschaft, um zu bestimmen, welcher Teil der Beschriftung als Link gekennzeichnet wird.  
  
3. In der <xref:System.Windows.Forms.LinkLabel.LinkClicked> -Ereignishandler in einen Ausnahmebehandlungsblock, rufen Sie eine zweite Prozedur, die festlegt der <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> Eigenschaft `true` und verwendet die <xref:System.Diagnostics.Process.Start%2A> Methode, um den Standardbrowser mit einer URL zu starten. Verwenden der <xref:System.Diagnostics.Process.Start%2A> Methode müssen Sie zum Hinzufügen eines Verweises auf die <xref:System.Diagnostics?displayProperty=nameWithType> Namespace.  
  
    > [!IMPORTANT]
    >  Wenn Sie der folgenden Code in einer teilweise vertrauenswürdigen Umgebung ausgeführt wird (z. B. auf einem freigegebenen Laufwerk), schlägt fehl, wenn der JIT-Compiler die `VisitLink` Methode wird aufgerufen. Die `System.Diagnostics.Process.Start` Anweisung bewirkt, dass einen Linkaufruf, der ein Fehler auftritt. Durch die Ausnahme abfangen, wenn die `VisitLink` Methode aufgerufen wird, wird der folgende Code stellt sicher, dass der JIT-Compiler ein Fehler auftritt, der Fehler ordnungsgemäß behandelt wird.  
  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- [Übersicht über das LinkLabel-Steuerelement](linklabel-control-overview-windows-forms.md)
- [Vorgehensweise: Ändern der Darstellung des LinkLabel-Steuerelement von Windows Forms](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [LinkLabel-Steuerelement](linklabel-control-windows-forms.md)
