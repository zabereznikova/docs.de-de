---
title: "How to: Display Item Headers in a DataRepeater Control (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, item headers"
  - "DataRepeater, selection indicators"
ms.assetid: 37321447-0ffa-43e1-bdc9-0480e392b90f
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Display Item Headers in a DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Der Elementheader in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement fungiert als visueller Hinweis, wenn ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> ausgewählt wird.  Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>\-Eigenschaft auf <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles> \(Standardeinstellung\) festgelegt ist, wird der Header auf der linken Seite jedes Elements angezeigt.  Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>\-Eigenschaft auf <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles> festgelegt ist, wird der Header am Anfang jedes Elements angezeigt.  
  
 Der Elementheader wird nach der ersten Auswahl in der durch die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>\-Eigenschaft definierten Farbe dargestellt, und es wird ein weißes Pfeilsymbol angezeigt.  
  
> [!NOTE]
>  Wenn Sie <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> auf <xref:System.Drawing.Color.White%2A> festlegen, wird das Auswahlsymbol bei der ersten Auswahl des Elements nicht eingeblendet.  
  
 Hat ein Feld in <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> den Fokus, ändert sich die Farbe des Elementheaders in die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>\-Hintergrundfarbe, und des Pfeilsymbol wird schwarz angezeigt.  Wenn Daten geändert wurden, wird im Elementheader ein Stiftsymbol angezeigt.  
  
 Die Standardbreite des Elementheaders \(bzw. die Standardhöhe, wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>\-Eigenschaft auf <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles> festgelegt ist\) beträgt 15 Pixel.  Sie ändern die Breite durch Festlegen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>\-Eigenschaft.  
  
> [!NOTE]
>  Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>\-Eigenschaft auf einen Wert unter 11 festgelegt ist, werden die Indikatorsymbole im Elementheader nicht angezeigt.  
  
 Sie können die Elementheader ausblenden, indem Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A>\-Eigenschaft auf **False** festlegen.  Wenn <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> auf **False** festgelegt ist, wird die Auswahl eines Elements nur durch eine gestrichelte Linie entlang des Umfangs von <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> angezeigt.  
  
> [!NOTE]
>  Sie können auch einen eigenen Auswahlindikator angeben, indem Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>\-Eigenschaft von <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>\-Ereignis des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements überwachen.  Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
### So ändern Sie die Darstellung von Elementheadern  
  
1.  Wählen Sie im Windows Forms\-Designer den unteren Bereich des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements aus.  
  
    > [!NOTE]
    >  Achten Sie darauf, dass Sie den unteren Bereich des Steuerelements auswählen.  Wenn Sie den Elementvorlagenbereich auswählen, werden im Eigenschaftenfenster andere Eigenschaften angezeigt.  
  
2.  Sie können die Farbe des Elementheaders mithilfe der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A>\-Eigenschaft im Eigenschaftenfenster ändern.  
  
    > [!NOTE]
    >  Wenn Sie <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> auf <xref:System.Drawing.Color.White%2A> festlegen, wird das Auswahlsymbol bei der ersten Auswahl des Elements nicht eingeblendet.  
  
3.  Mit der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>\-Eigenschaft können Sie die Breite \(oder Höhe\) der Elementheader ändern.  
  
    > [!NOTE]
    >  Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A>\-Eigenschaft auf einen Wert unter 11 festgelegt ist, werden die Indikatorsymbole im Elementheader nicht angezeigt.  
  
### So blenden Sie Elementheader aus  
  
1.  Wählen Sie im Windows Forms\-Designer den unteren Bereich des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements aus.  
  
    > [!NOTE]
    >  Achten Sie darauf, dass Sie den unteren Bereich des Steuerelements auswählen.  Wenn Sie den Elementvorlagenbereich auswählen, werden im Eigenschaftenfenster andere Eigenschaften angezeigt.  
  
2.  Legen Sie im Eigenschaftenfenster die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A>\-Eigenschaft auf **False** fest.  
  
     Wenn ein Element in <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> ausgewählt wurde, wird als einziger Hinweis eine gestrichelte Linie entlang des Umfangs von <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> angezeigt.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [How to: Change the Layout of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)