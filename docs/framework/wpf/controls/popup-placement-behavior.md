---
title: Verhalten beim Platzieren von Popups
description: In diesem Artikel erfahren Sie, wie Sie mithilfe von Eigenschaften die Position eines Windows Presentation Foundation-Popups im Verhältnis zu einem Steuerelement, zur Maus oder zu einem Bildschirmbereich angeben.
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 8184805518bc56693ead4c7d1f0e9a1bff9bff8f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167748"
---
# <a name="popup-placement-behavior"></a>Verhalten beim Platzieren von Popups
Ein <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement zeigt Inhalt in einem separaten Fenster an, das vor einer Anwendung eingeblendet wird. Die Position eines <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements kann mithilfe der Eigenschaften <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> im Verhältnis zu einem Steuerelement, zur Maus oder zu einem Bildschirmbereich angegeben werden.  Diese Eigenschaften spielen zusammen und geben Ihnen die Flexibilität, die Position des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements selbst festzulegen.  
  
> [!NOTE]
> Diese fünf Eigenschaften werden auch von den Klassen <xref:System.Windows.Controls.ToolTip> und <xref:System.Windows.Controls.ContextMenu> definiert, die sich ähnlich verhalten.  

<a name="Positioning"></a>
## <a name="positioning-the-popup"></a>Positionieren von Popups  
 Die Platzierung eines <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements kann in Relation zu einem <xref:System.Windows.UIElement>-Element oder zum gesamten Bildschirm angegeben werden.  Im folgenden Beispiel werden vier <xref:System.Windows.Controls.Primitives.Popup>-Steuerelemente erstellt, die in Bezug auf ein <xref:System.Windows.UIElement>-Element (in diesem Fall ein Bild) eine bestimmte Position aufweisen. Für alle <xref:System.Windows.Controls.Primitives.Popup>-Steuerelemente wurde die Eigenschaft <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> auf `image1` festgelegt, die Werte der Eigenschaft „Placement“ unterscheiden sich jedoch zwischen den einzelnen <xref:System.Windows.Controls.Primitives.Popup>-Steuerelementen.  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 In der folgenden Abbildung werden das Bild und die einzelnen <xref:System.Windows.Controls.Primitives.Popup>-Steuerelemente gezeigt:  
  
 ![Bild mit vier Popup-Steuerelementen](./media/popup-placement-behavior/popup-placement-intro.png "Bild mit vier Popups")
  
 Dieses einfache Beispiel veranschaulicht, wie die Eigenschaften <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> und <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> festgelegt werden. Mithilfe der Eigenschaften <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> lässt sich die Position eines <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements genauer steuern.  
  
<a name="Definitions"></a>
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Begriffsdefinition: Aufbau eines Popups  
 Die folgenden Begriffe sind hilfreich, um zu verstehen, in welchem Zusammenhang die Eigenschaften <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> zueinander und zum <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement stehen:  
  
- Das Zielobjekt  
  
- Der Zielbereich  
  
- Der Zielursprung  
  
- Der Popupausrichtungspunkt  
  
 Mit diesen Begriffen können Sie unkompliziert auf verschiedene Aspekte des <xref:System.Windows.Controls.Primitives.Popup>-Objekts und des dazugehörigen Steuerelements verweisen.  
  
### <a name="target-object"></a>Das Zielobjekt  
 Das *Zielobjekt* ist das Element, mit dem <xref:System.Windows.Controls.Primitives.Popup> verknüpft ist. Wenn die Eigenschaft <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> festgelegt ist, gibt sie das Zielobjekt an.  Ist <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> nicht festgelegt, und das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement verfügt über ein übergeordnetes Element, ist das übergeordnete Element das Zielobjekt.  Sind weder ein <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>-Wert noch übergeordnetes Element vorhanden, gibt es kein Zielobjekt, und das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement wird im Verhältnis zum Bildschirm positioniert.  
  
 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement erstellt, das ein untergeordnetes Element von <xref:System.Windows.Controls.Canvas> ist.  Die Eigenschaft <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird nicht für das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement festgelegt. Der Standardwert von <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> lautet <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>, sodass der <xref:System.Windows.Controls.Primitives.Popup> unterhalb von <xref:System.Windows.Controls.Canvas> angezeigt wird.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 Die folgende Abbildung zeigt das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement, das im Verhältnis zu <xref:System.Windows.Controls.Canvas> positioniert ist.  
  
 ![Popup-Steuerelement ohne PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Popup ohne PlacementTarget")  

 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement erstellt, das das untergeordnete Element eines <xref:System.Windows.Controls.Canvas>-Elements ist. Dieses Mal wird <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> jedoch auf `ellipse1` festgelegt, sodass das Popup unterhalb von <xref:System.Windows.Shapes.Ellipse> angezeigt wird.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 Die folgende Abbildung zeigt das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement, das im Verhältnis zu <xref:System.Windows.Shapes.Ellipse> positioniert ist.  
  
 ![Relativ zu einer Ellipse platziertes Popup](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Popup mit PlacementTarget")
  
> [!NOTE]
> Für <xref:System.Windows.Controls.ToolTip> entspricht der Standardwert von <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> dem Wert <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>.  Für <xref:System.Windows.Controls.ContextMenu> entspricht der Standardwert von <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> dem Wert <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>. Diese Werte werden später in „Zusammenwirken der Eigenschaften“ erklärt.  
  
### <a name="target-area"></a>Der Zielbereich  
 Der *Zielbereich* ist der Teil des Bildschirms, zu dem <xref:System.Windows.Controls.Primitives.Popup> in Relation gesetzt wird. In den vorherigen Beispielen wurde <xref:System.Windows.Controls.Primitives.Popup> an den Grenzen des Zielobjekts ausgerichtet. In bestimmten Fällen wird <xref:System.Windows.Controls.Primitives.Popup> jedoch in Bezug zu anderen Grenzen gesetzt, selbst wenn <xref:System.Windows.Controls.Primitives.Popup> ein Zielobjekt aufweist.  Wenn die Eigenschaft <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> festgelegt ist, unterscheidet sich der Zielbereich von den Grenzen des Zielobjekts.  
  
 Im folgenden Beispiel werden zwei <xref:System.Windows.Controls.Canvas>-Objekte erstellt, von denen jedes ein <xref:System.Windows.Shapes.Rectangle>-Steuerelement und ein <xref:System.Windows.Controls.Primitives.Popup>-Element enthält.  In beiden Fällen ist das <xref:System.Windows.Controls.Canvas>-Element das Zielobjekt des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements. Für das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement im ersten <xref:System.Windows.Controls.Canvas>-Element wurde die Eigenschaft <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> festgelegt, wobei ihre Eigenschaften <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A>und <xref:System.Windows.Rect.Height%2A> die Werte 50, 50, 50 bzw. 100 aufweisen. Für das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement im zweiten <xref:System.Windows.Controls.Canvas>-Element ist <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> nicht festgelegt.  Aus diesem Grund wird das erste <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement unter <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> und das zweite <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement unter <xref:System.Windows.Controls.Canvas> positioniert. Jedes <xref:System.Windows.Controls.Canvas>-Element enthält außerdem ein <xref:System.Windows.Shapes.Rectangle>-Element, das dieselben Grenzen wie das <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>-Element für das erste <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement aufweist.  Beachten Sie, dass <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> kein sichtbares Element in der Anwendung erstellt. Im Beispiel wird ein <xref:System.Windows.Shapes.Rectangle>-Element erstellt, um <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> darzustellen.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 Die folgende Abbildung zeigt das Ergebnis des vorherigen Beispiels.  
  
 ![Popup mit und ohne PlacementRectangle](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Popup mit und ohne PlacementRectangle")  

### <a name="target-origin-and-popup-alignment-point"></a>Zielursprung und Popupausrichtungspunkt  
 Der *Zielursprung* und *Popupausrichtungspunkt* sind Bezugspunkte für die Positionierung im Zielbereich und im Popup. Mithilfe der Eigenschaften <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> können Sie das Popup um einen bestimmten Wert im Verhältnis zum Zielbereich versetzen.  Die Eigenschaften <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> sind abhängig vom Zielursprung und vom Popupausrichtungspunkt. Der Wert der Eigenschaft <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> bestimmt, wo sich der Zielursprung und der Popupausrichtungspunkt befinden.  
  
 Im folgenden Beispiel wird zunächst ein <xref:System.Windows.Controls.Primitives.Popup> erstellt. Anschließend werden die Eigenschaften <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> auf 20 festgelegt.  Die Eigenschaft <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> wird auf <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> festgelegt (Standard), sodass der Zielursprung der linken unteren Ecke des Zielbereichs und der Popupausrichtungspunkt der linken oberen Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements entspricht.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 Die folgende Abbildung zeigt das Ergebnis des vorherigen Beispiels.  
  
 ![Popupplatzierung mit Zielursprung-Ausrichtungspunkt](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Popup mit HorizontalOffset und VerticalOffset")
  
<a name="How"></a>
## <a name="how-the-properties-work-together"></a>Zusammenwirken der Eigenschaften  
 Die Werte von <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> und <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> müssen zusammen betrachtet werden, um den richtigen Zielbereich, Zielursprung und Popupausrichtungspunkt zu ermitteln.  Wenn der Wert von <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> z. B. <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> lautet, gibt es kein Zielobjekt, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird ignoriert, und der Zielbereich entspricht den Grenzen des Mauszeigers. Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> hingegen <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> ist, bestimmt <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder das übergeordnete Element das Zielobjekt, und <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> legt den Zielbereich fest.  
  
 In der folgenden Tabelle werden das Zielobjekt, der Zielbereich, der Zielursprung und der Popupausrichtungspunkt beschrieben. Außerdem wird angegeben, ob <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> und <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> für jeden <xref:System.Windows.Controls.Primitives.PlacementMode>-Enumerationswert verwendet werden.  
  
|PlacementMode|Das Zielobjekt|Der Zielbereich|Der Zielursprung|Der Popupausrichtungspunkt|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Der Bildschirm oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn die Eigenschaft festgelegt ist.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird im Verhältnis zum Bildschirm positioniert.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Der Bildschirm oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn die Eigenschaft festgelegt ist.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird im Verhältnis zum Bildschirm positioniert.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder das übergeordnete Element|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn die Eigenschaft festgelegt ist.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird im Verhältnis zum Zielobjekt positioniert.|Die linke untere Ecke des Zielbereichs|Die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder das übergeordnete Element|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn die Eigenschaft festgelegt ist.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird im Verhältnis zum Zielobjekt positioniert.|Die Mitte des Zielbereichs|Die Mitte des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder das übergeordnete Element|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn die Eigenschaft festgelegt ist.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird im Verhältnis zum Zielobjekt positioniert.|Von <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> definiert|Von <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> definiert|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder das übergeordnete Element|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn die Eigenschaft festgelegt ist.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird im Verhältnis zum Zielobjekt positioniert.|Die linke obere Ecke des Zielbereichs|Die rechte obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Die Grenzen des Mauszeigers <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird ignoriert.|Die linke untere Ecke des Zielbereichs|Die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Die Grenzen des Mauszeigers <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird ignoriert.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder das übergeordnete Element|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn die Eigenschaft festgelegt ist.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird im Verhältnis zum Zielobjekt positioniert.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder das übergeordnete Element|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn die Eigenschaft festgelegt ist.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird im Verhältnis zum Zielobjekt positioniert.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder das übergeordnete Element|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn die Eigenschaft festgelegt ist.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird im Verhältnis zum Zielobjekt positioniert.|Die rechte obere Ecke des Zielbereichs|Die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder das übergeordnete Element|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, wenn die Eigenschaft festgelegt ist.  <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird im Verhältnis zum Zielobjekt positioniert.|Die linke obere Ecke des Zielbereichs|Die linke untere Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements|  
  
 Die folgenden Abbildungen zeigen das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement, der Zielbereich, der Zielursprung und der Popupausrichtungspunkt für die einzelnen <xref:System.Windows.Controls.Primitives.PlacementMode>-Werte. Der Zielbereich ist gelb eingefärbt, das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement blau.  
  
 ![Popup mit Absolute- oder AbsolutePoint-Platzierung](./media/popup-placement-behavior/popup-placement-absolute.png "Placement entspricht Absolute oder AbsolutePoint")
  
 ![Popup mit Bottom-Platzierung](./media/popup-placement-behavior/popup-placement-bottom.png "Placement entspricht Bottom")
  
 ![Popup mit Center-Platzierung](./media/popup-placement-behavior/popup-placement-center.png "Placement entspricht Center")
  
 ![Popup mit Left-Platzierung](./media/popup-placement-behavior/popup-placement-left.png "Placement entspricht Left")
  
 ![Popup mit Mouse-Platzierung](./media/popup-placement-behavior/popup-placement-mouse.png "Placement entspricht Mouse")  
  
 ![Popup mit MousePoint-Platzierung](./media/popup-placement-behavior/popup-placement-mousepoint.png "Placement entspricht MousePoint")  
  
 ![Popup mit Relative- oder RelativePoint-Platzierung](./media/popup-placement-behavior/popup-placement-relative.png "Placement entspricht Relative oder RelativePoint")
  
 ![Popup mit Right-Platzierung](./media/popup-placement-behavior/popup-placement-right.png "Placement entspricht Right")
  
 ![Popup mit Top-Platzierung](./media/popup-placement-behavior/popup-placement-top.png "Placement entspricht Top")
  
<a name="When"></a>
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Wenn das Popup auf einen Bildschirmrand trifft  
 Aus Sicherheitsgründen kann ein <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement nicht durch einen Bildschirmrand verdeckt werden. Wenn ein <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement auf einen Bildschirmrand trifft, tritt eines der folgenden drei Szenarios ein:  
  
- Das Popup wird an dem Bildschirmrand neu ausgerichtet, der das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement verdecken würde.  
  
- Das Popup verwendet einen anderen Popupausrichtungspunkt.  
  
- Das Popup verwendet einen anderen Zielursprungs und Popupausrichtungspunkt.  
  
 Diese Optionen werden weiter unten in diesem Abschnitt beschrieben.  
  
 Das Verhalten, das das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement beim Treffen auf einen Bildschirmrand aufweist, hängt vom Wert der Eigenschaft <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> und davon ab, um welchen Bildschirmrand es sich handelt. In der folgenden Tabelle ist für jeden <xref:System.Windows.Controls.Primitives.PlacementMode>-Wert aufgeführt, wie sich das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement verhält, wenn es auf einen Bildschirmrand stößt.  
  
|PlacementMode|Oberer Rand|Unterer Rand|Linker Rand|Rechter Rand|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Richtet sich am oberen Rand aus|Der Popupausrichtungspunkt wird auf die untere linke Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements verlegt.|Richtet sich am linken Rand aus|Der Popupausrichtungspunkt wird auf die obere rechte Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements verlegt.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Richtet sich am oberen Rand aus|Der Zielursprung wird auf die linke obere Ecke des Zielbereichs und der Popupausrichtungspunkt auf die linke untere Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements verlegt.|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Der Zielursprung wird auf die rechte obere Ecke des Zielbereichs und der Popupausrichtungspunkt auf die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements verlegt.|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Richtet sich am oberen Rand aus|Der Zielursprung wird auf die linke obere Ecke des Zielbereichs (die Grenzen des Mauszeigers) und der Popupausrichtungspunkt auf die linke untere Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements verlegt.|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Richtet sich am oberen Rand aus|Der Popupausrichtungspunkt wird auf die untere linke Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements verlegt.|Richtet sich am linken Rand aus|Der Ausrichtungspunkt wird auf die obere rechte Ecke des Popups geändert.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Richtet sich am oberen Rand aus|Der Popupausrichtungspunkt wird auf die untere linke Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements verlegt.|Richtet sich am linken Rand aus|Der Ausrichtungspunkt wird auf die obere rechte Ecke des Popups geändert.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Der Zielursprung wird auf die linke obere Ecke des Zielbereichs und der Popupausrichtungspunkt auf die rechte obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements verlegt.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|Der Zielursprung wird auf die linke untere Ecke des Zielbereichs und der Popupausrichtungspunkt auf die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements verlegt. Die Ausrichtung erfolgt im Grunde genommen nach demselben Prinzip, wie wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> den Wert <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> aufweist.|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
  
### <a name="aligning-to-the-screen-edge"></a>Ausrichten am Bildschirmrand  
 Ein <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement kann am Bildschirmrand ausgerichtet werden. Dazu positioniert sich das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement neu, sodass es vollständig auf dem Bildschirm angezeigt wird.  Bei diesem Vorgang kann der Abstand zwischen dem Zielursprung und dem Popupausrichtungspunkt von den Werten von <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> abweichen. Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> den Wert <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, <xref:System.Windows.Controls.Primitives.PlacementMode.Center> oder <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> aufweist, richtet sich das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement selbst am Bildschirmrand aus.  Angenommen, ein <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement verfügt über die Eigenschaften <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> und <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>, die auf <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> bzw. „100“ festgelegt sind.  Wenn der untere Bildschirmrand das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement ganz oder teilweise verdeckt, positioniert sich das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement automatisch entlang des unteren Bildschirmrands neu. Der vertikale Abstand zwischen dem Zielursprung und Popupausrichtungspunkt ist kleiner als 100. Dies wird in der folgenden Abbildung veranschaulicht.  
  
 ![Am Bildschirmrand ausgerichtetes Popup](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Popup wird am Bildschirmrand ausgerichtet")
  
### <a name="changing-the-popup-alignment-point"></a>Ändern des Popupausrichtungspunkts  
 Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> den Wert <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint> oder <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint> aufweist, ändert sich der Popupausrichtungspunkt, wenn das Popup auf den unteren oder rechten Bildschirmrand trifft.  
  
 Die folgende Abbildung zeigt, dass der Popupausrichtungspunkt der unteren linken Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements entspricht, wenn der untere Bildschirmrand das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement ganz oder teilweise verdeckt.  
  
 ![Neuer Ausrichtungspunkt durch unteren Bildschirmrand](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "Popup trifft auf den unteren Bildschirmrand und ändert den Popupausrichtungspunkt")  

 Die folgende Abbildung zeigt, dass der Popupausrichtungspunkt der oberen rechten Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements entspricht, wenn der rechte Bildschirmrand das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement verdeckt.  
  
 ![Neuer Popupausrichtungspunkt durch Bildschirmrand](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "Popup trifft auf den rechten Bildschirmrand und ändert den Popupausrichtungspunkt")
  
 Wenn das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement auf den unteren und rechten Bildschirmrand trifft, entspricht der Popupausrichtungspunkt der unteren rechten Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Ändern des Zielursprungs und des Popupausrichtungspunkts  
 Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> auf den Wert <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right> oder <xref:System.Windows.Controls.Primitives.PlacementMode.Top> festgelegt ist, werden der Zielursprung und der Popupausrichtungspunkt geändert, wenn das Steuerelement auf einen bestimmten Bildschirmrand trifft.  Der Bildschirmrand, der die Neupositionierung verursacht, hängt vom Wert von <xref:System.Windows.Controls.Primitives.PlacementMode> ab.  
  
 Die folgende Abbildung zeigt, dass der Zielursprung der linken oberen Ecke des Zielbereichs und der Popupausrichtungspunkt der unteren linken Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements entspricht, wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> den Wert <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> aufweist und das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement auf den unteren Bildschirmrand trifft.  
  
 ![Neuer Ausrichtungspunkt durch unteren Bildschirmrand](./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "Placement entspricht Bottom, und das Popup trifft auf den unteren Bildschirmrand.")
  
 Die folgende Abbildung zeigt, dass der Zielursprung der rechten oberen Ecke des Zielbereichs und der Popupausrichtungspunkt der oberen linken Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements entspricht, wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> den Wert <xref:System.Windows.Controls.Primitives.PlacementMode.Left> aufweist und das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement auf den linken Bildschirmrand trifft.  
  
 ![Neuer Ausrichtungspunkt durch linken Bildschirmrand](./media/popup-placement-behavior/popup-placement-left-screen-edge.png "Placement entspricht Left, und das Popup trifft auf den linken Bildschirmrand.")  
  
 Die folgende Abbildung zeigt, dass der Zielursprung der linken oberen Ecke des Zielbereichs und der Popupausrichtungspunkt der oberen rechten Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements entspricht, wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> den Wert <xref:System.Windows.Controls.Primitives.PlacementMode.Right> aufweist und das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement auf den rechten Bildschirmrand trifft.  
  
 ![Neuer Ausrichtungspunkt durch rechten Bildschirmrand](./media/popup-placement-behavior/popup-placement-right-screen-edge.png "Placement entspricht Right, und das Popup trifft auf den rechten Bildschirmrand.")  

 Die folgende Abbildung zeigt, dass der Zielursprung der linken unteren Ecke des Zielbereichs und der Popupausrichtungspunkt der oberen linken Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements entspricht, wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> den Wert <xref:System.Windows.Controls.Primitives.PlacementMode.Top> aufweist und das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement auf den oberen Bildschirmrand trifft.  
  
 ![Neuer Ausrichtungspunkt durch obere Bildschirmrand](./media/popup-placement-behavior/popup-placement-top-screen-edge.png "Placement entspricht Top, und das Popup trifft auf den oberen Bildschirmrand.")  
  
 Die folgende Abbildung zeigt, dass der Zielursprung der linken oberen Ecke des Zielbereichs (Grenzen des Mauszeigers) und der Popupausrichtungspunkt der unteren linken Ecke des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements entspricht, wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> den Wert <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> aufweist und das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement auf den unteren Bildschirmrand trifft.  
  
 ![Neuer Ausrichtungspunkt durch Maus in der Nähe des Bildschirmrands](./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "Placement entspricht Mouse, und das Popup trifft auf den unteren Bildschirmrand.")
  
### <a name="customizing-popup-placement"></a>Anpassen der Popupplatzierung  
 Sie können den Zielursprung und den Popupausrichtungspunkt anpassen, indem Sie die Eigenschaft <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> auf <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> festlegen. Definieren Sie anschließend einen <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>-Delegaten, der eine Reihe möglicher Platzierungspunkte und primärer Achsen (in der bevorzugten Reihenfolge) für das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement zurückgibt. Der Punkt, an dem der größte Teil des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements anzeigt wird, wird ausgewählt.  Die Position des <xref:System.Windows.Controls.Primitives.Popup>-Steuerelements wird automatisch angepasst, wenn das <xref:System.Windows.Controls.Primitives.Popup>-Steuerelement vom Bildschirmrand verdeckt wird. Ein Beispiel finden Sie unter [Angeben einer benutzerdefinierten Popupposition](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>Siehe auch

- [Beispiel für das Platzieren eines Popups](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)
