---
title: "How to: Display Unbound Controls in a DataRepeater Control (Visual Studio) | Microsoft Docs"
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
  - "DataRepeater, adding unbound controls"
  - "DataRepeater"
  - "displaying unbound data"
ms.assetid: f234fa40-5a13-4209-930e-7c5f81e86e66
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Display Unbound Controls in a DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Sie können zusätzlich zu gebundenen Steuerelementen weitere Steuerelemente zu einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement hinzufügen, z. B. eine statische Bezeichnung oder ein Bild, die auf allen Elementen im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement wiederholt werden.  
  
> [!NOTE]
>  <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> muss mindestens ein gebundenes Steuerelement aufweisen, andernfalls wird zur Laufzeit nichts angezeigt.  
  
### So fügen Sie ungebundene Steuerelemente zu einem DataRepeater hinzu  
  
1.  Ziehen Sie ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement von der Registerkarte **Visual Basic PowerPacks** in der **Toolbox** in ein Formular\- oder Containersteuerelement.  
  
2.  Ziehen Sie die Handles für die Größenanpassung und die Position, und positionieren Sie das Steuerelement.  
  
     Sie können die Größe und Position des Steuerelements auch anpassen, indem Sie die Eigenschaften **Size** und **Position** im Eigenschaftenfenster ändern.  
  
3.  Fügen Sie dem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement mindestens ein datengebundenes Steuerelement hinzu.  Weitere Informationen hierzu finden Sie unter [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md).  
  
4.  Ziehen Sie ein Steuerelement aus der **Toolbox** auf den Elementvorlagenbereich des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements.  
  
     Beachten Sie, dass das Steuerelement über zwei rechteckige Bereiche verfügt.  Der innere Bereich ist die *Elementvorlage*. Steuerelemente, die der Vorlage hinzugefügt werden, werden zur Laufzeit in jedem Element des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements wiederholt.  Der äußere Bereich ist der *Viewport*, in dem die Elemente angezeigt werden. Steuerelemente, die diesem Bereich hinzugefügt werden, werden zur Laufzeit nicht angezeigt.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [How to: Create a Master\/Detail Form by Using Two DataRepeater Controls](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)   
 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)