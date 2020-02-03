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
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="2f7bc-102">Gewusst wie: Anzeigen von Hyperlinks mit dem RichTextBox-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2f7bc-102">How to: Display Web-Style Links with the Windows Forms RichTextBox Control</span></span>

<span data-ttu-id="2f7bc-103">Das Windows Forms <xref:System.Windows.Forms.RichTextBox>-Steuerelement kann Weblinks farblich anzeigen und unterstrichen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2f7bc-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display Web links as colored and underlined.</span></span> <span data-ttu-id="2f7bc-104">Sie können Code schreiben, mit dem ein Browserfenster geöffnet wird, in dem die im Linktext angegebene Website angezeigt wird, wenn auf den Link geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="2f7bc-104">You can write code that opens a browser window showing the Web site specified in the link text when the link is clicked.</span></span>

### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a><span data-ttu-id="2f7bc-105">So verknüpfen Sie eine Webseite mit dem RichTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2f7bc-105">To link to a Web page with the RichTextBox control</span></span>

1. <span data-ttu-id="2f7bc-106">Legen Sie die <xref:System.Windows.Forms.RichTextBox.Text%2A>-Eigenschaft auf eine Zeichenfolge fest, die eine gültige URL enthält (z. b. "http://www.microsoft.com/").</span><span class="sxs-lookup"><span data-stu-id="2f7bc-106">Set the <xref:System.Windows.Forms.RichTextBox.Text%2A> property to a string that includes a valid URL (for example, "http://www.microsoft.com/").</span></span>

2. <span data-ttu-id="2f7bc-107">Stellen Sie sicher, dass die <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>-Eigenschaft auf `true` (Standardeinstellung) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2f7bc-107">Make sure the <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> property is set to `true` (the default).</span></span>

3. <span data-ttu-id="2f7bc-108">Erstellen Sie eine neue globale Instanz des <xref:System.Diagnostics.Process> Objekts.</span><span class="sxs-lookup"><span data-stu-id="2f7bc-108">Create a new global instance of the <xref:System.Diagnostics.Process> object.</span></span>

4. <span data-ttu-id="2f7bc-109">Schreiben Sie einen Ereignishandler für das <xref:System.Windows.Forms.RichTextBox.LinkClicked> Ereignis, das den Browser den gewünschten Text sendet.</span><span class="sxs-lookup"><span data-stu-id="2f7bc-109">Write an event handler for the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event that sends the browser the desired text.</span></span>

    <span data-ttu-id="2f7bc-110">Im folgenden Beispiel wird mit dem <xref:System.Windows.Forms.RichTextBox.LinkClicked>-Ereignis eine Instanz von Internet Explorer für die URL geöffnet, die in der <xref:System.Windows.Forms.RichTextBox.Text%2A>-Eigenschaft des <xref:System.Windows.Forms.RichTextBox>-Steuer Elements angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="2f7bc-110">In the example below, the <xref:System.Windows.Forms.RichTextBox.LinkClicked> event opens an instance of Internet Explorer to the URL specified in the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="2f7bc-111">In diesem Beispiel wird ein Formular mit einem <xref:System.Windows.Forms.RichTextBox>-Steuerelement angenommen.</span><span class="sxs-lookup"><span data-stu-id="2f7bc-111">This example assumes a form with a <xref:System.Windows.Forms.RichTextBox> control.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2f7bc-112">Wenn Sie die <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>-Methode aufrufen, tritt eine <xref:System.Security.SecurityException> Ausnahme auf, wenn Sie den Code in einem teilweise vertrauenswürdigen Kontext ausführen, weil Sie nicht über ausreichende Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="2f7bc-112">In calling the <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> method, you will encounter a <xref:System.Security.SecurityException> exception if you are running the code in a partial-trust context because of insufficient privileges.</span></span> <span data-ttu-id="2f7bc-113">Weitere Informationen finden Sie unter [Code Access Security Basics](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="2f7bc-113">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

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

    <span data-ttu-id="2f7bc-114">(Visual C++) Sie müssen Prozess `p`initialisieren, indem Sie die folgende Anweisung in den Konstruktor Ihres Formulars einschließen:</span><span class="sxs-lookup"><span data-stu-id="2f7bc-114">(Visual C++) You must initialize process `p`, which you can do by including the following statement in the constructor of your form:</span></span>

    ```cpp
    p = gcnew System::Diagnostics::Process();
    ```

    <span data-ttu-id="2f7bc-115">(Visualisierung C#, Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="2f7bc-115">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>

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

    <span data-ttu-id="2f7bc-116">Es ist wichtig, dass Sie den von Ihnen erstellten Prozess sofort beenden, nachdem Sie die Arbeit mit dem Prozess abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="2f7bc-116">It is important to immediately stop the process you have created once you have finished working with it.</span></span> <span data-ttu-id="2f7bc-117">Der Code, der sich auf den oben dargestellten Code bezieht, könnte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="2f7bc-117">Referring to the code presented above, your code to stop the process might look like this:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2f7bc-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f7bc-118">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="2f7bc-119">RichTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2f7bc-119">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="2f7bc-120">Steuerelemente für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2f7bc-120">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
