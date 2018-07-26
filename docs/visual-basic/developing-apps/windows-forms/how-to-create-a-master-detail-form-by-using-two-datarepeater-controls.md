---
title: 'Vorgehensweise: Erstellen einer Master-/ Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, master/detail tables
ms.assetid: eec43ae3-05d8-45a1-8d41-3803c6359dbe
ms.openlocfilehash: 84639a5d49a3fa4a8c6845793c39fc8a67c31e02
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245528"
---
# <a name="how-to-create-a-masterdetail-form-by-using-two-datarepeater-controls-visual-studio"></a>Gewusst wie: Erstellen eines Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)
Sie können verknüpfte Daten anzeigen, indem Sie mithilfe von zwei oder mehr <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelemente zum Erstellen eines Master/Detail-Formulars. Beispielsweise sollten Sie zum Anzeigen einer Liste von Kunden in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, und wenn der Benutzer einen Kunden auswählt, zeigen Sie eine Liste der Bestellungen des Kunden in einer Sekunde <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.  
  
 Sie können verknüpfte Daten anzuzeigen, ziehen die Detailelemente, die den gleichen Mastertabellenknoten aus zu verwenden die **Datenquellen** auf eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement. Z. B. Wenn Sie eine Datenquelle, die einer Customers-Tabelle und einer verknüpften Bestellungstabelle aufweist verfügen, Sie finden Sie in beide Tabellen als Knoten der obersten Ebene in der Strukturansicht in die **Datenquellen** Fenster. Erweitern Sie den Kunden-Knoten, sodass die Spalten angezeigt werden können. Beachten Sie, dass die letzte Spalte in der Liste einen erweiterbaren Knoten handelt, der die Orders-Tabelle darstellt. Dieser Knoten entspricht den verknüpften Bestellungen eines Kunden.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-display-related-data-in-two-datarepeater-controls"></a>Zum Anzeigen von verknüpfter Daten in zwei DataRepeater-Steuerelementen  
  
1.  Ziehen Sie zwei <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelemente aus der **Visual Basic PowerPacks** Registerkarte die **Toolbox** in ein Formular oder Containersteuerelement.  
  
2.  Ziehen Sie die Größe und Position die bildhandles, um die Größe der Steuerelemente, und positionieren Sie diese Seite-an-Seite.  
  
3.  Klicken Sie im Menü **Daten** auf **Datenquellen anzeigen**.  
  
    > [!NOTE]
    >  Wenn die **Datenquellen** leer ist, fügen Sie eine Datenquelle hinzu. Weitere Informationen finden Sie unter [Neue Datenquelle hinzufügen](/visualstudio/data-tools/add-new-data-sources).  
  
4.  In der **Datenquellen** Fenster, wählen Sie den obersten Knoten für die Mastertabelle.  
  
5.  Ändern Sie den Ablagetyp für die Mastertabelle Details durch Klicken auf **Details** in der Dropdown-Liste für den Tabellenknoten.  
  
6.  Ziehen Sie den master-Tabelle in den Elementvorlagenbereich des ersten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
7.  Erweitern Sie den Knoten für die Mastertabelle, und wählen Sie den Detailknoten für die verknüpfte Tabelle.  
  
8.  Ändern Sie den Ablagetyp für die Detailtabelle Details durch Klicken auf **Details** in der Dropdown-Liste für den Tabellenknoten.  
  
9. Wählen Sie diese Tabellenknoten, und ziehen Sie es in den Elementvorlagenbereich des zweiten <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Anzeigen von verknüpften Daten in einer Windows Forms-Anwendung](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)  
 [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
