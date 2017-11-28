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
ms.openlocfilehash: 5391c48720e68a8a7e6e0fb7735252d00025adc6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="f1f6f-102">Gewusst wie: Anzeigen von Hyperlinks mit dem RichTextBox-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f1f6f-102">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="f1f6f-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> -Steuerelement kann Weblinks farbig und unterstrichen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f1f6f-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display Web links as colored and underlined.</span></span> <span data-ttu-id="f1f6f-104">Sie können Code schreiben, die öffnet ein Browserfenster mit der Website, die in der Text des Links angegeben werden, wenn auf der Link geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="f1f6f-104">You can write code that opens a browser window showing the Web site specified in the link text when the link is clicked.</span></span>  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a><span data-ttu-id="f1f6f-105">So verknüpfen Sie mit einer Webseite mit dem RichTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f1f6f-105">To link to a Web page with the RichTextBox control</span></span>  
  
1.  <span data-ttu-id="f1f6f-106">Legen Sie die <xref:System.Windows.Forms.RichTextBox.Text%2A> -Eigenschaft in eine Zeichenfolge, die eine gültige URL (z. B. "http://www.microsoft.com/") enthält.</span><span class="sxs-lookup"><span data-stu-id="f1f6f-106">Set the <xref:System.Windows.Forms.RichTextBox.Text%2A> property to a string that includes a valid URL (for example, "http://www.microsoft.com/").</span></span>  
  
2.  <span data-ttu-id="f1f6f-107">Stellen Sie sicher, dass die <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> -Eigenschaftensatz auf `true` (Standard).</span><span class="sxs-lookup"><span data-stu-id="f1f6f-107">Make sure the <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> property is set to `true` (the default).</span></span>  
  
3.  <span data-ttu-id="f1f6f-108">Erstellen Sie eine neue globale Instanz von der <xref:System.Diagnostics.Process> Objekt.</span><span class="sxs-lookup"><span data-stu-id="f1f6f-108">Create a new global instance of the <xref:System.Diagnostics.Process> object.</span></span>  
  
4.  <span data-ttu-id="f1f6f-109">Schreiben Sie einen Ereignishandler für das <xref:System.Windows.Forms.RichTextBox.LinkClicked> Ereignis, das vom Browser auf den gewünschten Text gesendet.</span><span class="sxs-lookup"><span data-stu-id="f1f6f-109">Write an event handler for the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event that sends the browser the desired text.</span></span>  
  
     <span data-ttu-id="f1f6f-110">Im folgenden Beispiel wird die <xref:System.Windows.Forms.RichTextBox.LinkClicked> Ereignis öffnet eine Instanz von Internet Explorer, der im angegebenen URL der <xref:System.Windows.Forms.RichTextBox.Text%2A> Eigenschaft von der <xref:System.Windows.Forms.RichTextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f1f6f-110">In the example below, the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event opens an instance of Internet Explorer to the URL specified in the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="f1f6f-111">In diesem Beispiel wird angenommen, ein Formular mit einem <xref:System.Windows.Forms.RichTextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f1f6f-111">This example assumes a form with a <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f1f6f-112">Im Aufruf der <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> -Methode, tritt eine <xref:System.Security.SecurityException> -Ausnahme aus, wenn Sie den Code in einem teilweise vertrauenswürdigen Kontext aufgrund unzureichender Berechtigungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f1f6f-112">In calling the <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> method, you will encounter a <xref:System.Security.SecurityException> exception if you are running the code in a partial-trust context because of insufficient privileges.</span></span> <span data-ttu-id="f1f6f-113">Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../../docs/framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="f1f6f-113">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
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
  
     <span data-ttu-id="f1f6f-114">([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Müssen Sie den Prozess initialisieren `p`, wozu Sie verwenden können, indem Sie die folgende Anweisung in den Konstruktor des Formulars einschließen:</span><span class="sxs-lookup"><span data-stu-id="f1f6f-114">([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) You must initialize process `p`, which you can do by including the following statement in the constructor of your form:</span></span>  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     <span data-ttu-id="f1f6f-115">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Fügen Sie den folgenden Code in den Konstruktor der Form ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="f1f6f-115">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="f1f6f-116">Es ist wichtig, den Prozess sofort zu beenden, den Sie erstellt haben, nachdem Sie die Arbeit daran fertig haben.</span><span class="sxs-lookup"><span data-stu-id="f1f6f-116">It is important to immediately stop the process you have created once you have finished working with it.</span></span> <span data-ttu-id="f1f6f-117">In Bezug auf den oben aufgeführten Code kann der Code, den Prozess beenden wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="f1f6f-117">Referring to the code presented above, your code to stop the process might look like this:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f1f6f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1f6f-118">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>  
 <xref:System.Windows.Forms.RichTextBox.LinkClicked>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="f1f6f-119">RichTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f1f6f-119">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="f1f6f-120">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="f1f6f-120">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
