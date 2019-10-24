---
title: Verhalten beim Platzieren von Popups
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: ca984aa724cf3f076d6073aa8b8179abfb91d26c
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "69951733"
---
# <a name="popup-placement-behavior"></a>Verhalten beim Platzieren von Popups
Ein <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement zeigt Inhalt in einem separaten Fenster an, das über einer Anwendung schwebt. Sie können die Position einer <xref:System.Windows.Controls.Primitives.Popup> relativ zu einem Steuerelement, mit der Maus oder dem Bildschirm angeben, indem Sie die Eigenschaften <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> verwenden.  Diese Eigenschaften arbeiten zusammen, um Ihnen Flexibilität bei der Angabe der Position der <xref:System.Windows.Controls.Primitives.Popup> zu bieten.  
  
> [!NOTE]
> Die Klassen <xref:System.Windows.Controls.ToolTip> und <xref:System.Windows.Controls.ContextMenu> definieren außerdem diese fünf Eigenschaften und Verhalten sich ähnlich.  

<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>Positionieren von Popups  
 Die Platzierung eines <xref:System.Windows.Controls.Primitives.Popup> kann relativ zu einem <xref:System.Windows.UIElement> oder zum gesamten Bildschirm sein.  Im folgenden Beispiel werden vier <xref:System.Windows.Controls.Primitives.Popup>-Steuerelemente erstellt, die relativ zu einem <xref:System.Windows.UIElement> sind – in diesem Fall ein Bild. Für alle <xref:System.Windows.Controls.Primitives.Popup>-Steuerelemente ist die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>-Eigenschaft auf `image1` festgelegt, jede <xref:System.Windows.Controls.Primitives.Popup> hat jedoch einen anderen Wert für die Platzierungs Eigenschaft.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 Die folgende Abbildung zeigt das Bild und die <xref:System.Windows.Controls.Primitives.Popup> Steuerelemente  
  
 ![Bild mit vier Popup-Steuerelementen](./media/popup-placement-behavior/popup-placement-intro.png "Bild mit vier Popups")    
  
 In diesem einfachen Beispiel wird veranschaulicht, wie die Eigenschaften <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> und <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> festgelegt werden. mithilfe der Eigenschaften <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> können Sie jedoch noch besser steuern, wo die <xref:System.Windows.Controls.Primitives.Popup> positioniert ist.  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Begriffsdefinition: der Aufbau eines Popups  
 Die folgenden Begriffe sind hilfreich, um zu verstehen, wie sich die Eigenschaften <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> miteinander und <xref:System.Windows.Controls.Primitives.Popup> zusammensetzen:  
  
- Das Zielobjekt  
  
- Der Zielbereich  
  
- Der Zielursprung  
  
- Der Popupausrichtungspunkt  
  
 Diese Begriffe stellen eine bequeme Möglichkeit dar, auf verschiedene Aspekte der <xref:System.Windows.Controls.Primitives.Popup> und das Steuerelement zu verweisen, dem es zugeordnet ist.  
  
### <a name="target-object"></a>Das Zielobjekt  
 Das *Zielobjekt* ist das Element, dem die <xref:System.Windows.Controls.Primitives.Popup> zugeordnet ist. Wenn die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>-Eigenschaft festgelegt ist, wird das Zielobjekt angegeben.  Wenn <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> nicht festgelegt ist und die <xref:System.Windows.Controls.Primitives.Popup> über ein übergeordnetes Element verfügt, ist das übergeordnete Objekt das Zielobjekt.  Wenn kein <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> Wert und kein übergeordnetes Element vorhanden ist, gibt es kein Zielobjekt, und die <xref:System.Windows.Controls.Primitives.Popup> wird relativ zum Bildschirm positioniert.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.Primitives.Popup> erstellt, die das untergeordnete Element eines <xref:System.Windows.Controls.Canvas> ist.  Im Beispiel wird die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>-Eigenschaft für den <xref:System.Windows.Controls.Primitives.Popup> nicht festgelegt. Der Standardwert für <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>, sodass der <xref:System.Windows.Controls.Primitives.Popup> unter dem <xref:System.Windows.Controls.Canvas> angezeigt wird.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 In der folgenden Abbildung wird gezeigt, dass der <xref:System.Windows.Controls.Primitives.Popup> relativ zum <xref:System.Windows.Controls.Canvas> positioniert ist.  
  
 ![Popup-Steuerelement ohne PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Popup ohne PlacementTarget.")  

 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.Primitives.Popup> erstellt, die das untergeordnete Element eines <xref:System.Windows.Controls.Canvas> ist, aber dieses Mal wird der <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> auf `ellipse1` festgelegt, sodass das Popup unter dem <xref:System.Windows.Shapes.Ellipse> angezeigt wird.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 In der folgenden Abbildung wird gezeigt, dass der <xref:System.Windows.Controls.Primitives.Popup> relativ zum <xref:System.Windows.Shapes.Ellipse> positioniert ist.  
  
 ![Relativ zu einer Ellipse platziertes Popup](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Popup mit PlacementTarget")    
  
> [!NOTE]
> Für <xref:System.Windows.Controls.ToolTip> ist der Standardwert <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>.  Für <xref:System.Windows.Controls.ContextMenu> ist der Standardwert <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>. Diese Werte werden später in „Zusammenwirken der Eigenschaften“ erklärt.  
  
### <a name="target-area"></a>Der Zielbereich  
 Der *Zielbereich* ist der Bereich auf dem Bildschirm, zu dem der <xref:System.Windows.Controls.Primitives.Popup> relativ ist. In den vorherigen Beispielen wird der <xref:System.Windows.Controls.Primitives.Popup> an den Begrenzungen des Zielobjekts ausgerichtet, aber in einigen Fällen wird die <xref:System.Windows.Controls.Primitives.Popup> an anderen Begrenzungen ausgerichtet, auch wenn die <xref:System.Windows.Controls.Primitives.Popup> ein Zielobjekt aufweist.  Wenn die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>-Eigenschaft festgelegt wird, unterscheidet sich der Zielbereich von den Begrenzungen des Zielobjekts.  
  
 Im folgenden Beispiel werden zwei <xref:System.Windows.Controls.Canvas>-Objekte erstellt, die jeweils eine <xref:System.Windows.Shapes.Rectangle> und eine <xref:System.Windows.Controls.Primitives.Popup> enthalten.  In beiden Fällen ist das Zielobjekt für den <xref:System.Windows.Controls.Primitives.Popup> die <xref:System.Windows.Controls.Canvas>. Der <xref:System.Windows.Controls.Primitives.Popup> im ersten <xref:System.Windows.Controls.Canvas> verfügt über die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, deren <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A> und <xref:System.Windows.Rect.Height%2A> Eigenschaften auf 50, 50, 50 und 100 festgelegt sind. Der <xref:System.Windows.Controls.Primitives.Popup> in der zweiten <xref:System.Windows.Controls.Canvas> ist nicht <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> festgelegt.  Demzufolge wird der erste <xref:System.Windows.Controls.Primitives.Popup> unterhalb der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> positioniert, und der zweite <xref:System.Windows.Controls.Primitives.Popup> wird unter dem <xref:System.Windows.Controls.Canvas> positioniert. Jede <xref:System.Windows.Controls.Canvas> enthält auch eine <xref:System.Windows.Shapes.Rectangle>, die die gleichen Begrenzungen wie die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> für den ersten <xref:System.Windows.Controls.Primitives.Popup> aufweist.  Beachten Sie, dass das <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> kein sichtbares Element in der Anwendung erstellt. im Beispiel wird eine <xref:System.Windows.Shapes.Rectangle> erstellt, um die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> darzustellen.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 Die folgende Abbildung zeigt das Ergebnis des vorherigen Beispiels.  
  
 ![Popup mit und ohne PlacementRectangle](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Popup mit und ohne placementrechteck.")  

### <a name="target-origin-and-popup-alignment-point"></a>Zielursprung und Popupausrichtungspunkt  
 Der *Zielursprung* und *Popupausrichtungspunkt* sind Bezugspunkte für die Positionierung im Zielbereich und im Popup. Sie können die Eigenschaften "<xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>" und "<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>" verwenden, um das Popup aus dem Zielbereich zu versetzen.  Die <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> sind relativ zum Ziel Ursprung und zum Popup Ausrichtungs Punkt. Der Wert der <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>-Eigenschaft bestimmt, wo sich der Ziel Ursprung und der Popup Ausrichtungs Punkt befinden.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.Primitives.Popup> erstellt und die Eigenschaften <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> auf 20 festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>-Eigenschaft ist auf <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (Standardeinstellung) festgelegt, sodass der Ziel Ursprung die linke untere Ecke des Zielbereichs und der Popup Ausrichtungs Punkt die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup> ist.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 Die folgende Abbildung zeigt das Ergebnis des vorherigen Beispiels.  
  
 ![Popupplatzierung mit Zielursprung-Ausrichtungspunkt](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Popup mit HorizontalOffset und VerticalOffset.")    
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>Zusammenwirken der Eigenschaften  
 Die Werte <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> und <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> müssen in Erwägung gezogen werden, um den richtigen Zielbereich, den Ziel Ursprung und den Popup Ausrichtungs Punkt zu ermitteln.  Wenn der Wert von <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> z. b. <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> ist, gibt es kein Zielobjekt, das <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird ignoriert, und der Zielbereich ist die Begrenzungen des Mauszeigers. Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> hingegen <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> ist, bestimmt die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder das übergeordnete Objekt das Zielobjekt, und <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> bestimmt den Zielbereich.  
  
 Die folgende Tabelle beschreibt das Zielobjekt, den Zielbereich, den Ziel Ursprung und den Popup Ausrichtungs Punkt und gibt an, ob für jeden <xref:System.Windows.Controls.Primitives.PlacementMode> Enumerationswert <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> und <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> verwendet werden.  
  
|PlacementMode|Das Zielobjekt|Der Zielbereich|Der Zielursprung|Der Popupausrichtungspunkt|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Der Bildschirm, oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn er festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Bildschirm.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Der Bildschirm, oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn er festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Bildschirm.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke untere Ecke des Zielbereichs|Die linke obere Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die Mitte des Zielbereichs|Der Mittelpunkt der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Definiert durch die <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|Definiert durch die <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Die obere rechte Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Die Grenzen des Mauszeigers <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird ignoriert.|Die linke untere Ecke des Zielbereichs|Die linke obere Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Die Grenzen des Mauszeigers <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird ignoriert.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die rechte obere Ecke des Zielbereichs|Die linke obere Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Die linke untere Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 Die folgenden Abbildungen zeigen die <xref:System.Windows.Controls.Primitives.Popup>, den Zielbereich, den Ziel Ursprung und den Popup Ausrichtungs Punkt für jeden <xref:System.Windows.Controls.Primitives.PlacementMode> Wert. Der Zielbereich in jeder Abbildung ist gelb, und die <xref:System.Windows.Controls.Primitives.Popup> ist blau.  
  
 ![Popup mit Absolute- oder AbsolutePoint-Platzierung](./media/popup-placement-behavior/popup-placement-absolute.png "Die Platzierung ist absolut oder AbsolutePoint.")    
  
 ![Popup mit Bottom-Platzierung](./media/popup-placement-behavior/popup-placement-bottom.png "Die Platzierung ist "Bottom".")   
  
 ![Popup mit Center-Platzierung](./media/popup-placement-behavior/popup-placement-center.png "Die Platzierung ist "Center".")    
  
 ![Popup mit Left-Platzierung](./media/popup-placement-behavior/popup-placement-left.png "Die Platzierung ist "Left".")   
  
 ![Popup mit Mouse-Platzierung](./media/popup-placement-behavior/popup-placement-mouse.png "Die Platzierung ist "Mouse".")  
  
 ![Popup mit MousePoint-Platzierung](./media/popup-placement-behavior/popup-placement-mousepoint.png "Die Platzierung ist "moustipoint".")  
  
 ![Popup mit Relative- oder RelativePoint-Platzierung](./media/popup-placement-behavior/popup-placement-relative.png "Die Platzierung ist "relative" oder "RelativePoint".")    
  
 ![Popup mit Right-Platzierung](./media/popup-placement-behavior/popup-placement-right.png "Die Platzierung ist "Right".")    
  
 ![Popup mit Top-Platzierung](./media/popup-placement-behavior/popup-placement-top.png "Die Platzierung ist "Top".")    
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Wenn das Popup auf einen Bildschirmrand trifft  
 Aus Sicherheitsgründen kann eine <xref:System.Windows.Controls.Primitives.Popup> nicht am Rand eines Bildschirms ausgeblendet werden. Eine der folgenden drei Dinge tritt auf, wenn das <xref:System.Windows.Controls.Primitives.Popup> einen Bildschirmrand findet:  
  
- Das Popup richtet sich am Bildschirmrand neu, der die <xref:System.Windows.Controls.Primitives.Popup> verdecken würde.  
  
- Das Popup verwendet einen anderen Popupausrichtungspunkt.  
  
- Das Popup verwendet einen anderen Zielursprungs und Popupausrichtungspunkt.  
  
 Diese Optionen werden weiter unten in diesem Abschnitt beschrieben.  
  
 Das Verhalten der <xref:System.Windows.Controls.Primitives.Popup>, wenn ein Bildschirmrand gefunden wird, hängt vom Wert der Eigenschaft <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> und von dem Bildschirmrand ab, auf den das Popup trifft. In der folgenden Tabelle wird das Verhalten zusammengefasst, wenn die <xref:System.Windows.Controls.Primitives.Popup> für jeden <xref:System.Windows.Controls.Primitives.PlacementMode> Wert auf einen Bildschirmrand stößt.  
  
|PlacementMode|Oberer Rand|Unterer Rand|Linker Rand|Rechter Rand|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Richtet sich am oberen Rand aus|Der Popup Ausrichtungs Punkt ändert sich in die linke untere Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Der Popup Ausrichtungs Punkt ändert sich in die obere rechte Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Richtet sich am oberen Rand aus|Der Ziel Ursprung wird in die linke obere Ecke des Zielbereichs geändert, und der Popup Ausrichtungs Punkt ändert sich in der linken unteren Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Der Ziel Ursprung ändert sich in die rechte obere Ecke des Zielbereichs, und der Popup Ausrichtungs Punkt ändert sich in die linke obere Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Richtet sich am oberen Rand aus|Der Ziel Ursprung ändert sich in die linke obere Ecke des Zielbereichs (die Begrenzungen des Mauszeigers), und der Popup Ausrichtungs Punkt ändert sich in die linke untere Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Richtet sich am oberen Rand aus|Der Popup Ausrichtungs Punkt ändert sich in die linke untere Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Der Ausrichtungspunkt wird auf die obere rechte Ecke des Popups geändert.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Richtet sich am oberen Rand aus|Der Popup Ausrichtungs Punkt ändert sich in die linke untere Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Der Ausrichtungspunkt wird auf die obere rechte Ecke des Popups geändert.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Der Ziel Ursprung wird in die linke obere Ecke des Zielbereichs geändert, und der Popup Ausrichtungs Punkt ändert sich in die obere rechte Ecke der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|Der Ziel Ursprung wird in die linke untere Ecke des Zielbereichs geändert, und der Popup Ausrichtungs Punkt ändert sich in die linke obere Ecke der <xref:System.Windows.Controls.Primitives.Popup>. Dies ist das gleiche wie bei der <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>.|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
  
### <a name="aligning-to-the-screen-edge"></a>Ausrichten am Bildschirmrand  
 Eine <xref:System.Windows.Controls.Primitives.Popup> kann am Bildschirmrand ausgerichtet werden, indem Sie sich selbst neu positioniert, sodass die gesamte <xref:System.Windows.Controls.Primitives.Popup> auf dem Bildschirm sichtbar ist.  In diesem Fall kann sich der Abstand zwischen dem Ziel Ursprung und dem Popup Ausrichtungs Punkt von den Werten <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> unterscheiden. Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, <xref:System.Windows.Controls.Primitives.PlacementMode.Center> oder <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> ist, richtet sich der <xref:System.Windows.Controls.Primitives.Popup> an jedem Bildschirmrand.  Nehmen Sie beispielsweise an, dass für ein <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> auf <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> auf 100 festgelegt ist.  Wenn der untere Rand des Bildschirms den gesamten <xref:System.Windows.Controls.Primitives.Popup> oder einen Teil davon verbirgt, wird der <xref:System.Windows.Controls.Primitives.Popup> am unteren Bildschirmrand neu positioniert, und der vertikale Abstand zwischen dem Ziel Ursprung und dem Popup Ausrichtungs Punkt ist kleiner als 100. Dies wird in der folgenden Abbildung veranschaulicht.  
  
 ![Am Bildschirmrand ausgerichtetes Popup](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Popup richtet sich am Bildschirmrand aus.")    
  
### <a name="changing-the-popup-alignment-point"></a>Ändern des Popupausrichtungspunkts  
 Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint> oder <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint> ist, ändert sich der Popup Ausrichtungs Punkt, wenn das Popup auf den unteren oder rechten Bildschirmrand trifft.  
  
 In der folgenden Abbildung wird veranschaulicht, dass der Popup Ausrichtungs Punkt die untere linke Ecke der <xref:System.Windows.Controls.Primitives.Popup> ist, wenn der untere Bildschirmrand die <xref:System.Windows.Controls.Primitives.Popup> oder einen Teil des ausblendet.  
  
 ![Neuer Ausrichtungspunkt durch unteren Bildschirmrand](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "Popup stößt auf den unteren Rand des Bildschirms und ändert den Popup Ausrichtungs Punkt.")  

 In der folgenden Abbildung wird veranschaulicht, dass der Popup Ausrichtungs Punkt die obere rechte Ecke der <xref:System.Windows.Controls.Primitives.Popup> ist, wenn die <xref:System.Windows.Controls.Primitives.Popup> vom rechten Bildschirmrand ausgeblendet wird.  
  
 ![Neuer Popupausrichtungspunkt durch Bildschirmrand](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "Popup trifft den rechten Rand des Bildschirms und ändert den Popup Ausrichtungs Punkt.")    
  
 Wenn das <xref:System.Windows.Controls.Primitives.Popup> den unteren und rechten Bildschirmrand trifft, ist der Popup Ausrichtungs Punkt die untere rechte Ecke des <xref:System.Windows.Controls.Primitives.Popup>.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Ändern des Zielursprungs und des Popupausrichtungspunkts  
 Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right> oder <xref:System.Windows.Controls.Primitives.PlacementMode.Top> ist, ändern sich der Ziel Ursprung und der Popup Ausrichtungs Punkt, wenn eine bestimmte Bildschirm Kante erreicht wird.  Der Bildschirmrand, der bewirkt, dass die Position geändert wird, hängt vom <xref:System.Windows.Controls.Primitives.PlacementMode> Wert ab.  
  
 In der folgenden Abbildung wird veranschaulicht, dass der Ziel Ursprung die linke obere Ecke des Zielbereichs und der Popup Ausrichtungs Punkt die untere linke Ecke der <xref:System.Windows.Controls.Primitives.Popup> ist, wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> ist und die <xref:System.Windows.Controls.Primitives.Popup> auf den unteren Bildschirmrand stößt.  
  
 ![Neuer Ausrichtungspunkt durch unteren Bildschirmrand](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "Die Platzierung erfolgt unten, und das Popup stößt auf den unteren Rand des Bildschirms.")    
  
 In der folgenden Abbildung wird veranschaulicht, dass wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Left> und der <xref:System.Windows.Controls.Primitives.Popup> den linken Bildschirmrand trifft, der Ziel Ursprung die obere rechte Ecke des Zielbereichs und der Popup Ausrichtungs Punkt die linke obere Ecke der <xref:System.Windows.Controls.Primitives.Popup> ist.  
  
 ![Neuer Ausrichtungspunkt durch linken Bildschirmrand](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "Die Platzierung ist "Left", und das Popup stößt auf den linken Rand des Bildschirms.")  
  
 In der folgenden Abbildung wird veranschaulicht, dass der Ziel Ursprung die linke obere Ecke des Zielbereichs und der Popup Ausrichtungs Punkt die obere rechte Ecke der <xref:System.Windows.Controls.Primitives.Popup> ist, wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Right> ist und die <xref:System.Windows.Controls.Primitives.Popup> auf den rechten Bildschirmrand trifft.  
  
 ![Neuer Ausrichtungspunkt durch rechten Bildschirmrand](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "Die Platzierung ist "Right", und das Popup stößt auf den rechten Bildschirmrand.")  

 In der folgenden Abbildung wird veranschaulicht, dass wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Top> und die <xref:System.Windows.Controls.Primitives.Popup> auf den oberen Bildschirmrand stößt, der Ziel Ursprung die linke untere Ecke des Zielbereichs und der Popup Ausrichtungs Punkt die linke obere Ecke der <xref:System.Windows.Controls.Primitives.Popup> ist.  
  
 ![Neuer Ausrichtungspunkt durch obere Bildschirmrand](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "Die Platzierung ist "Top", und das Popup stößt auf den oberen Rand des Bildschirms.")  
  
 In der folgenden Abbildung wird veranschaulicht, dass der Ziel Ursprung die linke obere Ecke des Zielbereichs (die Begrenzungen des Mauszeigers) und der Popup Ausrichtungs Punkt die untere linke Ecke ist, wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> ist und die <xref:System.Windows.Controls.Primitives.Popup> auf den unteren Bildschirmrand trifft. Ecke der <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungspunkt durch Maus in der Nähe des Bildschirmrands](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "Die Platzierung ist "Mouse", und das Popup stößt auf den unteren Rand des Bildschirms.")    
  
### <a name="customizing-popup-placement"></a>Anpassen der Popup-Platzierung  
 Sie können den Ziel Ursprung und den Popup Ausrichtungs Punkt anpassen, indem Sie die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>-Eigenschaft auf <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> festlegen. Definieren Sie dann einen <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> Delegaten, der einen Satz möglicher Platzierungs Punkte und primäre Achsen (in der bevorzugten Reihenfolge) für die <xref:System.Windows.Controls.Primitives.Popup> zurückgibt. Der Punkt, der den größten Teil des <xref:System.Windows.Controls.Primitives.Popup> anzeigt, wird ausgewählt.  Die Position des <xref:System.Windows.Controls.Primitives.Popup> wird automatisch angepasst, wenn der <xref:System.Windows.Controls.Primitives.Popup> vom Bildschirmrand ausgeblendet wird. Ein Beispiel finden Sie unter [Angeben einer benutzerdefinierten Popup-Position](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>Siehe auch

- [Beispiel für das Platzieren eines Popups](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)
