---
title: 'Gewusst wie: Ändern des Layouts eines DataRepeater-Steuerelements (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, changing layout style
- DataRepeater, changing orientation
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
ms.openlocfilehash: fa780ee40171143c17b5bdbda4a97179ed5f2151
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590841"
---
# <a name="how-to-change-the-layout-of-a-datarepeater-control-visual-studio"></a>Gewusst wie: Ändern des Layouts eines DataRepeater-Steuerelements (Visual Studio)
Die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement kann angezeigt werden, in einem vertikal (vertikaler Bildlauf der Elemente) oder Horizontal (horizontaler Bildlauf der Elemente) Ausrichtung. Sie können die Ausrichtung zur Entwurfszeit oder zur Laufzeit ändern, indem Sie ändern die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> Eigenschaft. Wenn Sie ändern die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> Eigenschaft zur Laufzeit, Sie sollten auch ändern der Größe der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> und die untergeordneten Steuerelemente neu positionieren.  
  
> [!NOTE]
>  Wenn Sie auf Steuerelemente neu positionieren der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> zur Laufzeit müssen Sie zum Aufrufen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> und <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> Methoden am Anfang und Ende des Codeblocks, der die Steuerelemente neu positioniert.  
  
### <a name="to-change-the-layout-at-design-time"></a>So ändern Sie das Layout zur Entwurfszeit  
  
1.  Wählen Sie in der Windows Forms-Designer die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
    > [!NOTE]
    >  Wählen Sie den äußeren Rahmen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement, indem Sie auf den unteren Bereich des Steuerelements nicht in der oberen <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> Region.  
  
2.  Legen Sie im Fenster Eigenschaften die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> -Eigenschaft entweder <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> oder <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.  
  
### <a name="to-change-the-layout-at-run-time"></a>So ändern Sie das Layout zur Laufzeit  
  
1.  Fügen Sie den folgenden Code, um eine Schaltfläche oder ein Menü `Click` Ereignishandler:  
  
     [!code-csharp[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  In den meisten Fällen sollten Sie zum Hinzufügen von Code ähnlich dem im Beispielabschnitt angezeigt wird, um die Größe der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> und Neuanordnen von Steuerelementen entsprechend die neue Ausrichtung.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie So reagieren Sie auf die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> Ereignis in einem Ereignishandler. Dieses Beispiel benötigen Sie ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement namens `DataRepeater1` auf ein Formular, und dass seine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> enthalten zwei <xref:System.Windows.Forms.TextBox> -Steuerelemente namens `TextBox1` und `TextBox2`.  
  
 [!code-csharp[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>  
 [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
