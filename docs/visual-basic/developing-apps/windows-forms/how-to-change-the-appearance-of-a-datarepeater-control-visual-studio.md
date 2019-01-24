---
title: 'Vorgehensweise: Ändern der Darstellung eines DataRepeater-Steuerelements (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, customizing
- DataRepeater, changing run time appearance
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
ms.openlocfilehash: e5508329ba716b53eff0c9e1bfe13e190fa1fd85
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716634"
---
# <a name="how-to-change-the-appearance-of-a-datarepeater-control-visual-studio"></a>Vorgehensweise: Ändern der Darstellung eines DataRepeater-Steuerelements (Visual Studio)
Sie können das Erscheinungsbild des eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement zur Entwurfszeit durch Festlegen von Eigenschaften oder zur Laufzeit durch Behandeln der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> Ereignis.  
  
 Eigenschaften, die Sie zur Entwurfszeit festlegen, wenn die Elementvorlagenbereich des Steuerelements ausgewählt ist, werden für jede wiederholt werden <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> zur Laufzeit. Darstellungseigenschaften des der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement selbst werden zur Laufzeit nur, wenn ein Teil des Containers bleibt im Detail angezeigt (z. B., wenn die <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft auf einen hohen Wert festgelegt ist).  
  
 Zur Laufzeit können Darstellungseigenschaften basierend auf Bedingungen festgelegt werden. Beispielsweise können in einer Anwendung planen Sie ändern die Hintergrundfarbe eines Elements aus, um Benutzer zu warnen, wenn ein Element überfällig ist. In der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> -Ereignishandler, wenn Sie eine Eigenschaft wie z. B. in einer bedingten Anweisung festlegen `If…Then`, Sie müssen auch verwenden, ein `Else` -Klausel, um die Darstellung zu geben, wenn die Bedingung nicht erfüllt ist.  
  
### <a name="to-change-the-appearance-at-design-time"></a>So ändern Sie die Darstellung zur Entwurfszeit  
  
1.  Wählen Sie in der Windows Forms-Designer, den Elementvorlagenbereich (oberer Bereich) von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
2.  Klicken Sie im Fenster "Eigenschaften" Wählen Sie eine Eigenschaft, und ändern Sie den Wert. Allgemeine Eigenschaften, die Darstellung auswirken, gehören <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A>, und <xref:System.Windows.Forms.Control.ForeColor%2A>.  
  
### <a name="to-change-the-appearance-at-run-time"></a>So ändern Sie die Darstellung zur Laufzeit  
  
1.  Klicken Sie im Code-Editor in der Dropdownliste „Ereignis“ auf **DrawItem**.  
  
2.  In der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> -Ereignishandler Code hinzufügen, um die Eigenschaften festlegen:  
  
     [!code-csharp[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Einige häufige Anpassungen für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement gehört das Anzeigen von Zeilen in wechselnden Farben, und die Farbe eines Felds auf Grundlage einer Bedingung ändern. Das folgende Beispiel zeigt, wie Sie diese Anpassungen vornehmen. In diesem Beispiel wird davon ausgegangen, dass Sie haben eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement, das in der Produkttabelle, in der Northwind-Datenbank gebunden ist.  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.vb)]
 [!code-csharp[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.cs)]  
  
 Beachten Sie, dass für beide dieser Anpassungen Sie Code zum Festlegen der Eigenschaften für beide Seiten der Bedingung bereitstellen müssen. Wenn Sie keinen angeben der `Else` Bedingung, werden Sie zur Laufzeit unerwartete Ergebnisse angezeigt.  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>
- [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [Vorgehensweise: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)
- [Vorgehensweise: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)
- [Vorgehensweise: Anzeigen von Elementheadern in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
