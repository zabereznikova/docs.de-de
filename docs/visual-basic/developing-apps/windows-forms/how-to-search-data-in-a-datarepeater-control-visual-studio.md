---
title: 'Gewusst wie: Suchen von Daten in einem DataRepeater-Steuerelement (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, implementing search
- DataRepeater, searching data
ms.assetid: a8ab5d17-b94f-43c4-8dd7-d0450226d73f
ms.openlocfilehash: 689990ee125c85c3151a4e965b619fde068d220e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-search-data-in-a-datarepeater-control-visual-studio"></a>Gewusst wie: Suchen von Daten in einem DataRepeater-Steuerelement (Visual Studio)
Beim Verwenden einer <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement, das viele Datensätze enthält, können Sie Benutzern die Suche nach einem bestimmten Datensatz empfiehlt. Sie können eine Suche durch Abfragen der zugrunde liegende implementieren, anstatt das Durchsuchen der Daten in das Steuerelement, <xref:System.Windows.Forms.BindingSource>. Wenn das Element gefunden wird, können Sie dann die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.CurrentItemIndex%2A> Eigenschaft wählen Sie das Element, und es per Bildlauf anzeigen.  
  
### <a name="to-implement-search"></a>Suche implementiert.  
  
1.  Ziehen Sie ein <xref:System.Windows.Forms.TextBox> -Steuerelement aus der **Toolbox** auf das Formular, das das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement enthält.  
  
2.  Ändern Sie im Eigenschaftenfenster die Eigenschaft **Name** in **SearchTextBox**.  
  
3.  Ziehen Sie ein <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Formular, das das <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> -Steuerelement enthält.  
  
4.  Ändern Sie im Eigenschaftenfenster die Eigenschaft **Name** in **SearchButton**. Ändern Sie die **Text** -Eigenschaft in **Search**.  
  
5.  Doppelklicken Sie auf das <xref:System.Windows.Forms.Button> -Steuerelement, um den Code-Editor zu öffnen, und fügen Sie dem `SearchButton_Click` -Ereignishandler den folgenden Code hinzu:  
  
     [!code-vb[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-search-data-in-a-datarepeater-control-visual-studio_1.vb)]
     [!code-csharp[VbPowerPacksDataRepeaterSearch#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-search-data-in-a-datarepeater-control-visual-studio_1.cs)]  
  
     Ersetzen Sie *ProductsBindingSource* durch den Namen des der <xref:System.Windows.Forms.BindingSource> für Ihre <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>, und Ersetzen Sie *"ProductID"* mit dem Namen des Felds, das Sie suchen möchten.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
