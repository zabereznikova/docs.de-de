---
title: 'Gewusst wie: Anzeigen von Elementheadern in einem DataRepeater-Steuerelement (Visual Studio)'
ms.date: 07/20/2015
helpviewer_keywords:
- DataRepeater, item headers
- DataRepeater, selection indicators
ms.assetid: 37321447-0ffa-43e1-bdc9-0480e392b90f
ms.openlocfilehash: 07f6a7e06c5b1e91597ab6b6d816407a2c172278
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33592132"
---
# <a name="how-to-display-item-headers-in-a-datarepeater-control-visual-studio"></a>Gewusst wie: Anzeigen von Elementheadern in einem DataRepeater-Steuerelement (Visual Studio)
Elementheaders in einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement verfügt über einen visuellen Indikator bei einem <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> ausgewählt ist. Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> -Eigenschaftensatz auf <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Vertical> (Standard), der Header wird auf der linken Seite jedes Elements angezeigt. Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> -Eigenschaftensatz auf <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>, wird der Header am oberen Rand jedes Element angezeigt.  
  
 Wenn es zuerst aktiviert ist, wird der Header in der Farbe, die von angegeben wird angezeigt die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> Eigenschaft und das Symbol mit einem weißen Pfeil angezeigt wird.  
  
> [!NOTE]
>  Wenn Sie festlegen, die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> zu <xref:System.Drawing.Color.White%2A>, das Auswahlsymbol wird nicht sichtbar sein, wenn Sie zuerst das Element ausgewählt ist.  
  
 Wenn ein Feld in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> den Fokus besitzt, die Farbe des Elementheaders in die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemTemplate%2A> Hintergrundfarbe und das Pfeilsymbol auf Schwarz festgelegt wird. Wenn Daten geändert werden, wird im Elementheader ein Stiftsymbol angezeigt.  
  
 Die Standardbreite (oder der Höhe bei der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.LayoutStyle%2A> -Eigenschaftensatz auf <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterLayoutStyles.Horizontal>) des Elements Header beträgt 15 Pixel. Sie können die Breite ändern, durch Festlegen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> Eigenschaft.  
  
> [!NOTE]
>  Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> Eigenschaft auf einen Wert, der kleiner als 11 festgelegt ist, werden die Indikatorsymbole im Elementheader nicht angezeigt werden.  
  
 Sie können die Elementheader ausblenden, indem Sie festlegen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> Eigenschaft **"false"**. Wenn <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> festgelegt ist, um **"false"**, lediglich den Hinweis, dass ein Element ausgewählt ist, wird eine gepunktete Linie, um den Umriss der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
> [!NOTE]
>  Sie können auch eigene Auswahlindikator angeben, durch die Überwachung der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A> Eigenschaft von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem> in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> -Ereignis für die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem.IsCurrent%2A>.  
  
### <a name="to-change-the-appearance-of-item-headers"></a>So ändern Sie die Darstellung von Elementheadern  
  
1.  Wählen Sie in der Windows Forms-Designer den unteren Bereich des der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
    > [!NOTE]
    >  Sie müssen den unteren Bereich des Steuerelements auswählen. Wenn Sie den Abschnitt "Element" Vorlage auswählen, wird eine andere Gruppe von Eigenschaften im Eigenschaftenfenster angezeigt.  
  
2.  Verwenden Sie im Fenster Eigenschaften die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> Eigenschaft, die die Farbe des Elementheaders geändert.  
  
    > [!NOTE]
    >  Wenn Sie festlegen, die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.SelectionColor%2A> zu <xref:System.Drawing.Color.White%2A>, das Auswahlsymbol wird nicht sichtbar sein, wenn Sie zuerst das Element ausgewählt ist.  
  
3.  Verwenden der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> Eigenschaft, die (Höhe oder Breite) des Elementheaders geändert.  
  
    > [!NOTE]
    >  Wenn die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderSize%2A> Eigenschaft auf einen Wert, der kleiner als 11 festgelegt ist, werden die Indikatorsymbole im Elementheader nicht angezeigt werden.  
  
### <a name="to-hide-item-headers"></a>So blenden Sie Elementheader aus  
  
1.  Wählen Sie in der Windows Forms-Designer den unteren Bereich des der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Steuerelement.  
  
    > [!NOTE]
    >  Sie müssen den unteren Bereich des Steuerelements auswählen. Wenn Sie den Abschnitt "Element" Vorlage auswählen, wird eine andere Gruppe von Eigenschaften im Eigenschaftenfenster angezeigt.  
  
2.  Legen Sie im Fenster Eigenschaften die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.ItemHeaderVisible%2A> Eigenschaft **"false"**.  
  
     Wenn ein Element in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> ist ausgewählt, wird das einzige Anzeichen einer gepunkteten Linie um den Umriss werden die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItem>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [Gewusst wie: Ändern des Layouts eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
