---
title: "Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements (Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, customizing
- DataRepeater, changing run time appearance
ms.assetid: 2af6dfce-760b-489e-b863-8da967f315c3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 585ff4c942185f3199fe6e9e47a4ebd9f1f0a478
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-a-datarepeater-control-visual-studio"></a>Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements (Visual Studio)
Sie können die Darstellung der Ändern einer <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelements zur Entwurfszeit durch Festlegen von Eigenschaften oder zur Laufzeit durch Behandeln der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> Ereignis.  
  
 Eigenschaften, die zur Entwurfszeit festgelegt werden Wenn der Elementvorlagenbereich des Steuerelements aktiviert ist, werden für jede wiederholt werden <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> zur Laufzeit. Darstellungseigenschaften des der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement selbst werden zur Laufzeit nur, wenn ein Teil des Containers bleibt aufgedeckt angezeigt (z. B. wenn die <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft auf einen hohen Wert festgelegt ist).  
  
 Zur Laufzeit können Darstellungseigenschaften auf Bedingungen Basis festgelegt werden. Beispielsweise können in einer planungsanwendung Sie ändern die Farbe des Hintergrunds eines Elements, um Benutzer zu warnen, wenn ein Element überfällig ist. In der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> Ereignishandler, d. h. Wenn Sie eine Eigenschaft wie z. B. in einer bedingten Anweisung festlegen `If…Then`, müssen Sie auch verwenden eine `Else` -Klausel, um die Darstellung festzulegen, wenn die Bedingung nicht erfüllt wird.  
  
### <a name="to-change-the-appearance-at-design-time"></a>So ändern Sie die Darstellung zur Entwurfszeit  
  
1.  Wählen Sie in der Windows Forms-Designer den Elementvorlagenbereich (oberer Bereich) von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
2.  Klicken Sie im Eigenschaftenfenster wählen Sie eine Eigenschaft, und ändern Sie den Wert. Allgemeine Eigenschaften, die Darstellung beeinflussen enthalten <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, <xref:System.Windows.Forms.Panel.BorderStyle%2A>, und <xref:System.Windows.Forms.Control.ForeColor%2A>.  
  
### <a name="to-change-the-appearance-at-run-time"></a>So ändern Sie die Darstellung zur Laufzeit  
  
1.  Klicken Sie im Code-Editor in der Dropdownliste „Ereignis“ auf **DrawItem**.  
  
2.  In der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> -Ereignishandler Code hinzufügen, um die Eigenschaften festlegen:  
  
     [!code-csharp[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterAppearance#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Einige allgemeine Anpassungen für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement gehört das Anzeigen von Zeilen abwechselnde Farben und die Farbe eines Felds auf Grundlage einer Bedingung zu ändern. Das folgende Beispiel zeigt, wie diese Anpassungen ausführen. In diesem Beispiel wird davon ausgegangen, dass Sie haben eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement, das die Products-Tabelle in der Northwind-Datenbank gebunden ist.  
  
 [!code-vb[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.vb)]
 [!code-csharp[VbPowerPacksDataRepeaterAlternateBackColor#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio_2.cs)]  
  
 Beachten Sie, dass für beide diese Anpassungen Sie Code zum Festlegen der Eigenschaften für beide Seiten der Bedingung angeben müssen. Wenn Sie keinen angeben der `Else` Bedingung, werden Sie zur Laufzeit unerwartete Ergebnisse angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>  
 [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Anzeigen von nicht gebundenen Steuerelementen in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Anzeigen von Elementheadern in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)
