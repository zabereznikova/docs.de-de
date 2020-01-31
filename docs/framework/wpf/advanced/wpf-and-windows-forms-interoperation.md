---
title: WPF-und Windows Forms-Interop
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- nester interoperation [WPF]
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid control [WPF interoperability]
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
ms.openlocfilehash: 5141b84ecd002d920f0d4130bdc2529c0fce4994
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794053"
---
# <a name="wpf-and-windows-forms-interoperation"></a>Interaktion zwischen WPF und Windows Forms
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und Windows Forms stellen zwei verschiedene Architekturen zum Erstellen von Anwendungsschnittstellen dar. Der <xref:System.Windows.Forms.Integration?displayProperty=nameWithType>-Namespace stellt Klassen bereit, die gängige interoperation-Szenarien ermöglichen. Die beiden Schlüssel Klassen, die Interoperation-Funktionen implementieren, sind <xref:System.Windows.Forms.Integration.WindowsFormsHost> und <xref:System.Windows.Forms.Integration.ElementHost>. In diesem Thema wird beschrieben, welche Interoperations-Szenarios unterstützt werden und welche nicht.  
  
> [!NOTE]
> Besondere Augenmerk wird dabei auf Szenarios mit *hybriden Steuerelementen* gelegt. Ein hybrides Steuerelement ist ein Steuerelement einer Technologie, das in ein Steuerelement anderer Technologie geschachtelt ist. Daher nennt man dies auch eine *geschachtelte Interoperation*. Ein *mehrstufiges hybrides Steuerelement* verfügt über mehr als eine Ebene hybrider Steuerelement-Schachtelung. Ein Beispiel für eine verschachtelte Interoperation mit mehreren Ebenen ist ein Windows Forms Steuerelement, das ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelement enthält, das ein anderes Windows Forms Steuerelement enthält. Mehrstufige hybride Steuerelemente werden nicht unterstützt.  

<a name="Windows_Presentation_Foundation_Application_Hosting"></a>   
## <a name="hosting-windows-forms-controls-in-wpf"></a>Hosten eines Windows Forms-Steuerelements in WPF  
 Die folgenden interoperation-Szenarien werden unterstützt, wenn ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelement ein Windows Forms Steuerelement hostet:  
  
- Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelement kann ein oder mehrere Windows Forms Steuerelemente mithilfe von XAML hosten.  
  
- Es kann ein oder mehrere Windows Forms Steuerelemente mithilfe von Code hosten.  
  
- Sie kann Windows Forms Container-Steuerelemente hosten, die andere Windows Forms Steuerelemente enthalten.  
  
- Es kann ein Master-/Detailformular mit einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Master und Windows Forms Details hosten.  
  
- Es kann ein Master-/Detailformular mit einem Windows Forms Master und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Details hosten.  
  
- Es kann ein oder mehrere ActiveX-Steuerelemente hosten.  
  
- Es kann ein oder mehrere zusammengesetzte Steuerelemente hosten.  
  
- Es kann hybride Steuerelemente mithilfe von [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] hosten.  
  
- Es kann hybride Steuerelemente mithilfe von Code hosten.  
  
### <a name="layout-support"></a>Layout-Unterstützung  
 In der folgenden Liste werden die bekannten Einschränkungen beschrieben, wenn das <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Element versucht, das gehostete Windows Forms-Steuerelement in das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Layoutsystem zu integrieren.  
  
- In einigen Fällen können Windows Forms Steuerelemente nicht geändert werden, oder Sie können nur für bestimmte Dimensionen angepasst werden. Beispielsweise unterstützt ein Windows Forms <xref:System.Windows.Forms.ComboBox>-Steuerelement nur eine einzige Höhe, die durch den Schrift Grad des Steuer Elements definiert wird. In einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dynamisches Layout, bei dem davon ausgegangen wird, dass Elemente vertikal gestreckt werden können, wird ein gehostetes <xref:System.Windows.Forms.ComboBox> Steuerelement nicht erwartungsgemäß gestreckt.  
  
- Windows Forms Steuerelemente können nicht gedreht oder verzerrt werden. Wenn Sie z. b. die Benutzeroberfläche um 90 Grad drehen, behalten die gehosteten Windows Forms Steuerelemente ihre eigen Position bei.  
  
- In den meisten Fällen unterstützen Windows Forms Steuerelemente keine proportionale Skalierung. Obwohl die gesamten Dimensionen des Steuerelements skaliert werden, können untergeordnete Steuerelemente und Komponenten des Steuerelements unter Umständen nicht wie erwartet skaliert werden. Diese Einschränkung hängt davon ab, wie gut die einzelnen Windows Forms Steuerelemente die Skalierung unterstützen  
  
- In einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Benutzeroberfläche können Sie die Z-Reihenfolge der Elemente ändern, um ihr Verhalten bei Überlappung zu steuern. Ein gehostetes Windows Forms Steuerelement wird in einem separaten HWND gezeichnet, sodass es immer auf [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elementen gezeichnet wird.  
  
- Windows Forms Steuerelemente unterstützen die automatische Skalierung basierend auf dem Schrift Grad. In einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Benutzeroberfläche bewirkt eine Änderung des Schriftgrads keine Größenänderung des gesamten Layouts; einzelne Elemente können ihre Größe jedoch ggf. dynamisch anpassen.  
  
### <a name="ambient-properties"></a>Umgebungseigenschaften  
 Einige Umgebungs Eigenschaften von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelementen verfügen über Windows Forms Entsprechungen. Diese Umgebungs Eigenschaften werden an die gehosteten Windows Forms-Steuerelemente weitergegeben und als öffentliche Eigenschaften des <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuer Elements verfügbar gemacht. Das <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement übersetzt jede [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ambient-Eigenschaft in die entsprechende Windows Forms-Entsprechung.  
  
 Weitere Informationen finden Sie unter [Eigenschaftenzuordnung von Windows Forms und WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Verhalten  
 In der folgenden Tabelle werden Interoperations-Verhalten beschrieben.  
  
|Verhalten|unterstützt|Nicht unterstützt|  
|--------------|---------------|-------------------|  
|Transparenz|Windows Forms-Steuerelement Rendering unterstützt Transparenz. Der Hintergrund des übergeordneten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuer Elements kann der Hintergrund von gehosteten Windows Forms Steuerelementen werden.|Einige Windows Forms-Steuerelemente unterstützen keine Transparenz. Beispielsweise sind die Steuerelemente <xref:System.Windows.Forms.TextBox> und <xref:System.Windows.Forms.ComboBox> nicht transparent, wenn Sie von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]gehostet werden.|  
|Wechseln mit der Tabulatortaste|Die Aktivier Reihenfolge für gehostete Windows Forms Steuerelemente ist identisch mit dem, wenn diese Steuerelemente in einer Windows Forms basierten Anwendung gehostet werden.<br /><br /> Die Tab-Taste von einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelement zu einem Windows Forms-Steuerelement mit der Tab-Taste und der UMSCHALT + TAB-Taste funktioniert wie üblich.<br /><br /> Windows Forms Steuerelemente, die den <xref:System.Windows.Forms.Control.TabStop%2A>-Eigenschafts Wert `false` aufweisen, erhalten keinen Fokus, wenn der Benutzer die Registerkarten durch Steuerelemente durchläuft<br /><br /> -Jedes <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement verfügt über einen <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> Wert, der bestimmt, wann <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement den Fokus erhält.<br />-Windows Forms Steuerelemente, die in einem <xref:System.Windows.Forms.Integration.WindowsFormsHost> Container enthalten sind, folgen der von der <xref:System.Windows.Forms.Control.TabIndex%2A>-Eigenschaft angegebenen Reihenfolge. Wechselt man vom letzten Tabulatorindex weiter, wird der Fokus auf das nächste [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelement gesetzt, falls dies existiert. Wenn kein anderes Fokus bares [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelement vorhanden ist, kehrt Tabulator zum ersten Windows Forms-Steuerelement in der Aktivier Reihenfolge zurück.<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> Werte für Steuerelemente innerhalb des <xref:System.Windows.Forms.Integration.WindowsFormsHost> sind relativ zu gleich geordneten Windows Forms Steuerelementen, die im <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement enthalten sind.<br />-   Das Wechseln mit der Tabulatortaste respektiert Steuerelement-spezifisches Verhalten. Beispielsweise wird durch Drücken der Tab-Taste in einem <xref:System.Windows.Forms.TextBox> Steuerelement, das den <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A>-Eigenschafts Wert `true` hat, eine Registerkarte im Textfeld angezeigt, anstatt den Fokus zu verschieben.|Nicht zutreffend.|  
|Navigation mit Pfeiltasten|-Die Navigation mit Pfeiltasten im <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement ist identisch mit denen in einem normalen Windows Forms Container-Steuerelement: die nach-oben-und nach-links-Taste wählen das vorherige Steuerelement aus, und die nach-unten-und nach-rechts-Taste wählen das nächste Steuerelement<br />-Die Pfeil-nach-oben-Taste und die nach-links-Taste des ersten Steuer Elements, das im <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement enthalten ist, führen dieselbe Aktion aus wie die Tastenkombination UMSCHALT + TAB. Wenn ein Fokussier bares [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelement vorhanden ist, wird der Fokus außerhalb des <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuer Elements verschoben. Dieses Verhalten unterscheidet sich vom Standard <xref:System.Windows.Forms.ContainerControl> Verhalten darin, dass keine Wrapping zum letzten Steuerelement erfolgt. Wenn kein anderes Fokus bares [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelement vorhanden ist, kehrt der Fokus zum letzten Windows Forms Steuerelement in der Aktivier Reihenfolge zurück.<br />-Die nach-unten-Taste und die nach-rechts-Taste aus dem letzten Steuerelement, das im <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement enthalten ist, führen dieselbe Aktion aus wie die Tab-Taste. Wenn ein Fokussier bares [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelement vorhanden ist, wird der Fokus außerhalb des <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuer Elements verschoben. Dieses Verhalten unterscheidet sich vom Standard <xref:System.Windows.Forms.ContainerControl> Verhalten in, dass keine Wrapping zum ersten Steuerelement erfolgt. Wenn kein anderes Fokus bares [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelement vorhanden ist, kehrt der Fokus zum ersten Windows Forms Steuerelement in der Aktivier Reihenfolge zurück.|Nicht zutreffend.|  
|Zugriffstasten|Zugriffstasten funktionieren wie üblich, außer den in der Spalte "Nicht unterstützt" angegebenen.|Technologieübergreifend doppelt belegte Zugriffstasten funktionieren nicht wie gewöhnlich doppelt belegte Zugriffstasten. Wenn eine Zugriffstaste über Technologien hinweg dupliziert wird, wobei mindestens eine auf einem Windows Forms Steuerelement und der andere auf einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelement vorhanden ist, empfängt das Windows Forms Steuerelement immer die Zugriffstaste. Bei gedrückter Zugriffstaste wechselt der Fokus nicht zwischen den beiden Steuerelementen.|  
|Tastenkombinationen|Tastenkombinationen funktionieren wie üblich, außer den in der Spalte "Nicht unterstützt" angegebenen.|-Windows Forms Tastenkombinationen, die in der Vorverarbeitungs Phase behandelt werden, haben immer Vorrang vor [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Tastenkombinationen. Wenn Sie z. b. ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement mit den Tastenkombinationen Strg + s definiert haben und ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Befehl an Strg + s gebunden ist, wird der <xref:System.Windows.Forms.ToolStrip> Steuerelement Handler immer zuerst aufgerufen, unabhängig vom Fokus.<br />-Windows Forms Tastenkombinationen, die vom <xref:System.Windows.Forms.Control.KeyDown>-Ereignis behandelt werden, werden zuletzt in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]verarbeitet. Sie können dieses Verhalten vermeiden, indem Sie die <xref:System.Windows.Forms.Control.IsInputKey%2A>-Methode des Windows Forms-Steuer Elements überschreiben oder das <xref:System.Windows.Forms.Control.PreviewKeyDown>-Ereignis behandeln. Geben Sie `true` aus der <xref:System.Windows.Forms.Control.IsInputKey%2A>-Methode zurück, oder legen Sie den Wert der Eigenschaft <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=nameWithType> auf `true` in Ihrem <xref:System.Windows.Forms.Control.PreviewKeyDown>-Ereignishandler fest.|  
|AcceptsReturn, AcceptsTab und andere steuerelementspezifische Verhalten|Eigenschaften, die das standardmäßige Tastatur Verhalten ändern, funktionieren wie üblich, vorausgesetzt, dass das Windows Forms-Steuerelement die <xref:System.Windows.Forms.Control.IsInputKey%2A>-Methode überschreibt, um `true`zurückzugeben|Windows Forms Steuerelemente, die das Standardtastatur Verhalten ändern, indem Sie das <xref:System.Windows.Forms.Control.KeyDown>-Ereignis verarbeiten, werden zuletzt im Host [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelement verarbeitet. Da diese Steuerelemente zuletzt verarbeitet werden, können sie zu unerwartetem Verhalten führen.|  
|Enter- und Leave-Ereignisse|Wenn der Fokus nicht auf das enthaltende <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement geht, werden die Enter-und Leave-Ereignisse wie gewohnt ausgelöst, wenn sich der Fokus in einem einzelnen <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement befindet.|Bei folgenden Fokusänderungen werden die Enter- und Leave-Ereignisse nicht ausgelöst:<br /><br /> -Von innen nach außerhalb eines <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuer Elements.<br />-Von außen nach innerhalb eines <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuer Elements.<br />-Außerhalb eines <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Steuer Elements.<br />-Von einem Windows Forms Steuerelement, das in einem <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Steuerelement gehostet wird, zu einem <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement, das innerhalb desselben <xref:System.Windows.Forms.Integration.WindowsFormsHost>gehostet|  
|Multithreading|Alle Arten von Multithreading werden unterstützt.|Sowohl für die Windows Forms-als auch für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Technologien wird ein Single Thread-Parallelitäts Modell angenommen. Während des Debuggens lösen Aufrufe von Framework-Objekten aus anderen Threads eine Ausnahme aus, um diese Anforderung zu erzwingen.|  
|Sicherheit|Alle Interoperationsszenarios erfordern volle Vertrauenswürdigkeit.|Keine dieser Szenarios sind in teilweiser Vertrauenswürdigkeit zulässig.|  
|Barrierefreiheit|Alle Eingabehilfenszenarios werden unterstützt. Hilfstechnologieprodukte funktionieren ordnungsgemäß, wenn Sie für Hybrid Anwendungen verwendet werden, die sowohl Windows Forms als auch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente enthalten.|Nicht zutreffend.|  
|Zwischenablage|Alle Zwischenablageoperationen funktionieren wie üblich. Dies schließt das Ausschnitten und Einfügen zwischen Windows Forms und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelementen ein.|Nicht zutreffend.|  
|Drag & Drop-Funktion|Alle Drag & Drop-Operationen funktionieren wie üblich. Dies schließt Vorgänge zwischen Windows Forms und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelementen ein.|Nicht zutreffend.|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>   
## <a name="hosting-wpf-controls-in-windows-forms"></a>Hosten von WPF-Steuerelementen in Windows Forms  
 Die folgenden interoperation-Szenarien werden unterstützt, wenn ein Windows Forms-Steuerelement ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelement hostet:  
  
- Hosten von einem oder mehreren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelementen mithilfe von Code  
  
- Zuordnen eines Eigenschaftenblatts zu einem oder mehreren gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelementen  
  
- Hosten einer oder mehrerer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Seiten in einem Formular  
  
- Starten eines [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Fensters  
  
- Hosting eines Master-/Detailformulars mit einem Windows Forms Master und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Details.  
  
- Hosting eines Master-/Detailformulars mit einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Master und Windows Forms Details.  
  
- Hosten von benutzerdefinierten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelementen  
  
- Hosten von hybriden Steuerelementen  
  
### <a name="ambient-properties"></a>Umgebungseigenschaften  
 Einige Umgebungs Eigenschaften von Windows Forms-Steuerelementen verfügen über [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Entsprechungen. Diese Umgebungs Eigenschaften werden an die gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelemente weitergegeben und als öffentliche Eigenschaften des <xref:System.Windows.Forms.Integration.ElementHost> Steuer Elements verfügbar gemacht. Das <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement übersetzt jede Windows Forms Ambient-Eigenschaft in die entsprechende [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Entsprechung.  
  
 Weitere Informationen finden Sie unter [Eigenschaftenzuordnung von Windows Forms und WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Verhalten  
 In der folgenden Tabelle werden Interoperations-Verhalten beschrieben.  
  
|Verhalten|unterstützt|Nicht unterstützt|  
|--------------|---------------|-------------------|  
|Transparenz|Rendern von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelementen unterstützt Transparenz. Der Hintergrund des übergeordneten Windows Forms Steuer Elements kann der Hintergrund von gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelementen werden.|Nicht zutreffend.|  
|Multithreading|Alle Arten von Multithreading werden unterstützt.|Sowohl für die Windows Forms-als auch für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Technologien wird ein Single Thread-Parallelitäts Modell angenommen. Während des Debuggens lösen Aufrufe von Framework-Objekten aus anderen Threads eine Ausnahme aus, um diese Anforderung zu erzwingen.|  
|Sicherheit|Alle Interoperationsszenarios erfordern volle Vertrauenswürdigkeit.|Keine dieser Szenarios sind in teilweiser Vertrauenswürdigkeit zulässig.|  
|Barrierefreiheit|Alle Eingabehilfenszenarios werden unterstützt. Hilfstechnologieprodukte funktionieren ordnungsgemäß, wenn Sie für Hybrid Anwendungen verwendet werden, die sowohl Windows Forms als auch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente enthalten.|Nicht zutreffend.|  
|Zwischenablage|Alle Zwischenablageoperationen funktionieren wie üblich. Dies schließt das Ausschnitten und Einfügen zwischen Windows Forms und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelementen ein.|Nicht zutreffend.|  
|Drag & Drop-Funktion|Alle Drag & Drop-Operationen funktionieren wie üblich. Dies schließt Vorgänge zwischen Windows Forms und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelementen ein.|Nicht zutreffend.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Exemplarische Vorgehensweise: Hosten eines Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Eigenschaftenzuordnung von Windows Forms und WPF](windows-forms-and-wpf-property-mapping.md)
