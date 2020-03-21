---
title: WPF- und Windows Forms-Interop
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- nester interoperation [WPF]
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid control [WPF interoperability]
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
ms.openlocfilehash: 76d1e97c92946267aa1217f52c93594fb63d20de
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187151"
---
# <a name="wpf-and-windows-forms-interoperation"></a>Interaktion zwischen WPF und Windows Forms
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]und Windows Forms stellen zwei verschiedene Architekturen zum Erstellen von Anwendungsschnittstellen dar. Der <xref:System.Windows.Forms.Integration?displayProperty=nameWithType> Namespace stellt Klassen bereit, die allgemeine Interoperationsszenarien ermöglichen. Die beiden Schlüsselklassen, die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Interoperationsfunktionen implementieren, sind und <xref:System.Windows.Forms.Integration.ElementHost>. In diesem Thema wird beschrieben, welche Interoperations-Szenarios unterstützt werden und welche nicht.  
  
> [!NOTE]
> Besondere Augenmerk wird dabei auf Szenarios mit *hybriden Steuerelementen* gelegt. Ein hybrides Steuerelement ist ein Steuerelement einer Technologie, das in ein Steuerelement anderer Technologie geschachtelt ist. Daher nennt man dies auch eine *geschachtelte Interoperation*. Ein *mehrstufiges hybrides Steuerelement* verfügt über mehr als eine Ebene hybrider Steuerelement-Schachtelung. Ein Beispiel für eine mehrstufige verschachtelte Interoperation [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist ein Windows Forms-Steuerelement, das ein Steuerelement enthält, das ein anderes Windows Forms-Steuerelement enthält. Mehrstufige hybride Steuerelemente werden nicht unterstützt.  

<a name="Windows_Presentation_Foundation_Application_Hosting"></a>
## <a name="hosting-windows-forms-controls-in-wpf"></a>Hosten eines Windows Forms-Steuerelements in WPF  
 Die folgenden Interoperationsszenarien werden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt, wenn ein Steuerelement ein Windows Forms-Steuerelement hostet:  
  
- Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelement kann ein oder mehrere Windows Forms-Steuerelemente mit XAML hosten.  
  
- Es kann ein oder mehrere Windows Forms-Steuerelemente mithilfe von Code hosten.  
  
- Es kann Windows Forms-Containersteuerelemente hosten, die andere Windows Forms-Steuerelemente enthalten.  
  
- Es kann ein Master-/Detailformular mit einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Master- und Windows Forms-Details hosten.  
  
- Es kann ein Master-/Detailformular mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] einem Windows Forms-Master und Details hosten.  
  
- Es kann ein oder mehrere ActiveX-Steuerelemente hosten.  
  
- Es kann ein oder mehrere zusammengesetzte Steuerelemente hosten.  
  
- Es kann hybride Steuerelemente mithilfe von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] hosten.  
  
- Es kann hybride Steuerelemente mithilfe von Code hosten.  
  
### <a name="layout-support"></a>Layout-Unterstützung  
 In der folgenden Liste werden <xref:System.Windows.Forms.Integration.WindowsFormsHost> die bekannten Einschränkungen beschrieben, wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das Element versucht, das gehostete Windows Forms-Steuerelement in das Layoutsystem zu integrieren.  
  
- In einigen Fällen kann die Größe von Windows Forms-Steuerelementen nicht oder nur für bestimmte Dimensionen geändert werden. Ein Windows Forms-Steuerelement <xref:System.Windows.Forms.ComboBox> unterstützt beispielsweise nur eine einzelne Höhe, die durch die Schriftgröße des Steuerelements definiert wird. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] einem dynamischen Layout, das davon ausgeht, <xref:System.Windows.Forms.ComboBox> dass Elemente vertikal gestreckt werden können, wird ein gehostetes Steuerelement nicht wie erwartet dehnt.  
  
- Windows Forms-Steuerelemente können nicht gedreht oder verzerrt werden. Wenn Sie beispielsweise ihre Benutzeroberfläche um 90 Grad drehen, behalten gehostete Windows Forms-Steuerelemente ihre aufrechte Position bei.  
  
- In den meisten Fällen unterstützen Windows Forms-Steuerelemente keine proportionale Skalierung. Obwohl die gesamten Dimensionen des Steuerelements skaliert werden, können untergeordnete Steuerelemente und Komponenten des Steuerelements unter Umständen nicht wie erwartet skaliert werden. Diese Einschränkung hängt davon ab, wie gut jedes Windows Forms-Steuerelement die Skalierung unterstützt.  
  
- In einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Benutzeroberfläche können Sie die Z-Reihenfolge der Elemente ändern, um ihr Verhalten bei Überlappung zu steuern. Ein gehostetes Windows Forms-Steuerelement wird in einem separaten HWND [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gezeichnet, sodass es immer über Elemente gezeichnet wird.  
  
- Windows Forms-Steuerelemente unterstützen die automatische Skalierung basierend auf der Schriftgröße. In einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Benutzeroberfläche bewirkt eine Änderung des Schriftgrads keine Größenänderung des gesamten Layouts; einzelne Elemente können ihre Größe jedoch ggf. dynamisch anpassen.  
  
### <a name="ambient-properties"></a>Umgebungseigenschaften  
 Einige umgebungseigenschaften [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] von Steuerelementen verfügen über Windows Forms-Äquivalente. Diese Umgebungseigenschaften werden an die gehosteten Windows Forms-Steuerelemente <xref:System.Windows.Forms.Integration.WindowsFormsHost> weitergegeben und als öffentliche Eigenschaften für das Steuerelement verfügbar gemacht. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement übersetzt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] jede Umgebungseigenschaft in das Windows Forms-Äquivalent.  
  
 Weitere Informationen finden Sie unter [Windows Forms and WPF Property Mapping (Eigenschaftenzuordnung von Windows Forms und WPF)](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Verhalten  
 In der folgenden Tabelle werden Interoperations-Verhalten beschrieben.  
  
|Verhalten|Unterstützt|Nicht unterstützt|  
|--------------|---------------|-------------------|  
|Transparenz|Das Windows Forms-Steuerelementrendering unterstützt Transparenz. Der Hintergrund des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] übergeordneten Steuerelements kann zum Hintergrund der gehosteten Windows Forms-Steuerelemente werden.|Einige Windows Forms-Steuerelemente unterstützen keine Transparenz. Die <xref:System.Windows.Forms.TextBox> und-Steuerelemente <xref:System.Windows.Forms.ComboBox> sind z. B. nicht transparent, wenn sie von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]gehostet werden.|  
|Wechseln mit der Tabulatortaste|Die Tab-Reihenfolge für gehostete Windows Forms-Steuerelemente ist die gleiche wie beim Gehosteten dieser Steuerelemente in einer Windows Forms-basierten Anwendung.<br /><br /> Das Tabing [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] von einem Steuerelement auf ein Windows Forms-Steuerelement mit der TAB-Taste und den UMSCHALT+TAB-Tasten funktioniert wie gewohnt.<br /><br /> Windows Forms-Steuerelemente <xref:System.Windows.Forms.Control.TabStop%2A> mit `false` einem Eigenschaftswert von erhalten keinen Fokus, wenn der Benutzer über Steuerelemente tabiert.<br /><br /> - <xref:System.Windows.Forms.Integration.WindowsFormsHost> Jedes Steuerelement <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> hat einen Wert, der bestimmt, wann dieses <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement den Fokus erhält.<br />- Windows Forms-Steuerelemente, <xref:System.Windows.Forms.Integration.WindowsFormsHost> die in einem <xref:System.Windows.Forms.Control.TabIndex%2A> Container enthalten sind, folgen der von der Eigenschaft angegebenen Reihenfolge. Wechselt man vom letzten Tabulatorindex weiter, wird der Fokus auf das nächste [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelement gesetzt, falls dies existiert. Wenn kein anderes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fokussierbares Steuerelement vorhanden ist, kehrt das Tabbing zum ersten Windows Forms-Steuerelement in der Registerkartenreihenfolge zurück.<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A>Werte für Steuerelemente innerhalb des <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelements sind relativ <xref:System.Windows.Forms.Integration.WindowsFormsHost> zu gleichgeordneten Windows Forms-Steuerelementen, die im Steuerelement enthalten sind.<br />-   Das Wechseln mit der Tabulatortaste respektiert Steuerelement-spezifisches Verhalten. Wenn Sie z. B. <xref:System.Windows.Forms.TextBox> die TAB-TASTE in einem Steuerelement drücken, das einen <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A> Eigenschaftswert von `true` hat, wird eine Registerkarte in das Textfeld eingegeben, anstatt den Fokus zu verschieben.|Nicht zutreffend|  
|Navigation mit Pfeiltasten|- Die Navigation mit <xref:System.Windows.Forms.Integration.WindowsFormsHost> den Pfeiltasten im Steuerelement ist die gleiche wie in einem gewöhnlichen Windows Forms-Containersteuerelement: Die Tasten UP ARROW und LEFT ARROW wählen das vorherige Steuerelement aus, und die Tasten DOWN ARROW und RIGHT ARROW wählen das nächste Steuerelement aus.<br />- Die Tasten UP ARROW und LEFT ARROW aus <xref:System.Windows.Forms.Integration.WindowsFormsHost> dem ersten Steuerelement, das im Steuerelement enthalten ist, führen die gleiche Aktion aus wie die Tastenkombination UMSCHALT+TAB. Wenn ein fokussierbares [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelement vorhanden <xref:System.Windows.Forms.Integration.WindowsFormsHost> ist, bewegt sich der Fokus außerhalb des Steuerelements. Dieses Verhalten unterscheidet sich <xref:System.Windows.Forms.ContainerControl> vom Standardverhalten dadurch, dass keine Umhüllung bis zum letzten Steuerelement erfolgt. Wenn kein anderes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fokussierbares Steuerelement vorhanden ist, kehrt der Fokus zum letzten Windows Forms-Steuerelement in der Registerkartenreihenfolge zurück.<br />- Die Tasten DOWN ARROW und RIGHT ARROW aus <xref:System.Windows.Forms.Integration.WindowsFormsHost> dem letzten Steuerelement, das im Steuerelement enthalten ist, führen die gleiche Aktion wie die TAB-Taste aus. Wenn ein fokussierbares [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelement vorhanden <xref:System.Windows.Forms.Integration.WindowsFormsHost> ist, bewegt sich der Fokus außerhalb des Steuerelements. Dieses Verhalten unterscheidet sich <xref:System.Windows.Forms.ContainerControl> vom Standardverhalten dadurch, dass kein Umbruch zum ersten Steuerelement erfolgt. Wenn kein anderes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fokussierbares Steuerelement vorhanden ist, kehrt der Fokus zum ersten Windows Forms-Steuerelement in der Registerkartenreihenfolge zurück.|Nicht zutreffend|  
|Zugriffstasten|Zugriffstasten funktionieren wie üblich, außer den in der Spalte "Nicht unterstützt" angegebenen.|Technologieübergreifend doppelt belegte Zugriffstasten funktionieren nicht wie gewöhnlich doppelt belegte Zugriffstasten. Wenn ein Beschleuniger über Technologien hinweg dupliziert wird, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wobei mindestens eine in einem Windows Forms-Steuerelement und die andere für ein Steuerelement verwendet wird, empfängt das Windows Forms-Steuerelement immer den Beschleuniger. Bei gedrückter Zugriffstaste wechselt der Fokus nicht zwischen den beiden Steuerelementen.|  
|Tastenkombinationen|Tastenkombinationen funktionieren wie üblich, außer den in der Spalte "Nicht unterstützt" angegebenen.|- Windows Forms-Tastenkombinationen, die in der Vorverarbeitungsphase behandelt werden, haben immer Vorrang vor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Tastenkombinationen. Wenn Sie z. <xref:System.Windows.Forms.ToolStrip> B. ein Steuerelement mit STRG+S-Tastenkombinationen definiert haben und ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Befehl an STRG+S gebunden ist, wird der <xref:System.Windows.Forms.ToolStrip> Steuerelementhandler immer zuerst aufgerufen, unabhängig vom Fokus.<br />- Windows Forms-Tastenkombinationen, <xref:System.Windows.Forms.Control.KeyDown> die vom Ereignis [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]behandelt werden, werden zuletzt in verarbeitet. Sie können dieses Verhalten verhindern, indem Sie <xref:System.Windows.Forms.Control.IsInputKey%2A> die Methode <xref:System.Windows.Forms.Control.PreviewKeyDown> des Windows Forms-Steuerelements überschreiben oder das Ereignis behandeln. Geben `true` Sie <xref:System.Windows.Forms.Control.IsInputKey%2A> von der Methode zurück, oder legen Sie den Wert der <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=nameWithType> Eigenschaft in Ihrem `true` <xref:System.Windows.Forms.Control.PreviewKeyDown> Ereignishandler fest.|  
|AcceptsReturn, AcceptsTab und andere steuerelementspezifische Verhalten|Eigenschaften, die das Standardverhalten der Tastatur ändern, funktionieren wie <xref:System.Windows.Forms.Control.IsInputKey%2A> gewohnt, `true`vorausgesetzt, das Windows Forms-Steuerelement überschreibt die Methode, die zurückgegeben werden soll.|Windows Forms-Steuerelemente, die das <xref:System.Windows.Forms.Control.KeyDown> Standardmäßige Tastaturverhalten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] durch Behandlung des Ereignisses ändern, werden zuletzt im Hoststeuerelement verarbeitet. Da diese Steuerelemente zuletzt verarbeitet werden, können sie zu unerwartetem Verhalten führen.|  
|Enter- und Leave-Ereignisse|Wenn der Fokus nicht <xref:System.Windows.Forms.Integration.ElementHost> auf das enthaltende Steuerelement ausgerichtet ist, werden die <xref:System.Windows.Forms.Integration.WindowsFormsHost> Enter- und Leave-Ereignisse wie gewohnt ausgelöst, wenn sich der Fokus in einem einzelnen Steuerelement ändert.|Bei folgenden Fokusänderungen werden die Enter- und Leave-Ereignisse nicht ausgelöst:<br /><br /> - Von innen <xref:System.Windows.Forms.Integration.WindowsFormsHost> nach außen ein Steuerelement.<br />- Von außen <xref:System.Windows.Forms.Integration.WindowsFormsHost> nach innen ein Steuerelement.<br />- Außerhalb einer <xref:System.Windows.Forms.Integration.WindowsFormsHost> Kontrolle.<br />- Von einem Windows Forms-Steuerelement, das in einem <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement gehostet wird, bis hin zu einem <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement, das innerhalb derselben <xref:System.Windows.Forms.Integration.WindowsFormsHost>gehostet wird.|  
|Multithreading|Alle Arten von Multithreading werden unterstützt.|Sowohl die Windows [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Forms als auch die Technologien setzen ein Parallelitätsmodell mit einem Thread voraus. Während des Debuggens lösen Aufrufe von Framework-Objekten aus anderen Threads eine Ausnahme aus, um diese Anforderung zu erzwingen.|  
|Sicherheit|Alle Interoperationsszenarios erfordern volle Vertrauenswürdigkeit.|Keine dieser Szenarios sind in teilweiser Vertrauenswürdigkeit zulässig.|  
|Barrierefreiheit|Alle Eingabehilfenszenarios werden unterstützt. Hilfstechnologieprodukte funktionieren ordnungsgemäß, wenn sie für Hybridanwendungen verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] werden, die sowohl Windows Forms als auch Steuerelemente enthalten.|Nicht zutreffend|  
|Zwischenablage|Alle Zwischenablageoperationen funktionieren wie üblich. Dazu gehört das Schneiden und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Einfügen zwischen Windows Forms und Steuerelementen.|Nicht zutreffend|  
|Drag & Drop-Funktion|Alle Drag & Drop-Operationen funktionieren wie üblich. Dies schließt Vorgänge [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zwischen Windows Forms und Steuerelementen ein.|Nicht zutreffend|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>
## <a name="hosting-wpf-controls-in-windows-forms"></a>Hosten von WPF-Steuerelementen in Windows Forms  
 Die folgenden Interoperationsszenarien werden unterstützt, wenn [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein Windows Forms-Steuerelement ein Steuerelement hostet:  
  
- Hosten von einem oder mehreren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelementen mithilfe von Code  
  
- Zuordnen eines Eigenschaftenblatts zu einem oder mehreren gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelementen  
  
- Hosten einer oder mehrerer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Seiten in einem Formular  
  
- Starten eines [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Fensters  
  
- Hosten eines Master-/Detailformulars [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mit einem Windows Forms-Master und Details.  
  
- Hosten eines Master-/Detailformulars mit einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Master- und Windows Forms-Details.  
  
- Hosten von benutzerdefinierten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelementen  
  
- Hosten von hybriden Steuerelementen  
  
### <a name="ambient-properties"></a>Umgebungseigenschaften  
 Einige der Umgebungseigenschaften von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Windows Forms-Steuerelementen weisen Entsprechungen auf. Diese Umgebungseigenschaften werden an die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gehosteten Steuerelemente weitergegeben <xref:System.Windows.Forms.Integration.ElementHost> und als öffentliche Eigenschaften für das Steuerelement verfügbar gemacht. Das <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement übersetzt jede Windows Forms-Umgebungseigenschaft in ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Äquivalente.  
  
 Weitere Informationen finden Sie unter [Windows Forms and WPF Property Mapping (Eigenschaftenzuordnung von Windows Forms und WPF)](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Verhalten  
 In der folgenden Tabelle werden Interoperations-Verhalten beschrieben.  
  
|Verhalten|Unterstützt|Nicht unterstützt|  
|--------------|---------------|-------------------|  
|Transparenz|Rendern von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelementen unterstützt Transparenz. Der Hintergrund des übergeordneten Windows Forms-Steuerelements kann zum Hintergrund gehosteter [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente werden.|Nicht zutreffend|  
|Multithreading|Alle Arten von Multithreading werden unterstützt.|Sowohl die Windows [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Forms als auch die Technologien setzen ein Parallelitätsmodell mit einem Thread voraus. Während des Debuggens lösen Aufrufe von Framework-Objekten aus anderen Threads eine Ausnahme aus, um diese Anforderung zu erzwingen.|  
|Sicherheit|Alle Interoperationsszenarios erfordern volle Vertrauenswürdigkeit.|Keine dieser Szenarios sind in teilweiser Vertrauenswürdigkeit zulässig.|  
|Barrierefreiheit|Alle Eingabehilfenszenarios werden unterstützt. Hilfstechnologieprodukte funktionieren ordnungsgemäß, wenn sie für Hybridanwendungen verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] werden, die sowohl Windows Forms als auch Steuerelemente enthalten.|Nicht zutreffend|  
|Zwischenablage|Alle Zwischenablageoperationen funktionieren wie üblich. Dazu gehört das Schneiden und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Einfügen zwischen Windows Forms und Steuerelementen.|Nicht zutreffend|  
|Drag & Drop-Funktion|Alle Drag & Drop-Operationen funktionieren wie üblich. Dies schließt Vorgänge [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zwischen Windows Forms und Steuerelementen ein.|Nicht zutreffend|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Eigenschaftenzuordnung von Windows Forms und WPF](windows-forms-and-wpf-property-mapping.md)
