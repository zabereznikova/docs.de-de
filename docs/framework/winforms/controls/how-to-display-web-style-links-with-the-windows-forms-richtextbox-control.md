---
title: "Gewusst wie: Anzeigen von Hyperlinks mit dem RichTextBox-Steuerelement von Windows Forms"
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
- text boxes [Windows Forms], displaying Web links
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], linking to Web pages
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 80f794be15eae33ca4e28dc0cfe04872f63230b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>Gewusst wie: Anzeigen von Hyperlinks mit dem RichTextBox-Steuerelement von Windows Forms
Windows Forms <xref:System.Windows.Forms.RichTextBox> -Steuerelement kann Weblinks farbig und unterstrichen anzeigen. Sie können Code schreiben, die öffnet ein Browserfenster mit der Website, die in der Text des Links angegeben werden, wenn auf der Link geklickt wird.  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>So verknüpfen Sie mit einer Webseite mit dem RichTextBox-Steuerelement  
  
1.  Legen Sie die <xref:System.Windows.Forms.RichTextBox.Text%2A> -Eigenschaft in eine Zeichenfolge, die eine gültige URL (z. B. "http://www.microsoft.com/") enthält.  
  
2.  Stellen Sie sicher, dass die <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> -Eigenschaftensatz auf `true` (Standard).  
  
3.  Erstellen Sie eine neue globale Instanz von der <xref:System.Diagnostics.Process> Objekt.  
  
4.  Schreiben Sie einen Ereignishandler für das <xref:System.Windows.Forms.RichTextBox.LinkClicked> Ereignis, das vom Browser auf den gewünschten Text gesendet.  
  
     Im folgenden Beispiel wird die <xref:System.Windows.Forms.RichTextBox.LinkClicked> Ereignis öffnet eine Instanz von Internet Explorer, der im angegebenen URL der <xref:System.Windows.Forms.RichTextBox.Text%2A> Eigenschaft von der <xref:System.Windows.Forms.RichTextBox> Steuerelement. In diesem Beispiel wird angenommen, ein Formular mit einem <xref:System.Windows.Forms.RichTextBox> Steuerelement.  
  
    > [!IMPORTANT]
    >  Im Aufruf der <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> -Methode, tritt eine <xref:System.Security.SecurityException> -Ausnahme aus, wenn Sie den Code in einem teilweise vertrauenswürdigen Kontext aufgrund unzureichender Berechtigungen ausgeführt werden. Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../../docs/framework/misc/code-access-security-basics.md).  
  
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
  
     ([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Müssen Sie den Prozess initialisieren `p`, wozu Sie verwenden können, indem Sie die folgende Anweisung in den Konstruktor des Formulars einschließen:  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Fügen Sie den folgenden Code in den Konstruktor der Form ein, um den Ereignishandler zu registrieren.  
  
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
  
     Es ist wichtig, den Prozess sofort zu beenden, den Sie erstellt haben, nachdem Sie die Arbeit daran fertig haben. In Bezug auf den oben aufgeführten Code kann der Code, den Prozess beenden wie folgt aussehen:  
  
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
 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>  
 <xref:System.Windows.Forms.RichTextBox.LinkClicked>  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
