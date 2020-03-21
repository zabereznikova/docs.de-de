---
title: Verhalten beim Platzieren von Popups
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 063b309ebaf0944787ce40725eed250e59f09dff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176759"
---
# <a name="popup-placement-behavior"></a>Verhalten beim Platzieren von Popups
Ein <xref:System.Windows.Controls.Primitives.Popup> Steuerelement zeigt Inhalt in einem separaten Fenster an, das über einer Anwendung schwebt. Sie können die Position <xref:System.Windows.Controls.Primitives.Popup> eines Relativen zu einem Steuerelement, der <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>Maus <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>oder <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> dem Bildschirm mithilfe der Eigenschaften , , , und und anzeigen angeben.  Diese Eigenschaften arbeiten zusammen, um Ihnen Flexibilität <xref:System.Windows.Controls.Primitives.Popup>bei der Angabe der Position der zu geben.  
  
> [!NOTE]
> Die <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ContextMenu> und-Klassen definieren auch diese fünf Eigenschaften und verhalten sich ähnlich.  

<a name="Positioning"></a>
## <a name="positioning-the-popup"></a>Positionieren von Popups  
 Die Platzierung <xref:System.Windows.Controls.Primitives.Popup> eines kann relativ <xref:System.Windows.UIElement> zu einem oder zum gesamten Bildschirm sein.  Im folgenden Beispiel <xref:System.Windows.Controls.Primitives.Popup> werden vier Steuerelemente erstellt, die relativ zu einem <xref:System.Windows.UIElement>–in diesem Fall einem Bild , sind. Für alle <xref:System.Windows.Controls.Primitives.Popup> Steuerelemente <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> ist `image1`die Eigenschaft <xref:System.Windows.Controls.Primitives.Popup> auf festgelegt, aber jedes Steuerelement hat einen anderen Wert für die Platzierungseigenschaft.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 Die folgende Abbildung zeigt <xref:System.Windows.Controls.Primitives.Popup> das Bild und die  
  
 ![Bild mit vier Popup-Steuerelementen](./media/popup-placement-behavior/popup-placement-intro.png "Bild mit vier Popups")
  
 In diesem einfachen Beispiel <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> veranschaulicht, wie <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>die <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>und-Eigenschaften festgelegt werden, aber durch die Verwendung der , und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> der Eigenschaften haben Sie noch mehr Kontrolle darüber, wo der <xref:System.Windows.Controls.Primitives.Popup> positioniert ist.  
  
<a name="Definitions"></a>
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Begriffsdefinition: der Aufbau eines Popups  
 Die folgenden Begriffe sind nützlich, um <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>zu <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> verstehen, wie die <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, und Eigenschaften zueinander und die :  
  
- Zielobjekt  
  
- Der Zielbereich  
  
- Der Zielursprung  
  
- Der Popupausrichtungspunkt  
  
 Diese Begriffe bieten eine bequeme Möglichkeit, <xref:System.Windows.Controls.Primitives.Popup> auf verschiedene Aspekte der und der Steuerung, die es zugeordnet ist, zu verweisen.  
  
### <a name="target-object"></a>Zielobjekt  
 Das *Zielobjekt* ist das <xref:System.Windows.Controls.Primitives.Popup> Element, dem der zugeordnet ist. Wenn <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> die Eigenschaft festgelegt ist, gibt sie das Zielobjekt an.  Wenn <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> nicht festgelegt ist <xref:System.Windows.Controls.Primitives.Popup> und das über ein übergeordnetes Element verfügt, ist das übergeordnete Objekt das Zielobjekt.  Wenn kein <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> Wert und kein übergeordnetes Objekt vorhanden <xref:System.Windows.Controls.Primitives.Popup> ist, gibt es kein Zielobjekt, und das wird relativ zum Bildschirm positioniert.  
  
 Im folgenden Beispiel <xref:System.Windows.Controls.Primitives.Popup> wird ein erstellt, das das untergeordnete Element einer <xref:System.Windows.Controls.Canvas>ist.  Im Beispiel wird <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> die Eigenschaft <xref:System.Windows.Controls.Primitives.Popup>nicht für die festgelegt. Der Standardwert <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>für ist <xref:System.Windows.Controls.Primitives.Popup> , <xref:System.Windows.Controls.Canvas>also wird der unter dem angezeigt.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 Die folgende Abbildung <xref:System.Windows.Controls.Primitives.Popup> zeigt, dass <xref:System.Windows.Controls.Canvas>der relativ zum positioniert ist.  
  
 ![Popup-Steuerelement ohne PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Popup ohne PlacementTarget.")  

 Im folgenden Beispiel <xref:System.Windows.Controls.Primitives.Popup> wird ein erstellt, das das untergeordnete Element einer <xref:System.Windows.Controls.Canvas>ist, aber dieses Mal ist die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> auf `ellipse1`festgelegt, sodass das Popup unter dem <xref:System.Windows.Shapes.Ellipse>angezeigt wird.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 Die folgende Abbildung <xref:System.Windows.Controls.Primitives.Popup> zeigt, dass <xref:System.Windows.Shapes.Ellipse>der relativ zum positioniert ist.  
  
 ![Relativ zu einer Ellipse platziertes Popup](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Popup mit PlacementTarget")
  
> [!NOTE]
> Für <xref:System.Windows.Controls.ToolTip>ist der <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Standardwert von <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>.  Für <xref:System.Windows.Controls.ContextMenu>ist der <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Standardwert von <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>. Diese Werte werden später in „Zusammenwirken der Eigenschaften“ erklärt.  
  
### <a name="target-area"></a>Der Zielbereich  
 Der *Zielbereich* ist der Bereich <xref:System.Windows.Controls.Primitives.Popup> auf dem Bildschirm, zu dem der relativ ist. In den vorherigen <xref:System.Windows.Controls.Primitives.Popup> Beispielen wird der an den Grenzen des Zielobjekts <xref:System.Windows.Controls.Primitives.Popup> ausgerichtet, in einigen Fällen jedoch <xref:System.Windows.Controls.Primitives.Popup> an anderen Grenzen ausgerichtet, auch wenn der über ein Zielobjekt verfügt.  Wenn <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> die Eigenschaft festgelegt ist, unterscheidet sich der Zielbereich von den Grenzen des Zielobjekts.  
  
 Im folgenden Beispiel <xref:System.Windows.Controls.Canvas> werden zwei Objekte <xref:System.Windows.Shapes.Rectangle> erstellt, von denen jedes eine und eine <xref:System.Windows.Controls.Primitives.Popup>enthält.  In beiden Fällen ist das <xref:System.Windows.Controls.Primitives.Popup> Zielobjekt für die . <xref:System.Windows.Controls.Canvas> Der <xref:System.Windows.Controls.Primitives.Popup> im <xref:System.Windows.Controls.Canvas> ersten <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> hat den <xref:System.Windows.Rect.X%2A>Satz <xref:System.Windows.Rect.Y%2A> <xref:System.Windows.Rect.Width%2A>mit <xref:System.Windows.Rect.Height%2A> , , und eigenschaften auf 50, 50, 50 und 100 festgelegt. Der <xref:System.Windows.Controls.Primitives.Popup> in <xref:System.Windows.Controls.Canvas> der zweiten <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> hat nicht das Set.  Als Ergebnis wird <xref:System.Windows.Controls.Primitives.Popup> die erste <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> unterhalb der <xref:System.Windows.Controls.Primitives.Popup> und die <xref:System.Windows.Controls.Canvas>zweite unter der positioniert. Jede <xref:System.Windows.Controls.Canvas> enthält <xref:System.Windows.Shapes.Rectangle> auch eine, die die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> gleichen <xref:System.Windows.Controls.Primitives.Popup>Grenzen wie die für die erste hat.  Beachten Sie, dass der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> kein sichtbares Element in der Anwendung erstellt. im Beispiel <xref:System.Windows.Shapes.Rectangle> wird ein <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>erstellt, um die darzustellen.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 Die folgende Abbildung zeigt das Ergebnis des vorherigen Beispiels.  
  
 ![Popup mit und ohne PlacementRectangle](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Popup mit und ohne PlacementRectangle.")  

### <a name="target-origin-and-popup-alignment-point"></a>Zielursprung und Popupausrichtungspunkt  
 Der *Zielursprung* und *Popupausrichtungspunkt* sind Bezugspunkte für die Positionierung im Zielbereich und im Popup. Sie können <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> die <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> und Eigenschaften verwenden, um das Popup aus dem Zielbereich zu versetzen.  Die <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> und sind relativ zum Zielursprung und dem Popupausrichtungspunkt. Der Wert <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> der Eigenschaft bestimmt, wo sich der Zielursprung und der Popupausrichtungspunkt befinden.  
  
 Im folgenden Beispiel <xref:System.Windows.Controls.Primitives.Popup> wird <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> a <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> erstellt und die und-Eigenschaften auf 20 festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Eigenschaft ist <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> auf (Standardeinstellung) festgelegt, sodass der Zielursprung die untere linke Ecke des Zielbereichs <xref:System.Windows.Controls.Primitives.Popup>und der Popupausrichtungspunkt die obere linke Ecke des ist.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 Die folgende Abbildung zeigt das Ergebnis des vorherigen Beispiels.  
  
 ![Popupplatzierung mit Zielursprung-Ausrichtungspunkt](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Popup mit HorizontalOffset und VerticalOffset.")
  
<a name="How"></a>
## <a name="how-the-properties-work-together"></a>Zusammenwirken der Eigenschaften  
 Die Werte <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>von <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> , und müssen zusammen betrachtet werden, um den richtigen Zielbereich, Zielursprung und Popupausrichtungspunkt zu ermitteln.  Wenn z. B. <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>der Wert von ist <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , gibt es kein Zielobjekt, der wird ignoriert, und der Zielbereich ist die Begrenzung des Mauszeigers. Auf der anderen <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Seite, wenn ist <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, bestimmt das oder das <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> übergeordnete Objekt das Zielobjekt und <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> bestimmt den Zielbereich.  
  
 In der folgenden Tabelle werden das Zielobjekt, der Zielbereich, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Zielursprung <xref:System.Windows.Controls.Primitives.PlacementMode> und der Popupausrichtungspunkt beschrieben und gibt an, ob und ob diese für jeden Enumerationswert verwendet werden.  
  
|PlacementMode|Zielobjekt|Der Zielbereich|Der Zielursprung|Der Popupausrichtungspunkt|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Nicht zutreffend <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Der Bildschirm, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> oder wenn er eingestellt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Bildschirm.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke <xref:System.Windows.Controls.Primitives.Popup>der .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Nicht zutreffend <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Der Bildschirm, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> oder wenn er eingestellt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Bildschirm.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke <xref:System.Windows.Controls.Primitives.Popup>der .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>oder Elternteil.|Das Zielobjekt, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> oder wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke untere Ecke des Zielbereichs|Die linke obere Ecke <xref:System.Windows.Controls.Primitives.Popup>der .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>oder Elternteil.|Das Zielobjekt, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> oder wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die Mitte des Zielbereichs|Das Zentrum <xref:System.Windows.Controls.Primitives.Popup>der .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>oder Elternteil.|Das Zielobjekt, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> oder wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Definiert durch <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>die .|Definiert durch <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>die .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>oder Elternteil.|Das Zielobjekt, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> oder wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Die obere rechte Ecke <xref:System.Windows.Controls.Primitives.Popup>der .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Nicht zutreffend <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Die Grenzen des Mauszeigers <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird ignoriert.|Die linke untere Ecke des Zielbereichs|Die linke obere Ecke <xref:System.Windows.Controls.Primitives.Popup>der .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Nicht zutreffend <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Die Grenzen des Mauszeigers <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird ignoriert.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke <xref:System.Windows.Controls.Primitives.Popup>der .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>oder Elternteil.|Das Zielobjekt, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> oder wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke <xref:System.Windows.Controls.Primitives.Popup>der .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>oder Elternteil.|Das Zielobjekt, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> oder wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke <xref:System.Windows.Controls.Primitives.Popup>der .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>oder Elternteil.|Das Zielobjekt, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> oder wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die rechte obere Ecke des Zielbereichs|Die linke obere Ecke <xref:System.Windows.Controls.Primitives.Popup>der .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>oder Elternteil.|Das Zielobjekt, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> oder wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Die untere linke <xref:System.Windows.Controls.Primitives.Popup>Ecke der .|  
  
 Die folgenden Abbildungen <xref:System.Windows.Controls.Primitives.Popup>zeigen den , Zielbereich, Zielursprung <xref:System.Windows.Controls.Primitives.PlacementMode> und Popupausrichtungspunkt für jeden Wert. In jeder Abbildung ist der Zielbereich <xref:System.Windows.Controls.Primitives.Popup> gelb und der blau.  
  
 ![Popup mit Absolute- oder AbsolutePoint-Platzierung](./media/popup-placement-behavior/popup-placement-absolute.png "Platzierung ist Absolute oder AbsolutePoint.")
  
 ![Popup mit Bottom-Platzierung](./media/popup-placement-behavior/popup-placement-bottom.png "Platzierung ist Bottom.")
  
 ![Popup mit Center-Platzierung](./media/popup-placement-behavior/popup-placement-center.png "Platzierung ist Center.")
  
 ![Popup mit Left-Platzierung](./media/popup-placement-behavior/popup-placement-left.png "Platzierung ist Links.")
  
 ![Popup mit Mouse-Platzierung](./media/popup-placement-behavior/popup-placement-mouse.png "Platzierung ist Maus.")  
  
 ![Popup mit MousePoint-Platzierung](./media/popup-placement-behavior/popup-placement-mousepoint.png "Platzierung ist MousePoint.")  
  
 ![Popup mit Relative- oder RelativePoint-Platzierung](./media/popup-placement-behavior/popup-placement-relative.png "Platzierung ist Relative oder RelativePoint.")
  
 ![Popup mit Right-Platzierung](./media/popup-placement-behavior/popup-placement-right.png "Platzierung ist richtig.")
  
 ![Popup mit Top-Platzierung](./media/popup-placement-behavior/popup-placement-top.png "Platzierung ist Top.")
  
<a name="When"></a>
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Wenn das Popup auf einen Bildschirmrand trifft  
 Aus Sicherheitsgründen <xref:System.Windows.Controls.Primitives.Popup> kann eine nicht am Rand eines Bildschirms ausgeblendet werden. Eines der folgenden drei Dinge <xref:System.Windows.Controls.Primitives.Popup> geschieht, wenn der auf eine Bildschirmkante trifft:  
  
- Das Popup richtet sich entlang der Bildschirmkante <xref:System.Windows.Controls.Primitives.Popup>neu aus, wodurch die verdeckt wird.  
  
- Das Popup verwendet einen anderen Popupausrichtungspunkt.  
  
- Das Popup verwendet einen anderen Zielursprungs und Popupausrichtungspunkt.  
  
 Diese Optionen werden weiter unten in diesem Abschnitt beschrieben.  
  
 Das Verhalten <xref:System.Windows.Controls.Primitives.Popup> der, wenn sie auf eine Bildschirmkante trifft, hängt vom Wert der <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Eigenschaft und der Bildschirmkante ab, auf die das Popup trifft. In der folgenden Tabelle wird <xref:System.Windows.Controls.Primitives.Popup> das Verhalten zusammengefasst, wenn der für jeden <xref:System.Windows.Controls.Primitives.PlacementMode> Wert eine Bildschirmkante findet.  
  
|PlacementMode|Oberer Rand|Unterer Rand|Linker Rand|Rechter Rand|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Richtet sich am oberen Rand aus|Der Popup-Ausrichtungspunkt ändert sich in <xref:System.Windows.Controls.Primitives.Popup>die untere linke Ecke des .|Richtet sich am linken Rand aus|Der Popup-Ausrichtungspunkt ändert sich in <xref:System.Windows.Controls.Primitives.Popup>die obere rechte Ecke des .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Richtet sich am oberen Rand aus|Der Zielursprung ändert sich in die linke obere Ecke des Zielbereichs, und der <xref:System.Windows.Controls.Primitives.Popup>Popupausrichtungspunkt ändert sich in die untere linke Ecke des .|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Der Zielursprung ändert sich in die obere rechte Ecke des Zielbereichs, und der <xref:System.Windows.Controls.Primitives.Popup>Popupausrichtungspunkt ändert sich in die obere linke Ecke des .|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Richtet sich am oberen Rand aus|Der Zielursprung ändert sich in die linke obere Ecke des Zielbereichs (die Grenzen des Mauszeigers), und der <xref:System.Windows.Controls.Primitives.Popup>Popupausrichtungspunkt ändert sich in die untere linke Ecke des .|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Richtet sich am oberen Rand aus|Der Popup-Ausrichtungspunkt ändert sich in <xref:System.Windows.Controls.Primitives.Popup>die untere linke Ecke des .|Richtet sich am linken Rand aus|Der Ausrichtungspunkt wird auf die obere rechte Ecke des Popups geändert.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Richtet sich am oberen Rand aus|Der Popup-Ausrichtungspunkt ändert sich in <xref:System.Windows.Controls.Primitives.Popup>die untere linke Ecke des .|Richtet sich am linken Rand aus|Der Ausrichtungspunkt wird auf die obere rechte Ecke des Popups geändert.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Der Zielursprung ändert sich in die linke obere Ecke des Zielbereichs, und der <xref:System.Windows.Controls.Primitives.Popup>Popupausrichtungspunkt ändert sich in die obere rechte Ecke des .|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|Der Zielursprung ändert sich in die untere linke Ecke des Zielbereichs, und der <xref:System.Windows.Controls.Primitives.Popup>Popupausrichtungspunkt ändert sich in die obere linke Ecke der . In der Tat ist dies das gleiche wie wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>.|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
  
### <a name="aligning-to-the-screen-edge"></a>Ausrichten am Bildschirmrand  
 A <xref:System.Windows.Controls.Primitives.Popup> kann am Rand des Bildschirms ausgerichtet <xref:System.Windows.Controls.Primitives.Popup> werden, indem er sich neu positioniert, sodass das Gesamte auf dem Bildschirm sichtbar ist.  In diesem Fall kann der Abstand zwischen dem Zielursprung und <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> dem <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>Popupausrichtungspunkt von den Werten von und abweichen. Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>ist <xref:System.Windows.Controls.Primitives.PlacementMode.Center>, <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>oder <xref:System.Windows.Controls.Primitives.Popup> , richtet sich der an jeder Bildschirmkante aus.  <xref:System.Windows.Controls.Primitives.Popup> Angenommen, a <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> hat auf <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> 100 gesetzt und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> auf 100 gesetzt.  Wenn der untere Rand des Bildschirms <xref:System.Windows.Controls.Primitives.Popup>ganz <xref:System.Windows.Controls.Primitives.Popup> oder teilweise des ausblendet, positioniert sich der am unteren Rand des Bildschirms neu positioniert, und der vertikale Abstand zwischen dem Zielursprung und dem Popupausrichtungspunkt beträgt weniger als 100. Dies wird in der folgenden Abbildung veranschaulicht.  
  
 ![Am Bildschirmrand ausgerichtetes Popup](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Popup wird am Rand des Bildschirms ausgerichtet.")
  
### <a name="changing-the-popup-alignment-point"></a>Ändern des Popupausrichtungspunkts  
 Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>ist <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>oder , ändert sich der Popupausrichtungspunkt, wenn das Popup auf den unteren oder rechten Bildschirmrand trifft.  
  
 Die folgende Abbildung zeigt, dass der Popupausrichtungspunkt die untere linke Ecke des <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Primitives.Popup>ist, wenn die untere Bildschirmkante ganz oder teilweise ausgeblendet wird.  
  
 ![Neuer Ausrichtungspunkt durch unteren Bildschirmrand](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "Popup trifft auf den unteren Rand des Bildschirms und ändert den Popup-Ausrichtungspunkt.")  

 Die folgende Abbildung zeigt, dass der Popupausrichtungspunkt die obere rechte Ecke <xref:System.Windows.Controls.Primitives.Popup> des <xref:System.Windows.Controls.Primitives.Popup>ist, wenn er durch den rechten Bildschirmrand ausgeblendet wird.  
  
 ![Neuer Popupausrichtungspunkt durch Bildschirmrand](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "Popup trifft auf den rechten Rand des Bildschirms und ändert den Popupausrichtungspunkt.")
  
 Wenn <xref:System.Windows.Controls.Primitives.Popup> der auf den unteren und rechten Bildschirmrand trifft, ist <xref:System.Windows.Controls.Primitives.Popup>der Popupausrichtungspunkt die untere rechte Ecke des .  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Ändern des Zielursprungs und des Popupausrichtungspunkts  
 Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left> <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right>, <xref:System.Windows.Controls.Primitives.PlacementMode.Top>oder , ändern sich der Zielursprung und der Popupausrichtungspunkt, wenn eine bestimmte Bildschirmkante gefunden wird.  Die Bildschirmkante, die bewirkt, <xref:System.Windows.Controls.Primitives.PlacementMode> dass sich die Position ändert, hängt vom Wert ab.  
  
 Die folgende Abbildung <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> zeigt, dass der Zielursprung die linke obere Ecke des Zielbereichs <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> und <xref:System.Windows.Controls.Primitives.Popup> der Popupausrichtungspunkt die untere linke Ecke des <xref:System.Windows.Controls.Primitives.Popup>ist.  
  
 ![Neuer Ausrichtungspunkt durch unteren Bildschirmrand](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "Platzierung ist unten und das Popup trifft auf den unteren Rand des Bildschirms.")
  
 Die folgende Abbildung <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> zeigt, dass <xref:System.Windows.Controls.Primitives.PlacementMode.Left> <xref:System.Windows.Controls.Primitives.Popup> der Zielursprung die obere rechte Ecke des Zielbereichs und der Popupausrichtungspunkt die obere <xref:System.Windows.Controls.Primitives.Popup>linke Ecke des ist.  
  
 ![Neuer Ausrichtungspunkt durch linken Bildschirmrand](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "Platzierung ist Links und das Popup trifft auf den linken Rand des Bildschirms.")  
  
 Die folgende Abbildung <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> zeigt, dass <xref:System.Windows.Controls.Primitives.PlacementMode.Right> <xref:System.Windows.Controls.Primitives.Popup> der Zielursprung die obere linke Ecke des Zielbereichs und der Popupausrichtungspunkt die obere <xref:System.Windows.Controls.Primitives.Popup>rechte Ecke des ist.  
  
 ![Neuer Ausrichtungspunkt durch rechten Bildschirmrand](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "Die Platzierung ist richtig und das Popup trifft auf den rechten Rand des Bildschirms.")  

 Die folgende Abbildung <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> zeigt, dass <xref:System.Windows.Controls.Primitives.PlacementMode.Top> <xref:System.Windows.Controls.Primitives.Popup> der Zielursprung die untere linke Ecke des Zielbereichs und der Popupausrichtungspunkt die <xref:System.Windows.Controls.Primitives.Popup>obere linke Ecke des ist.  
  
 ![Neuer Ausrichtungspunkt durch obere Bildschirmrand](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "Platzierung ist Top und das Popup trifft auf den oberen Rand des Bildschirms.")  
  
 Die folgende Abbildung <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> zeigt, dass <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> <xref:System.Windows.Controls.Primitives.Popup> der Zielursprung die linke obere Ecke des Zielbereichs (die Grenzen des Mauszeigers) und der Popupausrichtungspunkt die <xref:System.Windows.Controls.Primitives.Popup>untere linke Ecke des ist.  
  
 ![Neuer Ausrichtungspunkt durch Maus in der Nähe des Bildschirmrands](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "Platzierung ist Maus und das Popup trifft auf den unteren Rand des Bildschirms.")
  
### <a name="customizing-popup-placement"></a>Anpassen der Popupplatzierung  
 Sie können den Zielursprung und den Popupausrichtungspunkt anpassen, indem Sie die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Eigenschaft auf <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>festlegen. Definieren Sie <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> dann einen Delegaten, der eine Reihe möglicher Platzierungspunkte <xref:System.Windows.Controls.Primitives.Popup>und Primärachsen (in der Reihenfolge der Präferenz) für die zurückgibt. Der Punkt, der den <xref:System.Windows.Controls.Primitives.Popup> größten Teil des zeigt, ist ausgewählt.  Die Position <xref:System.Windows.Controls.Primitives.Popup> des wird automatisch <xref:System.Windows.Controls.Primitives.Popup> angepasst, wenn der am Rand des Bildschirms ausgeblendet wird. Ein Beispiel finden Sie unter [Angeben einer benutzerdefinierten Popupposition](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Beispiel für das Platzieren eines Popups](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)
