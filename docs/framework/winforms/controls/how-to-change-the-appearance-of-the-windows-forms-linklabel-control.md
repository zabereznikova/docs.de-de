---
title: 'Gewusst wie: Ändern der Darstellung des LinkLabel-Steuerelements in Windows Forms'
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
ms.openlocfilehash: e1bb0ecba6fd8ddf66c6debb90ef4dd94641a97e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531485"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a><span data-ttu-id="cbc2f-102">Gewusst wie: Ändern der Darstellung des LinkLabel-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cbc2f-102">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>
<span data-ttu-id="cbc2f-103">Sie können ändern, der vom angezeigte Text der <xref:System.Windows.Forms.LinkLabel> Steuerelement entsprechend eine Vielzahl von Zwecken.</span><span class="sxs-lookup"><span data-stu-id="cbc2f-103">You can change the text displayed by the <xref:System.Windows.Forms.LinkLabel> control to suit a variety of purposes.</span></span> <span data-ttu-id="cbc2f-104">Beispielsweise ist es gängige Praxis, um zu verdeutlichen, dass Text geklickt werden kann, durch Festlegen des Texts in einer bestimmten Farbe mit einer Unterstreichung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cbc2f-104">For example, it is common practice to indicate to the user that text can be clicked by setting the text to appear in a specific color with an underline.</span></span> <span data-ttu-id="cbc2f-105">Nachdem der Benutzer den Text klickt, ändert sich die Farbe in eine andere Farbe.</span><span class="sxs-lookup"><span data-stu-id="cbc2f-105">After the user clicks the text, the color changes to a different color.</span></span> <span data-ttu-id="cbc2f-106">Um dieses Verhalten zu steuern, können Sie fünf verschiedene Eigenschaften festlegen: die <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, und <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="cbc2f-106">To control this behavior, you can set five different properties: the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> properties.</span></span>  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a><span data-ttu-id="cbc2f-107">So ändern Sie die Darstellung des LinkLabel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="cbc2f-107">To change the appearance of a LinkLabel control</span></span>  
  
1.  <span data-ttu-id="cbc2f-108">Legen Sie die <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> und <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> Eigenschaften, um die gewünschten Farben.</span><span class="sxs-lookup"><span data-stu-id="cbc2f-108">Set the <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> and <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> properties to the colors you want.</span></span>  
  
     <span data-ttu-id="cbc2f-109">Dies kann erfolgen entweder programmgesteuert oder zur Entwurfszeit in den **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="cbc2f-109">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
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
  
2.  <span data-ttu-id="cbc2f-110">Legen Sie die <xref:System.Windows.Forms.LinkLabel.Text%2A> Eigenschaft, um eine geeignete Beschriftung.</span><span class="sxs-lookup"><span data-stu-id="cbc2f-110">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>  
  
     <span data-ttu-id="cbc2f-111">Dies kann erfolgen entweder programmgesteuert oder zur Entwurfszeit in den **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="cbc2f-111">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3.  <span data-ttu-id="cbc2f-112">Legen Sie die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> -Eigenschaft können Sie bestimmen, welcher Teil der Beschriftung als Link gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="cbc2f-112">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>  
  
     <span data-ttu-id="cbc2f-113">Die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Wert wird dargestellt, mit einem <xref:System.Windows.Forms.LinkArea> mit zwei Zahlen, die Anfangsposition und die Anzahl der Zeichen.</span><span class="sxs-lookup"><span data-stu-id="cbc2f-113">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented with a <xref:System.Windows.Forms.LinkArea> containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="cbc2f-114">Dies kann erfolgen entweder programmgesteuert oder zur Entwurfszeit in den **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="cbc2f-114">This can be done either programmatically or at design time in the **Properties** window.</span></span>  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4.  <span data-ttu-id="cbc2f-115">Legen Sie die <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> Eigenschaft <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, oder <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span><span class="sxs-lookup"><span data-stu-id="cbc2f-115">Set the <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> property to <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, or <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.</span></span>  
  
     <span data-ttu-id="cbc2f-116">Wenn sie, um festgelegt ist <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, der Teil der Beschriftung, die bestimmt, indem <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> wird nur unterstrichen werden, wenn der Mauszeiger darauf positioniert.</span><span class="sxs-lookup"><span data-stu-id="cbc2f-116">If it is set to <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, the part of the caption determined by <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> will only be underlined when the pointer rests on it.</span></span>  
  
5.  <span data-ttu-id="cbc2f-117">In der <xref:System.Windows.Forms.LinkLabel.LinkClicked> legen Sie Ereignishandler, d. h. die <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="cbc2f-117">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="cbc2f-118">Wenn ein Link aktiviert wurde, ist es üblich, dessen Darstellung in irgendeiner Form in der Regel nach ihrer Farbe geändert.</span><span class="sxs-lookup"><span data-stu-id="cbc2f-118">When a link has been visited, it is common practice to change its appearance in some way, usually by color.</span></span> <span data-ttu-id="cbc2f-119">Der Text ändert sich die Farbe gemäß der <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="cbc2f-119">The text will change to the color specified by the <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cbc2f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbc2f-120">See Also</span></span>  
 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>  
 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>  
 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>  
 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>  
 [<span data-ttu-id="cbc2f-121">Übersicht über das LinkLabel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="cbc2f-121">LinkLabel Control Overview</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)  
 [<span data-ttu-id="cbc2f-122">Gewusst wie: Verknüpfen eines Objekts oder einer Webseite mit dem LinkLabel-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cbc2f-122">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)  
 [<span data-ttu-id="cbc2f-123">LinkLabel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="cbc2f-123">LinkLabel Control</span></span>](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
