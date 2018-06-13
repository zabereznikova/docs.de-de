---
title: Verhalten beim Platzieren von Popups
ms.date: 03/30/2017
helpviewer_keywords:
- popups [WPF]
- Popup control [WPF], placing
- placing popups [WPF]
- positioning popups [WPF]
ms.assetid: fbf642e9-f670-4efd-a7af-a67468a1c8e1
ms.openlocfilehash: 3aef3d7863bc02aa4164b1fc9ef4464fbe799cb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558342"
---
# <a name="popup-placement-behavior"></a>Verhalten beim Platzieren von Popups
Ein <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement zeigt den Inhalt in einem separaten Fenster, die über eine Anwendung gleitet. Sie können angeben, der die Position des eine <xref:System.Windows.Controls.Primitives.Popup> relativ zu einem Steuerelement, die Maus oder den Bildschirm mit den <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> Eigenschaften.  Diese Eigenschaften arbeiten zusammen, um die Flexibilität in die Position des angeben der <xref:System.Windows.Controls.Primitives.Popup>.  
  
> [!NOTE]
>  Die <xref:System.Windows.Controls.ToolTip> und <xref:System.Windows.Controls.ContextMenu> Klassen auch definieren diese fünf Eigenschaften und Verhalten sich ähnlich.  
  

  
<a name="Positioning"></a>   
## <a name="positioning-the-popup"></a>Positionieren von Popups  
 Die Platzierung von einer <xref:System.Windows.Controls.Primitives.Popup> kann relativ zu einer <xref:System.Windows.UIElement> oder den gesamten Bildschirm.  Das folgende Beispiel erstellt vier <xref:System.Windows.Controls.Primitives.Popup> Steuerelemente relativ zu einem <xref:System.Windows.UIElement>– in diesem Fall kann ein Bild. Alle der <xref:System.Windows.Controls.Primitives.Popup> Steuerelemente verfügen über die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> -Eigenschaftensatz auf `image1`, aber jedes <xref:System.Windows.Controls.Primitives.Popup> verfügt über einen anderen Wert für die Platzierungseigenschaft.  
  
 [!code-xaml[PopupPositionSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#3)]  
  
 Die folgende Abbildung zeigt das Bild und die <xref:System.Windows.Controls.Primitives.Popup> Steuerelemente  
  
 ![Bild mit vier Popup-Steuerelementen](../../../../docs/framework/wpf/controls/media/popupplacementintro.png "PopupPlacementIntro")  
Bild mit vier Popups  
  
 Dieses einfache Beispiel veranschaulicht das Festlegen der <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> und <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Eigenschaften, aber mithilfe der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> Eigenschaften, Sie haben noch mehr Kontrolle über die Where der <xref:System.Windows.Controls.Primitives.Popup> positioniert ist.  
  
<a name="Definitions"></a>   
## <a name="definitions-of-terms-the-anatomy-of-a-popup"></a>Begriffsdefinition: der Aufbau eines Popups  
 Die folgenden Begriffe sind hilfreich zu verstehen, wie die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> Eigenschaften aufeinander beziehen und die <xref:System.Windows.Controls.Primitives.Popup>:  
  
-   Das Zielobjekt  
  
-   Der Zielbereich  
  
-   Der Zielursprung  
  
-   Der Popupausrichtungspunkt  
  
 Diese Begriffe stellen eine bequeme Möglichkeit zum Verweisen auf verschiedene Aspekte der <xref:System.Windows.Controls.Primitives.Popup> und das Steuerelement, das diesem zugeordnet ist.  
  
### <a name="target-object"></a>Das Zielobjekt  
 Die *Zielobjekt* ist das Element, das die <xref:System.Windows.Controls.Primitives.Popup> zugeordnet ist. Wenn die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> Eigenschaft festgelegt ist, gibt das Zielobjekt.  Wenn <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> nicht festgelegt ist, und die <xref:System.Windows.Controls.Primitives.Popup> besitzt ein übergeordnetes Element das übergeordnete Element ist das Zielobjekt.  Liegt keine <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> Wert und kein übergeordnetes Element kein Zielobjekt vorhanden ist und die <xref:System.Windows.Controls.Primitives.Popup> relativ zu dem Bildschirm befindet.  
  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Primitives.Popup> also das untergeordnete Element des eine <xref:System.Windows.Controls.Canvas>.  Im Beispiel wird nicht festgelegt. die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> Eigenschaft auf die <xref:System.Windows.Controls.Primitives.Popup>. Der Standardwert für <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom?displayProperty=nameWithType>, sodass die <xref:System.Windows.Controls.Primitives.Popup> wird unterhalb der <xref:System.Windows.Controls.Canvas>.  
  
 [!code-xaml[PopupPositionSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#1)]  
  
 Die folgende Abbildung zeigt, dass die <xref:System.Windows.Controls.Primitives.Popup> positioniert ist, relativ zu den <xref:System.Windows.Controls.Canvas>.  
  
 ![Popup-Steuerelement ohne PlacementTarget](../../../../docs/framework/wpf/controls/media/popupplacementnoplacementtarget.PNG "PopupPlacementNoPlacementTarget")  
Popup ohne PlacementTarget  
  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Primitives.Popup> also das untergeordnete Element des eine <xref:System.Windows.Controls.Canvas>, dieses Mal jedoch die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> auf festgelegt ist `ellipse1`, sodass das Popupfenster angezeigt, unter wird der <xref:System.Windows.Shapes.Ellipse>.  
  
 [!code-xaml[PopupPositionSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#2)]  
  
 Die folgende Abbildung zeigt, dass die <xref:System.Windows.Controls.Primitives.Popup> positioniert ist, relativ zu den <xref:System.Windows.Shapes.Ellipse>.  
  
 ![Relativ zu einer Ellipse platziertes Popup](../../../../docs/framework/wpf/controls/media/popupplacementwithplacementtarget.PNG "PopupPlacementWithPlacementTarget")  
Popup mit PlacementTarget  
  
> [!NOTE]
>  Für <xref:System.Windows.Controls.ToolTip>, der Standardwert von <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>.  Für <xref:System.Windows.Controls.ContextMenu>, der Standardwert von <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>. Diese Werte werden später in „Zusammenwirken der Eigenschaften“ erklärt.  
  
### <a name="target-area"></a>Der Zielbereich  
 Die *Zielbereich* ist der Bereich auf dem Bildschirm, der <xref:System.Windows.Controls.Primitives.Popup> relativ ist. In den vorherigen Beispielen die <xref:System.Windows.Controls.Primitives.Popup> ausgerichtet ist, mit den Grenzen des Zielobjekts, aber in einigen Fällen die <xref:System.Windows.Controls.Primitives.Popup> zu anderen Grenzen ausgerichtet ist auch dann, wenn die <xref:System.Windows.Controls.Primitives.Popup> verfügt über ein Zielobjekt.  Wenn die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Eigenschaft festgelegt ist, der Zielbereich unterscheidet sich die Grenzen des Zielobjekts.  
  
 Das folgende Beispiel erstellt zwei <xref:System.Windows.Controls.Canvas> Objekte aufweist, jeweils mit einem <xref:System.Windows.Shapes.Rectangle> und ein <xref:System.Windows.Controls.Primitives.Popup>.  In beiden Fällen das Zielobjekt für den <xref:System.Windows.Controls.Primitives.Popup> ist die <xref:System.Windows.Controls.Canvas>. Die <xref:System.Windows.Controls.Primitives.Popup> in der ersten <xref:System.Windows.Controls.Canvas> hat die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> festgelegt wird, mit dessen <xref:System.Windows.Rect.X%2A>, <xref:System.Windows.Rect.Y%2A>, <xref:System.Windows.Rect.Width%2A>, und <xref:System.Windows.Rect.Height%2A> Eigenschaften, die auf 50, 50, 50 und 100 festgelegt. Die <xref:System.Windows.Controls.Primitives.Popup> in der zweiten <xref:System.Windows.Controls.Canvas> verfügt nicht über die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> festgelegt.  Daher die erste <xref:System.Windows.Controls.Primitives.Popup> unten positioniert ist die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> und das zweite <xref:System.Windows.Controls.Primitives.Popup> befindet sich unterhalb der <xref:System.Windows.Controls.Canvas>. Jede <xref:System.Windows.Controls.Canvas> enthält auch eine <xref:System.Windows.Shapes.Rectangle> , besitzt die gleichen Grenzen wie die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> für die erste <xref:System.Windows.Controls.Primitives.Popup>.  Beachten Sie, dass die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> erstellt keine visible-Element in der Anwendung ein, das Beispiel erstellt eine <xref:System.Windows.Shapes.Rectangle> zur Darstellung der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>.  
  
 [!code-xaml[PopupPositionSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#4)]  
  
 Die folgende Abbildung zeigt das Ergebnis des vorherigen Beispiels.  
  
 ![Popup mit und ohne PlacementRectangle](../../../../docs/framework/wpf/controls/media/popupplacementplacementrectangle.PNG "PopupPlacementPlacementRectangle")  
Popup mit und ohne PlacementRectangle  
  
### <a name="target-origin-and-popup-alignment-point"></a>Zielursprung und Popupausrichtungspunkt  
 Der *Zielursprung* und *Popupausrichtungspunkt* sind Bezugspunkte für die Positionierung im Zielbereich und im Popup. Sie können die <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> Eigenschaften, um das Popup aus dem Zielbereich versetzt.  Die <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> sind relativ zum Zielursprung und das Popup-Ausrichtungspunkt an. Der Wert, der die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Eigenschaft bestimmt, in dem sich der Ursprung und Popup befinden.  
  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.Primitives.Popup> und legt die <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> Eigenschaften auf 20.  Die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> -Eigenschaftensatz auf <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> (Standard), daher ist des Ursprungs Ziel der unteren linken Ecke des Zielbereichs und der Popup-Ausrichtungspunkt an ist die linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.  
  
 [!code-xaml[PopupPositionSnippet#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupPositionSnippet/CS/Window1.xaml#5)]  
  
 Die folgende Abbildung zeigt das Ergebnis des vorherigen Beispiels.  
  
 ![Popup-Platzierung mit Zielursprungsausrichtungspunkt](../../../../docs/framework/wpf/controls/media/popupplacementtargetoriginalignmentpoint.PNG "PopupPlacementTargetOriginAlignmentPoint")  
Popup mit HorizontalOffset und VerticalOffset  
  
<a name="How"></a>   
## <a name="how-the-properties-work-together"></a>Zusammenwirken der Eigenschaften  
 Die Werte der <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, und <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> müssen zusammen berücksichtigt werden, um das richtige Zielbereich Zielursprung und Popup-Ausrichtungspunkt an zu ermitteln.  Z. B. wenn der Wert der <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, es wurde kein Zielobjekt der <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ignoriert, und der Zielbereich ist die Grenzen des Mauszeigers. Andererseits, wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordneten bestimmt das Zielobjekt und <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> legt den Zielbereich.  
  
 Die folgende Tabelle beschreibt das Zielobjekt, Zielbereich Zielursprung und Popup-Ausrichtungspunkt an und gibt an, ob <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> und <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> werden verwendet, für die einzelnen <xref:System.Windows.Controls.Primitives.PlacementMode> -Enumerationswert.  
  
|PlacementMode|Das Zielobjekt|Der Zielbereich|Der Zielursprung|Der Popupausrichtungspunkt|  
|-------------------|-------------------|-----------------|-------------------|---------------------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Der Bildschirm oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zu dem Bildschirm.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Der Bildschirm oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zu dem Bildschirm.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke untere Ecke des Zielbereichs|Die linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die Mitte des Zielbereichs|Das Zentrum des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Custom>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Definiert durch den <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|Definiert durch den <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Der oberen rechten Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Die Grenzen des Mauszeigers <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird ignoriert.|Die linke untere Ecke des Zielbereichs|Die linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Nicht zutreffend. <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> wird ignoriert.|Die Grenzen des Mauszeigers <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> wird ignoriert.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Die linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die rechte obere Ecke des Zielbereichs|Die linke obere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|<xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> oder übergeordnetes Element.|Das Zielobjekt oder <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist die Eigenschaft festgelegt.  Die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> ist relativ zum Zielobjekt.|Die linke obere Ecke des Zielbereichs|Der unteren linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
  
 Die folgenden Abbildungen zeigen die <xref:System.Windows.Controls.Primitives.Popup>, Zielbereich Zielursprung und Ausrichtungspunkt zeigen für jede <xref:System.Windows.Controls.Primitives.PlacementMode> Wert. In jeder Abbildung ist der Zielbereich Gelb, und die <xref:System.Windows.Controls.Primitives.Popup> ist Blau.  
  
 ![Popup mit absolute- oder AbsolutePoint-Platzierung](../../../../docs/framework/wpf/controls/media/popupplacementabsolute.png "PopupPlacementAbsolute")  
Die Platzierung ist „Absolute“ oder „AbsolutePoint“  
  
 ![Popup mit Bottom-Platzierung](../../../../docs/framework/wpf/controls/media/popupplacementbottom.png "PopupPlacementBottom")  
Die Platzierung ist „Bottom“  
  
 ![Popup mit Center-Platzierung](../../../../docs/framework/wpf/controls/media/popupplacementcenter.png "PopupPlacementCenter")  
Die Platzierung ist „Center“  
  
 ![Popup mit Left-Platzierung](../../../../docs/framework/wpf/controls/media/popupplacementleft.png "PopupPlacementLeft")  
Die Platzierung ist „Left“  
  
 ![Popup mit Mouse-Platzierung](../../../../docs/framework/wpf/controls/media/popupplacementmouse.png "PopupPlacementMouse")  
Die Platzierung ist „Mouse“  
  
 ![Popup mit MousePoint-Platzierung](../../../../docs/framework/wpf/controls/media/popupplacementmousepoint.png "PopupPlacementMousePoint")  
Die Platzierung ist „MousePoint“  
  
 ![Popup mit relative- oder RelativePoint-Platzierung](../../../../docs/framework/wpf/controls/media/popupplacementrelative.png "PopupPlacementRelative")  
Die Platzierung ist „Relative“ oder „RelativePoint“  
  
 ![Popup mit Right-Platzierung](../../../../docs/framework/wpf/controls/media/popupplacementright.png "PopupPlacementRight")  
Die Platzierung ist „Right“  
  
 ![Popup mit Top-Platzierung](../../../../docs/framework/wpf/controls/media/popupplacementtop.png "PopupPlacementTop")  
Die Platzierung ist „Top“  
  
<a name="When"></a>   
## <a name="when-the-popup-encounters-the-edge-of-the-screen"></a>Wenn das Popup auf einen Bildschirmrand trifft  
 Aus Gründen der Sicherheit einer <xref:System.Windows.Controls.Primitives.Popup> kann nicht ausgeblendet werden, indem am Rand eines Bildschirms. Einer der drei folgenden Punkte geschieht bei der <xref:System.Windows.Controls.Primitives.Popup> trifft eine Bildschirmkante:  
  
-   Das Popup richtet sich selbst am Bildschirm Rand, die verdecken würde die <xref:System.Windows.Controls.Primitives.Popup>.  
  
-   Das Popup verwendet einen anderen Popupausrichtungspunkt.  
  
-   Das Popup verwendet einen anderen Zielursprungs und Popupausrichtungspunkt.  
  
 Diese Optionen werden weiter unten in diesem Abschnitt beschrieben.  
  
 Das Verhalten von der <xref:System.Windows.Controls.Primitives.Popup> Wenn festgestellt wird eine Bildschirmkante hängt vom Wert von der <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> -Eigenschaft und die Bildschirmrand das Popup stößt. In der folgenden Tabelle wird das Verhalten zusammengefasst. wenn die <xref:System.Windows.Controls.Primitives.Popup> trifft eine Bildschirmkante für jede <xref:System.Windows.Controls.Primitives.PlacementMode> Wert.  
  
|PlacementMode|Oberer Rand|Unterer Rand|Linker Rand|Rechter Rand|  
|-------------------|--------------|-----------------|---------------|----------------|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>|Richtet sich am oberen Rand aus|Das Popup-Ausrichtungspunkt an ändert sich in der unteren linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Das Popup-Ausrichtungspunkt an ändert sich in der oberen rechten Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>|Richtet sich am oberen Rand aus|Der Zielursprung ändert sich in der oberen linken Ecke des Zielbereichs und das Popup-Ausrichtungspunkt an ändert sich in der unteren linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Center>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Left>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Der Zielursprung ändert sich in der oberen rechten Ecke des Zielbereichs und das Popup-Ausrichtungspunkt an ändert sich in der oberen linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>|Richtet sich am oberen Rand aus|Der Zielursprung ändert sich in der oberen linken Ecke des Zielbereichs (die Grenzen des Mauszeigers) und das Popup-Ausrichtungspunkt an ändert sich in der unteren linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>|Richtet sich am oberen Rand aus|Das Popup-Ausrichtungspunkt an ändert sich in der unteren linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Der Ausrichtungspunkt wird auf die obere rechte Ecke des Popups geändert.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Relative>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>|Richtet sich am oberen Rand aus|Das Popup-Ausrichtungspunkt an ändert sich in der unteren linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|Richtet sich am linken Rand aus|Der Ausrichtungspunkt wird auf die obere rechte Ecke des Popups geändert.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Right>|Richtet sich am oberen Rand aus|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Der Zielursprung ändert sich in der oberen linken Ecke des Zielbereichs und das Popup-Ausrichtungspunkt an ändert sich in der oberen rechten Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.|  
|<xref:System.Windows.Controls.Primitives.PlacementMode.Top>|Der Zielursprung ändert sich in der unteren linken Ecke des Zielbereichs und das Popup-Ausrichtungspunkt an ändert sich in der oberen linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>. Aktiviert ist, dies ist genauso wie beim <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>.|Richtet sich am unteren Rand aus|Richtet sich am linken Rand aus|Richtet sich am rechten Rand aus|  
  
### <a name="aligning-to-the-screen-edge"></a>Ausrichten am Bildschirmrand  
 Ein <xref:System.Windows.Controls.Primitives.Popup> können ausrichten, die an den Rand des Bildschirms durch Neupositionieren selbst daher die gesamte <xref:System.Windows.Controls.Primitives.Popup> auf dem Bildschirm sichtbar ist.  In diesem Fall der Abstand zwischen dem Ursprung und Popup unterscheidet sich möglicherweise von den Werten der <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A>. Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Absolute>, <xref:System.Windows.Controls.Primitives.PlacementMode.Center>, oder <xref:System.Windows.Controls.Primitives.PlacementMode.Relative>die <xref:System.Windows.Controls.Primitives.Popup> richtet sich selbst an jeder Bildschirmkante aus.  Nehmen wir beispielsweise an, die eine <xref:System.Windows.Controls.Primitives.Popup> hat <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> festgelegt <xref:System.Windows.Controls.Primitives.PlacementMode.Relative> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffset%2A> auf 100 festgelegt.  Wenn der unteren Rand des Bildschirms ganz oder teilweise verdeckt die <xref:System.Windows.Controls.Primitives.Popup>die <xref:System.Windows.Controls.Primitives.Popup> positioniert selbst am unteren Rand des Bildschirms und dem vertikalen Abstand zwischen dem Zielursprung und Popup-Ausrichtungspunkt an ist kleiner als 100. Dies wird in der folgenden Abbildung veranschaulicht.  
  
 ![Popups, die auf den Rand des Bildschirms ausgerichtet](../../../../docs/framework/wpf/controls/media/popupplacementrelativescreenedge.png "PopupPlacementRelativeScreenEdge")  
Popup richtet sich am Bildschirmrand aus  
  
### <a name="changing-the-popup-alignment-point"></a>Ändern des Popupausrichtungspunkts  
 Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.AbsolutePoint>, <xref:System.Windows.Controls.Primitives.PlacementMode.RelativePoint>, oder <xref:System.Windows.Controls.Primitives.PlacementMode.MousePoint>, Popup-Ausrichtungspunkt an ändert, wenn das Popup unten oder rechter Bildschirmkante stößt.  
  
 Die folgende Abbildung zeigt, dass bei der unteren Bildschirmrand ganz oder teilweise Blendet die <xref:System.Windows.Controls.Primitives.Popup>, Popup-Ausrichtungspunkt an ist die linke untere Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungspunkt an unterer Bildschirmkante](../../../../docs/framework/wpf/controls/media/popupplacementrelativepointscreenedge.png "PopupPlacementRelativePointScreenEdge")  
Das Popup trifft auf den unteren Bildschirmrand und ändert den Popupausrichtungspunkt.  
  
 Die folgende Abbildung zeigt, dass wenn die <xref:System.Windows.Controls.Primitives.Popup> wird ausgeblendet, vom rechten Bildschirmrand Popup-Ausrichtungspunkt an der oberen rechten Ecke des ist die <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Popup-Ausrichtungspunkt an Bildschirmkante](../../../../docs/framework/wpf/controls/media/popupplacementrelativepointrightscreenedge.png "PopupPlacementRelativePointRightScreenEdge")  
Das Popup stößt auf den rechten Bildschirmrand und ändert den Popupausrichtungspunkt.  
  
 Wenn die <xref:System.Windows.Controls.Primitives.Popup> trifft die unteren und rechten Bildschirmrand Kanten, Popup-Ausrichtungspunkt an ist die unten rechts auf der die <xref:System.Windows.Controls.Primitives.Popup>.  
  
### <a name="changing-the-target-origin-and-popup-alignment-point"></a>Ändern des Zielursprungs und des Popupausrichtungspunkts  
 Wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom>, <xref:System.Windows.Controls.Primitives.PlacementMode.Left>, <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse>, <xref:System.Windows.Controls.Primitives.PlacementMode.Right>, oder <xref:System.Windows.Controls.Primitives.PlacementMode.Top>, die Ziel-Ursprungs- und der Popup-Ausrichtung zeigen ändern, wenn eine bestimmte Bildschirmkante kommt.  Hängt von der Bildschirmkante aus, die bewirkt, die Position dass so ändern Sie die <xref:System.Windows.Controls.Primitives.PlacementMode> Wert.  
  
 Die folgende Abbildung zeigt, dass wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Bottom> und die <xref:System.Windows.Controls.Primitives.Popup> erkennt den unteren Bildschirmrand Zielursprung der oberen linken Ecke des Zielbereichs und das Popup-Ausrichtungspunkt an der unteren linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungspunkt an unterer Bildschirmkante](../../../../docs/framework/wpf/controls/media/popupplacementbottomscreenedge.png "PopupPlacementBottomScreenEdge")  
Die Platzierung ist „Bottom“, und das Popup stößt auf den unteren Rand des Bildschirms  
  
 Die folgende Abbildung zeigt, dass wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Left> und <xref:System.Windows.Controls.Primitives.Popup> findet der Linker Bildschirmkante Zielursprung ist der oberen rechten Ecke des Zielbereichs und das Popup-Ausrichtungspunkt an der linken oberen Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungspunkt an Linker Bildschirmkante](../../../../docs/framework/wpf/controls/media/popupplacementleftscreenedge.png "PopupPlacementLeftScreenEdge")  
Die Platzierung ist „Left“, und das Popup stößt auf den linken Bildschirmrand.  
  
 Die folgende Abbildung zeigt, dass wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Right> und die <xref:System.Windows.Controls.Primitives.Popup> trifft die rechter Bildschirmkante Zielursprung der oberen linken Ecke des Zielbereichs und das Popup-Ausrichtungspunkt an der oberen rechten Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungspunkt an rechter Bildschirmkante](../../../../docs/framework/wpf/controls/media/popupplacementrightscreenedge.png "PopupPlacementRightScreenEdge")  
Die Platzierung ist „Right“, und das Popup stößt auf den rechten Bildschirmrand  
  
 Die folgende Abbildung zeigt, dass wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Top> und die <xref:System.Windows.Controls.Primitives.Popup> am oberen Bildschirmrand trifft Zielursprung der unteren linken Ecke des Zielbereichs und das Popup-Ausrichtungspunkt an der linken oberen Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungspunkt an oberer Bildschirmkante](../../../../docs/framework/wpf/controls/media/popupplacementtopscreenedge.png "PopupPlacementTopScreenEdge")  
Die Platzierung ist „Top“, und das Popup stößt auf den oberen Bildschirmrand  
  
 Die folgende Abbildung zeigt, dass wenn <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> ist <xref:System.Windows.Controls.Primitives.PlacementMode.Mouse> und <xref:System.Windows.Controls.Primitives.Popup> auf den unteren Bildschirmrand stößt der Zielursprung ist der linken oberen Ecke des Zielbereichs (die Grenzen des Mauszeigers) und dem Ausrichtungspunkt ist der unteren linken Ecke des der <xref:System.Windows.Controls.Primitives.Popup>.  
  
 ![Neuer Ausrichtungspunkt an Maus in der Nähe Bildschirmkante](../../../../docs/framework/wpf/controls/media/popupplacementmousescreenedge.png "PopupPlacementMouseScreenEdge")  
Die Platzierung ist „Mouse“, und das Popup stößt auf den unteren Rand des Bildschirms.  
  
### <a name="customizing-popup-placement"></a>Anpassen der Popupplatzierung  
 Sie können das Ziel Ursprungs- und der Popup-Ausrichtungspunkt an anpassen, indem Sie die Einstellung der <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Eigenschaft <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Definieren Sie dann eine <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> Delegat, der für eine Reihe von möglichen Platzierung Punkte und Primärachsen (in Prioritätsreihenfolge) gibt die <xref:System.Windows.Controls.Primitives.Popup>. Der Punkt, der den größten Teil zeigt die <xref:System.Windows.Controls.Primitives.Popup> ausgewählt ist.  Die Position des der <xref:System.Windows.Controls.Primitives.Popup> wird automatisch angepasst, wenn die <xref:System.Windows.Controls.Primitives.Popup> an der Ecke des Bildschirms ausgeblendet ist. Ein Beispiel finden Sie unter [Angeben einer benutzerdefinierten Popupposition](../../../../docs/framework/wpf/controls/how-to-specify-a-custom-popup-position.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Beispiel für das Platzieren eines Popups](http://go.microsoft.com/fwlink/?LinkID=160032)
