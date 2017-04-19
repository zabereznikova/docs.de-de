---
title: "&#220;bersicht &#252;ber Popups | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Steuerelemente, Kontextmenü"
  - "Popup-Steuerelement [WPF], Informationen über das Popup-Steuerelement"
ms.assetid: 774f53ca-bff8-470e-9ce9-3928b4cf3d4c
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# &#220;bersicht &#252;ber Popups
Das <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement bietet eine Möglichkeit, Inhalt in einem separaten Fenster auszugeben, das in Relation zu den festgelegten Element\- oder Bildschirmkoordinaten unverankert über anderen Fenstern der Anwendung angezeigt wird.  In diesem Thema wird das <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement vorgestellt sowie dessen Verwendung veranschaulicht.  
  
   
  
<a name="What_Is_a_Popup_"></a>   
## Was ist ein Popup?  
 Ein <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement zeigt Inhalt in einem separaten Fenster an, das in Relation zu einem Element oder zu einer Bildschirmposition unverankert über anderen Fenstern der Anwendung angezeigt wird.  Wenn das <xref:System.Windows.Controls.Primitives.Popup> sichtbar ist, ist die <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A>\-Eigenschaft auf `true` festgelegt.  
  
> [!NOTE]
>  Ein <xref:System.Windows.Controls.Primitives.Popup> wird nicht automatisch geöffnet, wenn der Mauszeiger über sein übergeordnetes Objekt bewegt wird.  Wenn Sie möchten, dass ein <xref:System.Windows.Controls.Primitives.Popup> automatisch geöffnet wird, verwenden Sie die <xref:System.Windows.Controls.ToolTip>\-Klasse oder die <xref:System.Windows.Controls.ToolTipService>\-Klasse.  Weitere Informationen finden Sie unter [Übersicht über die QuickInfo](../../../../docs/framework/wpf/controls/tooltip-overview.md).  
  
<a name="APopupExample"></a>   
## Erstellen eines Popups  
 Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement definiert wird, das das untergeordnete Element eines <xref:System.Windows.Controls.Button>\-Steuerelements ist.  Da ein <xref:System.Windows.Controls.Button>\-Steuerelement nur über ein untergeordnetes Element verfügen kann, wird in diesem Beispiel der Text für das <xref:System.Windows.Controls.Button>\-Steuerelement und das <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement in einem <xref:System.Windows.Controls.StackPanel> abgelegt.  Der Inhalt des <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelements wird in einem <xref:System.Windows.Controls.TextBlock>\-Steuerelement angezeigt, das den entsprechenden Text in einem separaten Fenster ausgibt, das unverankert über dem Anwendungsfenster in der Nähe des verknüpften <xref:System.Windows.Controls.Button>\-Steuerelements angezeigt wird.  
  
 [!code-xml[PopupSimple#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#1)]  
  
 [!code-xml[PopupSimple#CreatePopupCodeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PopupSimple/CSharp/Window1.xaml#createpopupcodexaml)]  
  
<a name="PopupUses"></a>   
## Steuerelemente, die ein Popup implementieren  
 Sie können <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelemente in andere Steuerelemente einbauen.  Die folgenden Steuerelemente implementieren das <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement für bestimmte Verwendungsmöglichkeiten:  
  
-   <xref:System.Windows.Controls.ToolTip>.  Wenn Sie für ein Element eine QuickInfo erstellen möchten, verwenden Sie die <xref:System.Windows.Controls.ToolTip>\-Klasse und die <xref:System.Windows.Controls.ToolTipService>\-Klasse.  Weitere Informationen finden Sie unter [Übersicht über die QuickInfo](../../../../docs/framework/wpf/controls/tooltip-overview.md).  
  
-   <xref:System.Windows.Controls.ContextMenu>.  Wenn Sie für ein Element ein Kontextmenü erstellen möchten, verwenden Sie das <xref:System.Windows.Controls.ContextMenu>\-Steuerelement.  Weitere Informationen finden Sie unter [Übersicht über ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md).  
  
-   <xref:System.Windows.Controls.ComboBox>.  Wenn Sie ein Auswahlsteuerelement mit einem Dropdown\-Listenfeld erstellen möchten, das angezeigt oder ausgeblendet werden kann, verwenden Sie das <xref:System.Windows.Controls.ComboBox>\-Steuerelement.  
  
-   <xref:System.Windows.Controls.Expander>.  Wenn Sie ein Steuerelement erstellen möchten, das einen Header mit einem reduzierbaren Bereich anzeigt, in dem Inhalt ausgegeben wird, verwenden Sie das <xref:System.Windows.Controls.Expander>\-Steuerelement.  Weitere Informationen finden Sie unter [Übersicht über Expander\-Steuerelemente](../../../../docs/framework/wpf/controls/expander-overview.md).  
  
<a name="PopupBehaviorandAppearance"></a>   
## Verhalten und Darstellung von Popups  
 Das <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement stellt Funktionalität bereit, mit der Sie das Verhalten und die Darstellung von Popups anpassen können.  So können Sie beispielsweise das Verhalten beim Öffnen und Schließen, die Animation, Durchlässigkeit und Bitmapeffekte sowie die Größe und Position für ein <xref:System.Windows.Controls.Primitives.Popup> festlegen.  
  
<a name="OpenandCloseBehavior"></a>   
### Verhalten beim Öffnen und Schließen  
 Ein <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement zeigt seinen Inhalt an, wenn die <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A>\-Eigenschaft auf `true` festgelegt ist.  Standardmäßig bleibt ein <xref:System.Windows.Controls.Primitives.Popup> geöffnet, bis die <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A>\-Eigenschaft auf `false` festgelegt wird.  Sie können jedoch das Standardverhalten ändern, indem Sie die <xref:System.Windows.Controls.Primitives.Popup.StaysOpen%2A>\-Eigenschaft auf `false` festlegen.  Wenn Sie diese Eigenschaft auf `false` festlegen, verfügt das <xref:System.Windows.Controls.Primitives.Popup>\-Inhaltsfenster über eine Mauszeigererkennung.  Sobald ein Mausereignis außerhalb des <xref:System.Windows.Controls.Primitives.Popup>\-Fensters auftritt, verliert das <xref:System.Windows.Controls.Primitives.Popup> die Mauszeigererkennung, und das Fenster wird geschlossen.  
  
 Beim Öffnen oder Schließen eines <xref:System.Windows.Controls.Primitives.Popup>\-Inhaltsfensters wird das <xref:System.Windows.Controls.Primitives.Popup.Opened>\-Ereignis bzw. das <xref:System.Windows.Controls.Primitives.Popup.Closed>\-Ereignis ausgelöst.  
  
<a name="Animation"></a>   
### Animation  
 Das <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement bietet eine integrierte Unterstützung für Animationen, die typischerweise mit Verhalten wie Einblenden und Hereingleiten verknüpft sind.  Sie können diese Animationen aktivieren, indem Sie die <xref:System.Windows.Controls.Primitives.Popup.PopupAnimation%2A>\-Eigenschaft auf einen <xref:System.Windows.Controls.Primitives.PopupAnimation>\-Enumerationswert festlegen.  Damit <xref:System.Windows.Controls.Primitives.Popup>\-Animationen ordnungsgemäß funktionieren, müssen Sie die <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A>\-Eigenschaft auf `true` festlegen.  
  
 Sie können außerdem Animationen wie <xref:System.Windows.Media.Animation.Storyboard> für das <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement übernehmen.  
  
<a name="OpacityandBitmapEffects"></a>   
### Durchlässigkeit und Bitmapeffekte  
 Die <xref:System.Windows.UIElement.Opacity%2A>\-Eigenschaft eines <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelements hat keine Auswirkungen auf seinen Inhalt.  Standardmäßig ist das <xref:System.Windows.Controls.Primitives.Popup>\-Inhaltsfenster nicht transparent.  Um ein transparentes <xref:System.Windows.Controls.Primitives.Popup> zu erstellen, legen Sie die <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A>\-Eigenschaft auf `true` fest.  
  
 Der Inhalt eines <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelements erbt keine Bitmapeffekte, z. B. <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>, die Sie direkt im <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement oder in einem beliebigen anderen Element im übergeordneten Fenster festgelegt haben.  Um Bitmapeffekte im <xref:System.Windows.Controls.Primitives.Popup>\-Inhalt anzuzeigen, müssen Sie die Bitmapeffekte direkt in dessen Inhalt festlegen.  Wenn z. B. das untergeordnete Steuerelement eines <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelements ein <xref:System.Windows.Controls.StackPanel> ist, legen Sie den Bitmapeffekt im <xref:System.Windows.Controls.StackPanel> fest.  
  
<a name="PopupSize"></a>   
### Größe von Popups  
 Standardmäßig wird die Größe eines <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelements automatisch an dessen Inhalt angepasst.  Bei einer automatischen Größenanpassung kann es vorkommen, dass einige Bitmapeffekte ausgeblendet werden, weil die für das <xref:System.Windows.Controls.Primitives.Popup> definierte Standardgröße des Bildschirmbereichs nicht genügend Platz zur Anzeige der Bitmapeffekte aufweist.  
  
 Der <xref:System.Windows.Controls.Primitives.Popup>\-Inhalt kann auch verdeckt werden, wenn Sie ein <xref:System.Windows.UIElement.RenderTransform%2A> auf den Inhalt festgelegt haben.  In diesem Szenario wird ein Teil des Inhalts ausgeblendet, wenn der Inhalt des transformierten <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelements über den Bereich des ursprünglichen <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelements hinausreicht.  Wenn ein Bitmapeffekt oder eine Transformation mehr Platz benötigt, können Sie einen Rand um den <xref:System.Windows.Controls.Primitives.Popup>\-Inhalt definieren, um für das Steuerelement einen größeren Bereich bereitzustellen.  
  
<a name="DefiningPopupPosition"></a>   
## Definieren der Position von Popups  
 Sie können ein Popup durch Festlegen der folgenden Eigenschaften positionieren: <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A>, <xref:System.Windows.Controls.Primitives.Popup.PlacementRectangle%2A>, <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>, <xref:System.Windows.Controls.Primitives.Popup.HorizontalOffset%2A> und <xref:System.Windows.Controls.Primitives.Popup.VerticalOffsetProperty>.  Weitere Informationen finden Sie unter [Verhalten beim Platzieren von Popups](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).  Wenn ein <xref:System.Windows.Controls.Primitives.Popup> auf dem Bildschirm angezeigt wird, wird es bei einer Neupositionierung des übergeordneten Elements nicht neu positioniert.  
  
<a name="CustomizingPopupPlacement"></a>   
### Anpassen der Platzierung von Popups  
 Sie können die Platzierung eines <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelements anpassen, indem Sie eine Reihe von Koordinaten festlegen, die in Relation zum <xref:System.Windows.Controls.Primitives.Popup.PlacementTarget%2A> angeben, wo das <xref:System.Windows.Controls.Primitives.Popup> angezeigt werden soll.  
  
 Um die Platzierung anzupassen, legen Sie die <xref:System.Windows.Controls.Primitives.Popup.Placement%2A>\-Eigenschaft auf <xref:System.Windows.Controls.Primitives.PlacementMode> fest.  Definieren Sie dann einen <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>\-Delegaten, der eine Reihe von möglichen Platzierungspunkten und Primärachsen \(nach dem Grad der Bevorzugung geordnet\) für das <xref:System.Windows.Controls.Primitives.Popup> zurückgibt.  Der Punkt, der den größten Teil des <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelements anzeigt, wird automatisch ausgewählt.  Ein Beispiel finden Sie unter [Angeben einer benutzerdefinierten Popup\-Position](../../../../docs/framework/wpf/controls/how-to-specify-a-custom-popup-position.md).  
  
<a name="PopupandtheVisualTree"></a>   
## Popup und visuelle Struktur  
 Ein <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement verfügt über keine eigene [visuelle Struktur](GTMT), sondern gibt stattdessen eine Größe von 0 \(null\) zurück, wenn die <xref:System.Windows.Controls.Primitives.Popup.MeasureOverride%2A>\-Methode für das <xref:System.Windows.Controls.Primitives.Popup> aufgerufen wird.  Wenn Sie jedoch die <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A>\-Eigenschaft des <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelements auf `true` festlegen, wird ein neues Fenster mit einer eigenen visuellen Struktur erstellt.  Das neue Fenster enthält den <xref:System.Windows.Controls.Primitives.Popup.Child%2A>\-Inhalt von <xref:System.Windows.Controls.Primitives.Popup>.  Die Breite und Höhe des neuen Fensters darf 75 Prozent der Bildschirmbreite oder \-höhe nicht überschreiten.  
  
 Das <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelement führt einen Verweis auf seinen <xref:System.Windows.Controls.Primitives.Popup.Child%2A>\-Inhalt als logisches untergeordnetes Element.  Beim Erstellen des neuen Fensters wird der <xref:System.Windows.Controls.Primitives.Popup>\-Inhalt ein visuelles untergeordnetes Fensterelement und bleibt weiterhin das logische untergeordnete Element des <xref:System.Windows.Controls.Primitives.Popup>\-Steuerelements.  Umgekehrt bleibt <xref:System.Windows.Controls.Primitives.Popup> das logische übergeordnete Element seines <xref:System.Windows.Controls.Primitives.Popup.Child%2A>\-Inhalts.  
  
## Siehe auch  
 <xref:System.Windows.Controls.Primitives.Popup>   
 <xref:System.Windows.Controls.Primitives.PopupPrimaryAxis>   
 <xref:System.Windows.Controls.Primitives.PlacementMode>   
 <xref:System.Windows.Controls.Primitives.CustomPopupPlacement>   
 <xref:System.Windows.Controls.Primitives.CustomPopupPlacementCallback>   
 <xref:System.Windows.Controls.ToolTip>   
 <xref:System.Windows.Controls.ToolTipService>   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)