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
ms.openlocfilehash: cd9c53527429dfc3e7156c4023b52509452b96cd
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046249"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a>Vorgehensweise: Verknüpfen eines Objekts oder einer Webseite mit dem LinkLabel-Steuerelement in Windows Forms

Das Windows Forms <xref:System.Windows.Forms.LinkLabel> Steuerelement ermöglicht das Erstellen von Links im Webformat auf Ihrem Formular. Wenn auf den Link geklickt wird, können Sie die zugehörige Farbe ändern, um anzugeben, dass der Link besucht wurde. Weitere Informationen zum Ändern der Farbe finden [Sie unter Gewusst wie: Ändern Sie das Aussehen des Windows Forms LinkLabel-](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)Steuer Elements.

## <a name="linking-to-another-form"></a>Verknüpfen mit einem anderen Formular

#### <a name="to-link-to-another-form-with-a-linklabel-control"></a>So verknüpfen Sie ein anderes Formular mit einem LinkLabel-Steuerelement

1. Legen Sie <xref:System.Windows.Forms.LinkLabel.Text%2A> die-Eigenschaft auf eine entsprechende Beschriftung fest.

2. Legen Sie <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> die-Eigenschaft fest, um zu bestimmen, welcher Teil der Beschriftung als Link angegeben wird. Wie dies angegeben wird, hängt von den Darstellungs bezogenen Eigenschaften der Link Bezeichnung ab. Der <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> -Wert wird durch ein <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> -Objekt dargestellt, das zwei Zahlen enthält: die Position des Anfangs Zeichens und die Anzahl der Zeichen. Die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> -Eigenschaft kann im-Eigenschaftenfenster oder im Code auf eine Weise festgelegt werden, die der folgenden ähnelt:

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

3. Rufen Sie im- <xref:System.Windows.Forms.Form.Show%2A> <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> `true`Ereignishandler die-Methode auf, um ein anderes Formular im Projekt zu öffnen, und legen Sie die-Eigenschaft auf fest. <xref:System.Windows.Forms.LinkLabel.LinkClicked>

    > [!NOTE]
    > Eine Instanz der <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> -Klasse enthält einen Verweis auf das <xref:System.Windows.Forms.LinkLabel> Steuerelement, auf das geklickt wurde, sodass das `sender` -Objekt nicht umgewandelt werden muss.

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

Das <xref:System.Windows.Forms.LinkLabel> -Steuerelement kann auch verwendet werden, um eine Webseite mit dem Standardbrowser anzuzeigen.

#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a>So starten Sie Internet Explorer und verknüpfen eine Webseite mit einem LinkLabel-Steuerelement

1. Legen Sie <xref:System.Windows.Forms.LinkLabel.Text%2A> die-Eigenschaft auf eine entsprechende Beschriftung fest.

2. Legen Sie <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> die-Eigenschaft fest, um zu bestimmen, welcher Teil der Beschriftung als Link angegeben wird.

3. Im- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> `true` <xref:System.Diagnostics.Process.Start%2A> Ereignishandler wird in der Mitte eines Ausnahme Behandlungs Blocks eine zweite Prozedur aufgerufen, mit der die-Eigenschaft auf festgelegt wird und die-Methode verwendet wird, um den Standardbrowser mit einer URL zu starten. <xref:System.Windows.Forms.LinkLabel.LinkClicked> Um die <xref:System.Diagnostics.Process.Start%2A> -Methode verwenden zu können, müssen Sie einen Verweis <xref:System.Diagnostics?displayProperty=nameWithType> auf den-Namespace hinzufügen.

    > [!IMPORTANT]
    > Wenn der folgende Code in einer teilweise vertrauenswürdigen Umgebung (z. b. auf einem freigegebenen Laufwerk) ausgeführt wird, schlägt der JIT `VisitLink` -Compiler fehl, wenn die-Methode aufgerufen wird. Die `System.Diagnostics.Process.Start` -Anweisung verursacht einen Verbindungs Aufruf, der fehlschlägt. Wenn Sie die Ausnahme abfangen `VisitLink` , wenn die-Methode aufgerufen wird, stellt der folgende Code sicher, dass der Fehler ordnungsgemäß behandelt wird, wenn der JIT-Compiler fehlschlägt.

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
- [Vorgehensweise: Ändern der Darstellung des Windows Forms LinkLabel-Steuer Elements](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [LinkLabel-Steuerelement](linklabel-control-windows-forms.md)
