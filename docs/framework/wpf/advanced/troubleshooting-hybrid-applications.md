---
title: "Problembehandlung f&#252;r Hybridanwendungen | Microsoft Docs"
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
  - "Hybridanwendungen [WPF-Interoperabilität]"
  - "Interoperabilität [WPF], Windows Forms"
  - "Meldungsschleifen [WPF]"
  - "Überlappende Steuerelemente"
  - "Windows Forms [WPF], Interoperabilität mit"
  - "Windows Forms, WPF-Interoperation"
ms.assetid: f440c23f-fa5d-4d5a-852f-ba61150e6405
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Problembehandlung f&#252;r Hybridanwendungen
<a name="introduction"></a> In diesem Thema werden häufige Probleme aufgeführt, die beim Erstellen von Hybridanwendungen auftreten können, die sowohl [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Technologie als auch [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Technologie verwenden.  
  
   
  
<a name="overlapping_controls"></a>   
## Überlappende Steuerelemente  
 Steuerelemente überlappen sich möglicherweise nicht wie erwartet.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] verwendet verschiedene HWNDs für die einzelnen Steuerelemente.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet ein HWND für den gesamten Inhalt einer Seite.  Dieser Unterschied bei der Implementierung verursacht unerwartetes Verhalten beim Überlappen.  
  
 Ein in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gehostetes [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement wird immer über dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt angezeigt.  
  
 In einem <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement gehosteter [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt wird in der Z\-Reihenfolge des <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelements angezeigt.  <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelemente können sich überlappen, aber der gehostete [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt wird nicht zusammengeführt, oder es findet keine Interaktion statt.  
  
<a name="child_property"></a>   
## Untergeordnete Eigenschaft  
 Die <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Klasse und die <xref:System.Windows.Forms.Integration.ElementHost>\-Klasse können nur ein einzelnes untergeordnetes Steuerelement oder Element hosten.  Um mehrere Steuerelemente oder Elemente zu hosten, müssen Sie einen Container als untergeordneten Inhalt verwenden.  Sie können beispielsweise [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente für Schaltflächen und Kontrollkästchen zu einem <xref:System.Windows.Forms.Panel?displayProperty=fullName>\-Steuerelement hinzufügen und anschließend den Bereich der <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A>\-Eigenschaft eines <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Steuerelements hinzufügen.  Sie können die Steuerelemente für die Schaltfläche und das Kontrollkästchen jedoch nicht einzeln zu demselben <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Steuerelement hinzufügen.  
  
<a name="scaling"></a>   
## Skalieren  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] haben verschiedene Skalierungsmodelle.  Nicht alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Skalierungstransformationen sind für [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente sinnvoll.  Das Skalieren eines [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelements auf 0 \(null\) ist zwar möglich, aber wenn Sie versuchen, das gleiche Steuerelement danach auf einen Wert zu skalieren, der nicht 0 entspricht, bleibt die Größe des Steuerelements 0.  Weitere Informationen finden Sie unter [Überlegungen zum Layout für das WindowsFormsHost\-Element](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="adapter"></a>   
## Adapter  
 Beim Bearbeiten der <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Klasse und der <xref:System.Windows.Forms.Integration.ElementHost>\-Klasse kann es zu Verwechslungen kommen, da diese Klassen einen ausgeblendeten Container enthalten.  Sowohl die <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Klasse als auch die <xref:System.Windows.Forms.Integration.ElementHost>\-Klasse enthält einen ausgeblendeten Container, der zum Hosten von Inhalt verwendet und als *Adapter* bezeichnet wird.  Für das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element wird der Adapter von der <xref:System.Windows.Forms.ContainerControl?displayProperty=fullName>\-Klasse abgeleitet.  Für das <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement wird der Adapter vom <xref:System.Windows.Controls.DockPanel>\-Element abgeleitet.  Wenn Sie in anderen Interoperationsthemen Verweise auf den Adapter finden, handelt es sich um diesen Container.  
  
<a name="nesting"></a>   
## Schachtelung  
 Das Schachteln eines <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Elements in einem <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelement wird nicht unterstützt.  Das Schachteln eines <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelements in einem <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element wird ebenfalls nicht unterstützt.  
  
<a name="focus"></a>   
## Focus  
 Der Fokus in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hat eine andere Funktionsweise als der in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Dies kann in einer Hybridanwendung zu Fokusproblemen führen.  Wenn sich beispielsweise der Fokus innerhalb eines <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Elements befindet und Sie die Seite entweder minimieren und wiederherstellen oder ein modales Dialogfeld anzeigen, kann der Fokus innerhalb des <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Elements verloren gehen.  Der Fokus befindet sich immer noch im <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element, jedoch möglicherweise nicht im Steuerelement.  
  
 Auch die Datenvalidierung wird vom Fokus beeinflusst.  Die Validierung funktioniert in einem <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element, jedoch nicht, wenn Sie durch Drücken der TAB\-TASTE das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element verlassen oder zwischen zwei verschiedenen <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Elementen wechseln.  
  
<a name="property_mapping"></a>   
## Eigenschaftenzuordnung  
 Einige Eigenschaftenzuordnungen erfordern eine ausführliche Auslegung, um unterschiedliche Implementierungen in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Technologie und der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Technologie zu überbrücken.  Durch Eigenschaftenzuordnungen ist der Code in der Lage, auf Änderungen von Schriftarten, Farben und anderen Eigenschaften zu reagieren.  Eigenschaftenzuordnungen funktionieren im Allgemeinen durch Überwachen von *Property*Changed\-Ereignissen oder On*Property*Changed\-Aufrufen und durch das Festlegen von geeigneten Eigenschaften für das untergeordnete Steuerelement oder den dazugehörigen Adapter.  Weitere Informationen finden Sie unter [Eigenschaftenzuordnung von Windows Forms und WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md).  
  
<a name="layoutrelated_properties_on_hosted_content"></a>   
## Layoutbezogene Eigenschaften in gehostetem Inhalt  
 Wenn die <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A?displayProperty=fullName>\-Eigenschaft oder die <xref:System.Windows.Forms.Integration.ElementHost.Child%2A?displayProperty=fullName>\-Eigenschaft zugewiesen ist, werden mehrere layoutbezogene Eigenschaften im gehosteten Inhalt automatisch festgelegt.  Wenn diese Inhaltseigenschaften geändert werden, kann dies ein unerwartetes Layoutverhalten verursachen.  
  
 Der gehostete Inhalt ist so angedockt, dass die übergeordneten Elemente <xref:System.Windows.Forms.Integration.WindowsFormsHost> und <xref:System.Windows.Forms.Integration.ElementHost> gefüllt werden.  Um dieses Füllverhalten zu aktivieren, werden beim Festlegen der untergeordneten Eigenschaft mehrere Eigenschaften festgelegt.  In der folgenden Tabelle werden die Inhaltseigenschaften aufgeführt, die von der <xref:System.Windows.Forms.Integration.ElementHost>\-Klasse und der <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Klasse festgelegt werden.  
  
|Host\-Klasse|Inhaltseigenschaften|  
|------------------|--------------------------|  
|<xref:System.Windows.Forms.Integration.ElementHost>|<xref:System.Windows.FrameworkElement.Height%2A><br /><br /> <xref:System.Windows.FrameworkElement.Width%2A><br /><br /> <xref:System.Windows.FrameworkElement.Margin%2A><br /><br /> <xref:System.Windows.FrameworkElement.VerticalAlignment%2A><br /><br /> <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>|  
|<xref:System.Windows.Forms.Integration.WindowsFormsHost>|<xref:System.Windows.Forms.Control.Margin%2A><br /><br /> <xref:System.Windows.Forms.Control.Dock%2A><br /><br /> <xref:System.Windows.Forms.Control.AutoSize%2A><br /><br /> <xref:System.Windows.Forms.Control.Location%2A><br /><br /> <xref:System.Windows.Forms.Control.MaximumSize%2A>|  
  
 Legen Sie diese Eigenschaften nicht direkt im gehosteten Inhalt fest.  Weitere Informationen finden Sie unter [Überlegungen zum Layout für das WindowsFormsHost\-Element](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md).  
  
<a name="navigation_applications"></a>   
## Navigationsanwendungen  
 Navigationsanwendungen behalten möglicherweise den Benutzerstatus nicht bei.  Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element erstellt seine Steuerelemente neu, wenn es in einer Navigationsanwendung verwendet wird.  Untergeordnete Steuerelemente werden neu erstellt, wenn der Benutzer die Seite verlässt, die das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element hostet, und dann zu der Seite zurückkehrt.  Jeglicher vom Benutzer eingegebener Inhalt geht verloren.  
  
<a name="message_loop_interoperation"></a>   
## Interoperation für Nachrichtenschleifen  
 Wenn sie mit [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Nachrichtenschleifen arbeiten, werden Meldungen möglicherweise nicht erwartungsgemäß verarbeitet.  Die <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>\-Methode wird vom <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Konstruktor aufgerufen.  Diese Methode fügt der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Nachrichtenschleife einen Meldungsfilter hinzu.  Dieser Filter ruft die <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=fullName>\-Methode auf, wenn ein <xref:System.Windows.Forms.Control?displayProperty=fullName> das Ziel der Meldung war, und die Meldung wird übersetzt\/weitergeleitet.  
  
 Wenn Sie ein <xref:System.Windows.Window> in einer [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Nachrichtenschleife mit <xref:System.Windows.Forms.Application.Run%2A?displayProperty=fullName> anzeigen, können Sie nur dann etwas eingeben, wenn Sie die <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>\-Methode aufrufen.  Die <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>\-Methode verwendet ein <xref:System.Windows.Window> und fügt einen <xref:System.Windows.Forms.IMessageFilter?displayProperty=fullName> hinzu, wodurch schlüsselbezogene Meldungen in die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Nachrichtenschleife umgeleitet werden.  Weitere Informationen finden Sie unter [Eingabearchitektur für die Interoperabilität zwischen Windows Forms und WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-interoperability-input-architecture.md).  
  
<a name="opacity_and_layering"></a>   
## Deckkraft und Überlagern  
 Das Überlagern wird von der <xref:System.Windows.Interop.HwndHost>\-Klasse nicht unterstützt.  Wenn die <xref:System.Windows.UIElement.Opacity%2A>\-Eigenschaft auf dem <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element festgelegt wird, hat dies keine Auswirkungen, und es findet kein Blending mit anderen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Fenstern statt, für die <xref:System.Windows.Window.AllowsTransparency%2A> auf `true` festgelegt ist.  
  
<a name="dispose"></a>   
## Dispose  
 Wenn Klassen nicht korrekt freigegeben werden, kann es zu Ressourcenverlusten kommen.  Vergewissern Sie sich, dass in Ihren Hybridanwendungen die <xref:System.Windows.Forms.Integration.WindowsFormsHost>\- und die <xref:System.Windows.Forms.Integration.ElementHost>\-Klasse freigegeben werden, da es sonst zu Ressourcenverlusten kommen kann.  [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] gibt <xref:System.Windows.Forms.Integration.ElementHost>\-Steuerelemente frei, wenn das nicht modale übergeordnete <xref:System.Windows.Forms.Form>\-Element geschlossen wird. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Elemente frei, wenn die Anwendung beendet wird.  In einem <xref:System.Windows.Window> einer [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Nachrichtenschleife kann ein <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element angezeigt werden.  In diesem Fall empfängt der Code möglicherweise keine Benachrichtigung, dass die Anwendung beendet wird.  
  
<a name="enabling_visual_styles"></a>   
## Aktivieren von visuellen Stilen  
 Visuelle [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]\-Stile auf einem [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelement dürfen nicht aktiviert werden.  Die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>\-Methode wird in der Vorlage für eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Anwendung aufgerufen.  Obwohl diese Methode nicht standardmäßig aufgerufen wird, wenn Sie [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] verwenden, um ein Projekt zu erstellen, rufen Sie [!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)] visuelle Stile für Steuerelemente ab, wenn Version 6.0 von Comctl32.dll verfügbar ist. Sie müssen die <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>\-Methode aufrufen, bevor Handles auf dem Thread erstellt werden.  Weitere Informationen finden Sie unter [Gewusst wie: Aktivieren von visuellen Stilen in einer Hybridanwendung](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
<a name="licensed_controls"></a>   
## Lizenzierte Steuerelemente  
 Lizenzierte [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]\-Steuerelemente, die Lizenzierungsinformationen in einem Meldungsfeld für den Benutzer anzeigen, können bei einer Hybridanwendung unerwartetes Verhalten verursachen.  Einige lizenzierte Steuerelemente zeigen als Reaktion auf das Erstellen von Handles ein Dialogfeld an.  Ein lizenziertes Steuerelement kann den Benutzer beispielsweise darüber informieren, dass eine Lizenz erforderlich ist oder dass der Benutzer das Steuerelement noch drei Mal zu Testzwecken verwenden kann.  
  
 Das <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Element wird von der <xref:System.Windows.Interop.HwndHost>\-Klasse abgeleitet, und das Handle für das untergeordnete Steuerelement wird innerhalb der <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A>\-Methode erstellt.  Die <xref:System.Windows.Interop.HwndHost>\-Klasse lässt es nicht zu, dass Meldungen in der <xref:System.Windows.Forms.Integration.WindowsFormsHost.BuildWindowCore%2A>\-Methode verarbeitet werden, aber wenn ein Dialogfeld angezeigt wird, verursacht dies, dass Meldungen gesendet werden.  Um dieses Lizenzierungsszenario zu ermöglichen, rufen Sie die <xref:System.Windows.Forms.Control.CreateControl%2A?displayProperty=fullName>\-Methode auf dem Steuerelement auf, bevor Sie es als das untergeordnete Element des <xref:System.Windows.Forms.Integration.WindowsFormsHost>\-Elements zuweisen.  
  
<a name="wpf_designer"></a>   
## WPF\-Designer  
 Sie können den WPF\-Inhalt mithilfe von [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] entwerfen.  In den folgenden Abschnitten sind häufige Probleme aufgelistet, die beim Erstellen von Hybridanwendungen mit dem [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] auftreten können.  
  
### BackColorTransparent wird zur Entwurfszeit ignoriert  
 Die <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>\-Eigenschaft funktioniert zur Entwurfszeit ggf. nicht wie erwartet.  
  
 Wenn ein WPF\-Steuerelement nicht auf einem sichtbaren übergeordneten Element angeordnet ist, ignoriert die WPF\-Laufzeit den <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A>\-Wert.  Der Grund dafür, dass <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> ggf. ignoriert wird, besteht darin, dass das <xref:System.Windows.Forms.Integration.ElementHost>\-Objekt in einem separaten <xref:System.AppDomain>\-Objekt erstellt wird.  Wenn Sie die Anwendung ausführen, funktioniert <xref:System.Windows.Forms.Integration.ElementHost.BackColorTransparent%2A> jedoch wie erwartet.  
  
### Entwurfszeitfehlerliste wird angezeigt, wenn der Ordner obj gelöscht wird  
 Wenn der Ordner obj gelöscht wird, wird die Entwurfszeitfehlerliste angezeigt.  
  
 Beim Entwerfen mit <xref:System.Windows.Forms.Integration.ElementHost> verwendet der Windows Forms\-Designer generierte Dateien im Ordner Debug bzw. Release innerhalb des Ordners obj des Projekts.  Wenn Sie diese Dateien löschen, wird die Entwurfszeitfehlerliste angezeigt.  Um dieses Problem zu beheben, müssen Sie das Projekt neu erstellen.  Weitere Informationen finden Sie unter [Entwurfszeitfehler im Windows Forms\-Designer](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md).  
  
<a name="elementhost_and_ime"></a>   
## ElementHost und IME  
 In einem <xref:System.Windows.Forms.Integration.ElementHost>\-Objekt gehostete WPF\-Steuerelemente unterstützen die <xref:System.Windows.Forms.Control.ImeMode%2A>\-Eigenschaft momentan nicht.  Änderungen von <xref:System.Windows.Forms.Control.ImeMode%2A> werden von den gehosteten Steuerelementen ignoriert.  
  
## Siehe auch  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Interoperabilität im WPF\-Designer](http://msdn.microsoft.com/de-de/2cb7c1ca-2a75-463b-8801-fba81e2b7042)   
 [Eingabearchitektur für die Interoperabilität zwischen Windows Forms und WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-interoperability-input-architecture.md)   
 [Gewusst wie: Aktivieren von visuellen Stilen in einer Hybridanwendung](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)   
 [Überlegungen zum Layout für das WindowsFormsHost\-Element](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)   
 [Eigenschaftenzuordnung von Windows Forms und WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)   
 [Entwurfszeitfehler im Windows Forms\-Designer](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)   
 [Migration und Interoperabilität](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)