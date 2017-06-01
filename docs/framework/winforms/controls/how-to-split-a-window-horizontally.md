---
title: "Gewusst wie: Horizontales Teilen eines Fensters | Microsoft Docs"
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
  - "SplitContainer-Steuerelement [Windows Forms], Horizontale Aufteilung"
  - "Splitterfenster, Ändern der Aufteilungsausrichtung"
  - "Splitterfenster, Horizontal"
  - "Fenster, Teilen horizontal"
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Horizontales Teilen eines Fensters
Im folgenden Codebeispiel wird der Splitter generiert, der das <xref:System.Windows.Forms.SplitContainer>\-Steuerelement horizontal teilt.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.SplitContainer.Orientation%2A>\-Eigenschaft des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements bestimmt die Richtung des Splitters, nicht die des Steuerelements.  
  
### So teilen Sie ein Fenster horizontal  
  
1.  Legen Sie innerhalb einer Prozedur die <xref:System.Windows.Forms.SplitContainer.Orientation%2A>\-Eigenschaft des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements auf <xref:System.Windows.Forms.Orientation> fest.  
  
    ```vb  
    Sub ShowSplitContainer()  
        Dim splitContainer1 as new SplitContainer()  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D  
        splitContainer1.Location = New System.Drawing.Point(74, 20)  
        splitContainer1.Name = "DemoSplitContainer"  
        splitContainer1.Size = New System.Drawing.Size(212, 435)  
        splitContainer1.TabIndex = 0  
        splitContainer1.Orientation = Orientation.Horizontal  
        Controls.Add(splitContainer1)  
    End Sub  
  
    ```  
  
    ```csharp  
    public void showSplitContainer()  
    {  
        SplitContainer splitContainer1 = new SplitContainer ();  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D;  
        splitContainer1.Location = new System.Drawing.Point (74, 20);  
        splitContainer1.Name = "DemoSplitContainer";  
        splitContainer1.Size = new System.Drawing.Size (212, 435);  
        splitContainer1.TabIndex = 0;  
        splitContainer1.Orientation = Orientation.Horizontal;  
        this.Controls.Add (splitContainer1);  
  
    }  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.SplitContainer>   
 [SplitContainer\-Steuerelement](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)