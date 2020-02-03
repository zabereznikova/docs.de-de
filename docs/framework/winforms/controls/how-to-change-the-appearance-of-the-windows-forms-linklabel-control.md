---
title: Ändern der Darstellung des LinkLabel-Steuer Elements
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
ms.openlocfilehash: 0b38722fb1647ea215c3bb8978dd3f54b300a0e0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746631"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a>Gewusst wie: Ändern der Darstellung des LinkLabel-Steuerelements in Windows Forms
Sie können den Text ändern, der vom <xref:System.Windows.Forms.LinkLabel>-Steuerelement angezeigt wird, um eine Vielzahl von Zwecken zu erfüllen. Es ist z. b. üblich, dem Benutzer anzuzeigen, dass auf Text geklickt werden kann, indem der Text auf eine bestimmte Farbe mit einer Unterstreichung festgelegt wird. Nachdem der Benutzer auf den Text geklickt hat, ändert sich die Farbe in eine andere Farbe. Um dieses Verhalten zu steuern, können Sie fünf verschiedene Eigenschaften festlegen: die Eigenschaften <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>und <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>.  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a>So ändern Sie die Darstellung eines LinkLabel-Steuer Elements  
  
1. Legen Sie die Eigenschaften "<xref:System.Windows.Forms.LinkLabel.LinkColor%2A>" und "<xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>" auf die gewünschten Farben fest.  
  
     Dies kann entweder Programm gesteuert oder zur Entwurfszeit im **Eigenschaften** Fenster erfolgen.  
  
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
  
2. Legen Sie die <xref:System.Windows.Forms.LinkLabel.Text%2A>-Eigenschaft auf eine entsprechende Beschriftung fest.  
  
     Dies kann entweder Programm gesteuert oder zur Entwurfszeit im **Eigenschaften** Fenster erfolgen.  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. Legen Sie die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>-Eigenschaft fest, um zu bestimmen, welcher Teil der Beschriftung als Link angegeben wird.  
  
     Der <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>-Wert wird mit einem <xref:System.Windows.Forms.LinkArea> dargestellt, der zwei Zahlen enthält: die Position des Anfangs Zeichens und die Anzahl der Zeichen. Dies kann entweder Programm gesteuert oder zur Entwurfszeit im **Eigenschaften** Fenster erfolgen.  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. Legen Sie die <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>-Eigenschaft auf <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>oder <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>fest.  
  
     Wenn Sie auf <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>festgelegt ist, wird der Teil der Beschriftung, der durch <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> bestimmt wird, nur unterstrichen, wenn der Zeiger darauf liegt.  
  
5. Legen Sie im Ereignishandler <xref:System.Windows.Forms.LinkLabel.LinkClicked> die Eigenschaft <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> auf `true`fest.  
  
     Wenn ein Link geöffnet wurde, ist es üblich, seine Darstellung in gewisser Weise zu ändern, üblicherweise nach Farbe. Der Text wird in die durch die <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>-Eigenschaft angegebene Farbe geändert.  
  
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
- [Gewusst wie: Verknüpfen eines Objekts oder einer Webseite mit dem LinkLabel-Steuerelement in Windows Forms](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [LinkLabel-Steuerelement](linklabel-control-windows-forms.md)
