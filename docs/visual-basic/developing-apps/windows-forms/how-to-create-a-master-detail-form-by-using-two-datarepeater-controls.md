---
title: 'Gewusst wie: Erstellen einer Master / Detail-Formular mit zwei DataRepeater-Steuerelementen (Visual Studio) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 23789bb11cab17b50928651e1dc00d5d59640c0f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a>Gewusst wie: Erstellen eines Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)
Sie können verknüpfte Daten anzeigen, indem Sie mithilfe von zwei oder mehr <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelemente zum Erstellen eines Master/Detail-Formulars.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Beispielsweise möchten Sie zeigt eine Liste von Kunden in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, und wenn der Benutzer einen Kunden auswählt, zeigen Sie eine Liste der Aufträge dieses Kunden pro Sekunde <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
 Verknüpfte Daten anzuzeigen, ziehen Sie Detailelemente, die die gleichen Mastertabelle befinden, aus der **Datenquellen** auf eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Z. B. Wenn Sie eine Datenquelle, die einer Kundentabelle und einer verknüpften Auftragstabelle verfügt haben, Sie finden Sie in beide Tabellen als Knoten der obersten Ebene in der Strukturansicht der **Datenquellen** Fenster. Erweitern Sie den Knoten Kunden aus, sodass die Spalten angezeigt werden können. Beachten Sie, dass die letzte Spalte in der Liste einen erweiterbaren Knoten handelt, der die Orders-Tabelle darstellt. Dieser Knoten entspricht den verknüpften Bestellungen eines Kunden.  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a>Um verknüpfte Daten in zwei DataRepeater-Steuerelementen anzuzeigen.  
  
1.  Ziehen Sie zwei <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>-Steuerelemente aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** in ein Formular oder Containersteuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
2.  Ziehen Sie die Ziehpunkte Größe und Position, um die Größe der Steuerelemente und positionieren Sie diese Seite-an-Seite.  
  
3.  Klicken Sie im Menü **Daten** auf **Datenquellen anzeigen**.  
  
    > [!NOTE]
    >  Wenn die **Datenquellen** Fenster leer ist, fügen Sie eine Datenquelle hinzu. Weitere Informationen finden Sie unter [neue Datenquellen hinzufügen](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).  
  
4.  In der **Datenquellen** Fenster Wählen Sie den Knoten den obersten Ebene für die Mastertabelle.  
  
5.  Ändern Sie den Ablagetyp der Mastertabelle in Details durch Klicken auf **Details** in der Dropdown-Liste auf den Knoten der Tabelle.  
  
6.  Ziehen Sie den Elementvorlagenbereich des ersten Knotens Mastertabelle <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
7.  Erweitern Sie den Tabellenknoten für die master-, und wählen Sie den Detailknoten für die verknüpfte Tabelle.  
  
8.  Ändern Sie den Ablagetyp der Detailtabelle in Details durch Klicken auf **Details** in der Dropdown-Liste auf den Knoten der Tabelle.  
  
9. Wählen Sie diesen Tabellenknoten aus, und ziehen Sie es in den Elementvorlagenbereich der zweiten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)   
 [Gewusst wie: Anzeigen von verknüpften Daten in einer Windows Forms-Anwendung](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)   
 [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
