---
title: Übersicht über Popups
description: Erfahren Sie mehr über das Windows Presentation Foundation Popup-Steuerelement, das eine Möglichkeit bietet, Inhalte in einem Fenster anzuzeigen, das über der aktuellen Anwendung schwebt.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: 84eaddc53366df6d1da1a0a005d3618268f8cce2
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167534"
---
# <a name="popup-overview"></a>Übersicht über Popups
Das- <xref:System.Windows.Controls.Primitives.Popup> Steuerelement bietet eine Möglichkeit, Inhalte in einem separaten Fenster anzuzeigen, das im aktuellen Anwendungsfenster relativ zu einem festgelegten Element oder einer bestimmten Bildschirm Koordinate schwebt. Dieses Thema enthält eine Einführung in das <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement und stellt Informationen zur Verwendung bereit.  

<a name="What_Is_a_Popup_"></a>
## <a name="what-is-a-popup"></a>Was ist ein Popup?  
 Ein- <xref:System.Windows.Controls.Primitives.Popup> Steuerelement zeigt Inhalt in einem separaten Fenster relativ zu einem Element oder einem Punkt auf dem Bildschirm an. Wenn der <xref:System.Windows.Controls.Primitives.Popup> sichtbar ist, wird die- <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> Eigenschaft auf festgelegt `true` .  
  
> [!NOTE]
> Eine <xref:System.Windows.Controls.Primitives.Popup> wird nicht automatisch geöffnet, wenn der Mauszeiger über das übergeordnete Objekt bewegt wird. Wenn ein <xref:System.Windows.Controls.Primitives.Popup> automatisch geöffnet werden soll, verwenden Sie die- <xref:System.Windows.Controls.ToolTip> Klasse oder die- <xref:System.Windows.Controls.ToolTipService> Klasse. Weitere Informationen finden Sie unter [Übersicht über die QuickInfo](tooltip-overview.md).  
  
<a name="APopupExample"></a>
## <a name="creating-a-popup"></a>Erstellen eines Popups  
 Im folgenden Beispiel wird gezeigt, wie ein- <xref:System.Windows.Controls.Primitives.Popup> Steuerelement definiert wird, das das untergeordnete Element eines-Steuer Elements ist <xref:System.Windows.Controls.Button> . Da eine <xref:System.Windows.Controls.Button> nur über ein untergeordnetes Element verfügen kann, wird in diesem Beispiel der Text für die Steuer <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.Popup> Elemente und in einem abgelegt <xref:System.Windows.Controls.StackPanel> . Der Inhalt von <xref:System.Windows.Controls.Primitives.Popup> wird in einem- <xref:System.Windows.Controls.TextBlock> Steuerelement angezeigt, das seinen Text in einem separaten Fenster anzeigt, das über das Anwendungsfenster in der Nähe des zugehörigen Steuer Elements schwebt <xref:System.Windows.Controls.Button> .  
  
 [!code-xaml[PopupSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>
## <a name="controls-that-implement-a-popup"></a>Steuerelemente, die ein Popup implementieren  
 Sie können Steuer <xref:System.Windows.Controls.Primitives.Popup> Elemente in anderen Steuerelementen erstellen. Die folgenden Steuerelemente implementieren das- <xref:System.Windows.Controls.Primitives.Popup> Steuerelement für bestimmte Verwendungszwecke:  
  
- <xref:System.Windows.Controls.ToolTip>. Wenn Sie eine QuickInfo für ein Element erstellen möchten, verwenden Sie die <xref:System.Windows.Controls.ToolTip> -Klasse und die- <xref:System.Windows.Controls.ToolTipService> Klasse. Weitere Informationen finden Sie unter [Übersicht über die QuickInfo](tooltip-overview.md).  
  
- <xref:System.Windows.Controls.ContextMenu>. Wenn Sie ein Kontextmenü für ein Element erstellen möchten, verwenden Sie das- <xref:System.Windows.Controls.ContextMenu> Steuerelement. Weitere Informationen finden Sie unter [Übersicht über ContextMenu](contextmenu-overview.md).  
  
- <xref:System.Windows.Controls.ComboBox>. Wenn Sie ein Auswahl Steuerelement mit einem Dropdown-Listenfeld erstellen möchten, das angezeigt oder ausgeblendet werden kann, verwenden Sie das- <xref:System.Windows.Controls.ComboBox> Steuerelement.  
  
- <xref:System.Windows.Controls.Expander>. Wenn Sie ein Steuerelement erstellen möchten, das einen Header mit einem redusible-Bereich anzeigt, in dem Inhalt angezeigt wird, verwenden Sie das- <xref:System.Windows.Controls.Expander> Steuerelement. Weitere Informationen finden Sie unter [Übersicht über Expander-Steuerelemente](expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>
## <a name="popup-behavior-and-appearance"></a>Popup-Verhalten und -Darstellung  
 Das- <xref:System.Windows.Controls.Primitives.Popup> Steuerelement stellt Funktionen bereit, die es Ihnen ermöglichen, das Verhalten und die Darstellung anzupassen. Beispielsweise können Sie das Verhalten für öffnen und schließen, Animation, Deckkraft und Bitmapeffekte sowie <xref:System.Windows.Controls.Primitives.Popup> Größe und Position festlegen.  
  
<a name="OpenandCloseBehavior"></a>
### <a name="open-and-close-behavior"></a>Öffnungs- und Schließverhalten  
 Ein- <xref:System.Windows.Controls.Primitives.Popup> Steuerelement zeigt seinen Inhalt <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> an, wenn die-Eigenschaft auf festgelegt ist `true` . Standardmäßig <xref:System.Windows.Controls.Primitives.Popup> bleibt geöffnet, bis die- <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> Eigenschaft auf festgelegt ist `false` . Sie können das Standardverhalten jedoch ändern, indem Sie die- <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> Eigenschaft auf festlegen `false` . Wenn Sie diese Eigenschaft auf festlegen `false` , <xref:System.Windows.Controls.Primitives.Popup> enthält das Inhalts Fenster die Maus Aufzeichnung. Das <xref:System.Windows.Controls.Primitives.Popup> verliert die Maus Aufzeichnung, und das Fenster wird geschlossen, wenn ein Maus Ereignis außerhalb des <xref:System.Windows.Controls.Primitives.Popup> Fensters auftritt.  
  
 Das <xref:System.Windows.Controls.Primitives.Popup.Opened> -Ereignis und das- <xref:System.Windows.Controls.Primitives.Popup.Closed> Ereignis werden ausgelöst, wenn das <xref:System.Windows.Controls.Primitives.Popup> Inhalts Fenster geöffnet oder geschlossen ist.  
  
<a name="Animation"></a>
### <a name="animation"></a>Animation  
 Das- <xref:System.Windows.Controls.Primitives.Popup> Steuerelement verfügt über integrierte Unterstützung für Animationen, die in der Regel mit Verhalten wie einblenden und Folie verknüpft sind. Sie können diese Animationen aktivieren, indem Sie die- <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> Eigenschaft auf einen- <xref:System.Windows.Controls.Primitives.PopupAnimation> Enumerationswert festlegen. Damit <xref:System.Windows.Controls.Primitives.Popup> Animationen ordnungsgemäß funktionieren, müssen Sie die- <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> Eigenschaft auf festlegen `true` .  
  
 Sie können auch Animationen wie <xref:System.Windows.Media.Animation.Storyboard> auf das- <xref:System.Windows.Controls.Primitives.Popup> Steuerelement anwenden.  
  
<a name="OpacityandBitmapEffects"></a>
### <a name="opacity-and-bitmap-effects"></a>Deckkraft und Bitmapeffekte  
 Die- <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft für ein <xref:System.Windows.Controls.Primitives.Popup> Steuerelement hat keine Auswirkung auf seinen Inhalt. Standardmäßig ist das <xref:System.Windows.Controls.Primitives.Popup> Inhalts Fenster nicht transparent. Um einen transparenten zu erstellen <xref:System.Windows.Controls.Primitives.Popup> , legen <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> Sie die-Eigenschaft auf fest `true` .  
  
 Der Inhalt eines <xref:System.Windows.Controls.Primitives.Popup> erbt keine Bitmapeffekte, wie z <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> . b., die Sie direkt für das <xref:System.Windows.Controls.Primitives.Popup> Steuerelement oder für ein beliebiges anderes Element im übergeordneten Fenster festgelegt haben. Damit Bitmapeffekte auf dem Inhalt eines angezeigt <xref:System.Windows.Controls.Primitives.Popup> werden, müssen Sie den Bitmapeffekt direkt auf seinen Inhalt festlegen. Wenn beispielsweise das untergeordnete Element eines <xref:System.Windows.Controls.Primitives.Popup> ist <xref:System.Windows.Controls.StackPanel> , legen Sie den Bitmapeffekt für die fest <xref:System.Windows.Controls.StackPanel> .  
  
<a name="PopupSize"></a>
### <a name="popup-size"></a>Popup-Größe  
 Standardmäßig wird ein-Wert <xref:System.Windows.Controls.Primitives.Popup> automatisch auf seinen Inhalt skaliert. Wenn die automatische Größenanpassung auftritt, können einige Bitmapeffekte ausgeblendet werden, da die für den Inhalt definierte Standardgröße des Bildschirmbereichs <xref:System.Windows.Controls.Primitives.Popup> nicht genügend Platz für die Anzeige der Bitmapeffekte bereitstellt.  
  
 <xref:System.Windows.Controls.Primitives.Popup>der Inhalt kann auch verdeckt werden, wenn Sie ein <xref:System.Windows.UIElement.RenderTransform%2A> für den Inhalt festlegen. In diesem Szenario können einige Inhalte ausgeblendet werden, wenn sich der Inhalt des transformierten <xref:System.Windows.Controls.Primitives.Popup> über den Bereich der ursprünglichen erstreckt <xref:System.Windows.Controls.Primitives.Popup> . Wenn für einen Bitmapeffekt oder eine Transformation mehr Platz benötigt wird, können Sie einen Rand um den Inhalt definieren, um <xref:System.Windows.Controls.Primitives.Popup> mehr Platz für das Steuerelement bereitzustellen.  
  
<a name="DefiningPopupPosition"></a>
## <a name="defining-the-popup-position"></a>Definieren der Popup-Position  
 Sie können ein Popup positionieren, indem Sie <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> die <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A> Eigenschaften,, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> , <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und festlegen <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> . Weitere Informationen finden Sie unter [Verhalten beim Platzieren von Popups](popup-placement-behavior.md). Wenn <xref:System.Windows.Controls.Primitives.Popup> auf dem Bildschirm angezeigt wird, wird er nicht neu positioniert, wenn das übergeordnete Element neu positioniert wird.  
  
<a name="CustomizingPopupPlacement"></a>
### <a name="customizing-popup-placement"></a>Anpassen der Popupplatzierung  
 Sie können die Platzierung eines Steuer Elements anpassen <xref:System.Windows.Controls.Primitives.Popup> , indem Sie einen Satz von Koordinaten angeben, die relativ zu dem sind, <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> in dem der <xref:System.Windows.Controls.Primitives.Popup> angezeigt werden soll.  
  
 Um die Platzierung anzupassen, legen <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Sie die-Eigenschaft auf fest <xref:System.Windows.Controls.Primitives.PlacementMode.Custom> . Definieren Sie dann einen Delegaten <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> , der einen Satz möglicher Platzierungs Punkte und primäre Achsen (in der bevorzugten Reihenfolge) für den zurückgibt <xref:System.Windows.Controls.Primitives.Popup> . Der Punkt, der den größten Teil des anzeigt, <xref:System.Windows.Controls.Primitives.Popup> wird automatisch ausgewählt. Ein Beispiel finden Sie unter [Angeben einer benutzerdefinierten Popupposition](how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>
## <a name="popup-and-the-visual-tree"></a>Popup und visuelle Struktur  
 Ein- <xref:System.Windows.Controls.Primitives.Popup> Steuerelement verfügt nicht über eine eigene visuelle Struktur; stattdessen wird eine Größe von 0 (null) zurückgegeben, wenn die- <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> Methode für <xref:System.Windows.Controls.Primitives.Popup> aufgerufen wird. Wenn Sie jedoch die- <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> Eigenschaft von <xref:System.Windows.Controls.Primitives.Popup> auf festlegen `true` , wird ein neues Fenster mit einer eigenen visuellen Struktur erstellt. Das neue Fenster enthält den <xref:System.Windows.Controls.Primitives.Popup.Child%2A> Inhalt von <xref:System.Windows.Controls.Primitives.Popup> . Die Breite und Höhe des neuen Fensters darf nicht größer als 75 Prozent der Breite oder Höhe des Bildschirms sein.  
  
 Das- <xref:System.Windows.Controls.Primitives.Popup> Steuerelement verwaltet einen Verweis auf seinen <xref:System.Windows.Controls.Primitives.Popup.Child%2A> Inhalt als logisches untergeordnetes Element. Wenn das neue Fenster erstellt wird, wird der Inhalt von <xref:System.Windows.Controls.Primitives.Popup> zu einem visuellen untergeordneten Element des Fensters und bleibt das logische untergeordnete Element von <xref:System.Windows.Controls.Primitives.Popup> . Umgekehrt <xref:System.Windows.Controls.Primitives.Popup> bleibt das logische übergeordnete Element seines <xref:System.Windows.Controls.Primitives.Popup.Child%2A> Inhalts.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.Primitives.Popup>
- <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>
- <xref:System.Windows.Controls.Primitives.PlacementMode>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [Artikel zu Vorgehensweisen](popup-how-to-topics.md)
- [Artikel zu Vorgehensweisen](tooltip-how-to-topics.md)
