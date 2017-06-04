---
title: "&#220;bersicht &#252;ber das SplitContainer-Steuerelement (Windows&#160;Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SplitContainer"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "SplitContainer-Steuerelement [Windows Forms], Informationen über das SplitContainer-Steuerelement"
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# &#220;bersicht &#252;ber das SplitContainer-Steuerelement (Windows&#160;Forms)
Das <xref:System.Windows.Forms.SplitContainer>\-Steuerelement in Windows Forms kann als zusammengesetztes Steuerelement betrachtet werden. Es setzt sich aus zwei Bereichen zusammen, die durch eine verschiebbare Leiste getrennt sind.  Wenn sich der Mauszeiger über der Leiste befindet, ändert sich sein Aussehen, um anzuzeigen, dass die Leiste verschiebbar ist.  
  
> [!IMPORTANT]
>  In der **Toolbox** ersetzt das <xref:System.Windows.Forms.SplitContainer>\-Steuerelement das <xref:System.Windows.Forms.Splitter>\-Steuerelement, das in der Vorgängerversion von [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] enthalten war.  Das <xref:System.Windows.Forms.SplitContainer>\-Steuerelement ist das bevorzugte Steuerelement gegenüber dem <xref:System.Windows.Forms.Splitter>\-Steuerelement.  Die <xref:System.Windows.Forms.Splitter>\-Klasse ist aus Gründen der Kompatibilität mit vorhandenen Anwendungen weiterhin in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] enthalten. Wir empfehlen jedoch ausdrücklich die Verwendung des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements bei neuen Projekten.  
  
 Mit dem <xref:System.Windows.Forms.SplitContainer>\-Steuerelement können Sie komplexe Benutzeroberflächen erstellen. Häufig bestimmt die Auswahl in dem einen Bereich, welche Objekte in dem anderen Bereich angezeigt werden.  Diese Anordnung eignet sich sehr gut für die Anzeige und das Durchsuchen von Informationen.  Die beiden Bereiche ermöglichen die in Bereiche getrennte Anordnung von Informationen. Mithilfe der Leiste, die auch "Splitter" genannt wird, können die Benutzer die Größe der Bereiche leicht anpassen.  
  
 Es können auch mehrere <xref:System.Windows.Forms.SplitContainer>\-Steuerelemente verwendt werden. Dabei wird das zweite <xref:System.Windows.Forms.SplitContainer>\-Steuerelement horizontal ausgerichtet, um die Bereiche übereinander anzuordnen.  
  
 Beachten Sie, dass auf das <xref:System.Windows.Forms.SplitContainer>\-Steuerelement standardmäßig über Tastatureingaben zugegriffen werden kann. Wenn die <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>\-Eigenschaft auf `false` festgelegt ist, können Benutzer den Splitter durch Drücken der PFEILTASTEN verschieben.  
  
 Die <xref:System.Windows.Forms.SplitContainer.Orientation%2A>\-Eigenschaft des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements bestimmt die Richtung des Splitters, nicht die des Steuerelements.  Wenn diese Eigenschaft auf <xref:System.Windows.Forms.Orientation> festgelegt ist, verläuft der Splitter daher von oben nach unten und erstellt einen linken und einen rechten Bereich.  
  
 Beachten Sie außerdem, dass der Wert der <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A>\-Eigenschaft entsprechend dem Wert der <xref:System.Windows.Forms.SplitContainer.Orientation%2A>\-Eigenschaft variiert.  Weitere Informationen finden Sie unter <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A>\-Eigenschaft.  
  
 Sie können auch die Größe und die Bewegung des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements beschränken.  Die <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>\-Eigenschaft bestimmt, welcher Bereich bei einer Größenänderung des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements seine ursprüngliche Größe beibehält. Die <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>\-Eigenschaft legt fest, ob der Splitter mithilfe der Tastatur oder der Maus verschoben werden kann.  
  
> [!NOTE]
>  Auch wenn die <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>\-Eigenschaft auf `true` festgelegt ist, kann der Splitter zum Beispiel unter Verwendung der <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>\-Eigenschaft programmgesteuert verschoben werden.  
  
 Nicht zuletzt verfügt jeder Bereich des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements über Eigenschaften, um die individuelle Bereichsgröße zu bestimmen.  
  
## Häufig verwendete Eigenschaften, Methoden und Ereignisse  
  
|Name|Beschreibung|  
|----------|------------------|  
|<xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>\-Eigenschaft|Bestimmt, welcher Bereich bei einer Größenänderung des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements die ursprüngliche Größe beibehält.|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>\-Eigenschaft|Bestimmt, ob der Splitter mit der Tastatur oder der Maus verschoben werden kann.|  
|<xref:System.Windows.Forms.SplitContainer.Orientation%2A>\-Eigenschaft|Bestimmt, ob der Splitter vertikal oder horizontal verläuft.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>\-Eigenschaft|Bestimmt den Abstand zwischen dem linken bzw. oberen Rand und der verschiebbaren Splitterleiste in Pixel.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>\-Eigenschaft|Bestimmt den Mindestabstand in Pixel, um den der Benutzer den Splitter verschieben kann.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A>\-Eigenschaft|Bestimmt die Breite des Splitters in Pixel.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoving>\-Ereignis|Tritt auf, wenn der Splitter gerade verschoben wird.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoved>\-Ereignis|Tritt auf, wenn der Splitter verschoben wurde.|  
  
## Siehe auch  
 <xref:System.Windows.Forms.SplitContainer>   
 [SplitContainer\-Steuerelement](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)   
 [SplitContainer Control Sample](http://msdn.microsoft.com/de-de/9015fad0-7108-4d85-a83a-a72d038c4f65)