---
title: 'Vorgehensweise: Erstellen einer Master / Detail-Formulars mit zwei DataRepeater-Steuerelementen (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
ms.openlocfilehash: 84639a5d49a3fa4a8c6845793c39fc8a67c31e02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a>Gewusst wie: Erstellen eines Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)
Sie können verknüpfte Daten anzeigen, indem Sie mithilfe von zwei oder mehr <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelemente zum Erstellen eines Master-/Detailformulars. Möglicherweise möchten z. B. eine Liste von Kunden in einem anzeigen <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, und wenn der Benutzer einen Kunden auswählt, zeigen Sie eine Liste der Bestellungen des Kunden in einer Sekunde <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
 Zeigen Sie verwandte Daten durch Ziehen von Detailelementen, die den gleichen Hauptschlüssel Tabellenknoten aus freigeben der **Datenquellen** auf eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement. Z. B. Wenn Sie eine Datenquelle, die einer Customers-Tabelle und einer verknüpften Bestellungstabelle aufweist verfügen, Sie finden Sie in beide Tabellen als Knoten der obersten Ebene in der Strukturansicht in die **Datenquellen** Fenster. Erweitern Sie den Kunden-Knoten, sodass die Spalten angezeigt werden können. Beachten Sie, dass die letzte Spalte in der Liste einen erweiterbaren Knoten handelt, der die Orders-Tabelle darstellt. Dieser Knoten entspricht den verknüpften Bestellungen eines Kunden.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a>Um die Anzeige zugehöriger Daten in zwei DataRepeater-Steuerelementen  
  
1.  Ziehen Sie zwei <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelemente aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** in einem Formular oder Containersteuerelement.  
  
2.  Ziehen Sie die Größe und Position Ziehpunkte, um die Größe der Steuerelemente, und positionieren Sie sie Seite-an-Seite.  
  
3.  Klicken Sie im Menü **Daten** auf **Datenquellen anzeigen**.  
  
    > [!NOTE]
    >  Wenn die **Datenquellen** Fenster leer ist, fügen Sie eine Datenquelle hinzu. Weitere Informationen finden Sie unter [Neue Datenquelle hinzufügen](/visualstudio/data-tools/add-new-data-sources).  
  
4.  In der **Datenquellen** Fenster, wählen Sie den Knoten den obersten Ebene für die Mastertabelle.  
  
5.  Ändern Sie den Ablagetyp für die Mastertabelle in Details durch Klicken auf **Details** in der Dropdown-Liste für den Tabellenknoten.  
  
6.  Ziehen Sie die Mastertabelle-Knoten in den Elementvorlagenbereich des ersten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
7.  Erweitern Sie den Hauptschlüssel Tabellenknoten, und wählen Sie den Detailknoten für die verknüpfte Tabelle.  
  
8.  Ändern Sie den Ablagetyp der Detailtabelle in Details durch Klicken auf **Details** in der Dropdown-Liste für den Tabellenknoten.  
  
9. Wählen Sie diese Tabellenknoten, und ziehen Sie es in den Elementvorlagenbereich des zweiten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Anzeigen von verknüpften Daten in einer Windows Forms-Anwendung](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
