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
ms.openlocfilehash: b85a607d2e44d6253359a81118f90e6ee05d2d3f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187324"
---
# <a name="troubleshooting-hybrid-applications"></a>Problembehandlung für Hybridanwendungen
<a name="introduction"></a>In diesem Thema werden einige häufige Probleme aufgeführt, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] beim Erstellen von Hybridanwendungen auftreten können, die sowohl Windows Forms-Technologien als auch Windows Forms-Technologien verwenden.  

<a name="overlapping_controls"></a>
## <a name="overlapping-controls"></a>Überlappende Steuerelemente  
 Steuerelemente überlappen sich möglicherweise nicht wie erwartet. Windows Forms verwendet für jedes Steuerelement eine separate HWND. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet ein HWND für den gesamten Inhalt auf einer Seite. Dieser Unterschied bei der Implementierung verursacht unerwartete Verhalten bei der Überlappung.  
  
 Ein windows Forms-Steuerelement, das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gehostet wird, wird immer über dem Inhalt angezeigt.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]In einem <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement gehostete Inhalte werden <xref:System.Windows.Forms.Integration.ElementHost> in der Z-Reihenfolge des Steuerelements angezeigt. Es ist möglich, Steuerelemente zu überlappen, <xref:System.Windows.Forms.Integration.ElementHost> aber der gehostete [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt wird nicht kombiniert oder interagiert nicht.  
  
<a name="child_property"></a>
## <a name="child-property"></a>Untergeordnete Eigenschaft  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.ElementHost> und-Klassen können nur ein einzelnes untergeordnetes Steuerelement oder Element hosten. Um mehr als ein Steuerelement oder Element zu hosten, muss ein Container als untergeordneter Inhalt verwendet werden. Sie können z. B. Windows Forms-Schaltflächen und Kontrollkästchensteuerelemente zu einem <xref:System.Windows.Forms.Panel?displayProperty=nameWithType> Steuerelement hinzufügen und dann das Bedienfeld der Eigenschaft eines <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelements <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> zuweisen. Sie können die Schaltflächen- und Kontrollkästchensteuerelemente <xref:System.Windows.Forms.Integration.WindowsFormsHost> jedoch nicht separat zu demselben Steuerelement hinzufügen.  
  
<a name="scaling"></a>
## <a name="scaling"></a>Skalierung  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]und Windows Forms haben unterschiedliche Skalierungsmodelle. Einige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Skalierungstransformationen sind für Windows Forms-Steuerelemente sinnvoll, andere jedoch nicht. Beispielsweise funktioniert das Skalieren eines Windows Forms-Steuerelements auf 0, aber wenn Sie versuchen, dasselbe Steuerelement auf einen Wert ungleich Null zu skalieren, bleibt die Größe des Steuerelements 0. Weitere Informationen finden Sie unter [Überlegungen zum Layout für das WindowsFormsHost-Element](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="adapter"></a>
## <a name="adapter"></a>Adapter  
 Beim Arbeiten der <xref:System.Windows.Forms.Integration.WindowsFormsHost> und-Klassen <xref:System.Windows.Forms.Integration.ElementHost> kann es zu Verwirrung kommen, da sie einen ausgeblendeten Container enthalten. Sowohl <xref:System.Windows.Forms.Integration.WindowsFormsHost> die <xref:System.Windows.Forms.Integration.ElementHost> als auch die Klassen verfügen über einen ausgeblendeten Container, der als *Adapter*bezeichnet wird und den sie zum Hosten von Inhalten verwenden. Für <xref:System.Windows.Forms.Integration.WindowsFormsHost> das Element leitet sich der <xref:System.Windows.Forms.ContainerControl?displayProperty=nameWithType> Adapter von der Klasse ab. Für <xref:System.Windows.Forms.Integration.ElementHost> das Steuerelement leitet sich der <xref:System.Windows.Controls.DockPanel> Adapter vom Element ab. Wenn Sie in anderen Interoperationsthemen Verweise auf den Adapter sehen, wird auf diesen Container Bezug genommen.  
  
<a name="nesting"></a>
## <a name="nesting"></a>Verschachtelung  
 Das Verschachteln <xref:System.Windows.Forms.Integration.WindowsFormsHost> <xref:System.Windows.Forms.Integration.ElementHost> eines Elements innerhalb eines Steuerelements wird nicht unterstützt. Das Verschachteln <xref:System.Windows.Forms.Integration.ElementHost> <xref:System.Windows.Forms.Integration.WindowsFormsHost> eines Steuerelements in einem Element wird ebenfalls nicht unterstützt.  
  
<a name="focus"></a>
## <a name="focus"></a>Focus  
 Fokus funktioniert [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in und Windows Forms anders, was bedeutet, dass Fokusprobleme in einer Hybridanwendung auftreten können. Wenn Sie z. B. <xref:System.Windows.Forms.Integration.WindowsFormsHost> den Fokus innerhalb eines Elements haben und entweder die Seite <xref:System.Windows.Forms.Integration.WindowsFormsHost> minimieren und wiederherstellen oder ein modales Dialogfeld anzeigen, kann der Fokus innerhalb des Elements verloren gehen. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element hat immer noch Fokus, aber die Kontrolle im Inneren kann nicht.  
  
 Die Datenvalidierung wird ebenfalls vom Fokus beeinflusst. Die Validierung <xref:System.Windows.Forms.Integration.WindowsFormsHost> funktioniert in einem Element, funktioniert jedoch <xref:System.Windows.Forms.Integration.WindowsFormsHost> nicht, wenn Sie <xref:System.Windows.Forms.Integration.WindowsFormsHost> das Element oder zwischen zwei verschiedenen Elementen ausklappen.  
  
<a name="property_mapping"></a>
## <a name="property-mapping"></a>Eigenschaftszuordnung  
 Einige Eigenschaftenzuordnungen erfordern eine umfassende Interpretation, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] um unterschiedliche Implementierungen zwischen den und Windows Forms-Technologien zu überbrücken. Eigenschaftszuordnungen ermöglichen es dem Code, auf Änderungen der Schriftarten, Farben und anderer Eigenschaften zu reagieren. Im Allgemeinen funktionieren Eigenschaftszuordnungen, indem Sie entweder *Property*Changed-Ereignisse oder On*Property*Changed-Aufrufe überwachen oder entsprechende Eigenschaften entweder für das untergeordnete Steuerelement oder den Adapter festlegen. Weitere Informationen finden Sie unter [Windows Forms and WPF Property Mapping (Eigenschaftenzuordnung von Windows Forms und WPF)](windows-forms-and-wpf-property-mapping.md).  
  
<a name="layoutrelated_properties_on_hosted_content"></a>
## <a name="layout-related-properties-on-hosted-content"></a>Layoutbezogene Eigenschaften in gehostetem Inhalt  
 Wenn <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=nameWithType> die <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=nameWithType> oder-Eigenschaft zugewiesen wird, werden mehrere layoutbezogene Eigenschaften für den gehosteten Inhalt automatisch festgelegt. Eine Änderung dieser Inhaltseigenschaften kann ein unerwartetes Layoutverhalten verursachen.  
  
 Ihr gehosteter Inhalt wird <xref:System.Windows.Forms.Integration.WindowsFormsHost> angedockt, um den und <xref:System.Windows.Forms.Integration.ElementHost> das übergeordnete Element auszufüllen. Zum Aktivieren dieses Füllverhaltens, werden bei der Festlegung der untergeordnete Eigenschaft mehrere Eigenschaften festgelegt. In der folgenden Tabelle wird aufgeführt, welche Inhaltseigenschaften von den <xref:System.Windows.Forms.Integration.ElementHost> und <xref:System.Windows.Forms.Integration.WindowsFormsHost> Klassen festgelegt werden.  
  
|Hostklasse|Content-Eigenschaften|  
|----------------|------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 Legen Sie diese Eigenschaften nicht direkt im gehosteten Inhalt fest. Weitere Informationen finden Sie unter [Überlegungen zum Layout für das WindowsFormsHost-Element](layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="navigation_applications"></a>
## <a name="navigation-applications"></a>Navigationsanwendungen  
 Navigationsanwendungen behalten den Benutzerstatus möglicherweise nicht bei. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element erstellt seine Steuerelemente neu, wenn es in einer Navigationsanwendung verwendet wird. Das erneute Erstellen von untergeordneten Steuerelementen tritt <xref:System.Windows.Forms.Integration.WindowsFormsHost> auf, wenn der Benutzer von der Seite, auf der das Element gehostet wird, weg navigiert und dann zu ihm zurückkehrt. Alle Inhalte, die vom Benutzer eingegeben wurden, gehen verloren.  
  
<a name="message_loop_interoperation"></a>
## <a name="message-loop-interoperation"></a>Interoperation für Nachrichtenschleifen  
 Beim Arbeiten mit Windows Forms-Nachrichtenschleifen werden Nachrichten möglicherweise nicht wie erwartet verarbeitet. Die <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> Methode wird <xref:System.Windows.Forms.Integration.WindowsFormsHost> vom Konstruktor aufgerufen. Diese Methode fügt der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Nachrichtenschleife einen Meldungsfilter hinzu. Dieser Filter <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> ruft die <xref:System.Windows.Forms.Control?displayProperty=nameWithType> Methode auf, wenn a das Ziel der Nachricht war, und übersetzt/sendet die Nachricht.  
  
 Wenn Sie <xref:System.Windows.Window> eine in einer Windows <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>Forms-Nachrichtenschleife mit anzeigen, können Sie nichts eingeben, es sei denn, Sie rufen die <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> Methode auf. Die <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> Methode <xref:System.Windows.Window> nimmt a <xref:System.Windows.Forms.IMessageFilter?displayProperty=nameWithType>und fügt eine hinzu, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die schlüsselbezogene Nachrichten an die Nachrichtenschleife umleitet. Weitere Informationen finden Sie unter [Eingabearchitektur für die Interoperabilität zwischen Windows Forms und WPF](windows-forms-and-wpf-interoperability-input-architecture.md).  
  
<a name="opacity_and_layering"></a>
## <a name="opacity-and-layering"></a>Deckkraft und Überlagern  
 Die <xref:System.Windows.Interop.HwndHost> Klasse unterstützt keine Layering. Dies bedeutet, <xref:System.Windows.UIElement.Opacity%2A> dass <xref:System.Windows.Forms.Integration.WindowsFormsHost> das Festlegen der Eigenschaft für das Element [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] keine <xref:System.Windows.Window.AllowsTransparency%2A> Auswirkungen `true`hat und keine Überblendung mit anderen Fenstern erfolgt, die auf festgelegt haben.  
  
<a name="dispose"></a>
## <a name="dispose"></a>Dispose  
 Wenn Klassen nicht korrekt gelöscht werden, kann es zu Ressourcenverlusten kommen. Stellen Sie in Ihren Hybridanwendungen sicher, dass die <xref:System.Windows.Forms.Integration.WindowsFormsHost> und-Klassen <xref:System.Windows.Forms.Integration.ElementHost> freigegeben sind, oder Sie können Ressourcen austreten. Windows Forms <xref:System.Windows.Forms.Integration.ElementHost> verfügt über Steuerelemente, wenn das nicht-modale <xref:System.Windows.Forms.Form> übergeordnete Element geschlossen wird. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]entsorgt <xref:System.Windows.Forms.Integration.WindowsFormsHost> Elemente, wenn die Anwendung heruntergefahren wird. Es ist möglich, <xref:System.Windows.Forms.Integration.WindowsFormsHost> ein <xref:System.Windows.Window> Element in einer in einer Windows Forms-Nachrichtenschleife anzuzeigen. In diesem Fall erhält der Code möglicherweise keine Benachrichtigung, dass die Anwendung beendet wird.  
  
<a name="enabling_visual_styles"></a>
## <a name="enabling-visual-styles"></a>Aktivieren von visuellen Stilen  
 Visuelle Stile von Microsoft Windows XP in einem Windows Forms-Steuerelement sind möglicherweise nicht aktiviert. Die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> Methode wird in der Vorlage für eine Windows Forms-Anwendung aufgerufen. Obwohl diese Methode nicht standardmäßig aufgerufen wird, erhalten Sie, wenn Sie Visual Studio zum Erstellen eines Projekts verwenden, visuelle Microsoft Windows XP-Stile für Steuerelemente, wenn Version 6.0 von Comctl32.dll verfügbar ist. Sie müssen <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> die Methode aufrufen, bevor Handles für den Thread erstellt werden. Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren von visuellen Stilen in einer Hybridanwendung](how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
<a name="licensed_controls"></a>
## <a name="licensed-controls"></a>Lizenzierte Steuerelemente  
 Lizenzierte Windows Forms-Steuerelemente, die dem Benutzer Lizenzinformationen in einem Meldungsfeld anzeigen, können zu unerwartetem Verhalten für eine Hybridanwendung führen. Einige lizenzierte Steuerelemente zeigen als Reaktion auf das Erstellen eines Ziehpunkts ein Dialogfeld an. Ein lizenziertes Steuerelement kann den Benutzer beispielsweise darüber informieren, dass eine Lizenz erforderlich ist oder der Benutzer das Steuerelement noch drei Mal zu Testzwecken benutzen kann.  
  
 Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Element leitet sich <xref:System.Windows.Interop.HwndHost> von der Klasse ab, und der <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> Handle des untergeordneten Steuerelements wird innerhalb der Methode erstellt. Die <xref:System.Windows.Interop.HwndHost> Klasse lässt nicht zu, <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A> dass Nachrichten in der Methode verarbeitet werden, aber das Anzeigen eines Dialogfelds bewirkt, dass Nachrichten gesendet werden. Um dieses Lizenzierungsszenario <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=nameWithType> zu aktivieren, rufen Sie die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Methode für das Steuerelement auf, bevor Sie sie als untergeordnetes Element zuweisen.  
  
<a name="wpf_designer"></a>
## <a name="wpf-designer"></a>WPF-Designer  
 Sie können Ihren WPF-Inhalt mithilfe des WPF-Designers für Visual Studio entwerfen. In den folgenden Abschnitten werden einige häufige Probleme aufgeführt, die beim Erstellen von Hybridanwendungen mit dem WPF-Designer auftreten können.  
  
### <a name="backcolortransparent-is-ignored-at-design-time"></a>BackColorTransparent wird zur Entwurfszeit ignoriert  
 Die <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> Eigenschaft funktioniert zur Entwurfszeit möglicherweise nicht wie erwartet.  
  
 Wenn sich ein WPF-Steuerelement nicht auf einem sichtbaren <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> übergeordneten Element befindet, ignoriert die WPF-Laufzeit den Wert. Der Grund, der ignoriert <xref:System.Windows.Forms.Integration.ElementHost> werden kann, <xref:System.AppDomain>ist, dass <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> ein Objekt in einem separaten erstellt wird. Wenn Sie die Anwendung <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> ausführen, funktioniert dies jedoch wie erwartet.  
  
### <a name="design-time-error-list-appears-when-the-obj-folder-is-deleted"></a>Entwurfszeit-Fehlerliste wird angezeigt, wenn der Ordner obj gelöscht wird  
 Wenn der Ordner obj gelöscht wird, wird die Entwurfszeit-Fehlerliste angezeigt.  
  
 Wenn Sie <xref:System.Windows.Forms.Integration.ElementHost>mit entwerfen, verwendet der Windows Forms Designer generierte Dateien im Ordner Debug oder Release im obj-Ordner Ihres Projekts. Wenn Sie diese Dateien löschen, wird die Entwurfszeit-Fehlerliste angezeigt. Um dieses Problem zu beheben, müssen Sie Ihr Projekt neu erstellen. Weitere Informationen finden Sie unter [Entwurfszeitfehler im Windows Forms-Designer](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md).  
  
<a name="elementhost_and_ime"></a>
## <a name="elementhost-and-ime"></a>ElementHost und IME  
 WPF-Steuerelemente, <xref:System.Windows.Forms.Integration.ElementHost> die in <xref:System.Windows.Forms.Control.ImeMode%2A> einer derzeit gehostetwerden, unterstützen die Eigenschaft nicht. Änderungen <xref:System.Windows.Forms.Control.ImeMode%2A> an werden von den gehosteten Steuerelementen ignoriert.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Interoperabilität im WPF-Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb628658(v=vs.100))
- [Eingabearchitektur für die Interoperabilität zwischen Windows Forms und WPF](windows-forms-and-wpf-interoperability-input-architecture.md)
- [Vorgehensweise: Aktivieren von visuellen Stilen in einer Hybridanwendung](how-to-enable-visual-styles-in-a-hybrid-application.md)
- [Überlegungen zum Layout für das WindowsFormsHost-Element](layout-considerations-for-the-windowsformshost-element.md)
- [Eigenschaftenzuordnung von Windows Forms und WPF](windows-forms-and-wpf-property-mapping.md)
- [Entwurfszeitfehler im Windows Forms-Designer](../../winforms/controls/design-time-errors-in-the-windows-forms-designer.md)
- [Migration und Interoperabilität](migration-and-interoperability.md)
