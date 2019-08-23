---
title: Übersicht über Popups
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: 7e6977737d362fd0df6321702bb8a1ac6cad66e0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951426"
---
# <a name="popup-overview"></a>Übersicht über Popups
Das <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement bietet eine Möglichkeit, Inhalte in einem separaten Fenster anzuzeigen, das im aktuellen Anwendungsfenster relativ zu einem festgelegten Element oder einer bestimmten Bildschirm Koordinate schwebt. Dieses Thema enthält eine <xref:System.Windows.Controls.Primitives.Popup> Einführung in das-Steuerelement und stellt Informationen zur Verwendung bereit.  

<a name="What_Is_a_Popup_"></a>   
## <a name="what-is-a-popup"></a>Was ist ein Popup?  
 Ein <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement zeigt Inhalt in einem separaten Fenster relativ zu einem Element oder einem Punkt auf dem Bildschirm an. Wenn der <xref:System.Windows.Controls.Primitives.Popup> sichtbar ist, wird <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> die-Eigenschaft auf `true`festgelegt.  
  
> [!NOTE]
> Eine <xref:System.Windows.Controls.Primitives.Popup> wird nicht automatisch geöffnet, wenn der Mauszeiger über das übergeordnete Objekt bewegt wird. Wenn ein <xref:System.Windows.Controls.Primitives.Popup> automatisch geöffnet werden soll, verwenden Sie die- <xref:System.Windows.Controls.ToolTipService> Klasse oder die <xref:System.Windows.Controls.ToolTip> -Klasse. Weitere Informationen finden Sie unter [Übersicht über die QuickInfo](tooltip-overview.md).  
  
<a name="APopupExample"></a>   
## <a name="creating-a-popup"></a>Erstellen eines Popups  
 Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement definiert wird, das das <xref:System.Windows.Controls.Button> untergeordnete Element eines-Steuer Elements ist. Da eine <xref:System.Windows.Controls.Button> nur über ein untergeordnetes Element verfügen kann, wird in diesem Beispiel der <xref:System.Windows.Controls.Button> Text für <xref:System.Windows.Controls.Primitives.Popup> die Steuerelemente <xref:System.Windows.Controls.StackPanel>und in einem abgelegt. Der Inhalt von <xref:System.Windows.Controls.Primitives.Popup> wird in einem <xref:System.Windows.Controls.TextBlock> -Steuerelement angezeigt, das seinen Text in einem separaten Fenster anzeigt, das über das Anwendungsfenster in <xref:System.Windows.Controls.Button> der Nähe des zugehörigen Steuer Elements schwebt.  
  
 [!code-xaml[PopupSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>   
## <a name="controls-that-implement-a-popup"></a>Steuerelemente, die ein Popup implementieren  
 Sie können Steuer <xref:System.Windows.Controls.Primitives.Popup> Elemente in anderen Steuerelementen erstellen. Die folgenden Steuerelemente implementieren <xref:System.Windows.Controls.Primitives.Popup> das-Steuerelement für bestimmte Verwendungszwecke:  
  
- <xref:System.Windows.Controls.ToolTip> Wenn Sie eine QuickInfo für ein Element erstellen möchten, verwenden Sie <xref:System.Windows.Controls.ToolTip> die <xref:System.Windows.Controls.ToolTipService> -Klasse und die-Klasse. Weitere Informationen finden Sie unter [Übersicht über die QuickInfo](tooltip-overview.md).  
  
- <xref:System.Windows.Controls.ContextMenu> Wenn Sie ein Kontextmenü für ein Element erstellen möchten, verwenden Sie das <xref:System.Windows.Controls.ContextMenu> -Steuerelement. Weitere Informationen finden Sie unter [Übersicht über ContextMenu](contextmenu-overview.md).  
  
- <xref:System.Windows.Controls.ComboBox> Wenn Sie ein Auswahl Steuerelement mit einem Dropdown-Listenfeld erstellen möchten, das angezeigt oder ausgeblendet werden kann, verwenden Sie <xref:System.Windows.Controls.ComboBox> das-Steuerelement.  
  
- <xref:System.Windows.Controls.Expander> Wenn Sie ein Steuerelement erstellen möchten, das einen Header mit einem redusible-Bereich anzeigt, in dem Inhalt <xref:System.Windows.Controls.Expander> angezeigt wird, verwenden Sie das-Steuerelement. Weitere Informationen finden Sie unter [Übersicht über Expander-Steuerelemente](expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>   
## <a name="popup-behavior-and-appearance"></a>Popup-Verhalten und -Darstellung  
 Das <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement stellt Funktionen bereit, die es Ihnen ermöglichen, das Verhalten und die Darstellung anzupassen. Beispielsweise können Sie das Verhalten für öffnen und schließen, Animation, Deckkraft und Bitmapeffekte sowie <xref:System.Windows.Controls.Primitives.Popup> Größe und Position festlegen.  
  
<a name="OpenandCloseBehavior"></a>   
### <a name="open-and-close-behavior"></a>Öffnungs- und Schließverhalten  
 Ein <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement zeigt seinen Inhalt <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> an, wenn die `true`-Eigenschaft auf festgelegt ist. Standardmäßig bleibt <xref:System.Windows.Controls.Primitives.Popup> geöffnet, bis die <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> -Eigenschaft auf `false`festgelegt ist. Sie können das Standardverhalten jedoch ändern, indem Sie die <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> -Eigenschaft `false`auf festlegen. Wenn Sie diese Eigenschaft auf `false`festlegen, enthält das Inhalts Fenster die <xref:System.Windows.Controls.Primitives.Popup> Maus Aufzeichnung. Das <xref:System.Windows.Controls.Primitives.Popup> verliert die Maus Aufzeichnung, und das Fenster wird geschlossen, wenn ein Maus <xref:System.Windows.Controls.Primitives.Popup> Ereignis außerhalb des Fensters auftritt.  
  
 Das <xref:System.Windows.Controls.Primitives.Popup.Opened> - <xref:System.Windows.Controls.Primitives.Popup.Closed> Ereignis und das-Ereignis <xref:System.Windows.Controls.Primitives.Popup> werden ausgelöst, wenn das Inhalts Fenster geöffnet oder geschlossen ist.  
  
<a name="Animation"></a>   
### <a name="animation"></a>Animation  
 Das <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement verfügt über integrierte Unterstützung für Animationen, die in der Regel mit Verhalten wie einblenden und Folie verknüpft sind. Sie können diese Animationen aktivieren, indem Sie die <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> -Eigenschaft auf <xref:System.Windows.Controls.Primitives.PopupAnimation> einen-Enumerationswert festlegen. Damit <xref:System.Windows.Controls.Primitives.Popup> Animationen ordnungsgemäß funktionieren, müssen Sie die <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> -Eigenschaft auf `true`festlegen.  
  
 Sie können auch Animationen wie <xref:System.Windows.Media.Animation.Storyboard> auf das <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement anwenden.  
  
<a name="OpacityandBitmapEffects"></a>   
### <a name="opacity-and-bitmap-effects"></a>Deckkraft und Bitmapeffekte  
 Die <xref:System.Windows.UIElement.Opacity%2A> -Eigenschaft für <xref:System.Windows.Controls.Primitives.Popup> ein Steuerelement hat keine Auswirkung auf seinen Inhalt. Standardmäßig ist das <xref:System.Windows.Controls.Primitives.Popup> Inhalts Fenster nicht transparent. Um einen transparenten <xref:System.Windows.Controls.Primitives.Popup>zu erstellen, legen <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> Sie die `true`-Eigenschaft auf fest.  
  
 Der Inhalt <xref:System.Windows.Controls.Primitives.Popup> eines erbt keine Bitmapeffekte, <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>wie z. b., die <xref:System.Windows.Controls.Primitives.Popup> Sie direkt für das Steuerelement oder für ein beliebiges anderes Element im übergeordneten Fenster festgelegt haben. Damit Bitmapeffekte auf dem Inhalt eines <xref:System.Windows.Controls.Primitives.Popup>angezeigt werden, müssen Sie den Bitmapeffekt direkt auf seinen Inhalt festlegen. Wenn beispielsweise das unter <xref:System.Windows.Controls.Primitives.Popup> geordnete Element eines <xref:System.Windows.Controls.StackPanel>ist, legen Sie den Bitmapeffekt für die <xref:System.Windows.Controls.StackPanel>fest.  
  
<a name="PopupSize"></a>   
### <a name="popup-size"></a>Popup-Größe  
 Standardmäßig wird ein <xref:System.Windows.Controls.Primitives.Popup> -Wert automatisch auf seinen Inhalt skaliert. Wenn die automatische Größenanpassung auftritt, können einige Bitmapeffekte ausgeblendet werden, da die für den <xref:System.Windows.Controls.Primitives.Popup> Inhalt definierte Standardgröße des Bildschirmbereichs nicht genügend Platz für die Anzeige der Bitmapeffekte bereitstellt.  
  
 <xref:System.Windows.Controls.Primitives.Popup>der Inhalt kann auch verdeckt werden, wenn Sie <xref:System.Windows.UIElement.RenderTransform%2A> ein für den Inhalt festlegen. In diesem Szenario können einige Inhalte ausgeblendet werden, wenn sich der Inhalt des transformierten <xref:System.Windows.Controls.Primitives.Popup> über den Bereich der ursprünglichen <xref:System.Windows.Controls.Primitives.Popup>erstreckt. Wenn für einen Bitmapeffekt oder eine Transformation mehr Platz benötigt wird, können <xref:System.Windows.Controls.Primitives.Popup> Sie einen Rand um den Inhalt definieren, um mehr Platz für das Steuerelement bereitzustellen.  
  
<a name="DefiningPopupPosition"></a>   
## <a name="defining-the-popup-position"></a>Definieren der Popup-Position  
 Sie können ein Popup positionieren, indem Sie <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>Eigenschaften <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>,, <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> und festlegen. Weitere Informationen finden Sie unter [Verhalten beim Platzieren von Popups](popup-placement-behavior.md). Wenn <xref:System.Windows.Controls.Primitives.Popup> auf dem Bildschirm angezeigt wird, wird er nicht neu positioniert, wenn das übergeordnete Element neu positioniert wird.  
  
<a name="CustomizingPopupPlacement"></a>   
### <a name="customizing-popup-placement"></a>Anpassen der Popupplatzierung  
 Sie können die Platzierung eines <xref:System.Windows.Controls.Primitives.Popup> Steuer Elements anpassen, indem Sie einen Satz von Koordinaten angeben, die relativ zu dem <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> sind, <xref:System.Windows.Controls.Primitives.Popup> in dem der angezeigt werden soll.  
  
 Um die Platzierung anzupassen, legen <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Sie die <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>-Eigenschaft auf fest. Definieren Sie dann <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> einen Delegaten, der einen Satz möglicher Platzierungs Punkte und primäre Achsen (in der bevorzugten Reihenfolge) <xref:System.Windows.Controls.Primitives.Popup>für den zurückgibt. Der Punkt, der den größten Teil des <xref:System.Windows.Controls.Primitives.Popup> anzeigt, wird automatisch ausgewählt. Ein Beispiel finden Sie unter [Angeben einer benutzerdefinierten Popupposition](how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>   
## <a name="popup-and-the-visual-tree"></a>Popup und visuelle Struktur  
 Ein <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement verfügt nicht über eine eigene visuelle Struktur; stattdessen wird eine Größe von 0 (null) zurück <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> gegeben, <xref:System.Windows.Controls.Primitives.Popup> wenn die-Methode für aufgerufen wird. Wenn Sie jedoch die <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> -Eigenschaft von <xref:System.Windows.Controls.Primitives.Popup> auf `true`festlegen, wird ein neues Fenster mit einer eigenen visuellen Struktur erstellt. Das neue Fenster enthält den <xref:System.Windows.Controls.Primitives.Popup.Child%2A> Inhalt von <xref:System.Windows.Controls.Primitives.Popup>. Die Breite und Höhe des neuen Fensters darf nicht größer als 75 Prozent der Breite oder Höhe des Bildschirms sein.  
  
 Das <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement verwaltet einen Verweis <xref:System.Windows.Controls.Primitives.Popup.Child%2A> auf seinen Inhalt als logisches untergeordnetes Element. Wenn das neue Fenster erstellt wird, wird der Inhalt <xref:System.Windows.Controls.Primitives.Popup> von zu einem visuellen untergeordneten Element des Fensters und bleibt das logische <xref:System.Windows.Controls.Primitives.Popup>untergeordnete Element von. Umgekehrt bleibt das logische übergeordnete Element seines <xref:System.Windows.Controls.Primitives.Popup.Child%2A> Inhalts. <xref:System.Windows.Controls.Primitives.Popup>  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.Primitives.Popup>
- <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>
- <xref:System.Windows.Controls.Primitives.PlacementMode>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Themen zu Vorgehensweisen](popup-how-to-topics.md)
- [Themen zu Vorgehensweisen](tooltip-how-to-topics.md)
