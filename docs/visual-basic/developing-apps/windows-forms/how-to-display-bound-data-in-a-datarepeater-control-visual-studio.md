---
title: "How to: Display Bound Data in a DataRepeater Control (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, data-binding"
  - "DataRepeater, displaying bound controls"
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# How to: Display Bound Data in a DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement wird häufig zur Anzeige gebundener Daten aus einer Datenbank oder einer anderen Datenquelle eingesetzt.  
  
 Sie können zusätzlich zu gebundenen Steuerelementen weitere Steuerelemente hinzufügen, z. B. eine statische Bezeichnung oder ein Bild, die auf allen Elementen im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement wiederholt werden.  Weitere Informationen hierzu finden Sie unter [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
 Sie können auch zur Laufzeit Objekte an eine Datenquelle binden, indem Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>\-Eigenschaft auf `True` festlegen und der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A>\-Eigenschaft eine Datenquelle zuweisen.  In diesem Fall müssen Sie alle Interaktion mit der Datenquelle verwalten.  Weitere Informationen hierzu finden Sie unter [Virtual Mode in the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### So erstellen Sie einen datengebundenen DataRepeater  
  
1.  Ziehen Sie ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement von der Registerkarte **Visual Basic PowerPacks** in der **Toolbox** in ein Formular\- oder Containersteuerelement.  
  
2.  Ziehen Sie die Handles für die Größenanpassung und die Position, und positionieren Sie das Steuerelement.  
  
     Beachten Sie, dass das Steuerelement über zwei rechteckige Bereiche verfügt.  Der obere Bereich ist die *Elementvorlage*. Steuerelemente, die der Vorlage hinzugefügt werden, werden zur Laufzeit in jedem Element des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements wiederholt.  Der untere Bereich ist der *Viewport*, an dem die Elemente angezeigt werden.  
  
     Sie können die Größe und Position des Steuerelements oder der Elementvorlage auch anpassen, indem Sie die Eigenschaften **Size** und **Position** im Eigenschaftenfenster ändern.  
  
3.  Klicken Sie im Menü **Daten** auf **Datenquellen anzeigen**.  
  
    > [!NOTE]
    >  Wenn das **Datenquellenfenster** leer ist, fügen Sie ihm eine Datenquelle hinzu.  Weitere Informationen hierzu finden Sie unter [Übersicht über Datenquellen](/visual-studio/data-tools/add-new-data-sources).  
  
4.  Wählen Sie im Fenster **Datenquellen** den Knoten der obersten Ebene für die Tabelle aus, die die zu bindenden Daten enthält.  
  
5.  Ändern Sie den Ablagetyp der Tabelle in `Details`, indem Sie in der Dropdownliste des Tabellenknotens auf `Details` klicken.  
  
6.  Wählen Sie den Tabellenknoten aus, und ziehen Sie diesen auf den Elementvorlagenbereich des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements.  
  
     Sie können angeben, welche Steuerelementtypen für jedes Feld angezeigt werden.  Weitere Informationen finden Sie unter [Festlegen des Steuerelements, das beim Ziehen aus dem Datenquellenfenster erstellt werden soll](/visual-studio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [How to: Create a Master\/Detail Form by Using Two DataRepeater Controls](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)   
 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)