---
title: "How to: Change the Layout of a DataRepeater Control (Visual Studio) | Microsoft Docs"
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
  - "DataRepeater, changing layout style"
  - "DataRepeater, changing orientation"
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Change the Layout of a DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement kann sowohl vertikal \(vertikaler Bildlauf der Elemente\) als auch horizontal \(horizontaler Bildlauf der Elemente\) ausgerichtet werden.  Die Ausrichtung kann zur Entwurfszeit oder Laufzeit geändert werden, indem Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>\-Eigenschaft bearbeiten.  Wenn Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>\-Eigenschaft zur Laufzeit ändern, sollten Sie ggf. die Größe von <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> anpassen und die untergeordneten Steuerelemente neu positionieren.  
  
> [!NOTE]
>  Beim Neupositionieren der Steuerelemente von <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> zur Laufzeit müssen Sie die Methoden <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> und <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> am Anfang und Ende des Codeblocks aufrufen, durch den die Steuerelemente neu positioniert werden.  
  
### So ändern Sie zur Entwurfszeit das Layout  
  
1.  Wählen Sie im Windows Forms\-Designer das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement aus.  
  
    > [!NOTE]
    >  Markieren Sie die Außenkante des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements, indem Sie auf den unteren Bereich des Steuerelements klicken. Klicken Sie nicht auf den oberen <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A>\-Bereich.  
  
2.  Legen Sie im Eigenschaftenfenster für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>\-Eigenschaft <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles> oder <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles> fest.  
  
### So ändern Sie zur Laufzeit das Layout  
  
1.  Fügen Sie dem `Click`\-Ereignishandler einer Schaltfläche oder eines Menüs folgenden Code hinzu:  
  
     [!code-cs[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/VbPowerPacksDataRepeaterLayoutCS/VbPowerPacksDataRepeaterLayout.cs#1)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/VbPowerPacksDataRepeaterLayout/VbPowerPacksDataRepeaterLayout.vb#1)]  
  
2.  In den meisten Fällen fügen Sie ähnlichen Code wie im Beispielsabschnitt hinzu, um die Größe von <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> zu ändern und die Steuerelemente entsprechend der neuen Ausrichtung anzuordnen.  
  
## Beispiel  
 Im folgenden Beispiel wird die Reaktion auf das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged>\-Ereignis in einem Ereignishandler veranschaulicht.  Für dieses Beispiel ist ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement mit dem Namen `DataRepeater1` in einem Formular erforderlich, dessen <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> zwei <xref:System.Windows.Forms.TextBox>\-Steuerelemente mit den Namen `TextBox1` und `TextBox2` enthält.  
  
 [!code-cs[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/VbPowerPacksDataRepeaterLayoutCS/VbPowerPacksDataRepeaterLayout.cs#2)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/VbPowerPacksDataRepeaterLayout/VbPowerPacksDataRepeaterLayout.vb#2)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)