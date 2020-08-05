---
title: Bewährte Methoden für Eingabehilfen
description: Erfahren Sie mehr über bewährte Methoden für die Barrierefreiheit in .net. Untersuchen Sie den programmgesteuerten Zugriff, die Benutzereinstellungen, den Entwurf der visuellen Benutzeroberfläche, die Navigation und multimodale
ms.date: 03/30/2017
helpviewer_keywords:
- best practices for accessibility
- accessibility, best practices for
ms.assetid: e6d5cd98-21a3-4b01-999c-fb953556d0e6
ms.openlocfilehash: 2980881bbcd34ca82f6cca7723cf976e0890f463
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557085"
---
# <a name="accessibility-best-practices"></a>Bewährte Methoden für die Barrierefreiheit

> [!NOTE]
> Dieser Artikel ist für .NET Framework Entwickler gedacht, die die im-Namespace definierten Klassen der Managed UI Automation verwenden möchten <xref:System.Windows.Automation> . Die neuesten Informationen zur Benutzeroberflächen Automatisierung finden Sie unter [Windows Automation-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Durch das Implementieren der folgenden bewährten Methoden in Steuerelementen oder Anwendungen wird die Barrierefreiheit für Personen verbessert, die Hilfstechnologiegeräte verwenden. Viele dieser bewährten Methoden konzentrieren sich auf einen guten Entwurf der Benutzeroberfläche. Jede bewährte Vorgehensweise umfasst Implementierungs Informationen für Windows Presentation Foundation (WPF)-Steuerelemente oder-Anwendungen. In vielen Fällen ist die Arbeit zum erfüllen dieser bewährten Methoden bereits in WPF-Steuerelementen enthalten.  
  
<a name="Programmatic_Access"></a>
## <a name="programmatic-access"></a>Programmgesteuerter Zugriff  
 Der programmgesteuerte Zugriff umfasst die Sicherstellung, dass alle Elemente der Benutzeroberfläche gekennzeichnet sind, Eigenschaftswerte verfügbar gemacht und entsprechende Ereignisse ausgelöst werden. Für WPF-Standard Steuerelemente ist der größte Teil dieser Arbeit bereits über erfolgt <xref:System.Windows.Automation.Peers.AutomationPeer> . Benutzerdefinierte Steuerelemente erfordern zusätzliche Arbeit, um sicherzustellen, dass der programmgesteuerte Zugriff ordnungsgemäß implementiert wurde.  
  
<a name="Enable_Programmatic_Access_to_all_UI_Elements_and_Text"></a>
### <a name="enable-programmatic-access-to-all-ui-elements-and-text"></a>Aktivieren des programmgesteuerten Zugriffs auf alle Elemente der Benutzeroberfläche und auf Text  
 Benutzeroberflächen Elemente (UI) sollten den programmgesteuerten Zugriff aktivieren. Wenn die Benutzeroberfläche ein Standardmäßiges WPF-Steuerelement ist, ist die Unterstützung für den programmgesteuerten Zugriff im Steuerelement enthalten. Wenn das Steuerelement ein benutzerdefiniertes Steuerelement ist, d. h. ein Steuerelement, das als Unterklasse eines allgemeinen Steuerelements oder als Unterklasse von "Control" abgeleitet wurde, müssen Sie die <xref:System.Windows.Automation.Peers.AutomationPeer> -Implementierung auf Bereiche prüfen, für die möglicherweise eine Änderung erforderlich ist.  
  
 Durch Befolgen dieser bewährten Vorgehensweise können Hilfstechnologieanbieter Elemente der Benutzeroberfläche Ihres Produkts identifizieren und bearbeiten.  
  
<a name="Place_Names__Titles_and_Descriptions_on_UI_Objects_"></a>
### <a name="place-names-titles-and-descriptions-on-ui-objects-frames-and-pages"></a>Platzieren von Namen, Titeln und Beschreibungen auf Benutzeroberflächenobjekte, Frames und Seiten  
 Hilfstechnologien, insbesondere Sprachausgaben, verwenden den Titel, um die Position von Frames, Objekten oder Seiten im Navigationsschema zu verstehen. Daher muss der Titel beschreibend sein. Beispielsweise ist der Titel "Microsoft-Webseite" für eine Webseite unbrauchbar, wenn der Benutzer weit in einen bestimmten Bereich vorgedrungen ist. Ein aussagekräftiger Titel ist wichtig für Benutzer, die blind sind und auf Sprachausgaben angewiesen sind. Ebenso sind für WPF-Steuerelemente <xref:System.Windows.Automation.AutomationProperties.NameProperty> und für <xref:System.Windows.Automation.AutomationProperties.HelpTextProperty> Hilfstechnologiegeräte wichtig.  
  
 Durch Befolgen dieser bewährten Vorgehensweise können Hilfstechnologien die Benutzeroberfläche in Beispiel Steuerelementen und-Anwendungen identifizieren und bearbeiten.  
  
<a name="Ensure_Programmatic_Events_are_Triggered_by_all_UI"></a>
### <a name="ensure-programmatic-events-are-triggered-by-all-ui-activities"></a>Gewährleisten der Auslösung programmgesteuerter Ereignisse durch alle Aktivitäten auf der Benutzeroberfläche  
 Durch Befolgen dieser bewährten Vorgehensweise können Hilfstechnologien auf Änderungen in der Benutzeroberfläche lauschen und den Benutzer über diese Änderungen benachrichtigen.  
  
<a name="User_Settings"></a>
## <a name="user-settings"></a>Benutzereinstellungen  
 Die bewährte Methode in diesem Abschnitt stellt sicher, dass Steuerelemente oder Anwendungen die Benutzereinstellungen nicht außer Kraft setzen.  
  
<a name="Respect_all_System_Wide_Settings_and_do_not_Interfere"></a>
### <a name="respect-all-system-wide-settings-and-do-not-interfere-with-accessibility-functions"></a>Respektieren aller systemweiten Einstellungen und Beachten der Barrierefreiheitsfunktionen  
 Benutzer können einige systemweite Flags über die Systemsteuerung festlegen, während andere Flags programmgesteuert festgelegt werden können. Diese Einstellungen dürfen nicht von Steuerelementen oder Anwendungen geändert werden. Darüber hinaus müssen Anwendungen die Einstellungen für die Barrierefreiheit ihres Hostbetriebssystems unterstützen.  
  
 Durch Befolgen dieser bewährten Methode können Benutzer Einstellungen für die Barrierefreiheit festlegen und dadurch wissen, dass diese Einstellungen von Anwendungen nicht geändert werden.  
  
<a name="Visual_UI_Design"></a>
## <a name="visual-ui-design"></a>Entwurf der visuellen Benutzeroberfläche  
 Die bewährten Methoden in diesem Abschnitt stellen sicher, dass Steuerelemente oder Anwendungen Farben und Bilder effektiv verwenden und von Hilfstechnologien verwendet werden können.  
  
<a name="Don_t_Hard_Code_Colors"></a>
### <a name="dont-hard-code-colors"></a>Vermeiden hartcodierter Farben  
 Personen, die farbenblind sind, eine Sehschwäche aufweisen oder einen monochromen Bildschirm verwenden, können Anwendungen mit hartcodierten Farben möglicherweise nicht verwenden.  
  
 Durch Befolgen dieser bewährten Methode können Benutzer die Farbkombinationen auf Grundlage individueller Anforderungen anpassen.  
  
<a name="Support_High_Contrast_and_all_System_Display_Attributes"></a>
### <a name="support-high-contrast-and-all-system-display-attributes"></a>Unterstützen von hohem Kontrast und allen Systemanzeigeattributen  
 Anwendungen sollten vom Benutzer ausgewählte, systemweite Kontrasteinstellungen, Farbauswahlen oder andere systemweite Anzeigeeinstellungen und -attribute nicht stören oder deaktivieren. Die von einem Benutzer übernommenen systemweiten Einstellungen erhöhen die Barrierefreiheit von Anwendungen, daher sollten sie von Anwendungen nicht deaktiviert oder ignoriert werden. Farben müssen in der richtigen Kombination für Vorder- und Hintergrund verwendet werden, um den geeigneten Kontrast zu bieten. Kombinieren Sie keine nicht verknüpften Farben, und ändern Sie keine Farben.  
  
 Viele Benutzer benötigen bestimmte kontrastreiche Kombinationen, z. B. weißen Text auf schwarzem Hintergrund. Die invertierte Darstellung mit schwarzem Text auf weißem Hintergrund führt dazu, dass der Hintergrund auf den Vordergrund übergreift und das Lesen für manche Benutzer erschwert wird.  
  
<a name="Ensure_all_UI_Correctly_Scales_by_any_DPI_Setting"></a>
### <a name="ensure-all-ui-correctly-scales-by-any-dpi-setting"></a>Gewährleisten der ordnungsgemäßen Skalierung aller Benutzeroberflächenelemente bei beliebiger DPI-Einstellung  
 Stellen Sie sicher, dass die gesamte Benutzeroberfläche nach jeder dpi-Einstellung (dpi) ordnungsgemäß skaliert werden kann. Stellen Sie außerdem sicher, dass Benutzeroberflächen Elemente in einem Bildschirm von 1024 x 768 mit 120 Punkten pro Zoll (dpi) passen.  
  
<a name="Navigation"></a>
## <a name="navigation"></a>Navigation  
 Die bewährten Methoden in diesem Abschnitt stellen sicher, dass die Navigation auf Steuerelemente und Anwendungen ausgerichtet ist.  
  
<a name="Provide_Keyboard_Interface_for_all_UI_Elements"></a>
### <a name="provide-keyboard-interface-for-all-ui-elements"></a>Bereitstellen einer Tastaturschnittstelle für alle Elemente der Benutzeroberfläche  
 Tabstopps, insbesondere wenn Sie sorgfältig geplant sind, haben Benutzern eine weitere Möglichkeit, die Benutzeroberfläche zu navigieren.  
  
 Anwendungen sollten die folgenden Tastaturschnittstellen bereitstellen:  
  
- Tabstopps für alle Steuerelemente, mit denen der Benutzer interagieren kann, z. B. Schaltflächen, Links oder Listenfelder  
  
- Logische Aktivierreihenfolge  
  
<a name="Show_the_Keyboard_Focus"></a>
### <a name="show-the-keyboard-focus"></a>Anzeigen des Tastaturfokus  
 Benutzer müssen wissen, welches Objekt den Tastaturfokus hat, damit sie die Auswirkungen ihrer Tastatureingaben voraussehen können. Verwenden Sie Farben, Schriftarten oder grafische Darstellungen (z. B. Rechtecke oder eine Vergrößerung), um den Tastaturfokus hervorzuheben. Um den Tastaturfokus zu verdeutlichen, ändern Sie das Volume, die Größe oder die Tonqualität.  
  
 Um Verwechselungen zu vermeiden, sollten Anwendungen alle visuellen Fokusindikatoren ausblenden und die Auswahl abblenden, die sich in inaktiven Fenstern (oder Bereichen) befindet.  
  
 Anwendungen sollten beim Tastaturfokus wie folgt vorgehen:  
  
- Der Tastaturfokus sollte immer bei einem Element liegen.  
  
- Der Tastaturfokus muss sichtbar und unverkennbar sein.  
  
- Die Auswahl und/oder Elemente mit Fokus müssen visuell hervorgehoben werden.  
  
<a name="Support_Navigation_Standards_and_Powerful_Navigation"></a>
### <a name="support-navigation-standards-and-powerful-navigation-schemes"></a>Unterstützen von Navigationsstandards und leistungsstarken Navigationsschemas  
 Verschiedene Aspekte der Tastaturnavigation bieten verschiedene Möglichkeiten für Benutzer, die Benutzeroberfläche zu navigieren.  
  
 Anwendungen sollten die folgenden Tastaturschnittstellen bereitstellen:  
  
- Tastenkombinationen und unterstrichene Zugriffstasten für alle Befehle, Menüs und Steuerelemente  
  
- Tastenkombinationen für wichtige Links  
  
- Alle Menüelemente verfügen über eine Tastenkombination, alle Schaltflächen verfügen über Tastenkombinationen, alle Befehle verfügen über eine Tastenkombination.  
  
<a name="Do_not_let_Mouse_Location_Interfere_with_Keyboard"></a>
### <a name="do-not-let-mouse-location-interfere-with-keyboard-navigation"></a>Vermeiden störender Auswirkungen der Mausposition auf die Tastaturnavigation  
 Die Position des Mauszeigers sollte nicht die Tastaturnavigation behindern. Wenn sich die Maus z. b. an einer bestimmten Position befindet und der Benutzer mit der Tastatur navigiert, darf ein Mausklick nur auftreten, wenn er vom Benutzer initiiert wird.  
  
<a name="Multimodal_Interface"></a>
## <a name="multimodal-interface"></a>Multimodale Schnittstelle  
 Die bewährten Methoden in diesem Abschnitt stellen sicher, dass die Benutzeroberfläche der Anwendung Alternativen für visuelle Elemente enthält.  
  
<a name="Provide_User_Selectable_Equivalents_for_Non_Text"></a>
### <a name="provide-user-selectable-equivalents-for-non-text-elements"></a>Bereitstellen von auswählbaren Entsprechungen für Nicht-Text-Elemente  
 Geben Sie für jedes Nicht-Textelement eine vom Benutzer auswählbare Entsprechung für Text, Aufzeichnungen oder Audiobeschreibungen ein, z. B. alternativen Text, Beschriftungen oder visuelles Feedback.  
  
 Nicht-Textelemente decken eine breite Palette von Elementen der Benutzeroberfläche ab, einschließlich: Bilder, Imagemapbereiche, Animationen, Applets, Frames, Skripts, grafische Schaltflächen, Sounds, eigenständige Audiodateien und Videos. Nicht-Textelemente sind wichtig, wenn Sie visuelle Informationen, Sprache oder allgemeine Audioinformationen enthalten, auf die der Benutzer Zugriff hat, um den Inhalt der Benutzeroberfläche zu verstehen.  
  
<a name="Use_Color_but_also_Provide_Alternatives_to_Color"></a>
### <a name="use-color-but-also-provide-alternatives-to-color"></a>Verwenden von Farbe und Bereitstellen von Alternativen für Farbe  
 Verwenden Sie Farbe, um Informationen aufzuwerten, zu betonen oder auf andere Weise angezeigte Informationen zu wiederholen. Vermitteln Sie die Informationen jedoch nicht ausschließlich über die Farbe. Benutzer, die farbenblind sind oder ein monochromes Display verwenden, benötigen Alternativen zu Farben.  
  
<a name="Use_Standard_Input_APIs_with_Devices_Independent"></a>
### <a name="use-standard-input-apis-with-device-independent-calls"></a>Verwenden von Standardeingabe-APIs mit geräteunabhängigen Aufrufen  
 Geräteunabhängige Aufrufe stellen die Gleichheit von Tastatur-und Mausfunktionen sicher, während Sie Hilfstechnologien mit erforderlichen Informationen über die Benutzeroberfläche bereitstellen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Automation.Peers>
- [NumericUpDown Custom Control with Theme and UI Automation Support Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771573(v=vs.90))(Benutzerdefiniertes NumericUpDown-Steuerelement mit Unterstützung von Design und Automatisierung)
- [Richtlinien zur Gestaltung einer tastaturgesteuerten Benutzeroberfläche](https://docs.microsoft.com/previous-versions/windows/desktop/dnacc/guidelines-for-keyboard-user-interface-design)
