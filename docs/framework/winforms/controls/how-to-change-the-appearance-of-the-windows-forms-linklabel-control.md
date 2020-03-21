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
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a>Gewusst wie: Ändern der Darstellung des LinkLabel-Steuerelements in Windows Forms
Sie können den vom <xref:System.Windows.Forms.LinkLabel> Steuerelement angezeigten Text an eine Vielzahl von Zwecken anpassen. Es ist z. B. üblich, dem Benutzer anzuzeigen, dass auf Text geklickt werden kann, indem der Text so so gesetzt wird, dass er in einer bestimmten Farbe mit einer Unterstreichung angezeigt wird. Nachdem der Benutzer auf den Text geklickt hat, ändert sich die Farbe in eine andere Farbe. Um dieses Verhalten zu steuern, können <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>Sie <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>fünf <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>verschiedene <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> Eigenschaften festlegen: die , , , und die Eigenschaften.  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a>So ändern Sie die Darstellung eines LinkLabel-Steuerelements  
  
1. Legen <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> Sie <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> die und eigenschaften auf die gewünschten Farben fest.  
  
     Dies kann entweder programmgesteuert oder zur Entwurfszeit im **Eigenschaftenfenster** erfolgen.  
  
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
  
2. Legen <xref:System.Windows.Forms.LinkLabel.Text%2A> Sie die Eigenschaft auf eine entsprechende Beschriftung fest.  
  
     Dies kann entweder programmgesteuert oder zur Entwurfszeit im **Eigenschaftenfenster** erfolgen.  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. Legen <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Sie die Eigenschaft fest, um zu bestimmen, welcher Teil der Beschriftung als Link angezeigt wird.  
  
     Der <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Wert wird <xref:System.Windows.Forms.LinkArea> mit einer mit zwei Zahlen, der Anfangszeichenposition und der Anzahl der Zeichen dargestellt. Dies kann entweder programmgesteuert oder zur Entwurfszeit im **Eigenschaftenfenster** erfolgen.  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. Legen <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> Sie <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>die <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>Eigenschaft <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>auf , oder fest.  
  
     Wenn er auf <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>festgelegt ist, wird <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> der von festgelegte Teil der Beschriftung nur unterstrichen, wenn der Zeiger darauf ruht.  
  
5. Legen <xref:System.Windows.Forms.LinkLabel.LinkClicked> Sie im Ereignishandler <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> `true`die Eigenschaft auf .  
  
     Wenn ein Link besucht wurde, ist es üblich, sein Aussehen in irgendeiner Weise zu ändern, in der Regel nach Farbe. Der Text ändert sich in <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> die von der Eigenschaft angegebene Farbe.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [Übersicht über das LinkLabel-Steuerelement](linklabel-control-overview-windows-forms.md)
- [Gewusst wie: Verknüpfen eines Objekts oder einer Webseite mit dem LinkLabel-Steuerelement in Windows Forms](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [LinkLabel-Steuerelement](linklabel-control-windows-forms.md)
