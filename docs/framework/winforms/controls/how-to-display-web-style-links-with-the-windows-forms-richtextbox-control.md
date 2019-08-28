---
title: 'Vorgehensweise: Anzeigen von Hyperlinks mit dem RichTextBox-Steuerelement von Windows Forms'
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
ms.openlocfilehash: ce71981f7b233d3e168689c766128646eed3e981
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046185"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>Vorgehensweise: Anzeigen von Hyperlinks mit dem RichTextBox-Steuerelement von Windows Forms

Das Windows Forms <xref:System.Windows.Forms.RichTextBox> Steuerelement kann Weblinks als farbige und unterstrichen anzeigen. Sie können Code schreiben, mit dem ein Browserfenster geöffnet wird, in dem die im Linktext angegebene Website angezeigt wird, wenn auf den Link geklickt wird.

### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>So verknüpfen Sie eine Webseite mit dem RichTextBox-Steuerelement

1. Legen Sie <xref:System.Windows.Forms.RichTextBox.Text%2A> die-Eigenschaft auf eine Zeichenfolge fest, die eine gültige URL enthält http://www.microsoft.com/ (z. b. "").

2. Stellen Sie sicher <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> , dass die- `true` Eigenschaft auf festgelegt ist (die Standardeinstellung).

3. Erstellen Sie eine neue globale Instanz des <xref:System.Diagnostics.Process> -Objekts.

4. Schreiben Sie einen Ereignishandler für <xref:System.Windows.Forms.RichTextBox.LinkClicked> das-Ereignis, das den Browser den gewünschten Text sendet.

    Im folgenden Beispiel öffnet das <xref:System.Windows.Forms.RichTextBox.LinkClicked> -Ereignis eine Instanz von Internet Explorer für die URL, die in der <xref:System.Windows.Forms.RichTextBox.Text%2A> -Eigenschaft des <xref:System.Windows.Forms.RichTextBox> -Steuer Elements angegeben ist. In diesem Beispiel wird ein Formular mit <xref:System.Windows.Forms.RichTextBox> einem-Steuerelement angenommen.

    > [!IMPORTANT]
    > Beim Aufrufen der <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> -Methode wird eine <xref:System.Security.SecurityException> -Ausnahme angezeigt, wenn Sie den Code in einem teilweise vertrauenswürdigen Kontext ausführen, weil Sie nicht über ausreichende Berechtigungen verfügen. Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../misc/code-access-security-basics.md).

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

    (Visual C++) Sie müssen den Prozess `p`initialisieren, indem Sie die folgende Anweisung in den Konstruktor Ihres Formulars einschließen:

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

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox-Steuerelement](richtextbox-control-windows-forms.md)
- [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)
