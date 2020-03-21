---
title: Übersicht über Popups
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: 911130d52744c5ba54750f214829a5d1900e083c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185956"
---
# <a name="popup-overview"></a>Übersicht über Popups
Das <xref:System.Windows.Controls.Primitives.Popup> Steuerelement bietet eine Möglichkeit, Inhalte in einem separaten Fenster anzuzeigen, das relativ zu einem bestimmten Element oder einer Bildschirmkoordinate über dem aktuellen Anwendungsfenster schwebt. In diesem <xref:System.Windows.Controls.Primitives.Popup> Thema wird das Steuerelement vorgestellt und Informationen zu seiner Verwendung enthalten.  

<a name="What_Is_a_Popup_"></a>
## <a name="what-is-a-popup"></a>Was ist ein Popup?  
 Ein <xref:System.Windows.Controls.Primitives.Popup> Steuerelement zeigt Inhalt in einem separaten Fenster relativ zu einem Element oder Punkt auf dem Bildschirm an. Wenn <xref:System.Windows.Controls.Primitives.Popup> der sichtbar <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> ist, wird `true`die Eigenschaft auf festgelegt.  
  
> [!NOTE]
> A <xref:System.Windows.Controls.Primitives.Popup> wird nicht automatisch geöffnet, wenn der Mauszeiger über das übergeordnete Objekt bewegt wird. Wenn Sie <xref:System.Windows.Controls.Primitives.Popup> möchten, dass ein <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> automatisch geöffnet wird, verwenden Sie die oder-Klasse. Weitere Informationen finden Sie unter [Übersicht über die QuickInfo](tooltip-overview.md).  
  
<a name="APopupExample"></a>
## <a name="creating-a-popup"></a>Erstellen eines Popups  
 Das folgende Beispiel zeigt, <xref:System.Windows.Controls.Primitives.Popup> wie Sie ein Steuerelement <xref:System.Windows.Controls.Button> definieren, das das untergeordnete Element eines Steuerelements ist. Da <xref:System.Windows.Controls.Button> ein Element nur über ein untergeordnetes Element <xref:System.Windows.Controls.Button> verfügen <xref:System.Windows.Controls.Primitives.Popup> kann, <xref:System.Windows.Controls.StackPanel>wird in diesem Beispiel der Text für die und die Steuerelemente in einem platziert. Der Inhalt <xref:System.Windows.Controls.Primitives.Popup> des wird <xref:System.Windows.Controls.TextBlock> in einem Steuerelement angezeigt, das seinen Text in einem <xref:System.Windows.Controls.Button> separaten Fenster anzeigt, das über dem Anwendungsfenster in der Nähe des zugehörigen Steuerelements schwebt.  
  
 [!code-xaml[PopupSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>
## <a name="controls-that-implement-a-popup"></a>Steuerelemente, die ein Popup implementieren  
 Sie können <xref:System.Windows.Controls.Primitives.Popup> Steuerelemente in andere Steuerelemente einbauen. Die folgenden Steuerelemente implementieren das <xref:System.Windows.Controls.Primitives.Popup> Steuerelement für bestimmte Verwendungen:  
  
- <xref:System.Windows.Controls.ToolTip>. Wenn Sie eine QuickInfo für ein Element <xref:System.Windows.Controls.ToolTip> <xref:System.Windows.Controls.ToolTipService> erstellen möchten, verwenden Sie die und-Klassen. Weitere Informationen finden Sie unter [Übersicht über die QuickInfo](tooltip-overview.md).  
  
- <xref:System.Windows.Controls.ContextMenu>. Wenn Sie ein Kontextmenü für ein Element <xref:System.Windows.Controls.ContextMenu> erstellen möchten, verwenden Sie das Steuerelement. Weitere Informationen finden Sie unter [Übersicht über ContextMenu](contextmenu-overview.md).  
  
- <xref:System.Windows.Controls.ComboBox>. Wenn Sie ein Auswahlsteuerelement mit einem Dropdown-Listenfeld erstellen möchten, das <xref:System.Windows.Controls.ComboBox> angezeigt oder ausgeblendet werden kann, verwenden Sie das Steuerelement.  
  
- <xref:System.Windows.Controls.Expander>. Wenn Sie ein Steuerelement erstellen möchten, das einen Header mit einem <xref:System.Windows.Controls.Expander> zusammenklappbaren Bereich anzeigt, der Inhalt anzeigt, verwenden Sie das Steuerelement. Weitere Informationen finden Sie unter [Übersicht über Expander-Steuerelemente](expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>
## <a name="popup-behavior-and-appearance"></a>Popup-Verhalten und -Darstellung  
 Das <xref:System.Windows.Controls.Primitives.Popup> Steuerelement bietet Funktionen, mit denen Sie das Verhalten und die Darstellung anpassen können. Sie können z. B. das Öffnen und Schließen von Verhalten, Animation, Deckkraft und Bitmap-Effekten sowie <xref:System.Windows.Controls.Primitives.Popup> Größe und Position festlegen.  
  
<a name="OpenandCloseBehavior"></a>
### <a name="open-and-close-behavior"></a>Öffnungs- und Schließverhalten  
 Ein <xref:System.Windows.Controls.Primitives.Popup> Steuerelement zeigt den <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> Inhalt an, wenn die Eigenschaft auf `true`festgelegt ist. Bleibt standardmäßig <xref:System.Windows.Controls.Primitives.Popup> geöffnet, <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> bis die `false`Eigenschaft auf festgelegt ist. Sie können jedoch das Standardverhalten <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> ändern, `false`indem Sie die Eigenschaft auf festlegen. Wenn Sie diese `false`Eigenschaft <xref:System.Windows.Controls.Primitives.Popup> auf festlegen, verfügt das Inhaltsfenster über die Mauserfassung. Die <xref:System.Windows.Controls.Primitives.Popup> verlorene Mausaufnahme und das Fenster wird <xref:System.Windows.Controls.Primitives.Popup> geschlossen, wenn ein Mausereignis außerhalb des Fensters auftritt.  
  
 Die <xref:System.Windows.Controls.Primitives.Popup.Opened> <xref:System.Windows.Controls.Primitives.Popup.Closed> und-Ereignisse werden <xref:System.Windows.Controls.Primitives.Popup> ausgelöst, wenn das Inhaltsfenster geöffnet oder geschlossen ist.  
  
<a name="Animation"></a>
### <a name="animation"></a>Animation  
 Das <xref:System.Windows.Controls.Primitives.Popup> Steuerelement bietet integrierte Unterstützung für die Animationen, die normalerweise mit Verhaltensweisen wie Einblenden und Einblenden verknüpft sind. Sie können diese Animationen <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> aktivieren, <xref:System.Windows.Controls.Primitives.PopupAnimation> indem Sie die Eigenschaft auf einen Enumerationswert festlegen. Damit <xref:System.Windows.Controls.Primitives.Popup> Animationen ordnungsgemäß funktionieren, müssen <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> Sie `true`die Eigenschaft auf festlegen.  
  
 Sie können auch <xref:System.Windows.Media.Animation.Storyboard> Animationen <xref:System.Windows.Controls.Primitives.Popup> wie auf das Steuerelement anwenden.  
  
<a name="OpacityandBitmapEffects"></a>
### <a name="opacity-and-bitmap-effects"></a>Deckkraft und Bitmapeffekte  
 Die <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft <xref:System.Windows.Controls.Primitives.Popup> für ein Steuerelement hat keine Auswirkungen auf ihren Inhalt. Standardmäßig ist <xref:System.Windows.Controls.Primitives.Popup> das Inhaltsfenster undurchsichtig. Um eine <xref:System.Windows.Controls.Primitives.Popup>transparente zu <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> erstellen, legen Sie die Eigenschaft auf fest. `true`  
  
 Der Inhalt <xref:System.Windows.Controls.Primitives.Popup> eines erbt keine Bitmap-Effekte, z. <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>B. <xref:System.Windows.Controls.Primitives.Popup> , die Sie direkt für das Steuerelement oder für ein anderes Element im übergeordneten Fenster festlegen. Damit Bitmapeffekte auf dem Inhalt <xref:System.Windows.Controls.Primitives.Popup>eines angezeigt werden, müssen Sie den Bitmapeffekt direkt auf den Inhalt festlegen. Wenn das untergeordnete Element <xref:System.Windows.Controls.Primitives.Popup> von <xref:System.Windows.Controls.StackPanel>a z. B. <xref:System.Windows.Controls.StackPanel>ein ist, legen Sie den Bitmapeffekt für die fest.  
  
<a name="PopupSize"></a>
### <a name="popup-size"></a>Popup-Größe  
 Standardmäßig wird <xref:System.Windows.Controls.Primitives.Popup> eine Größe automatisch auf den Inhalt angepasst. Wenn die automatische Größenänderung auftritt, können einige Bitmapeffekte ausgeblendet werden, da <xref:System.Windows.Controls.Primitives.Popup> die Standardgröße des für den Inhalt definierten Bildschirmbereichs nicht genügend Platz für die Anzeige der Bitmapeffekte bietet.  
  
 <xref:System.Windows.Controls.Primitives.Popup>Inhalte können auch verdeckt werden, <xref:System.Windows.UIElement.RenderTransform%2A> wenn Sie eine für den Inhalt festlegen. In diesem Szenario kann ein Teil des Inhalts <xref:System.Windows.Controls.Primitives.Popup> ausgeblendet werden, wenn <xref:System.Windows.Controls.Primitives.Popup>der Inhalt des Transformierten über den Bereich des Originals hinausgeht. Wenn ein Bitmapeffekt oder eine Transformation mehr Speicherplatz <xref:System.Windows.Controls.Primitives.Popup> erfordert, können Sie einen Rand um den Inhalt definieren, um mehr Fläche für das Steuerelement bereitzustellen.  
  
<a name="DefiningPopupPosition"></a>
## <a name="defining-the-popup-position"></a>Definieren der Popup-Position  
 Sie können ein Popup <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>positionieren, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>indem <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> Sie die Eigenschaften , <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, und festlegen. Weitere Informationen finden Sie unter [Verhalten beim Platzieren von Popups](popup-placement-behavior.md). Wenn <xref:System.Windows.Controls.Primitives.Popup> es auf dem Bildschirm angezeigt wird, positioniert es sich nicht neu, wenn sein übergeordnetes Element neu positioniert wird.  
  
<a name="CustomizingPopupPlacement"></a>
### <a name="customizing-popup-placement"></a>Anpassen der Popupplatzierung  
 Sie können die Platzierung <xref:System.Windows.Controls.Primitives.Popup> eines Steuerelements anpassen, indem Sie <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> einen Satz <xref:System.Windows.Controls.Primitives.Popup> von Koordinaten angeben, die relativ zu der Stelle sind, an der die angezeigt werden soll.  
  
 Um die Platzierung <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> anzupassen, <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>legen Sie die Eigenschaft auf fest. Definieren Sie <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> dann einen Delegaten, der eine Reihe möglicher Platzierungspunkte <xref:System.Windows.Controls.Primitives.Popup>und Primärachsen (in der Reihenfolge der Präferenz) für die zurückgibt. Der Punkt, der den <xref:System.Windows.Controls.Primitives.Popup> größten Teil des zeigt, wird automatisch ausgewählt. Ein Beispiel finden Sie unter [Angeben einer benutzerdefinierten Popupposition](how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>
## <a name="popup-and-the-visual-tree"></a>Popup und visuelle Struktur  
 Ein <xref:System.Windows.Controls.Primitives.Popup> Steuerelement verfügt nicht über einen eigenen visuellen Baum. Stattdessen wird die Größe 0 (Null) zurückgegeben, wenn die <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> Methode für <xref:System.Windows.Controls.Primitives.Popup> aufgerufen wird. Wenn Sie jedoch <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> die <xref:System.Windows.Controls.Primitives.Popup> Eigenschaft `true`von festlegen, wird ein neues Fenster mit einer eigenen visuellen Struktur erstellt. Das neue Fenster <xref:System.Windows.Controls.Primitives.Popup.Child%2A> enthält <xref:System.Windows.Controls.Primitives.Popup>den Inhalt von . Die Breite und Höhe des neuen Fensters darf nicht größer als 75 Prozent der Breite oder Höhe des Bildschirms sein.  
  
 Das <xref:System.Windows.Controls.Primitives.Popup> Steuerelement behält einen <xref:System.Windows.Controls.Primitives.Popup.Child%2A> Verweis auf seinen Inhalt als logisches untergeordnetes Element bei. Wenn das neue Fenster erstellt <xref:System.Windows.Controls.Primitives.Popup> wird, wird der Inhalt von zu <xref:System.Windows.Controls.Primitives.Popup>einem visuellen untergeordneten Element des Fensters und bleibt das logische untergeordnete Element von . Umgekehrt <xref:System.Windows.Controls.Primitives.Popup> bleibt das logische übergeordnete <xref:System.Windows.Controls.Primitives.Popup.Child%2A> Element seines Inhalts.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.Primitives.Popup>
- <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>
- <xref:System.Windows.Controls.Primitives.PlacementMode>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>
- <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>
- <xref:System.Windows.Controls.ToolTip>
- <xref:System.Windows.Controls.ToolTipService>
- [How-to-Themen](popup-how-to-topics.md)
- [How-to-Themen](tooltip-how-to-topics.md)
