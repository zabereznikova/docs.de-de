---
title: 'Vorgehensweise: Ändern der Darstellung des LinkLabel-Steuerelement von Windows Forms'
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
ms.openlocfilehash: 2e36bdc051ec83985bd508499640c9f97bdefc91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632126"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="20a87-102">Vorgehensweise: Ändern der Darstellung des LinkLabel-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="20a87-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="20a87-103">Sie können den Text durch Ändern der <xref:System.Windows.Forms.LinkLabel> Steuerelement an eine Vielzahl von Zwecken anpassen.</span><span class="sxs-lookup"><span data-stu-id="20a87-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="20a87-104">Beispielsweise ist es üblich, zu verdeutlichen, dass Text geklickt werden kann, durch Festlegen des Texts in einer bestimmten Farbe mit einer Unterstreichung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20a87-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="20a87-105">Nachdem der Benutzer den Text klickt, ändert sich die Farbe in eine andere Farbe.</span><span class="sxs-lookup"><span data-stu-id="20a87-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="20a87-106">Um dieses Verhalten zu steuern, können Sie fünf verschiedene Eigenschaften festlegen: die <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, und <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="20a87-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="20a87-107">So ändern Sie die Darstellung des LinkLabel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="20a87-107">To change the appearance of a LinkLabel control</span></span>  
  
1.  <span data-ttu-id="20a87-108">Legen Sie die <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> und <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> Eigenschaften, die Sie die gewünschten Farben.</span><span class="sxs-lookup"><span data-stu-id="20a87-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="20a87-109">Hierzu können entweder programmgesteuert oder zur Entwurfszeit in den **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="20a87-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
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
  
2.  <span data-ttu-id="20a87-110">Legen Sie die <xref:System.Windows.Forms.LinkLabel.Text%2A> Eigenschaft eine geeignete Beschriftung.</span><span class="sxs-lookup"><span data-stu-id="20a87-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="20a87-111">Hierzu können entweder programmgesteuert oder zur Entwurfszeit in den **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="20a87-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3.  <span data-ttu-id="20a87-112">Legen Sie die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Eigenschaft, um zu bestimmen, welcher Teil der Beschriftung als Link gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="20a87-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="20a87-113">Die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Wert wird dargestellt, mit einem <xref:System.Windows.Forms.LinkArea> mit zwei Zahlen, die Position des ersten Zeichens und die Anzahl der Zeichen.</span><span class="sxs-lookup"><span data-stu-id="20a87-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="20a87-114">Hierzu können entweder programmgesteuert oder zur Entwurfszeit in den **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="20a87-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4.  <span data-ttu-id="20a87-115">Legen Sie die <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> Eigenschaft <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, oder <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span><span class="sxs-lookup"><span data-stu-id="20a87-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="20a87-116">Wenn sie, um festgelegt ist <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, die Teil der Beschriftung, die bestimmt, indem <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> ist nur unterstrichen werden, wenn der Mauszeiger darauf positioniert.</span><span class="sxs-lookup"><span data-stu-id="20a87-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5.  <span data-ttu-id="20a87-117">In der <xref:System.Windows.Forms.LinkLabel.LinkClicked> ereignishandlers, der <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="20a87-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="20a87-118">Wenn Sie ein Link bereits besucht wurde, ist es üblich, dessen Darstellung auf irgendeine Weise, in der Regel nach ihrer Farbe zu ändern.</span><span class="sxs-lookup"><span data-stu-id="20a87-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="20a87-119">Der Text ändert sich in die Farbe, die gemäß der <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="20a87-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="20a87-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20a87-120">See also</span></span>
- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [<span data-ttu-id="20a87-121">Übersicht über das LinkLabel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="20a87-121">LinkLabel Control Overview</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="20a87-122">Vorgehensweise: Link zu einem Objekt oder Webseite mit dem LinkLabel-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="20a87-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="20a87-123">LinkLabel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="20a87-123">LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
