---
title: "Gewusst wie: Definieren des Verhaltens bei Gr&#246;&#223;en- und Positions&#228;nderungen in einem geteilten Fenster | Microsoft Docs"
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
  - "Geteilte Fenster, Größenänderung"
  - "SplitContainer-Steuerelement [Windows Forms], Größenänderung"
  - "Splitterfenster, Größenänderung"
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Gewusst wie: Definieren des Verhaltens bei Gr&#246;&#223;en- und Positions&#228;nderungen in einem geteilten Fenster
Die Bereiche des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements eignen sich sehr gut für Größenänderungen und sonstige Änderungen durch Benutzer.  Dennoch kann es zeitweilig vorkommen, dass Sie den Splitter durch das Programm steuern lassen möchten. Beispielsweise seine Position und die Möglichkeiten zum Verschieben sollen dann programmgesteuert festgelegt werden.  
  
 Mithilfe der <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>\-Eigenschaft und anderer Eigenschaften des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements können Sie das Verhalten der Benutzeroberfläche präzise an Ihre Anforderungen anpassen.  Diese Eigenschaften sind in der folgenden Tabelle aufgeführt.  
  
|Name|Beschreibung|  
|----------|------------------|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>\-Eigenschaft|Bestimmt, ob der Splitter mittels Tastatur oder Maus bewegt werden kann.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>\-Eigenschaft|Bestimmt den Abstand zwischen dem linken bzw. oberen Rand und der verschiebbaren Splitterleiste in Pixel.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>\-Eigenschaft|Bestimmt den Mindestabstand in Pixel, um den der Benutzer den Splitter verschieben kann.|  
  
 Im Beispiel unten wird die <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>\-Eigenschaft geändert, um den Effekt eines "springenden Splitters" zu erzeugen. Beim Verschieben des Splitters durch den Benutzer wird die Position in Schritten von 10 Pixel erhöht anstelle des Standardwerts von einem Pixel.  
  
### So definieren Sie das Verhalten von SplitContainer bei einer Änderung der Größe  
  
1.  Legen Sie innerhalb einer Prozedur die <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>\-Eigenschaft auf die gewünschte Größe fest, um das "springende" Verhalten des Splitters zu erreichen.  
  
     Im folgenden Codebeispiel wird innerhalb des <xref:System.Windows.Forms.Form.Load>\-Ereignisses des Formulars der Splitter im <xref:System.Windows.Forms.SplitContainer>\-Steuerelement auf eine Sprungweite von 10 Pixel beim Verschieben festgelegt.  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     Eine leichte Bewegung des Splitters nach links oder rechts führt zu keinem wahrnehmbaren Effekt. Wird der Mauszeiger jedoch um 10 Pixel in eine der beiden Richtungen bewegt, springt der Splitter zu der neuen Position.  
  
## Siehe auch  
 <xref:System.Windows.Forms.SplitContainer>   
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>