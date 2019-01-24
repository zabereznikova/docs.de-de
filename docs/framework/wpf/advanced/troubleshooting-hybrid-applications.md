---
title: Problembehandlung für Hybridanwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- overlapping controls [WPF]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid applications [WPF interoperability]
- message loops [WPF]
ms.assetid: f440c23f-fa5d-4d5a-852f-ba61150e6405
ms.openlocfilehash: 3e8b8d6f59525720def413b2d19f048d3cff329c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710117"
---
# <a name="troubleshooting-hybrid-applications"></a>Problembehandlung für Hybridanwendungen
<a name="introduction"></a>In diesem Thema werden einige der häufigsten Probleme aufgeführt, die beim Erstellen von Hybridanwendungen, die sowohl die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]- als auch die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Technologie verwenden, auftreten können,.  
  

  
<a name="overlapping_controls"></a>   
## <a name="overlapping-controls"></a>Überlappende Steuerelemente  
 Steuerelemente überlappen sich möglicherweise nicht wie erwartet. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] verwendet ein verschiedenes HWND für jedes Steuerelement. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet ein HWND für den gesamten Inhalt auf einer Seite. Dieser Unterschied bei der Implementierung verursacht unerwartete Verhalten bei der Überlappung.  
  
 Ein in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gehostetes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement wird immer über dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt angezeigt.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt gehostet wird, eine <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement angezeigt wird, auf die Z-Reihenfolge von der <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement. Es ist möglich, die sich überschneiden <xref:System.Windows.Forms.Integration.ElementHost> Steuerelemente verwendet werden soll, aber das gehostete [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt nicht kombiniert oder interagieren.  
  
<a name="child_property"></a>   
## <a name="child-property"></a>Untergeordnete Eigenschaft  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> und <xref:System.Windows.Forms.Integration.ElementHost> Klassen können nur ein einzelnes untergeordnetes Steuerelement oder Element hosten. Um mehr als ein Steuerelement oder Element zu hosten, muss ein Container als untergeordneter Inhalt verwendet werden. Sie könnten z. B. hinzufügen [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Schaltfläche und das Kontrollkästchen-Steuerelementen zu einem <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> steuern, und weisen Sie den Bereich ein <xref:System.Windows.Forms.Integration.WindowsFormsHost> des Steuerelements <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> Eigenschaft. Allerdings können Sie die Schaltfläche und das Kontrollkästchen Steuerelemente hinzufügen separat auf den gleichen <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement.  
  
<a name="scaling"></a>   
## <a name="scaling"></a>Skalieren  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] verfügen über unterschiedliche Skalierungsmodelle. Einige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Skalierungstransformationen eignen sich für [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelemente, andere jedoch nicht. Zum Beispiel funktioniert das Skalieren eines [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelements auf 0. Wenn Sie aber versuchen, das gleiche Steuerelement danach auf einen Wert ungleich null zu skalieren, bleibt die Größe des Steuerelements 0. Weitere Informationen finden Sie unter [Überlegungen zum Layout für das WindowsFormsHost-Element](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="adapter"></a>   
## <a name="adapter"></a>Adapter  
 Es kann zu Verwechslungen kommen bei der Arbeit der <xref:System.Windows.Forms.Integration.WindowsFormsHost> und <xref:System.Windows.Forms.Integration.ElementHost> Klassen, da sie einen ausgeblendeten Container enthalten. Sowohl die <xref:System.Windows.Forms.Integration.WindowsFormsHost> und <xref:System.Windows.Forms.Integration.ElementHost> Klassen verfügen über einen ausgeblendeten Container Namens eine *Adapter*, der zum Hosten von Inhalt verwendet. Für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element der Adapter leitet sich von der <xref:System.Windows.Forms.ContainerControl?displayProperty=nameWithType> Klasse. Für die <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement, der Adapter leitet sich von der <xref:System.Windows.Controls.DockPanel> Element. Wenn Sie in anderen Interoperationsthemen Verweise auf den Adapter sehen, wird auf diesen Container Bezug genommen.  
  
<a name="nesting"></a>   
## <a name="nesting"></a>Schachteln  
 Schachteln einer <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element innerhalb einer <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement wird nicht unterstützt. Schachteln einer <xref:System.Windows.Forms.Integration.ElementHost> -Steuerelement innerhalb einer <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element wird ebenfalls nicht unterstützt.  
  
<a name="focus"></a>   
## <a name="focus"></a>Fokus  
 Der Fokus funktioniert in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] anders als in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Daher können bei einer Hybridanwendung Fokusprobleme auftreten. Z. B., wenn Sie den Fokus innerhalb einer <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element, und Sie entweder zu minimieren und Wiederherstellen die Seite oder ein modales Dialogfeld anzeigen, konzentrieren Sie sich innerhalb der <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element möglicherweise verloren. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element weiterhin den Fokus besitzt, aber das Steuerelement möglicherweise nicht.  
  
 Die Datenvalidierung wird ebenfalls vom Fokus beeinflusst. Die Validierung funktioniert in einer <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element, aber es funktioniert nicht, wie Sie Sie auf der Registerkarte die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element, oder zwischen zwei verschiedenen <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente.  
  
<a name="property_mapping"></a>   
## <a name="property-mapping"></a>Eigenschaftszuordnung  
 Einige Eigenschaftszuordnungen benötigen eine umfangreiche Interpretation zur Überbrückung unterschiedlicher Implementierungen in den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]- und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Technologien. Eigenschaftszuordnungen ermöglichen es dem Code, auf Änderungen der Schriftarten, Farben und anderer Eigenschaften zu reagieren. Im Allgemeinen funktionieren Eigenschaftszuordnungen, indem Sie entweder *Property*Changed-Ereignisse oder On*Property*Changed-Aufrufe überwachen oder entsprechende Eigenschaften entweder für das untergeordnete Steuerelement oder den Adapter festlegen. Weitere Informationen finden Sie unter [Eigenschaftenzuordnung von Windows Forms und WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).  
  
<a name="layoutrelated_properties_on_hosted_content"></a>   
## <a name="layout-related-properties-on-hosted-content"></a>Layoutbezogene Eigenschaften in gehostetem Inhalt  
 Wenn die <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=nameWithType> oder <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=nameWithType> -Eigenschaft zugewiesen ist, werden mehrere layoutbezogene Eigenschaften im gehosteten Inhalt automatisch festgelegt. Eine Änderung dieser Inhaltseigenschaften kann ein unerwartetes Layoutverhalten verursachen.  
  
 Der gehostete Inhalt docken Sie füllend der <xref:System.Windows.Forms.Integration.WindowsFormsHost> und <xref:System.Windows.Forms.Integration.ElementHost> übergeordnete Element. Zum Aktivieren dieses Füllverhaltens, werden bei der Festlegung der untergeordnete Eigenschaft mehrere Eigenschaften festgelegt. Die folgende Tabelle enthält die Content-Eigenschaften, indem festgelegt werden die <xref:System.Windows.Forms.Integration.ElementHost> und <xref:System.Windows.Forms.Integration.WindowsFormsHost> Klassen.  
  
|Hostklasse|Content-Eigenschaften|  
|----------------|------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 Legen Sie diese Eigenschaften nicht direkt im gehosteten Inhalt fest. Weitere Informationen finden Sie unter [Überlegungen zum Layout für das WindowsFormsHost-Element](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="navigation_applications"></a>   
## <a name="navigation-applications"></a>Navigationsanwendungen  
 Navigationsanwendungen behalten den Benutzerstatus möglicherweise nicht bei. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> -Element erstellt seine Steuerelemente neu, wenn er in einer navigationsanwendung verwendet wird. Neuerstellen von untergeordneten Steuerelementen tritt auf, wenn der Benutzer, Weg von der Seite hostet navigiert die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element und anschließend zurück. Alle Inhalte, die vom Benutzer eingegeben wurden, gehen verloren.  
  
<a name="message_loop_interoperation"></a>   
## <a name="message-loop-interoperation"></a>Interoperation für Nachrichtenschleifen  
 Bei der Arbeit mit [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Nachrichtenschleifen werden Nachrichten möglicherweise nicht wie erwartet verarbeitet. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> Methode wird aufgerufen, indem die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Konstruktor. Diese Methode fügt der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Nachrichtenschleife einen Meldungsfilter hinzu. Dieser Filter Ruft die <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> Methode Wenn eine <xref:System.Windows.Forms.Control?displayProperty=nameWithType> war das Ziel der Nachricht und die Meldung wird übersetzt/weitergeleitet.  
  
 Wenn Sie anzeigen eine <xref:System.Windows.Window> in eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] -Nachrichtenschleife mit <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>, Sie können nicht alles eingeben, es sei denn, Sie rufen die <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> Methode. Die <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> -Methode übernimmt eine <xref:System.Windows.Window> und fügt eine <xref:System.Windows.Forms.IMessageFilter?displayProperty=nameWithType>, die leitet für Schlüssel relevante Nachrichten an die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Nachrichtenschleife. Weitere Informationen finden Sie unter [Eingabearchitektur für die Interoperabilität zwischen Windows Forms und WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-interoperability-input-architecture.md).  
  
<a name="opacity_and_layering"></a>   
## <a name="opacity-and-layering"></a>Deckkraft und Überlagern  
 Die <xref:System.Windows.Interop.HwndHost> Klasse unterstützt die Überlagerung nicht. Dies bedeutet, dass diese Einstellung die <xref:System.Windows.UIElement.Opacity%2A> Eigenschaft für die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element hat keine Auswirkungen, und keine Mischung erfolgt mit anderen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Windows die <xref:System.Windows.Window.AllowsTransparency%2A> festgelegt `true`.  
  
<a name="dispose"></a>   
## <a name="dispose"></a>Löschen  
 Wenn Klassen nicht korrekt gelöscht werden, kann es zu Ressourcenverlusten kommen. Stellen Sie in Ihren hybridanwendungen sicher, dass die <xref:System.Windows.Forms.Integration.WindowsFormsHost> und <xref:System.Windows.Forms.Integration.ElementHost> -Klassen gelöscht werden, oder Sie können zur Offenlegung von Ressourcen. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] verwirft <xref:System.Windows.Forms.Integration.ElementHost> steuert, wann das nicht modale <xref:System.Windows.Forms.Form> übergeordnete geschlossen wird. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwirft <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente, wenn die Anwendung beendet. Es ist möglich, zeigen eine <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element in einer <xref:System.Windows.Window> in eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Nachrichtenschleife. In diesem Fall erhält der Code möglicherweise keine Benachrichtigung, dass die Anwendung beendet wird.  
  
<a name="enabling_visual_styles"></a>   
## <a name="enabling-visual-styles"></a>Aktivieren von visuellen Stilen  
 Visuelle [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]-Stile für ein [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement dürfen nicht aktiviert werden. Die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> Methode wird aufgerufen, in der Vorlage für eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Anwendung. Obwohl diese Methode nicht standardmäßig aufgerufen wird, wenn Sie [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] zur Erstellung eines Projekts verwenden, erhalten Sie visuelle [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]-Stile für Steuerelemente, wenn Version 6.0 von Comctl32.dll verfügbar ist. Rufen Sie die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> -Methode auf, bevor die Handles für den Thread erstellt werden. Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren von visuellen Stilen in einer Hybridanwendung](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
<a name="licensed_controls"></a>   
## <a name="licensed-controls"></a>Lizenzierte Steuerelemente  
 Lizenzierte [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelemente, die dem Benutzer Lizenzierungsinformationen in einem Meldungsfeld anzeigen, können bei einer Hybridanwendung möglicherweise ein unerwartetes Verhalten auslösen. Einige lizenzierte Steuerelemente zeigen als Reaktion auf das Erstellen eines Ziehpunkts ein Dialogfeld an. Ein lizenziertes Steuerelement kann den Benutzer beispielsweise darüber informieren, dass eine Lizenz erforderlich ist oder der Benutzer das Steuerelement noch drei Mal zu Testzwecken benutzen kann.  
  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element leitet sich von der <xref:System.Windows.Interop.HwndHost> -Klasse, und dem untergeordneten Steuerelement Handle wird erstellt, in der <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> Methode. Die <xref:System.Windows.Interop.HwndHost> Klasse lässt sich nicht auf Nachrichten verarbeitet werden die <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> -Methode, aber das Anzeigen eines Dialogfelds bewirkt, dass Nachrichten gesendet werden. Um dieses Lizenzierungsszenario zu aktivieren, rufen die <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=nameWithType> Methode für das Steuerelement vor der Zuweisung als die <xref:System.Windows.Forms.Integration.WindowsFormsHost> untergeordnete Element des Elements.  
  
<a name="wpf_designer"></a>   
## <a name="wpf-designer"></a>WPF-Designer  
 Sie können den WPF-Inhalt mit dem [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] entwerfen. Die folgenden Abschnitte enthalten einige der häufigsten Probleme, die beim Erstellen von Hybridanwendungen mit dem [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] auftreten können.  
  
### <a name="backcolortransparent-is-ignored-at-design-time"></a>BackColorTransparent wird zur Entwurfszeit ignoriert  
 Die <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> Eigenschaft möglicherweise nicht erwartungsgemäß zur Entwurfszeit.  
  
 Wenn ein WPF-Steuerelement nicht auf einem übergeordneten Element sichtbar ist, ignoriert die WPF-Laufzeit die <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> Wert. Der Grund, <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> möglicherweise ignoriert liegt daran, dass <xref:System.Windows.Forms.Integration.ElementHost> -Objekt wird erstellt, in einer separaten <xref:System.AppDomain>. Wenn Sie jedoch die Anwendung ausführen <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> funktioniert wie erwartet.  
  
### <a name="design-time-error-list-appears-when-the-obj-folder-is-deleted"></a>Entwurfszeit-Fehlerliste wird angezeigt, wenn der Ordner obj gelöscht wird  
 Wenn der Ordner obj gelöscht wird, wird die Entwurfszeit-Fehlerliste angezeigt.  
  
 Beim Entwerfen mit <xref:System.Windows.Forms.Integration.ElementHost>, der Windows Forms-Designer verwendet die generierte Dateien im Ordner "Debug oder Release" im Ordner "Obj" Ihres Projekts. Wenn Sie diese Dateien löschen, wird die Entwurfszeit-Fehlerliste angezeigt. Um dieses Problem zu beheben, müssen Sie Ihr Projekt neu erstellen. Weitere Informationen finden Sie unter [Entwurfszeitfehler im Windows Forms-Designer](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md).  
  
<a name="elementhost_and_ime"></a>   
## <a name="elementhost-and-ime"></a>ElementHost und IME  
 Gehostete WPF-Steuerelemente einem <xref:System.Windows.Forms.Integration.ElementHost> unterstützen derzeit nicht die <xref:System.Windows.Forms.Control.ImeMode%2A> Eigenschaft. Änderungen an <xref:System.Windows.Forms.Control.ImeMode%2A> werden von den gehosteten Steuerelementen ignoriert.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Interoperabilität im WPF-Designer](https://msdn.microsoft.com/library/2cb7c1ca-2a75-463b-8801-fba81e2b7042)
- [Eingabearchitektur für die Interoperabilität zwischen Windows Forms und WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-interoperability-input-architecture.md)
- [Vorgehensweise: Aktivieren von visuellen Stilen in einer Hybridanwendung](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)
- [Überlegungen zum Layout für das WindowsFormsHost-Element](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)
- [Eigenschaftenzuordnung von Windows Forms und WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)
- [Entwurfszeitfehler im Windows Forms-Designer](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)
- [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
