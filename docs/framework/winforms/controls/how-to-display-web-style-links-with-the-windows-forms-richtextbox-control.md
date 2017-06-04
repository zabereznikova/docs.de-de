---
title: "Gewusst wie: Anzeigen von Hyperlinks mit dem RichTextBox-Steuerelement von Windows&#160;Forms | Microsoft Docs"
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
  - "Beispiele [Windows Forms], Textfelder"
  - "RichTextBox-Steuerelement [Windows Forms], Verknüpfen mit Webseiten"
  - "Textfelder, Anzeigen von Weblinks"
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Anzeigen von Hyperlinks mit dem RichTextBox-Steuerelement von Windows&#160;Forms
Das <xref:System.Windows.Forms.RichTextBox>\-Steuerelement von Windows Forms kann Weblinks farbig und unterstrichen anzeigen.  Sie können Code verfassen, mit dem beim Klicken auf den Link ein Browserfenster geöffnet wird, das die im Linktext angegebene Website anzeigt.  
  
### So verknüpfen Sie eine Webseite mit dem RichTextBox\-Steuerelement  
  
1.  Legen Sie die <xref:System.Windows.Forms.RichTextBox.Text%2A>\-Eigenschaft auf eine Zeichenfolge mit einer gültigen URL fest \(z. B. http:\/\/www.microsoft.com\/germany\).  
  
2.  Stellen Sie sicher, dass für die <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>\-Eigenschaft der Standardwert `true` festgelegt wurde.  
  
3.  Erstellen Sie eine neue globale Instanz des <xref:System.Diagnostics.Process>\-Objekts.  
  
4.  Schreiben Sie einen Ereignishandler für das <xref:System.Windows.Forms.RichTextBox.LinkClicked>\-Ereignis, das den gewünschten Text an den Browser sendet.  
  
     Im folgenden Beispiel öffnet das <xref:System.Windows.Forms.RichTextBox.LinkClicked>\-Ereignis eine Instanz von Internet Explorer für die in der <xref:System.Windows.Forms.RichTextBox.Text%2A>\-Eigenschaft des <xref:System.Windows.Forms.RichTextBox>\-Steuerelements enthaltene URL.  Bei diesem Beispiel wird vorausgesetzt, dass ein Formular bereits über ein <xref:System.Windows.Forms.RichTextBox>\-Steuerelement verfügt.  
  
    > [!IMPORTANT]
    >  Ein Aufruf der <xref:System.Diagnostics.Process.Start%2A?displayProperty=fullName>\-Methode führt aufgrund unzureichender Berechtigungen zu einer <xref:System.Security.SecurityException>\-Ausnahme, wenn Sie den Code in einem teilweise vertrauenswürdigen Kontext ausführen.  Weitere Informationen finden Sie unter [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).  
  
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
  
     \([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Sie müssen den Prozess`p` initialisieren. Sie können dazu die folgende Anweisung in den Konstruktor des Formulars einfügen:  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
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
  
     Achten Sie darauf, den Prozess sofort zu beenden, wenn Sie ihn nicht mehr benötigen.  Für das oben genannte Beispiel könnte der Code zum Anhalten des Prozesses wie folgt lauten:  
  
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
  
## Siehe auch  
 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>   
 <xref:System.Windows.Forms.RichTextBox.LinkClicked>   
 <xref:System.Windows.Forms.RichTextBox>   
 [RichTextBox\-Steuerelement](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)   
 [Steuerelemente für Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)