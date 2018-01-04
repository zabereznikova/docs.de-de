---
title: "Gewusst wie: Ändern der Darstellung des LinkLabel-Steuerelements in Windows Forms"
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
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7dc3963ab1b242ce8dce53d9bba996f52347679b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a>Gewusst wie: Ändern der Darstellung des LinkLabel-Steuerelements in Windows Forms
Sie können ändern, der vom angezeigte Text der <xref:System.Windows.Forms.LinkLabel> Steuerelement entsprechend eine Vielzahl von Zwecken. Beispielsweise ist es gängige Praxis, um zu verdeutlichen, dass Text geklickt werden kann, durch Festlegen des Texts in einer bestimmten Farbe mit einer Unterstreichung angezeigt werden. Nachdem der Benutzer den Text klickt, ändert sich die Farbe in eine andere Farbe. Um dieses Verhalten zu steuern, können Sie fünf verschiedene Eigenschaften festlegen: die <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, und <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> Eigenschaften.  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a>So ändern Sie die Darstellung des LinkLabel-Steuerelement  
  
1.  Legen Sie die <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> und <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> Eigenschaften, um die gewünschten Farben.  
  
     Dies kann erfolgen entweder programmgesteuert oder zur Entwurfszeit in den **Eigenschaften** Fenster.  
  
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
  
2.  Legen Sie die <xref:System.Windows.Forms.LinkLabel.Text%2A> Eigenschaft, um eine geeignete Beschriftung.  
  
     Dies kann erfolgen entweder programmgesteuert oder zur Entwurfszeit in den **Eigenschaften** Fenster.  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3.  Legen Sie die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> -Eigenschaft können Sie bestimmen, welcher Teil der Beschriftung als Link gekennzeichnet wird.  
  
     Die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> Wert wird dargestellt, mit einem <xref:System.Windows.Forms.LinkArea> mit zwei Zahlen, die Anfangsposition und die Anzahl der Zeichen. Dies kann erfolgen entweder programmgesteuert oder zur Entwurfszeit in den **Eigenschaften** Fenster.  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4.  Legen Sie die <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> Eigenschaft <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, oder <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>.  
  
     Wenn sie, um festgelegt ist <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>, der Teil der Beschriftung, die bestimmt, indem <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> wird nur unterstrichen werden, wenn der Mauszeiger darauf positioniert.  
  
5.  In der <xref:System.Windows.Forms.LinkLabel.LinkClicked> legen Sie Ereignishandler, d. h. die <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> Eigenschaft `true`.  
  
     Wenn ein Link aktiviert wurde, ist es üblich, dessen Darstellung in irgendeiner Form in der Regel nach ihrer Farbe geändert. Der Text ändert sich die Farbe gemäß der <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> Eigenschaft.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>  
 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>  
 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>  
 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>  
 [Übersicht über das LinkLabel-Steuerelement](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)  
 [Gewusst wie: Verknüpfen eines Objekts oder einer Webseite mit dem LinkLabel-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)  
 [LinkLabel-Steuerelement](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
