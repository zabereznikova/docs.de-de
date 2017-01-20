---
title: "How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "DataRepeater, master/detail tables"
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Sie können verknüpfte Daten anzeigen, indem Sie mithilfe von zwei oder mehr <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelementen ein Master\-\/Detailformular erstellen.  Sie können beispielsweise in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> eine Liste der Kunden anzeigen und nach Auswahl eines Kunden durch den Benutzer in einem zweiten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> die Aufträge dieses Kunden einblenden.  
  
 Um verknüpfte Daten anzuzeigen, ziehen Sie Detailelemente mit dem gleichen Mastertabellenknoten aus dem Fenster **Datenquellen** auf ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelement.  Wenn beispielsweise eine Datenquelle mit einer Kundentabelle und einer verknüpften Auftragstabelle vorliegt, werden beide Tabellen in der Strukturansicht als Knoten der höchsten Ebene im Fenster **Datenquellen** angezeigt.  Erweitern Sie den Knoten für Kunden, um die Spalten einzublenden.  Beachten Sie, dass die letzte Spalte in der Liste ein erweiterbarer Knoten ist, der die Auftragstabelle darstellt.  Dieser Knoten entspricht den verknüpften Bestellungen eines Kunden.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### So zeigen Sie verknüpfte Daten in zwei DataRepeater\-Steuerelementen an  
  
1.  Ziehen Sie zwei <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelemente von der Registerkarte **Visual Basic PowerPacks** in der **Toolbox** in ein Formular\- oder Containersteuerelement.  
  
2.  Ziehen Sie die Handles für die Größenanpassung und Position, um die Größe der Steuerelemente anzupassen und sie nebeneinander zu positionieren.  
  
3.  Klicken Sie im Menü **Daten** auf **Datenquellen anzeigen**.  
  
    > [!NOTE]
    >  Wenn das **Datenquellenfenster** leer ist, fügen Sie ihm eine Datenquelle hinzu.  Weitere Informationen hierzu finden Sie unter [Übersicht über Datenquellen](/visual-studio/data-tools/add-new-data-sources).  
  
4.  Wählen Sie im Fenster **Datenquellen** den Knoten der obersten Ebene für die Mastertabelle aus.  
  
5.  Ändern Sie den Ablagetyp der Mastertabelle in **Details**, indem Sie in der Dropdownliste des Tabellenknotens auf **Details** klicken.  
  
6.  Ziehen Sie den Mastertabellenknoten auf den Elementvorlagenbereich des ersten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements.  
  
7.  Erweitern Sie den Mastertabellenknoten, und wählen Sie den Detailknoten für die verknüpfte Tabelle aus.  
  
8.  Ändern Sie den Ablagetyp der Detailtabelle in **Details**, indem Sie in der Dropdownliste des Tabellenknotens auf **Details** klicken.  
  
9. Wählen Sie diesen Tabellenknoten aus, und ziehen Sie ihn auf den Elementvorlagenbereich des zweiten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>\-Steuerelements.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [Gewusst wie: Anzeigen von verknüpften Daten in einer Windows Forms\-Anwendung](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md)   
 [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)