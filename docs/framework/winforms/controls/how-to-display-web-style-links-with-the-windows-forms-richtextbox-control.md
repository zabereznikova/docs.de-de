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
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="4e7ef-102">Vorgehensweise: Anzeigen von Hyperlinks mit dem RichTextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4e7ef-102">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="4e7ef-103">Die Windows-Formulare <xref:System.Windows.Forms.RichTextBox> -Steuerelement können Weblinks farbig und unterstrichen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4e7ef-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display Web links as colored and underlined.</span></span> <span data-ttu-id="4e7ef-104">Sie können Code schreiben, die öffnet ein Browserfenster mit der Website, die in der Text des Links angegeben werden, wenn auf der Link geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="4e7ef-104">You can write code that opens a browser window showing the Web site specified in the link text when the link is clicked.</span></span>  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a><span data-ttu-id="4e7ef-105">So verknüpfen Sie mit der eine Webseite mit dem RichTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4e7ef-105">To link to a Web page with the RichTextBox control</span></span>  
  
1.  <span data-ttu-id="4e7ef-106">Legen Sie die <xref:System.Windows.Forms.RichTextBox.Text%2A> Eigenschaft, um eine Zeichenfolge, enthält eine gültige URL ein (z. B. "http://www.microsoft.com/").</span><span class="sxs-lookup"><span data-stu-id="4e7ef-106">Set the <xref:System.Windows.Forms.RichTextBox.Text%2A> property to a string that includes a valid URL (for example, "http://www.microsoft.com/").</span></span>  
  
2.  <span data-ttu-id="4e7ef-107">Stellen Sie sicher, dass die <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> -Eigenschaftensatz auf `true` (Standard).</span><span class="sxs-lookup"><span data-stu-id="4e7ef-107">Make sure the <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> property is set to `true` (the default).</span></span>  
  
3.  <span data-ttu-id="4e7ef-108">Erstellen Sie eine neue globale Instanz des der <xref:System.Diagnostics.Process> Objekt.</span><span class="sxs-lookup"><span data-stu-id="4e7ef-108">Create a new global instance of the <xref:System.Diagnostics.Process> object.</span></span>  
  
4.  <span data-ttu-id="4e7ef-109">Schreiben Sie einen Ereignishandler für die <xref:System.Windows.Forms.RichTextBox.LinkClicked> -Ereignis, das an den gewünschten Text durch den Browser sendet.</span><span class="sxs-lookup"><span data-stu-id="4e7ef-109">Write an event handler for the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event that sends the browser the desired text.</span></span>  
  
     <span data-ttu-id="4e7ef-110">Im folgenden Beispiel wird die <xref:System.Windows.Forms.RichTextBox.LinkClicked> Ereignis öffnet eine Instanz von Internet Explorer, um die URL in die <xref:System.Windows.Forms.RichTextBox.Text%2A> Eigenschaft der <xref:System.Windows.Forms.RichTextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4e7ef-110">In the example below, the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event opens an instance of Internet Explorer to the URL specified in the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="4e7ef-111">In diesem Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.RichTextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="4e7ef-111">This example assumes a form with a <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4e7ef-112">Im Aufruf der <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> -Methode, tritt ein <xref:System.Security.SecurityException> -Ausnahme aus, wenn Sie den Code in einem teilweise vertrauenswürdigen Kontext aufgrund fehlender Berechtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="4e7ef-112">In calling the <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> method, you will encounter a <xref:System.Security.SecurityException> exception if you are running the code in a partial-trust context because of insufficient privileges.</span></span> <span data-ttu-id="4e7ef-113">Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="4e7ef-113">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>  
  
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
  
     <span data-ttu-id="4e7ef-114">([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Sie müssen den Prozess initialisieren `p`, dies können Sie dazu die folgende Anweisung im Konstruktor des Formulars:</span><span class="sxs-lookup"><span data-stu-id="4e7ef-114">([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) You must initialize process `p`, which you can do by including the following statement in the constructor of your form:</span></span>  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     <span data-ttu-id="4e7ef-115">(Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="4e7ef-115">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="4e7ef-116">Es ist wichtig, um den Prozess sofort zu beenden, die, den Sie erstellt haben, sobald Sie damit fertig sind.</span><span class="sxs-lookup"><span data-stu-id="4e7ef-116">It is important to immediately stop the process you have created once you have finished working with it.</span></span> <span data-ttu-id="4e7ef-117">In Bezug auf den oben dargestellten Code, kann Code, um den Vorgang zu beenden, wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="4e7ef-117">Referring to the code presented above, your code to stop the process might look like this:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4e7ef-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e7ef-118">See also</span></span>
- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="4e7ef-119">RichTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4e7ef-119">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="4e7ef-120">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="4e7ef-120">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
