---
title: "How to: Change the Appearance of a DataRepeater Control (Visual Studio) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "DataRepeater, customizing"
  - "DataRepeater, changing run time appearance"
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# How to: Change the Appearance of a DataRepeater Control (Visual Studio)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Sie können die Darstellung eines <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements zur Entwurfszeit ändern, indem Sie Eigenschaften festlegen. Für eine Änderung während der Laufzeit muss das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>\-Ereignis verarbeitet werden.  
  
 Eigenschaften, die Sie während der Entwurfszeit bei Auswahl des Abschnitts für die Elementvorlage im Steuerelement festlegen, werden während der Laufzeit für jedes <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> wiederholt.  Darstellungsbezogene Einstellungen des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements selbst werden während der Laufzeit nur angezeigt, wenn der Container zumindest teilweise nicht überdeckt wurde \(z. B. wenn für die Eigenschaft <xref:System.Windows.Forms.Control.Padding%2A> ein hoher Wert festgelegt wurde\).  
  
 Zur Laufzeit können darstellungsbezogene Eigenschaften basierend auf Bedingungen festgelegt werden.  In einer Planungsanwendung können Sie z. B. die Hintergrundfarbe eines Elements ändern, um Benutzer darauf aufmerksam zu machen, dass der Fälligkeitstermin des Elements verstrichen ist.  Wenn Sie im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>Ereignishandler eine Eigenschaft in einer Bedingungsanweisung wie `If…Then` festlegen, müssen Sie mit einer `Else`\-Klausel die Darstellung angeben, die verwendet wird, wenn die Bedingung nicht erfüllt wird.  
  
### So ändern Sie zur Entwurfszeit die Darstellung  
  
1.  Wählen Sie im Windows Forms\-Designer den Elementvorlagenbereich \(oben\) des <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements aus.  
  
2.  Wählen Sie im Eigenschaftenfenster eine Eigenschaft aus, und ändern Sie den Wert.  Folgende allgemeine Eigenschaften wirken sich auf die Darstellung aus: <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A> und <xref:System.Windows.Forms.Control.ForeColor%2A>.  
  
### So ändern Sie zur Laufzeit die Darstellung  
  
1.  Klicken Sie im Code\-Editor in der Ereignis\-Dropdownliste auf **DrawItem**.  
  
2.  Fügen Sie im <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>\-Ereignishandler Code hinzu, um die Eigenschaften festzulegen:  
  
     [!code-cs[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.vb)]  
  
## Beispiel  
 Zu den häufigsten Anpassungen für das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement gehören die Anzeige der Zeilen in unterschiedlichen Farben und die Änderung der Farbe eines Felds auf Basis einer Bedingung.  Das folgende Beispiel veranschaulicht, wie diese Anpassungen vorgenommen werden.  In diesem Beispiel wird davon ausgegangen, dass Sie über ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement verfügen, das an die Products\-Tabelle in der Datenbank Northwind gebunden ist.  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.vb)]
 [!code-cs[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.cs)]  
  
 Beachten Sie, dass Sie für beide Anpassungen Code angeben müssen, um die Eigenschaften für beide Seiten der Bedingung festzulegen.  Wenn Sie die `Else`\-Bedingung nicht angeben, erhalten Sie zur Laufzeit unerwartete Ergebnisse.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)   
 [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [How to: Display Item Headers in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)