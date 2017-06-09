---
title: "Gewusst wie: &#196;ndern der Darstellung des LinkLabel-Steuerelements in Windows&#160;Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Beispiele [Windows Forms], LinkLabel-Steuerelement"
  - "LinkLabel-Steuerelement [Windows Forms], Ändern der Darstellung von Hyperlinks"
  - "LinkLabel-Steuerelement [Windows Forms], Beispiele"
  - "LinkLabel-Eigenschaften"
  - "Verknüpfungen, Ändern der Darstellung"
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Gewusst wie: &#196;ndern der Darstellung des LinkLabel-Steuerelements in Windows&#160;Forms
Sie können den vom <xref:System.Windows.Forms.LinkLabel>\-Steuerelement angezeigten Text an verschiedene Anforderungen anpassen.  Um darauf hinzuweisen, dass auf den Text geklickt werden kann, ist es beispielsweise üblich, ihn mit einer bestimmten Farbe und einer Unterstreichung zu versehen.  Nachdem der Benutzer auf den Text geklickt hat, ändert sich seine Farbe.  Um dieses Verhalten zu steuern, können Sie fünf verschiedene Eigenschaften festlegen, nämlich <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> und <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>.  
  
### So ändern Sie die Darstellung eines LinkLabel\-Steuerelements  
  
1.  Legen Sie die <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>\-Eigenschaft und die <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>\-Eigenschaft auf die gewünschten Farben fest.  
  
     Diesen Schritt können Sie entweder programmgesteuert oder zur Entwurfszeit im **Eigenschaftenfenster** ausführen.  
  
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
  
2.  Legen Sie für die <xref:System.Windows.Forms.LinkLabel.Text%2A>\-Eigenschaft eine geeignete Beschriftung fest.  
  
     Diesen Schritt können Sie entweder programmgesteuert oder zur Entwurfszeit im **Eigenschaftenfenster** ausführen.  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3.  Definieren Sie die <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>\-Eigenschaft, um festzulegen, welcher Teil der Beschriftung als Link gekennzeichnet wird.  
  
     Der<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>\-Wert wird durch einen <xref:System.Windows.Forms.LinkArea> mit zwei Zahlen dargestellt. Diese stehen für die Position des ersten Zeichens und die Anzahl der Zeichen.  Diesen Schritt können Sie entweder programmgesteuert oder zur Entwurfszeit im **Eigenschaftenfenster** ausführen.  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4.  Legen Sie die <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>\-Eigenschaft auf <xref:System.Windows.Forms.LinkBehavior>, <xref:System.Windows.Forms.LinkBehavior> oder <xref:System.Windows.Forms.LinkBehavior> fest.  
  
     Lautet die Einstellung <xref:System.Windows.Forms.LinkBehavior>, ist der durch <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> definierte Teil der Beschriftung nur unterstrichen, wenn der Mauszeiger darauf positioniert wird.  
  
5.  Legen Sie im <xref:System.Windows.Forms.LinkLabel.LinkClicked>\-Ereignishandler die <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>\-Eigenschaft auf `true` fest.  
  
     Nachdem ein Link aufgerufen wurde, wird für gewöhnlich seine Darstellung geändert, d. h. normalerweise die Farbe.  Der Text nimmt die Farbe an, die durch die <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>\-Eigenschaft vorgegeben wird.  
  
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
  
## Siehe auch  
 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>   
 <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>   
 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>   
 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>   
 [Übersicht über das LinkLabel\-Steuerelement](../../../../docs/framework/winforms/controls/linklabel-control-overview-windows-forms.md)   
 [Gewusst wie: Verknüpfen eines Objekts oder einer Webseite mit dem LinkLabel\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/link-to-an-object-or-web-page-with-wf-linklabel-control.md)   
 [LinkLabel\-Steuerelement](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)