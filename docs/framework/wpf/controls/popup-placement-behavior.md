---
title: Verhalten beim Platzieren von Popups
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 911c2064e34ed8d0a341ffd9a52f852eab677e0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771318"
---
# <a name="popup-placement-behavior"></a>Verhalten beim Platzieren von Popups
Ein <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement zeigt Inhalt in einem separaten Fenster, die über einer Anwendung schwebt. Sie können angeben, der die Position des ein <xref:System.Windows.Controls.Primitives.Popup> relativ zu einem Steuerelement, die Maus oder den Bildschirm mit der <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> Eigenschaften.  Diese Eigenschaften arbeiten zusammen, um die Flexibilität bei der die Position der Angabe der <xref:System.Windows.Controls.Primitives.Popup>.  
  
> [!NOTE]
>  Die <xref:System.Windows.Controls.ToolTip> und <xref:System.Windows.Controls.ContextMenu> Klassen auch definieren diese fünf Eigenschaften und Verhalten sich ähnlich.  

<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>Positionieren von Popups  
 Die Platzierung von eine <xref:System.Windows.Controls.Primitives.Popup> werden können, relativ zu einer <xref:System.Windows.UIElement> oder den gesamten Bildschirm.  Das folgende Beispiel erstellt vier <xref:System.Windows.Controls.Primitives.Popup> Steuerelemente relativ zu einem <xref:System.Windows.UIElement>– in diesem Fall ein Bild. Alle der <xref:System.Windows.Controls.Primitives.Popup> Steuerelemente verfügen über die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> -Eigenschaftensatz auf `image1`, aber jedes <xref:System.Windows.Controls.Primitives.Popup> verfügt über einen anderen Wert für die Placement-Eigenschaft.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 Die folgende Abbildung zeigt das Bild und die <xref:System.Windows.Controls.Primitives.Popup> Steuerelemente  
  
 ![Bild mit vier popupsteuerelementen](./media/popup-placement-behavior/popup-placement-intro.png "Bild mit vier Popups")    
  
 Dieses einfache Beispiel zeigt, wie Sie festlegen der <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> und <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Eigenschaften, jedoch mithilfe von der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> Eigenschaften, Sie haben noch mehr Kontrolle über Where der <xref:System.Windows.Controls.Primitives.Popup> positioniert ist.  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Definitionen von Begriffen: Der Aufbau eines Popups  
 Die folgenden Begriffe sind hilfreich, zu verstehen, wie die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> Eigenschaften aufeinander beziehen und die <xref:System.Windows.Controls.Primitives.Popup>:  
  
- Das Zielobjekt  
  
- Der Zielbereich  
  
- Der Zielursprung  
  
- Der Popupausrichtungspunkt  
  
 Diese Begriffe bieten eine einfache Möglichkeit zum Verweisen auf verschiedene Aspekte der <xref:System.Windows.Controls.Primitives.Popup> und das Steuerelement, das diesem zugeordnet ist.  
  
### <a name="target-object"></a>Das Zielobjekt  
 Die *Zielobjekt* ist das Element, das die <xref:System.Windows.Controls.Primitives.Popup> zugeordnet ist. Wenn die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> -Eigenschaft festgelegt ist, es gibt das Zielobjekt.  Wenn <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> nicht festgelegt ist, und die <xref:System.Windows.Controls.Primitives.Popup> besitzt ein übergeordnetes Element, das übergeordnete Element ist das Zielobjekt.  Liegt keine <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> Wert und kein übergeordnetes Element, es ist kein Zielobjekt, und die <xref:System.Windows.Controls.Primitives.Popup> relativ zum Bildschirm positioniert ist.  
  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Primitives.Popup> , das untergeordnete Element einer <xref:System.Windows.Controls.Canvas>.  Im Beispiel wird nicht festgelegt. die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> Eigenschaft für die <xref:System.Windows.Controls.Primitives.Popup>. Der Standardwert für <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>, sodass die <xref:System.Windows.Controls.Primitives.Popup> wird unterhalb der <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 Die folgende Abbildung zeigt, dass die <xref:System.Windows.Controls.Primitives.Popup> wird relativ dazu positioniert die <xref:System.Windows.Controls.Canvas>.  
  
 ![Popup-Steuerelement ohne PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Popup ohne PlacementTarget.")  

 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Primitives.Popup> , das untergeordnete Element des eine <xref:System.Windows.Controls.Canvas>, dieses Mal jedoch die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> nastaven NA hodnotu `ellipse1`, sodass das Popupfenster unterhalb der <xref:System.Windows.Shapes.Ellipse>.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 Die folgende Abbildung zeigt, dass die <xref:System.Windows.Controls.Primitives.Popup> wird relativ dazu positioniert die <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Relativ zu einer Ellipse platziertes Popup](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Popup mit PlacementTarget")    
  
> [!NOTE]
>  Für <xref:System.Windows.Controls.ToolTip>, der Standardwert von <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>.  Für <xref:System.Windows.Controls.ContextMenu>, der Standardwert von <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>. Diese Werte werden später in „Zusammenwirken der Eigenschaften“ erklärt.  
  
### <a name="target-area"></a>Der Zielbereich  
 Die *Zielbereich* ist ein Bereich, auf dem Bildschirm, der <xref:System.Windows.Controls.Primitives.Popup> relativ ist. In den vorherigen Beispielen die <xref:System.Windows.Controls.Primitives.Popup> orientiert sich die Grenzen des Zielobjekts, aber in einigen Fällen die <xref:System.Windows.Controls.Primitives.Popup> anderen Grenzen ausgerichtet ist auch wenn die <xref:System.Windows.Controls.Primitives.Popup> verfügt über ein Zielobjekt.  Wenn die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> -Eigenschaft festgelegt ist, der Zielbereich unterscheidet sich von der Grenzen des Zielobjekts.  
  
 Das folgende Beispiel erstellt zwei <xref:System.Windows.Controls.Canvas> Objekten, die jeweils mit einem <xref:System.Windows.Shapes.Rectangle> und <xref:System.Windows.Controls.Primitives.Popup>.  In beiden Fällen das Zielobjekt für den <xref:System.Windows.Controls.Primitives.Popup> ist die <xref:System.Windows.Controls.Canvas>. Die <xref:System.Windows.Controls.Primitives.Popup> in der ersten <xref:System.Windows.Controls.Canvas> hat die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> festgelegt ist, mit dessen <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A>, und <xref:System.Windows.Rect.Height%2A> Eigenschaften, die jeweils auf 50, 50, 50 und 100 festgelegt. Die <xref:System.Windows.Controls.Primitives.Popup> in der zweiten <xref:System.Windows.Controls.Canvas> verfügt nicht über die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> festgelegt.  Daher die erste <xref:System.Windows.Controls.Primitives.Popup> befindet sich unten die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> und das zweite <xref:System.Windows.Controls.Primitives.Popup> befindet sich unterhalb der <xref:System.Windows.Controls.Canvas>. Jede <xref:System.Windows.Controls.Canvas> enthält auch eine <xref:System.Windows.Shapes.Rectangle> , besitzt die gleichen Grenzen wie die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> für die erste <xref:System.Windows.Controls.Primitives.Popup>.  Beachten Sie, dass die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> erstellt keine sichtbares Element in der Anwendung, das Beispiel erstellt eine <xref:System.Windows.Shapes.Rectangle> zur Darstellung der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 Die folgende Abbildung zeigt das Ergebnis des vorherigen Beispiels.  
  
 ![Popup mit und ohne PlacementRectangle](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Popup mit und ohne PlacementRectangle.")  

### <a name="target-origin-and-popup-alignment-point"></a>Zielursprung und Popupausrichtungspunkt  
 Der *Zielursprung* und *Popupausrichtungspunkt* sind Bezugspunkte für die Positionierung im Zielbereich und im Popup. Sie können die <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> Eigenschaften für den offset des Popups aus dem Zielbereich.  Die <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> sind relativ zum Zielursprung und den popupausrichtungspunkt. Der Wert des der <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Eigenschaft bestimmt, wo sich der Zielursprung und den popupausrichtungspunkt befinden.  
  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Primitives.Popup> und legt die <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> Eigenschaften auf 20.  Die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (Standardeinstellung), daher wird der Zielursprung die linke obere Ecke des Zielbereichs und der Ausrichtungspunkt wird von der linken oberen Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 Die folgende Abbildung zeigt das Ergebnis des vorherigen Beispiels.  
  
 ![Popupplatzierung mit Zielursprung-Ausrichtungspunkt](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Popup mit HorizontalOffset und VerticalOffset.")    
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>Zusammenwirken der Eigenschaften  
 Die Werte der <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, und <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> müssen zusammen betrachtet werden, um die richtigen Zielbereich, Zielursprung und popupausrichtungspunkt zu ermitteln.  Z. B. wenn der Wert des <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, ist es kein Zielobjekt, das <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ignoriert, und der Zielbereich entspricht den Grenzen des Mauszeigers. Andererseits, wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnete Element bestimmt das Zielobjekt und <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> bestimmt den Zielbereich.  
  
 Die folgende Tabelle beschreibt das Zielobjekt, Zielbereich, Zielursprung und popupausrichtungspunkt und gibt an, ob <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> und <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> werden verwendet, für die einzelnen <xref:System.Windows.Controls.Primitives.PlacementMode> Enumerationswert.  
  
|PlacementMode|Das Zielobjekt|Der Zielbereich|Der Zielursprung|Der Popupausrichtungspunkt|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Dem Bildschirm oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Bildschirm.|Die linke obere Ecke des Zielbereichs|Der linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Dem Bildschirm oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Bildschirm.|Die linke obere Ecke des Zielbereichs|Der linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke untere Ecke des Zielbereichs|Der linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die Mitte des Zielbereichs|Die Mitte des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Definiert die <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|Definiert die <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Der oberen rechten Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Die Grenzen des Mauszeigers <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird ignoriert.|Die linke untere Ecke des Zielbereichs|Der linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Die Grenzen des Mauszeigers <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird ignoriert.|Die linke obere Ecke des Zielbereichs|Der linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Der linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Der linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die rechte obere Ecke des Zielbereichs|Der linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Die linke untere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 Die folgenden Abbildungen zeigen die <xref:System.Windows.Controls.Primitives.Popup>, zeigen Sie den Zielbereich, Zielursprung und popupausrichtungspunkt für jeden <xref:System.Windows.Controls.Primitives.PlacementMode> Wert. In jeder Abbildung ist der Zielbereich Gelb ist, und die <xref:System.Windows.Controls.Primitives.Popup> ist Blau.  
  
 ![Popup mit absolute- oder AbsolutePoint-Platzierung](./media/popup-placement-behavior/popup-placement-absolute.png "die Platzierung ist absolute- oder AbsolutePoint.")    
  
 ![Popup mit Bottom-Platzierung](./media/popup-placement-behavior/popup-placement-bottom.png "die Platzierung ist unten.")   
  
 ![Popup mit Center-Platzierung](./media/popup-placement-behavior/popup-placement-center.png "die Platzierung ist Center.")    
  
 ![Popup mit Left-Platzierung](./media/popup-placement-behavior/popup-placement-left.png "Platzierung ist \"Left\".")   
  
 ![Popup mit Mouse-Platzierung](./media/popup-placement-behavior/popup-placement-mouse.png "Platzierung Maus ist.")  
  
 ![Popup mit MousePoint-Platzierung](./media/popup-placement-behavior/popup-placement-mousepoint.png "Platzierung ist \"MousePoint\".")  
  
 ![Popup mit relative- oder RelativePoint-Platzierung](./media/popup-placement-behavior/popup-placement-relative.png "die Platzierung ist relative- oder RelativePoint.")    
  
 ![Popup mit Right-Platzierung](./media/popup-placement-behavior/popup-placement-right.png "Platzierung ist \"Right\".")    
  
 ![Popup mit Top-Platzierung](./media/popup-placement-behavior/popup-placement-top.png "Platzierung ist \"Top\".")    
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Wenn das Popup auf einen Bildschirmrand trifft  
 Aus Gründen der Sicherheit einer <xref:System.Windows.Controls.Primitives.Popup> kann nicht durch den Bildschirmrand nicht ausgeblendet werden. Eine der folgenden drei Schritte geschieht, wenn die <xref:System.Windows.Controls.Primitives.Popup> auf einen Bildschirmrand trifft:  
  
- Das Popup richtet sich am Bildschirmrand aus, die verdecken würde die <xref:System.Windows.Controls.Primitives.Popup>.  
  
- Das Popup verwendet einen anderen Popupausrichtungspunkt.  
  
- Das Popup verwendet einen anderen Zielursprungs und Popupausrichtungspunkt.  
  
 Diese Optionen werden weiter unten in diesem Abschnitt beschrieben.  
  
 Das Verhalten der <xref:System.Windows.Controls.Primitives.Popup> stößt er ein Bildschirmrand hängt vom Wert von der <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> -Eigenschaft und der Bildschirm das Popup stößt auf Edge. Die folgende Tabelle enthält, das Verhalten bei der <xref:System.Windows.Controls.Primitives.Popup> auf einen Bildschirmrand trifft, für die einzelnen <xref:System.Windows.Controls.Primitives.PlacementMode> Wert.  
  
|PlacementMode|Oberer Rand|Unterer Rand|Linker Rand|Rechter Rand|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Richtet sich am oberen Rand aus|Der popupausrichtungspunkt wird nun der unteren linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Der popupausrichtungspunkt wird nun der oberen rechten Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Richtet sich am oberen Rand aus|Der Zielursprung wird auf der linken oberen Ecke des Zielbereichs geändert und der Ausrichtungspunkt wird nun der unteren linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Der Zielursprung wird in der oberen rechten Ecke des Zielbereichs geändert und der popupausrichtungspunkt auf der linken oberen Ecke des ändert die <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Richtet sich am oberen Rand aus|Der Zielursprung wird auf der linken oberen Ecke des Zielbereichs (die Grenzen des Mauszeigers) geändert und der Ausrichtungspunkt wird nun der unteren linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Richtet sich am oberen Rand aus|Der popupausrichtungspunkt wird nun der unteren linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Der Ausrichtungspunkt wird auf die obere rechte Ecke des Popups geändert.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Richtet sich am oberen Rand aus|Der popupausrichtungspunkt wird nun der unteren linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Der Ausrichtungspunkt wird auf die obere rechte Ecke des Popups geändert.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Der Zielursprung wird auf der linken oberen Ecke des Zielbereichs geändert und der Ausrichtungspunkt wird nun der oberen rechten Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|Der Zielursprung wird in der unteren linken Ecke des Zielbereichs geändert und der popupausrichtungspunkt auf der linken oberen Ecke des ändert die <xref:System.Windows.Controls.Primitives.Popup>. Aktiviert ist, sieht Sie genauso wie beim <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>.|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
  
### <a name="aligning-to-the-screen-edge"></a>Ausrichten am Bildschirmrand  
 Ein <xref:System.Windows.Controls.Primitives.Popup> können Ausrichten am Rand des Bildschirms durch Neupositionieren also die gesamte <xref:System.Windows.Controls.Primitives.Popup> auf dem Bildschirm angezeigt wird.  In diesem Fall unterscheiden sich die Entfernung zwischen dem Zielursprung und den popupausrichtungspunkt von den Werten der <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>. Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, <xref:System.Windows.Controls.Primitives.PlacementMode.Center>, oder <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, <xref:System.Windows.Controls.Primitives.Popup> richtet sich selbst an jedem Bildschirmrand aus.  Nehmen wir beispielsweise an, die eine <xref:System.Windows.Controls.Primitives.Popup> hat <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> festgelegt <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> auf 100 festgelegt.  Wenn dem unteren Rand des Bildschirms ganz oder teilweise verdeckt die <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.Primitives.Popup> automatisch neu positioniert und am unteren Rand des Bildschirms und den vertikalen Abstand zwischen dem Zielursprung und dem Popup-Ausrichtungspunkt ist kleiner als 100. Dies wird in der folgenden Abbildung veranschaulicht.  
  
 ![Popupfenster, das Bildschirmrand ausgerichtet](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Popup richtet sich an den Rand des Bildschirms.")    
  
### <a name="changing-the-popup-alignment-point"></a>Ändern des Popupausrichtungspunkts  
 Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>, oder <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>, ändert sich der popupausrichtungspunkt, wenn das Popup stößt auf den unteren oder rechten Bildschirmrand.  
  
 Die folgende Abbildung zeigt, dass wenn der untere Bildschirmrand ganz oder teilweise verdeckt die <xref:System.Windows.Controls.Primitives.Popup>, der popupausrichtungspunkt wird der unteren linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungspunkt durch unteren Bildschirmrand](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "das Popup stößt auf unteren Rand des Bildschirms, und ändert den popupausrichtungspunkt.")  

 Die folgende Abbildung zeigt, dass wenn der <xref:System.Windows.Controls.Primitives.Popup> wird ausgeblendet, durch den rechten Bildschirmrand, der Ausrichtungspunkt auf der oberen rechten Ecke der ist die <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer popupausrichtungspunkt durch Bildschirmrand](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "das Popup stößt auf rechten Rand des Bildschirms, und ändert den popupausrichtungspunkt.")    
  
 Wenn die <xref:System.Windows.Controls.Primitives.Popup> erkennt den unteren oder rechten Bildschirmrand, der popupausrichtungspunkt wird der unteren rechten Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Ändern des Zielursprungs und des Popupausrichtungspunkts  
 Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right>, oder <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, der Zielursprung und den popupausrichtungspunkt Popup auf ändern, wenn ein bestimmte Bildschirmrand trifft.  Der Bildschirmrand, der die positionsänderung verursacht, hängt die <xref:System.Windows.Controls.Primitives.PlacementMode> Wert.  
  
 Die folgende Abbildung zeigt, dass wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> und <xref:System.Windows.Controls.Primitives.Popup> auf den unteren Bildschirmrand trifft der Zielursprung die linke obere Ecke des Zielbereichs und der Ausrichtungspunkt auf der unteren linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungspunkt durch unteren Bildschirmrand](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "Platzierung ist unten, und das Popup stößt auf den unteren Rand des Bildschirms.")    
  
 Die folgende Abbildung zeigt, dass wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Left> und <xref:System.Windows.Controls.Primitives.Popup> auf der linken Bildschirmrand stößt der Zielursprung ist der oberen rechten Ecke des Zielbereichs und der Ausrichtungspunkt auf der linken oberen Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungspunkt durch linken Bildschirmrand](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "Platzierung ist \"Left\", und das Popup stößt auf den linken Rand des Bildschirms.")  
  
 Die folgende Abbildung zeigt, dass wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Right> und <xref:System.Windows.Controls.Primitives.Popup> auf den rechten Bildschirmrand stößt der Zielursprung die linke obere Ecke des Zielbereichs und der Ausrichtungspunkt auf der oberen rechten Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungspunkt durch rechten Bildschirmrand](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "Platzierung ist \"Right\" und das Popup stößt auf den rechten Rand des Bildschirms.")  

 Die folgende Abbildung zeigt, dass wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Top> und <xref:System.Windows.Controls.Primitives.Popup> auf den oberen Bildschirmrand stößt der Zielursprung die linke obere Ecke des Zielbereichs und der Ausrichtungspunkt auf der linken oberen Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungspunkt an oberer Bildschirmkante](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "Platzierung ist \"Top\", und das Popup stößt auf den oberen Rand des Bildschirms.")  
  
 Die folgende Abbildung zeigt, dass wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> und <xref:System.Windows.Controls.Primitives.Popup> auf den unteren Bildschirmrand trifft der Zielursprung wird von der linken oberen Ecke des Zielbereichs (die Grenzen des Mauszeigers) und der popupausrichtungspunkt die linke obere Ecke der ist die <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungspunkt durch Maus in der Nähe des Bildschirmrands](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "Platzierung wird die Maus und das Popup stößt auf den unteren Rand des Bildschirms.")    
  
### <a name="customizing-popup-placement"></a>Anpassen der Popupplatzierung  
 Sie können die Ausrichtungspunkt für das Ziel Zielursprung und den popupausrichtungspunkt anpassen, indem Sie die Einstellung der <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Eigenschaft <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Definieren Sie dann eine <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> Delegat, der einen Satz von möglichen Platzierungspunkten und Primärachsen (sortiert nach Präferenz) für zurückgibt der <xref:System.Windows.Controls.Primitives.Popup>. Der Punkt, der den größten Teil zeigt die <xref:System.Windows.Controls.Primitives.Popup> ausgewählt ist.  Die Position der <xref:System.Windows.Controls.Primitives.Popup> automatisch angepasst wird, wenn die <xref:System.Windows.Controls.Primitives.Popup> wird ausgeblendet, indem Sie den Rand des Bildschirms. Ein Beispiel finden Sie unter [Angeben einer benutzerdefinierten Popupposition](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>Siehe auch

- [Beispiel für das Platzieren eines Popups](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)
