---
title: Anzeigen von Links im Webstil mit dem RichTextBox-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying Web links
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], linking to Web pages
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
ms.openlocfilehash: 78a07a250744018f121b03f2973b1661ed6bf764
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745532"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>Gewusst wie: Anzeigen von Hyperlinks mit dem RichTextBox-Steuerelement von Windows Forms

Das Windows Forms <xref:System.Windows.Forms.RichTextBox>-Steuerelement kann Weblinks farblich anzeigen und unterstrichen anzeigen. Sie können Code schreiben, mit dem ein Browserfenster geöffnet wird, in dem die im Linktext angegebene Website angezeigt wird, wenn auf den Link geklickt wird.

### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>So verknüpfen Sie eine Webseite mit dem RichTextBox-Steuerelement

1. Legen Sie die <xref:System.Windows.Forms.RichTextBox.Text%2A>-Eigenschaft auf eine Zeichenfolge fest, die eine gültige URL enthält (z. b. "http://www.microsoft.com/").

2. Stellen Sie sicher, dass die <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>-Eigenschaft auf `true` (Standardeinstellung) festgelegt ist.

3. Erstellen Sie eine neue globale Instanz des <xref:System.Diagnostics.Process> Objekts.

4. Schreiben Sie einen Ereignishandler für das <xref:System.Windows.Forms.RichTextBox.LinkClicked> Ereignis, das den Browser den gewünschten Text sendet.

    Im folgenden Beispiel wird mit dem <xref:System.Windows.Forms.RichTextBox.LinkClicked>-Ereignis eine Instanz von Internet Explorer für die URL geöffnet, die in der <xref:System.Windows.Forms.RichTextBox.Text%2A>-Eigenschaft des <xref:System.Windows.Forms.RichTextBox>-Steuer Elements angegeben ist. In diesem Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.RichTextBox>-Steuerelement angenommen.

    > [!IMPORTANT]
    > Wenn Sie die <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>-Methode aufrufen, tritt eine <xref:System.Security.SecurityException> Ausnahme auf, wenn Sie den Code in einem teilweise vertrauenswürdigen Kontext ausführen, weil Sie nicht über ausreichende Berechtigungen verfügen. Weitere Informationen finden Sie unter [Code Access Security Basics](../../misc/code-access-security-basics.md).

    ```vb
    Public p As New System.Diagnostics.Process
    Private Sub RichTextBox1_LinkClicked _
       (ByVal sender As Object, ByVal e As _
       System.Windows.Forms.LinkClickedEventArgs) _
       Handles RichTextBox1.LinkClicked
          ' Call Process.Start method to open a browser
          ' with link text as URL.
          p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText)
    End Sub
    ```

    ```csharp
    public System.Diagnostics.Process p = new System.Diagnostics.Process();

    private void richTextBox1_LinkClicked(object sender,
    System.Windows.Forms.LinkClickedEventArgs e)
    {
       // Call Process.Start method to open a browser
       // with link text as URL.
       p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText);
    }
    ```

    ```cpp
    public:
       System::Diagnostics::Process ^ p;

    private:
       void richTextBox1_LinkClicked(System::Object ^  sender,
          System::Windows::Forms::LinkClickedEventArgs ^  e)
       {
          // Call Process.Start method to open a browser
          // with link text as URL.
          p = System::Diagnostics::Process::Start("IExplore.exe",
             e->LinkText);
       }
    ```

    (Visual C++) Sie müssen Prozess `p`initialisieren, indem Sie die folgende Anweisung in den Konstruktor Ihres Formulars einschließen:

    ```cpp
    p = gcnew System::Diagnostics::Process();
    ```

    (Visualisierung C#, Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.

    ```csharp
    this.richTextBox1.LinkClicked += new
       System.Windows.Forms.LinkClickedEventHandler
       (this.richTextBox1_LinkClicked);
    ```

    ```cpp
    this->richTextBox1->LinkClicked += gcnew
       System::Windows::Forms::LinkClickedEventHandler
       (this, &Form1::richTextBox1_LinkClicked);
    ```

    Es ist wichtig, dass Sie den von Ihnen erstellten Prozess sofort beenden, nachdem Sie die Arbeit mit dem Prozess abgeschlossen haben. Der Code, der sich auf den oben dargestellten Code bezieht, könnte wie folgt aussehen:

    ```vb
    Public Sub StopWebProcess()
       p.Kill()
    End Sub
    ```

    ```csharp
    public void StopWebProcess()
    {
       p.Kill();
    }
    ```

    ```cpp
    public: void StopWebProcess()
    {
       p->Kill();
    }
    ```

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox-Steuerelement](richtextbox-control-windows-forms.md)
- [Steuerelemente für Windows Forms](controls-to-use-on-windows-forms.md)
