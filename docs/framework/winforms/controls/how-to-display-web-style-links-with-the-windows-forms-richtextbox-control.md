---
title: 'Vorgehensweise: Anzeigen von Hyperlinks mit dem RichTextBox-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 64a2c8d9a9f6b8a7271a659b80ca2a63c423b3bc
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718519"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>Vorgehensweise: Anzeigen von Hyperlinks mit dem RichTextBox-Steuerelement in Windows Forms
Die Windows-Formulare <xref:System.Windows.Forms.RichTextBox> -Steuerelement können Weblinks farbig und unterstrichen angezeigt. Sie können Code schreiben, die öffnet ein Browserfenster mit der Website, die in der Text des Links angegeben werden, wenn auf der Link geklickt wird.  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>So verknüpfen Sie mit der eine Webseite mit dem RichTextBox-Steuerelement  
  
1.  Legen Sie die <xref:System.Windows.Forms.RichTextBox.Text%2A> Eigenschaft, um eine Zeichenfolge, enthält eine gültige URL ein (z. B. "http://www.microsoft.com/").  
  
2.  Stellen Sie sicher, dass die <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> -Eigenschaftensatz auf `true` (Standard).  
  
3.  Erstellen Sie eine neue globale Instanz des der <xref:System.Diagnostics.Process> Objekt.  
  
4.  Schreiben Sie einen Ereignishandler für die <xref:System.Windows.Forms.RichTextBox.LinkClicked> -Ereignis, das an den gewünschten Text durch den Browser sendet.  
  
     Im folgenden Beispiel wird die <xref:System.Windows.Forms.RichTextBox.LinkClicked> Ereignis öffnet eine Instanz von Internet Explorer, um die URL in die <xref:System.Windows.Forms.RichTextBox.Text%2A> Eigenschaft der <xref:System.Windows.Forms.RichTextBox> Steuerelement. In diesem Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.RichTextBox> Steuerelement.  
  
    > [!IMPORTANT]
    >  Im Aufruf der <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> -Methode, tritt ein <xref:System.Security.SecurityException> -Ausnahme aus, wenn Sie den Code in einem teilweise vertrauenswürdigen Kontext aufgrund fehlender Berechtigungen ausführen. Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../misc/code-access-security-basics.md).  
  
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
  
     ([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Sie müssen den Prozess initialisieren `p`, dies können Sie dazu die folgende Anweisung im Konstruktor des Formulars:  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     (Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
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
  
     Es ist wichtig, um den Prozess sofort zu beenden, die, den Sie erstellt haben, sobald Sie damit fertig sind. In Bezug auf den oben dargestellten Code, kann Code, um den Vorgang zu beenden, wie folgt aussehen:  
  
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
