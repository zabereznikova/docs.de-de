---
title: Ändern der Darstellung von LinkLabel Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
ms.openlocfilehash: df66991289373a05fc7c27b7768a96643e3bbae0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142129"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="000be-102">Gewusst wie: Ändern der Darstellung des LinkLabel-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="000be-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="000be-103">Sie können den vom <xref:System.Windows.Forms.LinkLabel> Steuerelement angezeigten Text an eine Vielzahl von Zwecken anpassen.</span><span class="sxs-lookup"><span data-stu-id="000be-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="000be-104">Es ist z. B. üblich, dem Benutzer anzuzeigen, dass auf Text geklickt werden kann, indem der Text so so gesetzt wird, dass er in einer bestimmten Farbe mit einer Unterstreichung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="000be-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="000be-105">Nachdem der Benutzer auf den Text geklickt hat, ändert sich die Farbe in eine andere Farbe.</span><span class="sxs-lookup"><span data-stu-id="000be-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="000be-106">Um dieses Verhalten zu steuern, können <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>Sie <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>fünf <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>verschiedene <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> Eigenschaften festlegen: die , , , und die Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="000be-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="000be-107">So ändern Sie die Darstellung eines LinkLabel-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="000be-107">To change the appearance of a LinkLabel control</span></span>  
  
1. <span data-ttu-id="000be-108">Legen <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> Sie <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> die und eigenschaften auf die gewünschten Farben fest.</span><span class="sxs-lookup"><span data-stu-id="000be-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="000be-109">Dies kann entweder programmgesteuert oder zur Entwurfszeit im **Eigenschaftenfenster** erfolgen.</span><span class="sxs-lookup"><span data-stu-id="000be-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    ' You can set the color using decimal values for red, green, and blue  
    LinkLabel1.LinkColor = Color.FromArgb(0, 0, 255)  
    ' Or you can set the color using defined constants  
    LinkLabel1.VisitedLinkColor = Color.Purple  
    ```  
  
    ```csharp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1.LinkColor = Color.FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1.VisitedLinkColor = Color.Purple;  
    ```  
  
    ```cpp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1->LinkColor = Color::FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1->VisitedLinkColor = Color::Purple;  
    ```  
  
2. <span data-ttu-id="000be-110">Legen <xref:System.Windows.Forms.LinkLabel.Text%2A> Sie die Eigenschaft auf eine entsprechende Beschriftung fest.</span><span class="sxs-lookup"><span data-stu-id="000be-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="000be-111">Dies kann entweder programmgesteuert oder zur Entwurfszeit im **Eigenschaftenfenster** erfolgen.</span><span class="sxs-lookup"><span data-stu-id="000be-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. <span data-ttu-id="000be-112">Legen <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Sie die Eigenschaft fest, um zu bestimmen, welcher Teil der Beschriftung als Link angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="000be-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="000be-113">Der <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Wert wird <xref:System.Windows.Forms.LinkArea> mit einer mit zwei Zahlen, der Anfangszeichenposition und der Anzahl der Zeichen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="000be-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="000be-114">Dies kann entweder programmgesteuert oder zur Entwurfszeit im **Eigenschaftenfenster** erfolgen.</span><span class="sxs-lookup"><span data-stu-id="000be-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. <span data-ttu-id="000be-115">Legen <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> Sie <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>die <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>Eigenschaft <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>auf , oder fest.</span><span class="sxs-lookup"><span data-stu-id="000be-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="000be-116">Wenn er auf <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>festgelegt ist, wird <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> der von festgelegte Teil der Beschriftung nur unterstrichen, wenn der Zeiger darauf ruht.</span><span class="sxs-lookup"><span data-stu-id="000be-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5. <span data-ttu-id="000be-117">Legen <xref:System.Windows.Forms.LinkLabel.LinkClicked> Sie im Ereignishandler <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> `true`die Eigenschaft auf .</span><span class="sxs-lookup"><span data-stu-id="000be-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="000be-118">Wenn ein Link besucht wurde, ist es üblich, sein Aussehen in irgendeiner Weise zu ändern, in der Regel nach Farbe.</span><span class="sxs-lookup"><span data-stu-id="000be-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="000be-119">Der Text ändert sich in <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> die von der Eigenschaft angegebene Farbe.</span><span class="sxs-lookup"><span data-stu-id="000be-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked (ByVal sender As Object, _  
       ByVal e As EventArgs) Handles LinkLabel1.LinkClicked  
       ' Change the color of the link text  
       ' by setting LinkVisited to True.  
       LinkLabel1.LinkVisited = True  
       ' Then do whatever other action is appropriate  
    End Sub  
    ```  
  
    ```csharp  
    protected void LinkLabel1_LinkClicked(object sender, System.EventArgs e)  
    {  
       // Change the color of the link text by setting LinkVisited
       // to True.  
       linkLabel1.LinkVisited = true;  
       // Then do whatever other action is appropriate  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Change the color of the link text by setting LinkVisited
          // to True.  
          linkLabel1->LinkVisited = true;  
          // Then do whatever other action is appropriate  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="000be-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="000be-120">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [<span data-ttu-id="000be-121">Übersicht über das LinkLabel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="000be-121">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="000be-122">Gewusst wie: Verknüpfen eines Objekts oder einer Webseite mit dem LinkLabel-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="000be-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="000be-123">LinkLabel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="000be-123">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
