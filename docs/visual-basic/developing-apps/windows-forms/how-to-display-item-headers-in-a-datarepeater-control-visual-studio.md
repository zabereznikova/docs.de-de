---
title: 'Vorgehensweise: Anzeigen von Elementheadern in einem DataRepeater-Steuerelement (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, item headers
- DataRepeater, selection indicators
ms.assetid: 37321447-0ffa-43e1-bdc9-0480e392b90f
ms.openlocfilehash: eccac1b3b02da41a34d47072be267f6c51a7d490
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504560"
---
# <a name="how-to-display-item-headers-in-a-datarepeater-control-visual-studio"></a>Vorgehensweise: Anzeigen von Elementheadern in einem DataRepeater-Steuerelement (Visual Studio)
Der Header in eine <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement ist ein visueller Indikator bei einer <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> ausgewählt ist. Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> -Eigenschaftensatz auf <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> (Standardeinstellung), der Header wird auf der linken Seite jedes Elements angezeigt. Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> -Eigenschaftensatz auf <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>, den Header am oberen Rand jedes Element angezeigt.  
  
 Wenn sie zuerst ausgewählt wird, wird der Header angezeigt, in der Farbe, die angegeben wird die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> -Eigenschaft, und ein weißer Pfeil-Symbol wird angezeigt.  
  
> [!NOTE]
>  Setzen Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> zu <xref:System.Drawing.Color.White%2A>, das Auswahlsymbol ist nicht sichtbar, wenn das Element zum ersten Mal ausgewählt wird.  
  
 Wenn ein Feld in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> den Fokus hat, die Farbe des Elementheaders in die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> die Hintergrundfarbe und das Pfeilsymbol auf Schwarz festgelegt wird. Wenn Daten geändert werden, wird der Header ein Stiftsymbol.  
  
 Die Standardbreite (oder Höhe bei der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> -Eigenschaftensatz auf <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>) des Elements Header ist 15 Pixel. Sie können die Breite ändern, durch Festlegen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> Eigenschaft.  
  
> [!NOTE]
>  Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> -Eigenschaftensatz auf ein Wert, der kleiner als 11 ist, die Indikatorsymbole im Elementheader können nicht angezeigt werden.  
  
 Die Elementheader ausblenden, indem Sie die Einstellung der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> Eigenschaft **"false"**. Wenn <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> nastaven NA hodnotu **"false"**, der einzige Hinweis darauf, dass ein Element ausgewählt ist, wird eine gestrichelte Linie um den Umfang der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
> [!NOTE]
>  Sie können auch Ihre eigenen Auswahlindikator angeben, durch die Überwachung der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> Eigenschaft der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> in die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> Ereignis die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
### <a name="to-change-the-appearance-of-item-headers"></a>So ändern Sie die Darstellung der Elementheader  
  
1.  Wählen Sie im Windows Forms-Designer, den unteren Bereich des der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
    > [!NOTE]
    >  Sie müssen den unteren Bereich des Steuerelements auswählen. Wenn Sie den Elementvorlagenbereich auswählen, wird ein anderen Satz von Eigenschaften im Eigenschaftenfenster angezeigt.  
  
2.  Verwenden Sie im Fenster Eigenschaften die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> Eigenschaft, die die Farbe des Elementheaders geändert.  
  
    > [!NOTE]
    >  Setzen Sie die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> zu <xref:System.Drawing.Color.White%2A>, das Auswahlsymbol ist nicht sichtbar, wenn das Element zum ersten Mal ausgewählt wird.  
  
3.  Verwenden der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> Eigenschaft, die die Breite (oder Höhe) des Elementheaders geändert.  
  
    > [!NOTE]
    >  Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> -Eigenschaftensatz auf ein Wert, der kleiner als 11 ist, die Indikatorsymbole im Elementheader können nicht angezeigt werden.  
  
### <a name="to-hide-item-headers"></a>Elementheader ausblenden  
  
1.  Wählen Sie im Windows Forms-Designer, den unteren Bereich des der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
    > [!NOTE]
    >  Sie müssen den unteren Bereich des Steuerelements auswählen. Wenn Sie den Elementvorlagenbereich auswählen, wird ein anderen Satz von Eigenschaften im Eigenschaftenfenster angezeigt.  
  
2.  Legen Sie im Fenster Eigenschaften die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> Eigenschaft **"false"**.  
  
     Wenn ein Element in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> wird ausgewählt, der einzige Hinweis darauf werden eine gestrichelte Linie um den Umfang der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [Vorgehensweise: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)
- [Vorgehensweise: Ändern des Layouts eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)
- [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
