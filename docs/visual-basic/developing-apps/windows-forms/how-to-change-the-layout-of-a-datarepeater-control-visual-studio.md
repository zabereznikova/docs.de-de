---
title: 'Vorgehensweise: Ändern des Layouts eines DataRepeater-Steuerelements (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, changing layout style
- DataRepeater, changing orientation
ms.assetid: 33aa8fd5-ac63-4bd0-ba13-8c2ab17e7824
ms.openlocfilehash: 3389daa6383444b48faab4c5383b281e44349bce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625600"
---
# <a name="how-to-change-the-layout-of-a-datarepeater-control-visual-studio"></a>Vorgehensweise: Ändern des Layouts eines DataRepeater-Steuerelements (Visual Studio)
Die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement kann in einem vertikal (vertikaler Bildlauf-Elemente) oder Horizontal (horizontaler Bildlauf-Elemente) angezeigt werden Ausrichtung. Sie können die Ausrichtung, die zur Entwurfszeit oder zur Laufzeit ändern, durch Ändern der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> Eigenschaft. Wenn Sie ändern die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> -Eigenschaft zur Laufzeit, Sie sollten auch zum Ändern der Größe der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> und die untergeordneten Steuerelemente neu positionieren.  
  
> [!NOTE]
>  Wenn Sie auf Steuerelemente neu positionieren der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> zur Laufzeit müssen Sie zum Aufrufen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A> und <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A> Methoden am Anfang und Ende des Codeblocks, der die Steuerelemente neu positioniert.  
  
### <a name="to-change-the-layout-at-design-time"></a>So ändern Sie das Layout zur Entwurfszeit  
  
1.  Wählen Sie in der Windows Forms-Designer die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
    > [!NOTE]
    >  Sie müssen auswählen, dem der äußeren Rahmen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement, indem Sie auf den unteren Bereich des Steuerelements nicht in der oberen <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> Region.  
  
2.  Legen Sie im Fenster Eigenschaften die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> Eigenschaft entweder <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> oder <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>.  
  
### <a name="to-change-the-layout-at-run-time"></a>So ändern Sie das Layout zur Laufzeit  
  
1.  Fügen Sie den folgenden Code, um eine Schaltfläche oder ein Menü `Click` -Ereignishandler:  
  
     [!code-csharp[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterLayout#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_1.vb)]  
  
2.  In den meisten Fällen wird Code wie im Beispielabschnitt zum Ändern der Größe angezeigten hinzufügen möchten die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> und ordnen Sie Steuerelemente an die neue Ausrichtung anpassen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Vorgehensweise zum Reagieren auf die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyleChanged> Ereignis in einem Ereignishandler. In diesem Beispiel benötigen Sie eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement mit dem Namen `DataRepeater1` auf ein Formular, und dass die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> enthalten zwei <xref:System.Windows.Forms.TextBox> -Steuerelemente namens `TextBox1` und `TextBox2`.  
  
 [!code-csharp[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterLayout#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-change-the-layout-of-a-datarepeater-control-visual-studio_2.vb)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.BeginResetItemTemplate%2A>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.EndResetItemTemplate%2A>
- [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
- [Vorgehensweise: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
