---
title: Übersicht über Popups
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
ms.openlocfilehash: 370970c80221e371db5a97303ef2650d14300b14
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102777"
---
# <a name="popup-overview"></a>Übersicht über Popups
Die <xref:System.Windows.Controls.Primitives.Popup> Steuerelement bietet eine Möglichkeit, Inhalt in einem separaten Fenster angezeigt, die über relativ zu einer festgelegten Element- oder Bildschirmkoordinate das aktuelle Anwendungsfenster gleitet. In diesem Thema werden die <xref:System.Windows.Controls.Primitives.Popup> steuern und Informationen zu dessen Verwendung enthält.  

<a name="What_Is_a_Popup_"></a>   
## <a name="what-is-a-popup"></a>Was ist ein Popup?  
 Ein <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement zeigt Inhalt in einem separaten Fenster relativ zu einem Element oder einen Punkt auf dem Bildschirm. Wenn die <xref:System.Windows.Controls.Primitives.Popup> angezeigt wird, die <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> -Eigenschaftensatz auf `true`.  
  
> [!NOTE]
>  Ein <xref:System.Windows.Controls.Primitives.Popup> wird nicht automatisch geöffnet, wenn der Mauszeiger über sein übergeordnetes Objekt bewegt wird. Wenn Sie möchten eine <xref:System.Windows.Controls.Primitives.Popup> verwenden, um automatisch geöffnet, die <xref:System.Windows.Controls.ToolTip> oder <xref:System.Windows.Controls.ToolTipService> Klasse. Weitere Informationen finden Sie unter [Übersicht über die QuickInfo](tooltip-overview.md).  
  
<a name="APopupExample"></a>   
## <a name="creating-a-popup"></a>Erstellen eines Popups  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.Primitives.Popup> steuern, d. h. das untergeordnete Element einer <xref:System.Windows.Controls.Button> Steuerelement. Da eine <xref:System.Windows.Controls.Button> kann nur ein untergeordnetes Element, in diesem Beispiel werden des Texts für die <xref:System.Windows.Controls.Button> und die <xref:System.Windows.Controls.Primitives.Popup> -Steuerelemente in einem <xref:System.Windows.Controls.StackPanel>. Der Inhalt des der <xref:System.Windows.Controls.Primitives.Popup> wird in einer <xref:System.Windows.Controls.TextBlock> -Steuerelement, das den Text in einem separaten Fenster angezeigt, die über das Anwendungsfenster neben den zugehörigen gleitet <xref:System.Windows.Controls.Button> Steuerelement.  
  
 [!code-xaml[PopupSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>   
## <a name="controls-that-implement-a-popup"></a>Steuerelemente, die ein Popup implementieren  
 Sie können erstellen <xref:System.Windows.Controls.Primitives.Popup> Steuerelemente in anderen Steuerelementen. Die folgenden Steuerelemente implementieren das <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement für bestimmte Verwendungsmöglichkeiten:  
  
-   <xref:System.Windows.Controls.ToolTip>. Wenn Sie eine QuickInfo für ein Element erstellen möchten, verwenden Sie die <xref:System.Windows.Controls.ToolTip> und <xref:System.Windows.Controls.ToolTipService> Klassen. Weitere Informationen finden Sie unter [Übersicht über die QuickInfo](tooltip-overview.md).  
  
-   <xref:System.Windows.Controls.ContextMenu>. Wenn Sie ein Kontextmenü für ein Element erstellen möchten, verwenden Sie die <xref:System.Windows.Controls.ContextMenu> Steuerelement. Weitere Informationen finden Sie unter [Übersicht über ContextMenu](contextmenu-overview.md).  
  
-   <xref:System.Windows.Controls.ComboBox>. Wenn Sie möchten ein Auswahlsteuerelement mit einer Dropdown-Listenfeld, das ein- oder ausgeblendet ist, verwendet werden können, erstellen die <xref:System.Windows.Controls.ComboBox> Steuerelement.  
  
-   <xref:System.Windows.Controls.Expander>. Wenn ein Steuerelement zu erstellen, das eine Kopfzeile mit einem reduzierbaren Bereich anzeigt werden soll, Inhalt angezeigt, verwenden Sie die <xref:System.Windows.Controls.Expander> Steuerelement. Weitere Informationen finden Sie unter [Übersicht über Expander-Steuerelemente](expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>   
## <a name="popup-behavior-and-appearance"></a>Popup-Verhalten und -Darstellung  
 Die <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement bietet Funktionen, die Ihnen ermöglicht, die das Verhalten und die Darstellung anpassen. Sie können beispielsweise festlegen, Öffnungs-und Schließverhalten, Animation, Deckkraft und Bitmapeffekte und <xref:System.Windows.Controls.Primitives.Popup> Größe und Position.  
  
<a name="OpenandCloseBehavior"></a>   
### <a name="open-and-close-behavior"></a>Öffnungs- und Schließverhalten  
 Ein <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement zeigt den Inhalt bei der <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> -Eigenschaftensatz auf `true`. In der Standardeinstellung <xref:System.Windows.Controls.Primitives.Popup> bleibt bestehen, bis die <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> -Eigenschaftensatz auf `false`. Sie können jedoch das Standardverhalten ändern, durch Festlegen der <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> Eigenschaft `false`. Wenn Sie diese Eigenschaft festlegen, um `false`, <xref:System.Windows.Controls.Primitives.Popup> Fenster "Inhalt" verfügt über die Erfassung von Mauseingaben. Die <xref:System.Windows.Controls.Primitives.Popup> verliert die mauserfassung, Erfassung und das Fenster wird geschlossen beim Auftreten eines Mausereignisses außerhalb der <xref:System.Windows.Controls.Primitives.Popup> Fenster.  
  
 Die <xref:System.Windows.Controls.Primitives.Popup.Opened> und <xref:System.Windows.Controls.Primitives.Popup.Closed> Ereignisse werden ausgelöst, wenn die <xref:System.Windows.Controls.Primitives.Popup> -Inhaltsfenster geöffnet oder geschlossen ist.  
  
<a name="Animation"></a>   
### <a name="animation"></a>Animation  
 Die <xref:System.Windows.Controls.Primitives.Popup> Steuerelement bietet integrierte Unterstützung für Animationen, die typischerweise mit Verhalten wie einblenden und dem Einblenden verknüpft sind. Können Sie diese Animationen aktivieren, durch Festlegen der <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> Eigenschaft, um eine <xref:System.Windows.Controls.Primitives.PopupAnimation> Enumerationswert. Für <xref:System.Windows.Controls.Primitives.Popup> -Animationen ordnungsgemäß funktionieren müssen Sie festlegen, die <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> Eigenschaft `true`.  
  
 Sie können auch Animationen wie anwenden <xref:System.Windows.Media.Animation.Storyboard> auf die <xref:System.Windows.Controls.Primitives.Popup> Steuerelement.  
  
<a name="OpacityandBitmapEffects"></a>   
### <a name="opacity-and-bitmap-effects"></a>Deckkraft und Bitmapeffekte  
 Die <xref:System.Windows.UIElement.Opacity%2A> -Eigenschaft für eine <xref:System.Windows.Controls.Primitives.Popup> Steuerelement hat keine Auswirkungen auf dessen Inhalt. In der Standardeinstellung die <xref:System.Windows.Controls.Primitives.Popup> Fenster "Inhalt" ist nicht transparent. Erstellen Sie eine transparente <xref:System.Windows.Controls.Primitives.Popup>legen die <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> Eigenschaft `true`.  
  
 Der Inhalt des eine <xref:System.Windows.Controls.Primitives.Popup> erbt keine Bitmapeffekte wie z. B. <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>, dass Sie direkt auf Festlegen der <xref:System.Windows.Controls.Primitives.Popup> Steuerelement oder einem anderen Element im übergeordneten Fenster. Damit Bitmapeffekte auf dem Inhalt angezeigt werden. eine <xref:System.Windows.Controls.Primitives.Popup>, müssen Sie den Bitmapeffekt direkt auf dessen Inhalt festlegen. Z. B. wenn das untergeordnete Element ein <xref:System.Windows.Controls.Primitives.Popup> ist eine <xref:System.Windows.Controls.StackPanel>, legen Sie den Bitmapeffekt für die <xref:System.Windows.Controls.StackPanel>.  
  
<a name="PopupSize"></a>   
### <a name="popup-size"></a>Popup-Größe  
 Standardmäßig eine <xref:System.Windows.Controls.Primitives.Popup> automatisch an dessen Inhalt angepasst wird. Bei der automatischen Anpassung werden einige Bitmapeffekte ausgeblendet werden können, da die Standardgröße des Bildschirmbereichs, der für definierte die <xref:System.Windows.Controls.Primitives.Popup> Inhalt bietet nicht genügend Speicherplatz für die Bitmapeffekte angezeigt.  
  
 <xref:System.Windows.Controls.Primitives.Popup> Inhalt kann auch verdeckt werden, wenn Sie festlegen, eine <xref:System.Windows.UIElement.RenderTransform%2A> auf dem Inhalt. In diesem Szenario wird ein Teil des Inhalts möglicherweise ausgeblendet werden, wenn der Inhalt des transformierten <xref:System.Windows.Controls.Primitives.Popup> reicht über den Bereich des ursprünglichen <xref:System.Windows.Controls.Primitives.Popup>. Wenn ein Bitmapeffekt oder eine Transformation mehr Speicherplatz erforderlich ist, können Sie definieren einen Rand um den <xref:System.Windows.Controls.Primitives.Popup> Inhalt, um mehr Platz für das Steuerelement zu gewährleisten.  
  
<a name="DefiningPopupPosition"></a>   
## <a name="defining-the-popup-position"></a>Definieren der Popup-Position  
 Sie können die position eines Popups durch Festlegen der <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> Eigenschaften. Weitere Informationen finden Sie unter [Verhalten beim Platzieren von Popups](popup-placement-behavior.md). Wenn <xref:System.Windows.Controls.Primitives.Popup> wird angezeigt, auf dem Bildschirm, es ist nicht neu positionieren, selbst wenn das übergeordnete Element positioniert wird.  
  
<a name="CustomizingPopupPlacement"></a>   
### <a name="customizing-popup-placement"></a>Anpassen der Popupplatzierung  
 Sie können anpassen, dass die Platzierung von eine <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement durch Angabe der einen Satz von Koordinaten, die relativ sind die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> möchten Sie die <xref:System.Windows.Controls.Primitives.Popup> angezeigt werden.  
  
 Um die Platzierung anzupassen, legen Sie die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Eigenschaft <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Definieren Sie dann eine <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> Delegat, der einen Satz von möglichen Platzierungspunkten und Primärachsen (sortiert nach Präferenz) für zurückgibt der <xref:System.Windows.Controls.Primitives.Popup>. Der Punkt, der den größten Teil zeigt die <xref:System.Windows.Controls.Primitives.Popup> wird automatisch ausgewählt. Ein Beispiel finden Sie unter [Angeben einer benutzerdefinierten Popupposition](how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>   
## <a name="popup-and-the-visual-tree"></a>Popup und visuelle Struktur  
 Ein <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement besitzt keine eigene visuelle Struktur; es gibt stattdessen eine Größe von 0 (null) bei der <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> -Methode für <xref:System.Windows.Controls.Primitives.Popup> aufgerufen wird. Jedoch beim Festlegen der <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> Eigenschaft <xref:System.Windows.Controls.Primitives.Popup> zu `true`, ein neues Fenster mit eigener visueller Struktur wird erstellt. Das neue Fenster enthält die <xref:System.Windows.Controls.Primitives.Popup.Child%2A> des <xref:System.Windows.Controls.Primitives.Popup>. Die Breite und Höhe des neuen Fensters darf nicht größer als 75 Prozent der Breite oder Höhe des Bildschirms sein.  
  
 Die <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement behält einen Verweis auf die <xref:System.Windows.Controls.Primitives.Popup.Child%2A> Inhalte als ein untergeordnetes logisches Element. Wenn das neue Fenster erstellt wird, wird den Inhalt des <xref:System.Windows.Controls.Primitives.Popup> wird zu einem visuellen untergeordneten Element des Fensters und bleibt das logische untergeordnete Elemente <xref:System.Windows.Controls.Primitives.Popup>. Im Gegensatz dazu <xref:System.Windows.Controls.Primitives.Popup> bleibt das logische übergeordnete Element der <xref:System.Windows.Controls.Primitives.Popup.Child%2A> Inhalt.  
  
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
