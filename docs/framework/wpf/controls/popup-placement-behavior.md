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
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951733"
---
# <a name="popup-placement-behavior"></a>Verhalten beim Platzieren von Popups
Ein <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement zeigt Inhalt in einem separaten Fenster an, das über eine Anwendung schwebt. Mithilfe <xref:System.Windows.Controls.Primitives.Popup> der Eigenschaften,<xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, ,<xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> undkönnen<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> Sie die Position eines relativ zu einem Steuerelement, der Maus oder dem Bildschirm angeben. <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>  Diese Eigenschaften arbeiten zusammen, um Ihnen Flexibilität bei der Angabe der Position von <xref:System.Windows.Controls.Primitives.Popup>zu bieten.  
  
> [!NOTE]
> Die <xref:System.Windows.Controls.ToolTip> Klassen <xref:System.Windows.Controls.ContextMenu> und definieren außerdem diese fünf Eigenschaften und Verhalten sich ähnlich.  

<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>Positionieren von Popups  
 Die Platzierung <xref:System.Windows.Controls.Primitives.Popup> eines kann relativ zu einem <xref:System.Windows.UIElement> oder zum gesamten Bildschirm sein.  Im folgenden Beispiel werden vier <xref:System.Windows.Controls.Primitives.Popup> Steuerelemente erstellt, die relativ <xref:System.Windows.UIElement>zu einem – in diesem Fall ein Bild sind. Für alle-Steuer <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> `image1` <xref:System.Windows.Controls.Primitives.Popup> Elemente ist die-Eigenschaft auf festgelegt, aber jede weist einen anderen Wert für die Placement-Eigenschaft auf. <xref:System.Windows.Controls.Primitives.Popup>  
  
 [!code-xaml[PopupPositionSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 Die folgende Abbildung zeigt das Bild und die <xref:System.Windows.Controls.Primitives.Popup> Steuerelemente.  
  
 ![Bild mit vier Popup] -Steuerelementen (./media/popup-placement-behavior/popup-placement-intro.png "Bild mit vier Popups")    
  
 In diesem einfachen Beispiel wird veranschaulicht, wie <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> -Eigenschaft und die-Eigenschaft <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>festgelegt werden <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> . mit den Eigenschaften, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> <xref:System.Windows.Controls.Primitives.Popup> und haben Sie jedoch noch mehr Kontrolle darüber, wo positioniert ist.  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Definitionen der Begriffe: Die Anatomie eines Popups  
 Die folgenden Begriffe sind hilfreich, um zu verstehen <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>wie <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>sich die Eigenschaften <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> ,,, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>und in Beziehung zueinander <xref:System.Windows.Controls.Primitives.Popup>und befinden.  
  
- Das Zielobjekt  
  
- Der Zielbereich  
  
- Der Zielursprung  
  
- Der Popupausrichtungspunkt  
  
 Diese Begriffe stellen eine bequeme Möglichkeit dar, auf verschiedene Aspekte von <xref:System.Windows.Controls.Primitives.Popup> und auf das Steuerelement zu verweisen, dem es zugeordnet ist.  
  
### <a name="target-object"></a>Das Zielobjekt  
 Das *Zielobjekt* ist das Element, dem <xref:System.Windows.Controls.Primitives.Popup> der zugeordnet ist. Wenn die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> -Eigenschaft festgelegt ist, wird das Zielobjekt angegeben.  Wenn <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> nicht festgelegt ist und der <xref:System.Windows.Controls.Primitives.Popup> über ein übergeordnetes Element verfügt, ist das übergeordnete Objekt das Zielobjekt.  Wenn kein <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> Wert und kein übergeordnetes Element vorhanden ist, gibt es kein Zielobjekt, <xref:System.Windows.Controls.Primitives.Popup> und das-Objekt ist relativ zum Bildschirm positioniert.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.Primitives.Popup> erstellt, die das untergeordnete <xref:System.Windows.Controls.Canvas>Element von ist.  Im Beispiel wird die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> -Eigenschaft nicht <xref:System.Windows.Controls.Primitives.Popup>auf festgelegt. Der Standardwert für <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>, sodass <xref:System.Windows.Controls.Primitives.Popup> unter dem <xref:System.Windows.Controls.Canvas>angezeigt wird.  
  
 [!code-xaml[PopupPositionSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 Die folgende Abbildung zeigt, dass <xref:System.Windows.Controls.Primitives.Popup> der relativ <xref:System.Windows.Controls.Canvas>zum positioniert ist.  
  
 ![Popup-Steuerelement ohne PlacementTarget](./media/popup-placement-behavior/popup-placement-no-placement-target.png "Popup ohne PlacementTarget.")  

 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.Primitives.Popup> erstellt, die das untergeordnete <xref:System.Windows.Controls.Canvas>Element von ist <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> , aber dieses Mal wird `ellipse1`auf festgelegt, sodass das Popup <xref:System.Windows.Shapes.Ellipse>unter dem angezeigt wird.  
  
 [!code-xaml[PopupPositionSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 Die folgende Abbildung zeigt, dass <xref:System.Windows.Controls.Primitives.Popup> der relativ <xref:System.Windows.Shapes.Ellipse>zum positioniert ist.  
  
 ![Im Verhältnis zu einer Ellipse positioniertes Popup](./media/popup-placement-behavior/popup-placement-with-placement-target.png "Popup mit \"PlacementTarget") "    
  
> [!NOTE]
> Für <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist der<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>Standardwert von.  Für <xref:System.Windows.Controls.ContextMenu> <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist der<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>Standardwert von. Diese Werte werden später in „Zusammenwirken der Eigenschaften“ erklärt.  
  
### <a name="target-area"></a>Der Zielbereich  
 Der *Zielbereich* ist der Bereich auf dem Bildschirm, <xref:System.Windows.Controls.Primitives.Popup> zu dem der relativ ist. In den vorherigen Beispielen wird der <xref:System.Windows.Controls.Primitives.Popup> an den Begrenzungen des Zielobjekts ausgerichtet, aber in einigen Fällen wird der <xref:System.Windows.Controls.Primitives.Popup> an anderen Begrenzungen ausgerichtet, auch wenn der <xref:System.Windows.Controls.Primitives.Popup> über ein Zielobjekt verfügt.  Wenn die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> -Eigenschaft festgelegt wird, unterscheidet sich der Zielbereich von den Begrenzungen des Zielobjekts.  
  
 Im folgenden Beispiel werden zwei <xref:System.Windows.Controls.Canvas> -Objekte erstellt, die jeweils <xref:System.Windows.Shapes.Rectangle> einen und <xref:System.Windows.Controls.Primitives.Popup>einen enthalten.  In beiden Fällen <xref:System.Windows.Controls.Primitives.Popup> <xref:System.Windows.Controls.Canvas>ist das Zielobjekt für das. Der <xref:System.Windows.Controls.Primitives.Popup> in der ersten <xref:System.Windows.Controls.Canvas> verfügt über <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> den Satz, dessen <xref:System.Windows.Rect.X%2A>Eigenschaften <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A>, und <xref:System.Windows.Rect.Height%2A> auf 50, 50, 50 und 100 festgelegt sind. Der <xref:System.Windows.Controls.Primitives.Popup> in der zweiten <xref:System.Windows.Controls.Canvas> hat nicht den <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Satz.  Daher <xref:System.Windows.Controls.Primitives.Popup> wird der erste unter dem <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> positioniert und der zweite <xref:System.Windows.Controls.Primitives.Popup> unter dem <xref:System.Windows.Controls.Canvas>positioniert. Jede <xref:System.Windows.Controls.Canvas> enthält auch eine <xref:System.Windows.Shapes.Rectangle> , die die gleichen Begrenzungen wie die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> für die erste <xref:System.Windows.Controls.Primitives.Popup>aufweist.  Beachten Sie, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> dass von kein sichtbares Element in der Anwendung erstellt wird. im Beispiel <xref:System.Windows.Shapes.Rectangle> wird ein erstellt <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, das die darstellt.  
  
 [!code-xaml[PopupPositionSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 Die folgende Abbildung zeigt das Ergebnis des vorherigen Beispiels.  
  
 ![Popup mit und ohne placementrechteck](./media/popup-placement-behavior/popup-placement-placement-rectangle.png "Popup mit und ohne placementrechteck.")  

### <a name="target-origin-and-popup-alignment-point"></a>Zielursprung und Popupausrichtungspunkt  
 Der *Zielursprung* und *Popupausrichtungspunkt* sind Bezugspunkte für die Positionierung im Zielbereich und im Popup. Sie können die <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> -Eigenschaft <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> und die-Eigenschaft verwenden, um das Popup aus dem Zielbereich zu versetzen.  <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> Und<xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> sind relativ zum Ziel Ursprung und zum Popup Ausrichtungs Punkt. Der Wert <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> der-Eigenschaft bestimmt, wo sich der Ziel Ursprung und der Popup Ausrichtungs Punkt befinden.  
  
 Im folgenden Beispiel wird eine <xref:System.Windows.Controls.Primitives.Popup> erstellt und die <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> - <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> Eigenschaft und die-Eigenschaft auf 20 festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> -Eigenschaft wird auf <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (die Standardeinstellung) festgelegt, sodass der Ziel Ursprung die linke untere Ecke des Zielbereichs und der Popup Ausrichtungs Punkt die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>ist.  
  
 [!code-xaml[PopupPositionSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 Die folgende Abbildung zeigt das Ergebnis des vorherigen Beispiels.  
  
 ![Popup-Platzierung mit Ziel Ursprungs Ausrichtungs Punkt](./media/popup-placement-behavior/popup-placement-target-origin-alignment-point.png "Popup mit HorizontalOffset und VerticalOffset.")    
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>Zusammenwirken der Eigenschaften  
 Die Werte von <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>und <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> müssen in Erwägung gezogen werden, um den richtigen Zielbereich, den Ziel Ursprung und den Popup Ausrichtungs Punkt zu ermitteln.  Wenn der Wert von <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> beispielsweise ist <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, gibt es <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> kein Zielobjekt, wird ignoriert, und der Zielbereich ist die Begrenzungen des Mauszeigers. Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> andererseits ist <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, bestimmt das <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> übergeordnete Element oder das Zielobjekt und <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> bestimmt den Zielbereich.  
  
 Die folgende Tabelle beschreibt das Zielobjekt, den Zielbereich, den Ziel Ursprung und den Popup Ausrichtungs Punkt <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> und <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> gibt an, ob <xref:System.Windows.Controls.Primitives.PlacementMode> und für jeden Enumerationswert verwendet werden.  
  
|PlacementMode|Das Zielobjekt|Der Zielbereich|Der Zielursprung|Der Popupausrichtungspunkt|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>wird ignoriert.|Der Bildschirm oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , wenn er festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Bildschirm.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>wird ignoriert.|Der Bildschirm oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , wenn er festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Bildschirm.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke untere Ecke des Zielbereichs|Die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die Mitte des Zielbereichs|Der Mittelpunkt <xref:System.Windows.Controls.Primitives.Popup>der.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Definiert durch <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|Definiert durch <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Die obere rechte Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>wird ignoriert.|Die Grenzen des Mauszeigers <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>wird ignoriert.|Die linke untere Ecke des Zielbereichs|Die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>wird ignoriert.|Die Grenzen des Mauszeigers <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>wird ignoriert.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die rechte obere Ecke des Zielbereichs|Die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> , wenn es festgelegt ist.  Der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Die linke untere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 Die folgenden Abbildungen zeigen die <xref:System.Windows.Controls.Primitives.Popup>, den Zielbereich, den Ziel Ursprung und den Popup Ausrichtungs <xref:System.Windows.Controls.Primitives.PlacementMode> Punkt für die einzelnen Werte. In jeder Abbildung ist der Zielbereich gelb, und <xref:System.Windows.Controls.Primitives.Popup> ist blau.  
  
 ![Popup mit absoluter oder AbsolutePoint-Platzierung] Die (./media/popup-placement-behavior/popup-placement-absolute.png "Platzierung ist absolut oder AbsolutePoint.")    
  
 ![Popup mit unterer Platzierung] Die (./media/popup-placement-behavior/popup-placement-bottom.png "Platzierung ist \"Bottom\".")   
  
 ![Popup mit Center-Platzierung] Die (./media/popup-placement-behavior/popup-placement-center.png "Platzierung ist \"Center\".")    
  
 ![Popup mit linker Platzierung] Die (./media/popup-placement-behavior/popup-placement-left.png "Platzierung ist \"Left\".")   
  
 ![Popup mit Maus Platzierung] Die (./media/popup-placement-behavior/popup-placement-mouse.png "Platzierung ist \"Mouse\".")  
  
 ![Popup mit mouort-Platzierung] Die (./media/popup-placement-behavior/popup-placement-mousepoint.png "Platzierung ist \"moustipoint\".")  
  
 ![Popup mit relativer oder RelativePoint-Platzierung] Die (./media/popup-placement-behavior/popup-placement-relative.png "Platzierung ist \"relative\" oder \"RelativePoint\".")    
  
 ![Popup mit rechter Platzierung] Die (./media/popup-placement-behavior/popup-placement-right.png "Platzierung ist \"Right\".")    
  
 ![Popup mit Top-Platzierung] Die (./media/popup-placement-behavior/popup-placement-top.png "Platzierung ist \"Top\".")    
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Wenn das Popup auf einen Bildschirmrand trifft  
 Aus Sicherheitsgründen kann ein <xref:System.Windows.Controls.Primitives.Popup> nicht durch den Rand eines Bildschirms ausgeblendet werden. Eines der folgenden drei Dinge passiert, wenn <xref:System.Windows.Controls.Primitives.Popup> ein Bildschirmrand stößt:  
  
- Das Popup richtet sich am Bildschirmrand neu, der die <xref:System.Windows.Controls.Primitives.Popup>verdecken würde.  
  
- Das Popup verwendet einen anderen Popupausrichtungspunkt.  
  
- Das Popup verwendet einen anderen Zielursprungs und Popupausrichtungspunkt.  
  
 Diese Optionen werden weiter unten in diesem Abschnitt beschrieben.  
  
 Das Verhalten des <xref:System.Windows.Controls.Primitives.Popup> , wenn es auf einen Bildschirmrand stößt, hängt vom Wert <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> der-Eigenschaft und von dem Bildschirmrand ab, auf den das Popup trifft. In der folgenden Tabelle wird das Verhalten zusammen <xref:System.Windows.Controls.Primitives.Popup> gefasst, wenn der auf einen <xref:System.Windows.Controls.Primitives.PlacementMode> Bildschirmrand für jeden Wert stößt.  
  
|PlacementMode|Oberer Rand|Unterer Rand|Linker Rand|Rechter Rand|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Richtet sich am oberen Rand aus|Der Popup Ausrichtungs Punkt ändert sich in die linke untere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Der Popup Ausrichtungs Punkt ändert sich in die obere rechte Ecke von <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Richtet sich am oberen Rand aus|Der Ziel Ursprung wird in die linke obere Ecke des Zielbereichs geändert, und der Popup Ausrichtungs Punkt ändert sich in die linke untere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Der Ziel Ursprung ändert sich in die rechte obere Ecke des Zielbereichs, und der Popup Ausrichtungs Punkt ändert sich in die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Richtet sich am oberen Rand aus|Der Ziel Ursprung ändert sich in die linke obere Ecke des Zielbereichs (die Begrenzungen des Mauszeigers), und der Popup Ausrichtungs Punkt ändert sich in die linke untere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Richtet sich am oberen Rand aus|Der Popup Ausrichtungs Punkt ändert sich in die linke untere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Der Ausrichtungspunkt wird auf die obere rechte Ecke des Popups geändert.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Richtet sich am oberen Rand aus|Der Popup Ausrichtungs Punkt ändert sich in die linke untere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Der Ausrichtungspunkt wird auf die obere rechte Ecke des Popups geändert.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Der Ziel Ursprung wird in die linke obere Ecke des Zielbereichs geändert, und der Popup Ausrichtungs Punkt ändert sich in die obere rechte Ecke des <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|Der Ziel Ursprung wird in die linke untere Ecke des Zielbereichs geändert, und der Popup Ausrichtungs Punkt ändert sich in die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>. Tatsächlich ist dies identisch mit dem, wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> gleich ist. <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
  
### <a name="aligning-to-the-screen-edge"></a>Ausrichten am Bildschirmrand  
 Eine <xref:System.Windows.Controls.Primitives.Popup> kann am Bildschirmrand ausgerichtet werden, indem Sie sich selbst neu positioniert, sodass <xref:System.Windows.Controls.Primitives.Popup> die gesamte auf dem Bildschirm sichtbar ist.  In diesem Fall kann sich der Abstand zwischen dem Ziel Ursprung und dem Popup Ausrichtungs Punkt von den Werten <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> von <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>und unterscheiden. Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> , <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute> oder<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>ist, richtet sich der<xref:System.Windows.Controls.Primitives.Popup> an jedem Bildschirmrand. <xref:System.Windows.Controls.Primitives.PlacementMode.Center>  Nehmen Sie beispielsweise an, <xref:System.Windows.Controls.Primitives.Popup> dass <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ein auf <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> fest <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> gelegt ist und auf 100 festgelegt ist.  Wenn der untere Rand des Bildschirms den gesamten oder einen Teil von <xref:System.Windows.Controls.Primitives.Popup>verbirgt, <xref:System.Windows.Controls.Primitives.Popup> wird die Position am unteren Bildschirmrand neu angeordnet, und der vertikale Abstand zwischen dem Ziel Ursprung und dem Popup Ausrichtungs Punkt ist kleiner als 100. Dies wird in der folgenden Abbildung veranschaulicht.  
  
 ![Popup, das sich am Bildschirmrand anpasst](./media/popup-placement-behavior/popup-placement-relative-screen-edge.png "Popup richtet sich am Bildschirmrand aus.")    
  
### <a name="changing-the-popup-alignment-point"></a>Ändern des Popupausrichtungspunkts  
 Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> , <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint> oderist<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>, ändert sich der Popup Ausrichtungs Punkt, wenn das Popup auf den unteren oder rechten Bildschirmrand trifft <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>.  
  
 In der folgenden Abbildung wird veranschaulicht, dass der Popup Ausrichtungs Punkt die untere linke <xref:System.Windows.Controls.Primitives.Popup>Ecke <xref:System.Windows.Controls.Primitives.Popup>von ist, wenn der untere Bildschirmrand den gesamten oder einen Teil von verbirgt.  
  
 ![Neuer Ausrichtungs Punkt durch unteren Bildschirmrand](./media/popup-placement-behavior/popup-placement-relative-point-screen-edge.png "Popup stößt auf den unteren Rand des Bildschirms und ändert den Popup Ausrichtungs Punkt.")  

 In der folgenden Abbildung wird veranschaulicht, <xref:System.Windows.Controls.Primitives.Popup> dass der Popup Ausrichtungs Punkt die obere rechte Ecke <xref:System.Windows.Controls.Primitives.Popup>von ist, wenn der durch den rechten Bildschirmrand ausgeblendet wird.  
  
 ![Neuer Popup Ausrichtungs Punkt aufgrund von Bildschirmrand](./media/popup-placement-behavior/popup-placement-relative-point-right-screen-edge.png "Popup trifft den rechten Rand des Bildschirms und ändert den Popup Ausrichtungs Punkt.")    
  
 Wenn die unteren und rechten Bildschirmränder <xref:System.Windows.Controls.Primitives.Popup> trifft,istderPopupAusrichtungsPunktdieuntererechteEckedes.<xref:System.Windows.Controls.Primitives.Popup>  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Ändern des Zielursprungs und des Popupausrichtungspunkts  
 Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> , <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> ,,<xref:System.Windows.Controls.Primitives.PlacementMode.Top>oder ist,ändernsichderZielUrsprungundderPopupAusrichtungsPunkt,wenneinbestimmterBildschirmrandgefundenwird.<xref:System.Windows.Controls.Primitives.PlacementMode.Right> <xref:System.Windows.Controls.Primitives.PlacementMode.Left> <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>  Der Bildschirmrand, der bewirkt, dass die Position geändert wird <xref:System.Windows.Controls.Primitives.PlacementMode> , hängt vom Wert ab.  
  
 In der folgenden Abbildung wird veranschaulicht <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> , <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> dass wenn <xref:System.Windows.Controls.Primitives.Popup> und den unteren Bildschirmrand trifft, der Ziel Ursprung die linke obere Ecke des Zielbereichs und der Popup Ausrichtungs Punkt die untere linke Ecke des <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungs Punkt durch unteren Bildschirmrand] Die (./media/popup-placement-behavior/popup-placement-bottom-screen-edge.png "Platzierung erfolgt unten, und das Popup stößt auf den unteren Rand des Bildschirms.")    
  
 In der folgenden Abbildung wird veranschaulicht <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> , <xref:System.Windows.Controls.Primitives.PlacementMode.Left> dass wenn <xref:System.Windows.Controls.Primitives.Popup> ist und der linke Bildschirmrand stößt, der Ziel Ursprung die obere rechte Ecke des Zielbereichs und der Popup Ausrichtungs Punkt die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungs Punkt aufgrund von left Screen Edge] Die (./media/popup-placement-behavior/popup-placement-left-screen-edge.png "Platzierung ist \"Left\", und das Popup stößt auf den linken Rand des Bildschirms.")  
  
 In der folgenden Abbildung wird veranschaulicht <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> , <xref:System.Windows.Controls.Primitives.PlacementMode.Right> dass wenn <xref:System.Windows.Controls.Primitives.Popup> und den rechten Bildschirmrand trifft, der Ziel Ursprung die linke obere Ecke des Zielbereichs und der Popup Ausrichtungs Punkt die obere rechte Ecke des <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungs Punkt aufgrund rechter Bildschirm Kante] Die (./media/popup-placement-behavior/popup-placement-right-screen-edge.png "Platzierung ist \"Right\", und das Popup stößt auf den rechten Bildschirmrand.")  

 In der folgenden Abbildung wird veranschaulicht <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> , <xref:System.Windows.Controls.Primitives.PlacementMode.Top> dass wenn <xref:System.Windows.Controls.Primitives.Popup> ist und der obere Bildschirmrand trifft, der Ziel Ursprung die linke untere Ecke des Zielbereichs und der Popup Ausrichtungs Punkt die linke obere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungs Punkt aufgrund des oberen Bildschirm Rands] Die (./media/popup-placement-behavior/popup-placement-top-screen-edge.png "Platzierung ist \"Top\", und das Popup stößt auf den oberen Rand des Bildschirms.")  
  
 In der folgenden Abbildung wird veranschaulicht <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> , <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> dass wenn <xref:System.Windows.Controls.Primitives.Popup> und den unteren Bildschirmrand trifft, der Ziel Ursprung die linke obere Ecke des Zielbereichs (die Begrenzungen des Mauszeigers) und die Popup Ausrichtung. der Punkt ist die linke untere Ecke des <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![neuer Ausrichtungs Punkt aufgrund der Maus in der Nähe der Bildschirm Kante] Die (./media/popup-placement-behavior/popup-placement-mouse-screen-edge.png "Platzierung ist \"Mouse\", und das Popup stößt auf den unteren Rand des Bildschirms.")    
  
### <a name="customizing-popup-placement"></a>Anpassen der Popupplatzierung  
 Sie können den Ziel Ursprung und den Popup Ausrichtungs Punkt anpassen, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> indem Sie <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>die-Eigenschaft auf festlegen. Definieren Sie dann <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> einen Delegaten, der einen Satz möglicher Platzierungs Punkte und primäre Achsen (in der bevorzugten Reihenfolge) <xref:System.Windows.Controls.Primitives.Popup>für den zurückgibt. Der Punkt, der den größten Teil des <xref:System.Windows.Controls.Primitives.Popup> anzeigt, wird ausgewählt.  Die Position des <xref:System.Windows.Controls.Primitives.Popup> wird automatisch angepasst, wenn der <xref:System.Windows.Controls.Primitives.Popup> am Bildschirmrand ausgeblendet ist. Ein Beispiel finden Sie unter [Angeben einer benutzerdefinierten Popupposition](how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>Siehe auch

- [Beispiel für das Platzieren eines Popups](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS)
