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
ms.openlocfilehash: 46d8f00f9328e9c0a4df596b709195ae42d651bf
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960133"
---
# <a name="troubleshooting-hybrid-applications"></a>Problembehandlung für Hybridanwendungen
<a name="introduction"></a>In diesem Thema werden einige der häufigsten Probleme aufgeführt, die beim Erstellen von Hybridanwendungen, die sowohl die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]- als auch die [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Technologie verwenden, auftreten können,.  

<a name="overlapping_controls"></a>   
## <a name="overlapping-controls"></a>Überlappende Steuerelemente  
 Steuerelemente überlappen sich möglicherweise nicht wie erwartet. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] verwendet ein verschiedenes HWND für jedes Steuerelement. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet ein HWND für den gesamten Inhalt auf einer Seite. Dieser Unterschied bei der Implementierung verursacht unerwartete Verhalten bei der Überlappung.  
  
 Ein in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gehostetes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement wird immer über dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt angezeigt.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement gehosteter Inhalt wird in der z-Reihenfolge des <xref:System.Windows.Forms.Integration.ElementHost>-Steuer Elements angezeigt. Es ist möglich, <xref:System.Windows.Forms.Integration.ElementHost> Steuerelemente zu überlappen, aber der gehostete [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt kombiniert oder interagiert nicht.  
  
<a name="child_property"></a>   
## <a name="child-property"></a>Untergeordnete Eigenschaft  
 Die Klassen <xref:System.Windows.Forms.Integration.WindowsFormsHost> und <xref:System.Windows.Forms.Integration.ElementHost> können nur ein einzelnes untergeordnetes Steuerelement oder Element hosten. Um mehr als ein Steuerelement oder Element zu hosten, muss ein Container als untergeordneter Inhalt verwendet werden. Beispielsweise können Sie einem <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> Steuerelement [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Schaltflächen-und Kontrollkästchen-Steuerelemente hinzufügen und dann den Bereich der <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> Eigenschaft eines <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuer Elements zuweisen. Sie können jedoch die Schaltflächen-und Kontrollkästchen-Steuerelemente nicht separat dem gleichen <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement hinzufügen.  
  
<a name="scaling"></a>   
## <a name="scaling"></a>Skalieren  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] verfügen über unterschiedliche Skalierungsmodelle. Einige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Skalierungstransformationen eignen sich für [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelemente, andere jedoch nicht. Zum Beispiel funktioniert das Skalieren eines [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelements auf 0. Wenn Sie aber versuchen, das gleiche Steuerelement danach auf einen Wert ungleich null zu skalieren, bleibt die Größe des Steuerelements 0. Weitere Informationen finden Sie unter [Überlegungen zum Layout für das WindowsFormsHost-Element](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="adapter"></a>   
## <a name="adapter"></a>Adapter  
 Beim Arbeiten der <xref:System.Windows.Forms.Integration.WindowsFormsHost>-und <xref:System.Windows.Forms.Integration.ElementHost> Klassen können Verwirrung auftreten, da Sie einen verborgenen Container enthalten. Die Klassen <xref:System.Windows.Forms.Integration.WindowsFormsHost> und <xref:System.Windows.Forms.Integration.ElementHost> haben einen ausgeblendeten Container ( *Adapter*), den Sie zum Hosten von Inhalten verwenden. Für das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element wird der Adapter von der <xref:System.Windows.Forms.ContainerControl?displayProperty=nameWithType>-Klasse abgeleitet. Für das <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement wird der Adapter vom <xref:System.Windows.Controls.DockPanel>-Element abgeleitet. Wenn Sie in anderen Interoperationsthemen Verweise auf den Adapter sehen, wird auf diesen Container Bezug genommen.  
  
<a name="nesting"></a>   
## <a name="nesting"></a>Schachteln  
 Das Schachteln eines <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Elements in einem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement wird nicht unterstützt. Das Schachteln eines <xref:System.Windows.Forms.Integration.ElementHost>-Steuer Elements in einem <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element wird ebenfalls nicht unterstützt.  
  
<a name="focus"></a>   
## <a name="focus"></a>Fokus  
 Der Fokus funktioniert in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] anders als in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Daher können bei einer Hybridanwendung Fokusprobleme auftreten. Wenn Sie z. b. den Fokus innerhalb eines <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elements haben und die Seite minimieren und Wiederherstellen oder ein modales Dialogfeld anzeigen, kann der Fokus innerhalb des <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elements verloren gehen. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element hat noch den Fokus, aber das Steuerelement darin ist möglicherweise nicht.  
  
 Die Datenvalidierung wird ebenfalls vom Fokus beeinflusst. Die Validierung funktioniert in einem <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element, funktioniert aber nicht, wenn Sie das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element oder zwischen zwei unterschiedlichen <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elementen auslagern.  
  
<a name="property_mapping"></a>   
## <a name="property-mapping"></a>Eigenschaftszuordnung  
 Einige Eigenschaftszuordnungen benötigen eine umfangreiche Interpretation zur Überbrückung unterschiedlicher Implementierungen in den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]- und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Technologien. Eigenschaftszuordnungen ermöglichen es dem Code, auf Änderungen der Schriftarten, Farben und anderer Eigenschaften zu reagieren. Im Allgemeinen funktionieren Eigenschaftszuordnungen, indem Sie entweder *Property*Changed-Ereignisse oder On*Property*Changed-Aufrufe überwachen oder entsprechende Eigenschaften entweder für das untergeordnete Steuerelement oder den Adapter festlegen. Weitere Informationen finden Sie unter [Eigenschaftenzuordnung von Windows Forms und WPF](windows-forms-and-wpf-property-mapping.md).  
  
<a name="layoutrelated_properties_on_hosted_content"></a>   
## <a name="layout-related-properties-on-hosted-content"></a>Layoutbezogene Eigenschaften in gehostetem Inhalt  
 Wenn die <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=nameWithType>-oder <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=nameWithType>-Eigenschaft zugewiesen wird, werden mehrere Layouteigenschaften für den gehosteten Inhalt automatisch festgelegt. Eine Änderung dieser Inhaltseigenschaften kann ein unerwartetes Layoutverhalten verursachen.  
  
 Der gehostete Inhalt wird angedockt, um die <xref:System.Windows.Forms.Integration.WindowsFormsHost> und <xref:System.Windows.Forms.Integration.ElementHost> übergeordnetes Element auszufüllen. Zum Aktivieren dieses Füllverhaltens, werden bei der Festlegung der untergeordnete Eigenschaft mehrere Eigenschaften festgelegt. In der folgenden Tabelle sind die Inhalts Eigenschaften aufgeführt, die von den Klassen <xref:System.Windows.Forms.Integration.ElementHost> und <xref:System.Windows.Forms.Integration.WindowsFormsHost> festgelegt werden.  
  
|Hostklasse|Content-Eigenschaften|  
|----------------|------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 Legen Sie diese Eigenschaften nicht direkt im gehosteten Inhalt fest. Weitere Informationen finden Sie unter [Überlegungen zum Layout für das WindowsFormsHost-Element](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="navigation_applications"></a>   
## <a name="navigation-applications"></a>Navigationsanwendungen  
 Navigationsanwendungen behalten den Benutzerstatus möglicherweise nicht bei. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element erstellt seine Steuerelemente neu, wenn es in einer Navigations Anwendung verwendet wird. Das Neuerstellen von untergeordneten Steuerelementen erfolgt, wenn der Benutzer von der Seite weg navigiert, die das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element gehostet, und dann wieder zurückgegeben wird. Alle Inhalte, die vom Benutzer eingegeben wurden, gehen verloren.  
  
<a name="message_loop_interoperation"></a>   
## <a name="message-loop-interoperation"></a>Interoperation für Nachrichtenschleifen  
 Bei der Arbeit mit [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Nachrichtenschleifen werden Nachrichten möglicherweise nicht wie erwartet verarbeitet. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>-Methode wird vom <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Konstruktor aufgerufen. Diese Methode fügt der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Nachrichtenschleife einen Meldungsfilter hinzu. Dieser Filter Ruft die <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType>-Methode auf, wenn ein <xref:System.Windows.Forms.Control?displayProperty=nameWithType> das Ziel der Nachricht war und die Nachricht übersetzt/sendet.  
  
 Wenn Sie eine <xref:System.Windows.Window> in einer [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Message-Schleife mit <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>anzeigen, können Sie nichts eingeben, es sei denn, Sie nennen die <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>-Methode. Die <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>-Methode nimmt eine <xref:System.Windows.Window> an und fügt eine <xref:System.Windows.Forms.IMessageFilter?displayProperty=nameWithType>hinzu, mit der wichtige Meldungen an die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Nachrichten Schleife umgeleitet werden. Weitere Informationen finden Sie unter [Eingabearchitektur für die Interoperabilität zwischen Windows Forms und WPF](windows-forms-and-wpf-interoperability-input-architecture.md).  
  
<a name="opacity_and_layering"></a>   
## <a name="opacity-and-layering"></a>Deckkraft und Überlagern  
 Die <xref:System.Windows.Interop.HwndHost>-Klasse unterstützt keine Schichten. Dies bedeutet, dass das Festlegen der <xref:System.Windows.UIElement.Opacity%2A>-Eigenschaft für das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element keine Auswirkung hat und keine Vermischung mit anderen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Fenstern stattfindet, für die <xref:System.Windows.Window.AllowsTransparency%2A> auf `true`festgelegt ist.  
  
<a name="dispose"></a>   
## <a name="dispose"></a>Löschen  
 Wenn Klassen nicht korrekt gelöscht werden, kann es zu Ressourcenverlusten kommen. Stellen Sie in ihren Hybrid Anwendungen sicher, dass die Klassen <xref:System.Windows.Forms.Integration.WindowsFormsHost> und <xref:System.Windows.Forms.Integration.ElementHost> verworfen werden, oder Sie könnten Ressourcen verwerfen. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelemente frei, wenn das nicht modale <xref:System.Windows.Forms.Form> übergeordnete Element geschlossen wird. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] löscht <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente, wenn die Anwendung heruntergefahren wird. Es ist möglich, ein <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element in einer <xref:System.Windows.Window> in einer [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Message-Schleife anzuzeigen. In diesem Fall erhält der Code möglicherweise keine Benachrichtigung, dass die Anwendung beendet wird.  
  
<a name="enabling_visual_styles"></a>   
## <a name="enabling-visual-styles"></a>Aktivieren von visuellen Stilen  
 Visuelle Microsoft Windows XP-Stile in einem [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelement sind möglicherweise nicht aktiviert. Die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>-Methode wird in der Vorlage für eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Anwendung aufgerufen. Obwohl diese Methode nicht standardmäßig aufgerufen wird und Sie Visual Studio zum Erstellen eines Projekts verwenden, erhalten Sie visuelle Microsoft Windows XP-Stile für Steuerelemente, wenn Version 6,0 von ComCtl32. dll verfügbar ist. Sie müssen die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>-Methode vor dem Erstellen von Handles im Thread aufzurufen. Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren von visuellen Stilen in einer Hybridanwendung](how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
<a name="licensed_controls"></a>   
## <a name="licensed-controls"></a>Lizenzierte Steuerelemente  
 Lizenzierte [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelemente, die dem Benutzer Lizenzierungsinformationen in einem Meldungsfeld anzeigen, können bei einer Hybridanwendung möglicherweise ein unerwartetes Verhalten auslösen. Einige lizenzierte Steuerelemente zeigen als Reaktion auf das Erstellen eines Ziehpunkts ein Dialogfeld an. Ein lizenziertes Steuerelement kann den Benutzer beispielsweise darüber informieren, dass eine Lizenz erforderlich ist oder der Benutzer das Steuerelement noch drei Mal zu Testzwecken benutzen kann.  
  
 Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element wird von der <xref:System.Windows.Interop.HwndHost>-Klasse abgeleitet, und das Handle des untergeordneten Steuer Elements wird innerhalb der <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A>-Methode erstellt. Die <xref:System.Windows.Interop.HwndHost>-Klasse lässt die Verarbeitung von Nachrichten in der <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A>-Methode nicht zu, aber das Anzeigen eines Dialog Felds bewirkt, dass Nachrichten gesendet werden. Um dieses Lizenzierungs Szenario zu aktivieren, müssen Sie die <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=nameWithType>-Methode für das-Steuerelement aufzurufen, bevor Sie es als untergeordnetes <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element zuweisen.  
  
<a name="wpf_designer"></a>   
## <a name="wpf-designer"></a>WPF-Designer  
 Sie können den WPF-Inhalt mit dem WPF-Designer für Visual Studio entwerfen. In den folgenden Abschnitten werden einige allgemeine Probleme aufgelistet, die beim Erstellen von Hybrid Anwendungen mit dem WPF-Designer auftreten können.  
  
### <a name="backcolortransparent-is-ignored-at-design-time"></a>BackColorTransparent wird zur Entwurfszeit ignoriert  
 Die <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>-Eigenschaft funktioniert möglicherweise zur Entwurfszeit nicht wie erwartet.  
  
 Wenn ein WPF-Steuerelement nicht in einem sichtbaren übergeordneten Element ist, ignoriert die WPF-Laufzeit den <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> Wert. Der Grund, warum <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> ignoriert werden kann, liegt darin, dass <xref:System.Windows.Forms.Integration.ElementHost> Objekt in einem separaten <xref:System.AppDomain>erstellt wird. Wenn Sie die Anwendung ausführen, funktioniert <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> jedoch erwartungsgemäß.  
  
### <a name="design-time-error-list-appears-when-the-obj-folder-is-deleted"></a>Entwurfszeit-Fehlerliste wird angezeigt, wenn der Ordner obj gelöscht wird  
 Wenn der Ordner obj gelöscht wird, wird die Entwurfszeit-Fehlerliste angezeigt.  
  
 Wenn Sie mit <xref:System.Windows.Forms.Integration.ElementHost>entwerfen, verwendet die Windows Forms-Designer generierte Dateien im Ordner "Debug" oder "Release" im Ordner "obj" des Projekts. Wenn Sie diese Dateien löschen, wird die Entwurfszeit-Fehlerliste angezeigt. Um dieses Problem zu beheben, müssen Sie Ihr Projekt neu erstellen. Weitere Informationen finden Sie unter [Entwurfszeitfehler im Windows Forms-Designer](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md).  
  
<a name="elementhost_and_ime"></a>   
## <a name="elementhost-and-ime"></a>ElementHost und IME  
 WPF-Steuerelemente, die in einem <xref:System.Windows.Forms.Integration.ElementHost> gehostet werden, unterstützen derzeit die <xref:System.Windows.Forms.Control.ImeMode%2A>-Eigenschaft nicht. Änderungen an <xref:System.Windows.Forms.Control.ImeMode%2A> werden von den gehosteten Steuerelementen ignoriert.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Interoperabilität im WPF-Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628658(v=vs.100))
- [Eingabearchitektur für die Interoperabilität zwischen Windows Forms und WPF](windows-forms-and-wpf-interoperability-input-architecture.md)
- [Gewusst wie: Aktivieren von visuellen Stilen in einer Hybridanwendung](how-to-enable-visual-styles-in-a-hybrid-application.md)
- [Überlegungen zum Layout für das WindowsFormsHost-Element](layout-considerations-for-the-windowsformshost-element.md)
- [Eigenschaftenzuordnung von Windows Forms und WPF](windows-forms-and-wpf-property-mapping.md)
- [Entwurfszeitfehler im Windows Forms-Designer](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md)
- [Migration und Interoperabilität](migration-and-interoperability.md)
