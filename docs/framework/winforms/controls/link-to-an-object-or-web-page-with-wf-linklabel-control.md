---
title: Verknüpfung mit einem Objekt oder einer Webseite mit dem LinkLabel-Steuerelement
description: Erfahren Sie, wie Sie mit dem Windows Forms LinkLabel-Steuerelement Webstil Verknüpfungen zu einem Objekt oder einer Webseite erstellen.
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
ms.openlocfilehash: a5fb1c03e9a8d82fe77f4133ba04c42114787d23
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618311"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a><span data-ttu-id="56fce-103">Vorgehensweise: Verknüpfen eines Objekts oder einer Webseite mit dem LinkLabel-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="56fce-103">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>

<span data-ttu-id="56fce-104">Das Windows Forms <xref:System.Windows.Forms.LinkLabel> Steuerelement ermöglicht das Erstellen von Links im Webformat auf Ihrem Formular.</span><span class="sxs-lookup"><span data-stu-id="56fce-104">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to create Web-style links on your form.</span></span> <span data-ttu-id="56fce-105">Wenn auf den Link geklickt wird, können Sie die zugehörige Farbe ändern, um anzugeben, dass der Link besucht wurde.</span><span class="sxs-lookup"><span data-stu-id="56fce-105">When the link is clicked, you can change its color to indicate the link has been visited.</span></span> <span data-ttu-id="56fce-106">Weitere Informationen zum Ändern der Farbe finden Sie unter Gewusst [wie: Ändern der Darstellung des Windows Forms LinkLabel-Steuer](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)Elements.</span><span class="sxs-lookup"><span data-stu-id="56fce-106">For more information on changing the color, see [How to: Change the Appearance of the Windows Forms LinkLabel Control](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span></span>

## <a name="linking-to-another-form"></a><span data-ttu-id="56fce-107">Verknüpfen mit einem anderen Formular</span><span class="sxs-lookup"><span data-stu-id="56fce-107">Linking to Another Form</span></span>

#### <a name="to-link-to-another-form-with-a-linklabel-control"></a><span data-ttu-id="56fce-108">So verknüpfen Sie ein anderes Formular mit einem LinkLabel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="56fce-108">To link to another form with a LinkLabel control</span></span>

1. <span data-ttu-id="56fce-109">Legen Sie die- <xref:System.Windows.Forms.LinkLabel.Text%2A> Eigenschaft auf eine entsprechende Beschriftung fest.</span><span class="sxs-lookup"><span data-stu-id="56fce-109">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>

2. <span data-ttu-id="56fce-110">Legen Sie die- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Eigenschaft fest, um zu bestimmen, welcher Teil der Beschriftung als Link angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="56fce-110">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span> <span data-ttu-id="56fce-111">Wie dies angegeben wird, hängt von den Darstellungs bezogenen Eigenschaften der Link Bezeichnung ab.</span><span class="sxs-lookup"><span data-stu-id="56fce-111">How it is indicated depends on the appearance-related properties of the link label.</span></span> <span data-ttu-id="56fce-112">Der- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Wert wird durch ein <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> -Objekt dargestellt, das zwei Zahlen enthält: die Position des Anfangs Zeichens und die Anzahl der Zeichen.</span><span class="sxs-lookup"><span data-stu-id="56fce-112">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented by a <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> object containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="56fce-113">Die- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Eigenschaft kann im-Eigenschaftenfenster oder im Code auf eine Weise festgelegt werden, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="56fce-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property can be set in the Properties window or in code in a manner similar to the following:</span></span>

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

3. <span data-ttu-id="56fce-114"><xref:System.Windows.Forms.LinkLabel.LinkClicked>Rufen Sie im-Ereignishandler die <xref:System.Windows.Forms.Form.Show%2A> -Methode auf, um ein anderes Formular im Projekt zu öffnen, und legen Sie die- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> Eigenschaft auf fest `true` .</span><span class="sxs-lookup"><span data-stu-id="56fce-114">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, invoke the <xref:System.Windows.Forms.Form.Show%2A> method to open another form in the project, and set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="56fce-115">Eine Instanz der- <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> Klasse enthält einen Verweis auf das <xref:System.Windows.Forms.LinkLabel> Steuerelement, auf das geklickt wurde, sodass das-Objekt nicht umgewandelt werden muss `sender` .</span><span class="sxs-lookup"><span data-stu-id="56fce-115">An instance of the <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> class carries a reference to the <xref:System.Windows.Forms.LinkLabel> control that was clicked, so there is no need to cast the `sender` object.</span></span>

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

## <a name="linking-to-a-web-page"></a><span data-ttu-id="56fce-116">Verknüpfen mit einer Webseite</span><span class="sxs-lookup"><span data-stu-id="56fce-116">Linking to a Web Page</span></span>

<span data-ttu-id="56fce-117">Das- <xref:System.Windows.Forms.LinkLabel> Steuerelement kann auch verwendet werden, um eine Webseite mit dem Standardbrowser anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="56fce-117">The <xref:System.Windows.Forms.LinkLabel> control can also be used to display a Web page with the default browser.</span></span>

#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a><span data-ttu-id="56fce-118">So starten Sie Internet Explorer und verknüpfen eine Webseite mit einem LinkLabel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="56fce-118">To start Internet Explorer and link to a Web page with a LinkLabel control</span></span>

1. <span data-ttu-id="56fce-119">Legen Sie die- <xref:System.Windows.Forms.LinkLabel.Text%2A> Eigenschaft auf eine entsprechende Beschriftung fest.</span><span class="sxs-lookup"><span data-stu-id="56fce-119">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>

2. <span data-ttu-id="56fce-120">Legen Sie die- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Eigenschaft fest, um zu bestimmen, welcher Teil der Beschriftung als Link angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="56fce-120">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>

3. <span data-ttu-id="56fce-121">Im- <xref:System.Windows.Forms.LinkLabel.LinkClicked> Ereignishandler wird in der Mitte eines Ausnahme Behandlungs Blocks eine zweite Prozedur aufgerufen, mit der die <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> -Eigenschaft auf festgelegt wird `true` und die-Methode verwendet wird, <xref:System.Diagnostics.Process.Start%2A> um den Standardbrowser mit einer URL zu starten.</span><span class="sxs-lookup"><span data-stu-id="56fce-121">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, in the midst of an exception-handling block, call a second procedure that sets the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true` and uses the <xref:System.Diagnostics.Process.Start%2A> method to start the default browser with a URL.</span></span> <span data-ttu-id="56fce-122">Um die- <xref:System.Diagnostics.Process.Start%2A> Methode verwenden zu können, müssen Sie einen Verweis auf den- <xref:System.Diagnostics?displayProperty=nameWithType> Namespace hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="56fce-122">To use the <xref:System.Diagnostics.Process.Start%2A> method you need to add a reference to the <xref:System.Diagnostics?displayProperty=nameWithType> namespace.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="56fce-123">Wenn der folgende Code in einer teilweise vertrauenswürdigen Umgebung (z. b. auf einem freigegebenen Laufwerk) ausgeführt wird, schlägt der JIT-Compiler fehl, wenn die- `VisitLink` Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="56fce-123">If the code below is run in a partial-trust environment (such as on a shared drive), the JIT compiler fails when the `VisitLink` method is called.</span></span> <span data-ttu-id="56fce-124">Die- `System.Diagnostics.Process.Start` Anweisung verursacht einen Verbindungs Aufruf, der fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="56fce-124">The `System.Diagnostics.Process.Start` statement causes a link demand that fails.</span></span> <span data-ttu-id="56fce-125">Wenn Sie die Ausnahme abfangen, wenn die- `VisitLink` Methode aufgerufen wird, stellt der folgende Code sicher, dass der Fehler ordnungsgemäß behandelt wird, wenn der JIT-Compiler fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="56fce-125">By catching the exception when the `VisitLink` method is called, the code below ensures that if the JIT compiler fails, the error is handled gracefully.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="56fce-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56fce-126">See also</span></span>

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- [<span data-ttu-id="56fce-127">Übersicht über das LinkLabel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="56fce-127">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="56fce-128">Vorgehensweise: Ändern der Darstellung des LinkLabel-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="56fce-128">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [<span data-ttu-id="56fce-129">LinkLabel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="56fce-129">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
