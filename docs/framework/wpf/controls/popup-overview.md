---
title: "Übersicht über Popups"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], Popup
- Popup control [WPF], about Popup control
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0cb20895b5af35fec7274ca4c747740390104355
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="popup-overview"></a>Übersicht über Popups
Die <xref:System.Windows.Controls.Primitives.Popup> Steuerelement bietet eine Möglichkeit, Inhalte in einem separaten Fenster angezeigt, die über die aktuelle Anwendungsfenster relativ zu einer angegebenen Koordinate der Element- oder Bildschirm gleitet. Dieses Thema enthält die <xref:System.Windows.Controls.Primitives.Popup> steuern und enthält Informationen zu Verwendungsmöglichkeiten.  
  
 
  
<a name="What_Is_a_Popup_"></a>   
## <a name="what-is-a-popup"></a>Was ist ein Popup?  
 Ein <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement zeigt den Inhalt in einem separaten Fenster relativ zu einem Element oder einen Punkt auf dem Bildschirm. Wenn die <xref:System.Windows.Controls.Primitives.Popup> sichtbar ist, die <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> -Eigenschaftensatz auf `true`.  
  
> [!NOTE]
>  Ein <xref:System.Windows.Controls.Primitives.Popup> wird nicht automatisch geöffnet, wenn der Mauszeiger über das übergeordnete Objekt bewegt wird. Wenn Sie möchten eine <xref:System.Windows.Controls.Primitives.Popup> verwenden, um automatisch geöffnet, die <xref:System.Windows.Controls.ToolTip> oder <xref:System.Windows.Controls.ToolTipService> Klasse. Weitere Informationen finden Sie unter [Übersicht über die QuickInfo](../../../../docs/framework/wpf/controls/tooltip-overview.md).  
  
<a name="APopupExample"></a>   
## <a name="creating-a-popup"></a>Erstellen eines Popups  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.Controls.Primitives.Popup> steuern, d. h. das untergeordnete Element des ein <xref:System.Windows.Controls.Button> Steuerelement. Da eine <xref:System.Windows.Controls.Button> kann nur ein untergeordnetes Element, in diesem Beispiel wird des Texts für die <xref:System.Windows.Controls.Button> und <xref:System.Windows.Controls.Primitives.Popup> Steuerelemente in eine <xref:System.Windows.Controls.StackPanel>. Den Inhalt der <xref:System.Windows.Controls.Primitives.Popup> wird in eine <xref:System.Windows.Controls.TextBlock> Steuerelement, mit dem der Text in einem separaten Fenster angezeigt wird, die über das Anwendungsfenster in der Nähe der verwandte gleitet <xref:System.Windows.Controls.Button> Steuerelement.  
  
 [!code-xaml[PopupSimple#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xaml[PopupSimple#CreatePopupCodeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>   
## <a name="controls-that-implement-a-popup"></a>Steuerelemente, die ein Popup implementieren  
 Sie können erstellen <xref:System.Windows.Controls.Primitives.Popup> Steuerelementen in andere Steuerelemente. Die folgenden Steuerelemente implementieren die <xref:System.Windows.Controls.Primitives.Popup> Steuerelement für bestimmte Verwendungszwecke:  
  
-   <xref:System.Windows.Controls.ToolTip> Wenn Sie eine QuickInfo für ein Element erstellen möchten, verwenden Sie die <xref:System.Windows.Controls.ToolTip> und <xref:System.Windows.Controls.ToolTipService> Klassen. Weitere Informationen finden Sie unter [Übersicht über die QuickInfo](../../../../docs/framework/wpf/controls/tooltip-overview.md).  
  
-   <xref:System.Windows.Controls.ContextMenu> Wenn Sie ein Kontextmenü für ein Element erstellen möchten, verwenden Sie die <xref:System.Windows.Controls.ContextMenu> Steuerelement. Weitere Informationen finden Sie unter [Übersicht über ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md).  
  
-   <xref:System.Windows.Controls.ComboBox> Wenn Sie möchten ein Auswahlsteuerelement mit einem Dropdown-Listenfeld, die angezeigt oder ausgeblendet ist, verwendet werden können, erstellen die <xref:System.Windows.Controls.ComboBox> Steuerelement.  
  
-   <xref:System.Windows.Controls.Expander> Wenn ein Steuerelement zu erstellen, einen Header mit einem reduzierbaren Bereich angezeigt, werden sollen, die Inhalte anzeigt, verwenden Sie die <xref:System.Windows.Controls.Expander> Steuerelement. Weitere Informationen finden Sie unter [Übersicht über Expander-Steuerelemente](../../../../docs/framework/wpf/controls/expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>   
## <a name="popup-behavior-and-appearance"></a>Popup-Verhalten und -Darstellung  
 Die <xref:System.Windows.Controls.Primitives.Popup> Steuerelement verfügt über Funktionen, die Ihnen ermöglicht, die das Verhalten und die Darstellung anpassen. Sie können beispielsweise festlegen, Eröffnungs- und Verhalten, die Animation, Durchlässigkeit und Bitmapeffekte und <xref:System.Windows.Controls.Primitives.Popup> Größe und Position.  
  
<a name="OpenandCloseBehavior"></a>   
### <a name="open-and-close-behavior"></a>Öffnungs- und Schließverhalten  
 Ein <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement zeigt die Inhalte bei der <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> -Eigenschaftensatz auf `true`. Standardmäßig <xref:System.Windows.Controls.Primitives.Popup> bleibt geöffnet, bis die <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> -Eigenschaftensatz auf `false`. Allerdings können Sie das Standardverhalten ändern, durch Festlegen der <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A> Eigenschaft `false`. Wenn Sie diese Eigenschaft festlegen, um `false`, die <xref:System.Windows.Controls.Primitives.Popup> Content Fenster hat, Mauseingaben aufzufangen. Die <xref:System.Windows.Controls.Primitives.Popup> verliert Maus Capture als auch das Fenster geschlossen wird, tritt ein Mausereignis außerhalb der <xref:System.Windows.Controls.Primitives.Popup> Fenster.  
  
 Die <xref:System.Windows.Controls.Primitives.Popup.Opened> und <xref:System.Windows.Controls.Primitives.Popup.Closed> Ereignisse werden ausgelöst, wenn die <xref:System.Windows.Controls.Primitives.Popup> Content Fenster wird geöffnet oder geschlossen.  
  
<a name="Animation"></a>   
### <a name="animation"></a>Animation  
 Die <xref:System.Windows.Controls.Primitives.Popup> Steuerelement verfügt über integrierte Unterstützung für Animationen, die Verhaltensweisen wie auf- und Folie in in der Regel zugeordnet sind. Sie können diese Animationen aktivieren, durch Festlegen der <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A> Eigenschaft, um eine <xref:System.Windows.Controls.Primitives.PopupAnimation> Enumerationswert. Für <xref:System.Windows.Controls.Primitives.Popup> Animationen ordnungsgemäß funktioniert Sie müssen festlegen, die <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> Eigenschaft `true`.  
  
 Sie können auch anwenden, z. B. Animationen <xref:System.Windows.Media.Animation.Storyboard> auf die <xref:System.Windows.Controls.Primitives.Popup> Steuerelement.  
  
<a name="OpacityandBitmapEffects"></a>   
### <a name="opacity-and-bitmap-effects"></a>Deckkraft und Bitmapeffekte  
 Die <xref:System.Windows.UIElement.Opacity%2A> -Eigenschaft für eine <xref:System.Windows.Controls.Primitives.Popup> Steuerelement wirkt sich nicht auf dessen Inhalt. Wird standardmäßig die <xref:System.Windows.Controls.Primitives.Popup> Fensters Inhalt ist nicht transparent. So erstellen eine transparente <xref:System.Windows.Controls.Primitives.Popup>legen die <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> Eigenschaft `true`.  
  
 Der Inhalt des eine <xref:System.Windows.Controls.Primitives.Popup> erbt nicht Bitmapeffekte, z. B. <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>, dass Sie direkt festlegen der <xref:System.Windows.Controls.Primitives.Popup> Steuerelement oder ein anderes Element in das übergeordnete Fenster. Für Bitmapeffekte auf den Inhalt des angezeigt werden eine <xref:System.Windows.Controls.Primitives.Popup>, müssen Sie den Bitmapeffekt direkt auf dessen Inhalt festlegen. Z. B. wenn das untergeordnete Element des eine <xref:System.Windows.Controls.Primitives.Popup> ist ein <xref:System.Windows.Controls.StackPanel>, legen Sie den Bitmapeffekt ab, für die <xref:System.Windows.Controls.StackPanel>.  
  
<a name="PopupSize"></a>   
### <a name="popup-size"></a>Popup-Größe  
 Wird standardmäßig ein <xref:System.Windows.Controls.Primitives.Popup> automatisch an dessen Inhalt angepasst wird. Bei der automatischen Anpassung werden einige Bitmapeffekte ausgeblendet werden können, da die Standardgröße des Bildschirmbereichs, die für definiert ist die <xref:System.Windows.Controls.Primitives.Popup> Inhalte bietet keinen ausreichenden Speicherplatz für die Bitmapeffekte angezeigt.  
  
 <xref:System.Windows.Controls.Primitives.Popup>Inhalt kann auch verdeckt werden, wenn Sie festlegen, eine <xref:System.Windows.UIElement.RenderTransform%2A> auf den Inhalt. In diesem Szenario einige Inhalte möglicherweise ausgeblendet werden, wenn der Inhalt des transformierten <xref:System.Windows.Controls.Primitives.Popup> reicht über den Bereich des ursprünglichen <xref:System.Windows.Controls.Primitives.Popup>. Wenn ein Bitmapeffekt oder eine Transformation mehr Speicherplatz erforderlich ist, können Sie einen Rand um definieren die <xref:System.Windows.Controls.Primitives.Popup> Inhalt, um mehr Platz für das Steuerelement zu gewährleisten.  
  
<a name="DefiningPopupPosition"></a>   
## <a name="defining-the-popup-position"></a>Definieren der Popup-Position  
 Sie können ein Popup positionieren, durch Festlegen der <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A>, und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty> Eigenschaften. Weitere Informationen finden Sie unter [Verhalten beim Platzieren von Popups](../../../../docs/framework/wpf/controls/popup-placement-behavior.md). Wenn <xref:System.Windows.Controls.Primitives.Popup> wird angezeigt, auf dem Bildschirm, es ist nicht neu positionieren, selbst wenn das übergeordnete Element positioniert wird.  
  
<a name="CustomizingPopupPlacement"></a>   
### <a name="customizing-popup-placement"></a>Anpassen der Popupplatzierung  
 Können Sie die Platzierung der Anpassen einer <xref:System.Windows.Controls.Primitives.Popup> -Steuerelement durch Angabe der einen Satz von Koordinaten, die relativ sind die <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> soll die <xref:System.Windows.Controls.Primitives.Popup> angezeigt werden.  
  
 Um die Platzierung anzupassen, legen Sie die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A> Eigenschaft <xref:System.Windows.Controls.Primitives.PlacementMode.Custom>. Definieren Sie dann eine <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback> Delegat, der für eine Reihe von möglichen Platzierung Punkte und Primärachsen (in Prioritätsreihenfolge) gibt die <xref:System.Windows.Controls.Primitives.Popup>. Der Punkt, der den größten Teil zeigt die <xref:System.Windows.Controls.Primitives.Popup> wird automatisch ausgewählt. Ein Beispiel finden Sie unter [Angeben einer benutzerdefinierten Popupposition](../../../../docs/framework/wpf/controls/how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>   
## <a name="popup-and-the-visual-tree"></a>Popup und visuelle Struktur  
 Ein <xref:System.Windows.Controls.Primitives.Popup> Steuerelement verfügt nicht über einen eigenen visuellen Struktur; er gibt stattdessen eine Größe von 0 (null) bei der <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A> Methode zum <xref:System.Windows.Controls.Primitives.Popup> aufgerufen wird. Allerdings beim Festlegen der <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A> Eigenschaft <xref:System.Windows.Controls.Primitives.Popup> zu `true`, ein neues Fenster mit einer eigenen visuellen Struktur erstellt wird. Das neue Fenster enthält die <xref:System.Windows.Controls.Primitives.Popup.Child%2A> Inhalt der <xref:System.Windows.Controls.Primitives.Popup>. Die Breite und Höhe des neuen Fensters darf nicht größer als 75 Prozent der Breite oder Höhe des Bildschirms sein.  
  
 Die <xref:System.Windows.Controls.Primitives.Popup> Steuerelement behält einen Verweis auf die <xref:System.Windows.Controls.Primitives.Popup.Child%2A> als logischen untergeordneten Inhalt. Wenn das neue Fenster erstellt wird, wird den Inhalt des <xref:System.Windows.Controls.Primitives.Popup> wird ein visuelles untergeordnetes Fenster und bleibt Sie die logische untergeordneten von <xref:System.Windows.Controls.Primitives.Popup>. Im Gegensatz dazu <xref:System.Windows.Controls.Primitives.Popup> bleibt das logische übergeordnete Element seine <xref:System.Windows.Controls.Primitives.Popup.Child%2A> Inhalt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Primitives.Popup>  
 <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>  
 <xref:System.Windows.Controls.Primitives.PlacementMode>  
 <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>  
 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)
