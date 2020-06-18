---
title: Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters
description: Erfahren Sie, wie Sie einen serverseitigen Benutzeroberflächenautomatisierungs-Anbieter für ein benutzerdefiniertes Steuerelement in .NET implementieren. Die Implementierung für WPF-und nicht-WPF-Elemente ist unterschiedlich.
ms.date: 03/30/2017
helpviewer_keywords:
- server-side UI Automation provider implementation
- UI Automation, server-side provider implementation
- provider implementation, UI Automation
ms.assetid: 6acc6d08-bd67-4e2e-915c-9c1d34eb86fe
ms.openlocfilehash: ea1b5e668e29d854233d4dde4c0e6152d591da97
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903895"
---
# <a name="server-side-ui-automation-provider-implementation"></a>Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).

In diesem Abschnitt wird beschrieben, wie ein serverseitiger Benutzeroberflächenautomatisierungs-Anbieter für ein benutzerdefiniertes Steuerelement implementiert wird.

Die Implementierung für Windows Presentation Foundation (WPF)-Elemente und nicht-WPF-Elemente (z. b. die für Windows Forms vorgesehenen) unterscheiden sich grundlegend. WPF-Elemente unterstützen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] über eine von abgeleitete Klasse <xref:System.Windows.Automation.Peers.AutomationPeer> . Nicht-WPF-Elemente bieten Unterstützung durch Implementierungen von Anbieter Schnittstellen.

<a name="Security_Considerations"></a>

## <a name="security-considerations"></a>Überlegungen zur Sicherheit

Anbieter sollten so erstellt werden, dass sie in einer teilweise vertrauenswürdigen Umgebung funktionieren können. Da UIAutomationClient.dll nicht für die Ausführung mit teilweiser Vertrauenswürdigkeit konfiguriert ist, sollte der Anbietercode nicht auf diese Assembly verweisen. Wenn dies der Fall ist, kann der Code in einer voll vertrauenswürdigen Umgebung ausgeführt werden, während in einer teilweise vertrauenswürdigen Umgebung Fehler auftreten.

Verwenden Sie insbesondere keine Felder von Klassen in UIAutomationClient.dll, z. B. die Felder in <xref:System.Windows.Automation.AutomationElement>. Verwenden Sie stattdessen die entsprechenden Felder der Klassen in UIAutomationTypes.dll, z. B. <xref:System.Windows.Automation.AutomationElementIdentifiers>.

<a name="Provider_Implementation_by_WPF_Elements"></a>

## <a name="provider-implementation-by-windows-presentation-foundation-elements"></a>Anbieterimplementierung durch Windows Presentation Foundation-Elemente

Weitere Informationen zu diesem Thema finden Sie unter [Benutzeroberflächenautomatisierung eines benutzerdefinierten WPF-Steuerelements](../wpf/controls/ui-automation-of-a-wpf-custom-control.md).

<a name="Provider_Implementation_by_non_WPF_Elements"></a>

## <a name="provider-implementation-by-non-wpf-elements"></a>Anbieterimplementierung durch Nicht-WPF-Elemente

Benutzerdefinierte Steuerelemente, die nicht Teil des WPF-Frameworks, jedoch in verwaltetem Code geschrieben sind (meistens handelt es sich hierbei um Windows Forms-Steuerelemente), unterstützen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] durch das Implementieren von Schnittstellen. Jedes Element muss mindestens eine der in der ersten Tabelle des nächsten Abschnitts aufgeführten Schnittstellen implementieren. Außerdem muss ein Element, das ein oder mehrere Steuerelementmuster unterstützt, für jedes Steuerelementmuster die entsprechende Schnittstelle implementieren.

Das [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] --Anbieterprojekt muss auf die folgenden Assemblys verweisen:

- UIAutomationProviders.dll

- UIAutomationTypes.dll

- WindowsBase.dll

<a name="Provider_Interfaces"></a>

### <a name="provider-interfaces"></a>Anbieterschnittstellen

Jeder [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anbieter muss eine der folgenden Schnittstellen implementieren.

|Schnittstelle|BESCHREIBUNG|
|---------------|-----------------|
|<xref:System.Windows.Automation.Provider.IRawElementProviderSimple>|Stellt Funktionen für ein einfaches in einem Fenster gehostetes Steuerelement bereit, einschließlich der Unterstützung für Steuerelementmuster und Eigenschaften.|
|<xref:System.Windows.Automation.Provider.IRawElementProviderFragment>|Erbt von <xref:System.Windows.Automation.Provider.IRawElementProviderSimple>. Fügt Funktionen für ein Element in einem komplexen Steuerelement hinzu, einschließlich Navigation im Fragment, Festlegen des Fokus und Zurückgeben des umschließenden Rechtecks des Elements.|
|<xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot>|Erbt von <xref:System.Windows.Automation.Provider.IRawElementProviderFragment>. Fügt Funktionen für das Stammelement in einem komplexen Steuerelement hinzu, einschließlich Suchen eines untergeordneten Elements an angegebenen Koordinaten und Festlegen des Fokuszustands für das gesamte Steuerelement.|

Die folgenden Schnittstellen stellen weitere Funktionen bereit, müssen jedoch nicht implementiert werden.

|Schnittstelle|BESCHREIBUNG|
|---------------|-----------------|
|<xref:System.Windows.Automation.Provider.IRawElementProviderAdviseEvents>|Ermöglicht dem Anbieter, Anforderungen für Ereignisse zu verfolgen.|
|<xref:System.Windows.Automation.Provider.IRawElementProviderHwndOverride>|Ermöglicht das Neupositionieren von fensterbasierten Elementen innerhalb der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur eines Fragments.|

Alle anderen Schnittstellen im <xref:System.Windows.Automation.Provider> -Namespace dienen der Unterstützung von Steuerelementmustern.

<a name="Requirements_for_Non_WPF_Providers"></a>

### <a name="requirements-for-non-wpf-providers"></a>Anforderungen für Nicht-WPF-Anbieter

Um mit [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]zu kommunizieren, muss ein Steuerelement die folgenden Hauptfunktionalitätsbereiche implementieren:

|Funktionalität|Implementierung|
|-------------------|--------------------|
|Verfügbarmachen des Anbieters für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Antworten Sie auf eine an das Steuerelementfenster gesendete WM_GETOBJECT-Nachricht, indem Sie das Objekt zurückgeben, das <xref:System.Windows.Automation.Provider.IRawElementProviderSimple> (oder eine abgeleitete Schnittstelle) implementiert. Für Fragmente muss dies der Anbieter für den Fragmentstamm sein.|
|Bereitstellen von Eigenschaftswerten|Implementieren Sie <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPropertyValue%2A> , um Werte bereitzustellen oder zu überschreiben.|
|Ermöglichen der Interaktion des Clients mit dem Steuerelement|Implementieren Sie Schnittstellen, die Steuerelementmuster unterstützen, z. B. <xref:System.Windows.Automation.Provider.IInvokeProvider>. Geben Sie diese Musteranbieter in der Implementierung von <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A>zurück.|
|Auslösen von Ereignissen|Rufen Sie eine der statischen Methoden von <xref:System.Windows.Automation.Provider.AutomationInteropProvider> auf, um ein Ereignis auszulösen, das ein Client überwachen kann.|
|Ermöglichen der Navigation und Fokussierung in einem Fragment|Implementieren Sie <xref:System.Windows.Automation.Provider.IRawElementProviderFragment> für jedes Element innerhalb des Fragments. (Nicht für Elemente erforderlich, die kein Teil eines Fragments sind.)|
|Ermöglichen der Fokussierung und Positionierung eines untergeordneten Elements in einem Fragment|Implementieren Sie <xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot>. (Nicht für Elemente erforderlich, die keine Fragmentstämme sind.)|

<a name="Property_Values_in_Non_WPF_Providers"></a>

### <a name="property-values-in-non-wpf-providers"></a>Eigenschaftswerte in Nicht-WPF-Anbietern

[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anbieter für benutzerdefinierte Steuerelemente müssen bestimmte Eigenschaften unterstützen, die sowohl vom Automatisierungssystem als auch von Clientanwendungen verwendet werden können. Bei in Fenstern gehosteten Elementen (HWNDs) kann die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] einige Eigenschaften vom Standardfensteranbieter abrufen, andere müssen jedoch vom benutzerdefinierten Anbieter bezogen werden.

Anbieter für HWND-basierte Steuerelemente müssen die folgenden Eigenschaften (identifiziert nach Feldwerten) normalerweise nicht bereitstellen:

- <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.ProcessIdProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.ClassNameProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.HasKeyboardFocusProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.IsPasswordProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>

- <xref:System.Windows.Automation.AutomationElementIdentifiers.RuntimeIdProperty>

> [!NOTE]
> Die <xref:System.Windows.Automation.AutomationElementIdentifiers.RuntimeIdProperty> eines in einem Fenster gehosteten einfachen Elements oder Fragmentstamms wird vom Fenster bezogen. Fragmentelemente unterhalb des Stamms (wie Listeneinträge in einem Listenfeld) müssen jedoch eigene Bezeichner bereitstellen. Weitere Informationen finden Sie unter <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.GetRuntimeId%2A>.
>
> Die <xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty> sollte für Anbieter zurückgegeben werden, die in einem Windows Forms-Steuerelement gehostet werden. In diesem Fall ist der Standardfensteranbieter möglicherweise nicht in der Lage, den richtigen Wert abzurufen.
>
> Die <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> wird in der Regel vom Hostanbieter bereitgestellt. Wenn ein benutzerdefiniertes Steuerelement beispielsweise von <xref:System.Windows.Forms.Control>abgeleitet ist, wird der Name von der `Text` -Eigenschaft des Steuerelements abgeleitet

Beispielcode finden Sie unter [Return Properties from a UI Automation Provider](return-properties-from-a-ui-automation-provider.md).

<a name="Events_in_Non_WPF_Providers"></a>

### <a name="events-in-non-wpf-providers"></a>Ereignisse in Nicht-WPF-Anbietern

[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anbieter sollten Ereignisse auslösen, um Clientanwendungen über Zustandsänderungen der Benutzeroberfläche zu benachrichtigen. Ereignisse werden mit den folgenden Methoden ausgelöst.

|Methode|BESCHREIBUNG|
|------------|-----------------|
|<xref:System.Windows.Automation.Provider.AutomationInteropProvider.RaiseAutomationEvent%2A>|Löst verschiedene Ereignisse aus, einschließlich Ereignissen, die von Steuerelementmustern ausgelöst werden.|
|<xref:System.Windows.Automation.Provider.AutomationInteropProvider.RaiseAutomationPropertyChangedEvent%2A>|Löst ein Ereignis aus, wenn sich eine [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaft geändert hat.|
|<xref:System.Windows.Automation.Provider.AutomationInteropProvider.RaiseStructureChangedEvent%2A>|Löst ein Ereignis aus, wenn sich der Aufbau der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur geändert hat, z. B. durch Entfernen oder Hinzufügen eines Elements.|

Der Zweck eines Ereignisses liegt im Benachrichtigen des Clients über Vorgänge in der [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], unabhängig davon, ob eine Aktion vom [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -System selbst ausgelöst wird. Beispielsweise sollte das von <xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent> identifizierte Ereignis immer ausgelöst werden, wenn das Steuerelement aufgerufen wird, unabhängig davon, ob durch eine direkte Benutzereingabe oder durch die <xref:System.Windows.Automation.InvokePattern.Invoke%2A>aufrufende Clientanwendung.

Zum Optimieren der Leistung kann ein Anbieter Ereignisse selektiv auslösen oder keine Ereignisse auslösen, wenn für deren Empfang keine Clientanwendung registriert ist. Die folgenden Methoden werden zur Optimierung verwendet.

|Methode|BESCHREIBUNG|
|------------|-----------------|
|<xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A>|Diese statische Eigenschaft gibt an, ob es Clientanwendungen gibt, die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse abonniert haben.|
|<xref:System.Windows.Automation.Provider.IRawElementProviderAdviseEvents>|Durch die Implementierung dieser Schnittstelle durch den Anbieter auf einem Fragmentstamm kann kommuniziert werden, wenn Clients Registrierungen von Ereignishandlern für Ereignisse im Fragment vornehmen bzw. aufheben.|

<a name="Non_WPF_Provider_Navigation"></a>

### <a name="non-wpf-provider-navigation"></a>Navigation für Nicht-WPF-Anbieter

Anbieter für einfache Steuerelemente, z. B. eine benutzerdefinierte Schaltfläche, die in einem Fenster (HWND) gehostet wird, müssen die Navigation innerhalb der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur nicht unterstützen. Die Navigation zum und vom Element wird vom Standardanbieter für das Hostfenster verarbeitet, der in der Implementierung von <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.HostRawElementProvider%2A>angegeben ist. Wenn Sie jedoch einen Anbieter für ein komplexes benutzerdefiniertes Steuerelement implementieren, müssen Sie die Navigation zwischen dem Stammknoten des Fragments und seinen Nachfolgern sowie zwischen nebengeordneten Knoten unterstützen.

> [!NOTE]
> Die Nicht-Stammelemente eines Fragments müssen einen `null` -Verweis von <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.HostRawElementProvider%2A>zurückgeben, da sie nicht direkt in einem Fenster gehostet werden und die Navigation zu und von ihnen von keinem Standardanbieter unterstützt werden kann.

Die Struktur des Fragments wird durch Ihre Implementierung von <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A>festgelegt. Diese Methode gibt für jedes Fragment und jede mögliche Richtung das Anbieterobjekt für das in dieser Richtung liegende Element zurück. Wenn in einer Richtung kein Element vorhanden ist, gibt die Methode einen `null` -Verweis zurück.

Der Fragmentstamm unterstützt nur die Navigation zu untergeordneten Elementen. Beispielsweise gibt ein Listenfeld für die Richtung <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild>den ersten Eintrag und für die Richtung <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>den letzten Eintrag in der Liste zurück. Der Fragmentstamm unterstützt keine Navigation zu einem übergeordneten oder nebengeordneten Element; diese wird vom Hostfensteranbieter verarbeitet.

Die Nicht-Stammelemente eines Fragments müssen die Navigation zum übergeordneten Element sowie zu allen vorhandenen nebengeordneten und untergeordneten Elementen unterstützen.

<a name="Non_WPF_Provider_Reparenting"></a>

### <a name="non-wpf-provider-reparenting"></a>Neuzuordnung des übergeordneten Elements für Nicht-WPF-Anbieter

Genau genommen sind Popupfenster Fenster oberster Ebene und werden in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur standardmäßig als untergeordnete Elemente des Desktops angezeigt. Eigentlich sind Popupfenster in vielen Fällen jedoch untergeordnete Elemente anderer Steuerelemente. Beispielsweise ist die Dropdownliste eines Kombinationsfelds logischerweise ein untergeordnetes Element des Kombinationsfelds. Dementsprechend ist ein Menüpopupfenster logischerweise ein untergeordnetes Element des Menüs. Die[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] unterstützt für Popupfenster das Neuzuordnen des übergeordneten Elements, sodass sie als untergeordnete Elemente des zugehörigen Steuerelements angezeigt werden.

So ordnen Sie ein Popupfenster einem neuen übergeordneten Element zu

1. Erstellen Sie einen Anbieter für das Popupfenster. Hierfür muss die Klasse des Popupfensters im Voraus bekannt sein.

2. Implementieren Sie für das Popupfenster alle Eigenschaften und Muster, als ob es ein vollkommen eigenständiges Steuerelement ist.

3. Implementieren Sie die <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.HostRawElementProvider%2A> -Eigenschaft, sodass sie den mit <xref:System.Windows.Automation.Provider.AutomationInteropProvider.HostProviderFromHandle%2A>abgerufenen Wert zurückgibt. Der Parameter ist hierbei der Fensterhandle des Popupfensters.

4. Implementieren Sie für das Popupfenster und das übergeordnete Element <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> , sodass die Navigation vom logischen übergeordneten Element zum logischen untergeordneten Element sowie zwischen den nebengeordneten Elementen ordnungsgemäß verarbeitet wird.

Wenn die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] auf das Popupfenster als untergeordnetes Element des Desktops stößt, wird erkannt, dass die Standardnavigation überschrieben wurde, und das Popupfenster wird übersprungen. Stattdessen ist der Knoten nur über das Fragment erreichbar.

Das Neuzuordnen des übergeordneten Elements ist nicht geeignet, wenn ein Steuerelement ein Fenster einer beliebigen Klasse hosten kann. Beispielsweise kann in den Bändern einer Grundleiste jeder HWND-Typ gehostet werden. Für solche Fälle unterstützt die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] eine alternative Form der HWND-Umsetzung. Diese wird im nächsten Abschnitt beschrieben.

<a name="Non_WPF_Provider_Repositioning"></a>

### <a name="non-wpf-provider-repositioning"></a>Neupositionieren für Nicht-WPF-Anbieter

[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Fragmente enthalten möglicherweise zwei oder mehr Elemente, die jeweils in einem Fenster (HWND) enthalten sind. Da jedes HWND über einen eigenen Standardanbieter verfügt, der das HWND als ein untergeordnetes Element eines enthaltenden HWND ansieht, werden in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur die HWNDs im Fragment standardmäßig als untergeordnete Elemente des übergeordneten Fensters angezeigt. Dies ist in den meisten Fällen erwünscht. Manchmal kann es jedoch zu Verwirrung führen, da es nicht der logischen Struktur der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]entspricht.

Ein gutes Beispiel hierfür ist ein Grundleistensteuerelement. Eine Grundleiste enthält Bänder, die jeweils ein HWND-basiertes Steuerelement wie eine Symbolleiste, ein Eingabefeld oder ein Kombinationsfeld enthalten können. Für den Standardfensteranbieter für das Grundleisten-HWND sind die Bandsteuerelement-HWNDs untergeordnete Elemente, und für den Grundleistenanbieter sind die Bänder untergeordnete Elemente. Da der HWND-Anbieter und der Grundleistenanbieter zusammenarbeiten und ihre untergeordneten Elemente kombinieren, werden sowohl die Bänder als auch die HWND-basierten Steuerelemente als untergeordnete Elemente der Grundleiste angezeigt. Es sollten jedoch logischerweise nur die Bänder als untergeordnete Elemente der Grundleiste angezeigt werden, und jeder Bandanbieter sollte mit dem Standard-HWND-Anbieter für das enthaltene Steuerelement verbunden werden.

Hierfür stellt der Fragmentstammanbieter für die Grundleiste einen Satz an untergeordneten Elementen zur Verfügung, die die Bänder repräsentieren. Jedes Band verfügt über einen einzelnen Anbieter, der Eigenschaften und Muster zur Verfügung stellen kann. In dessen Implementierung von <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.HostRawElementProvider%2A>gibt der Bandanbieter den Standardfensteranbieter für das Steuerelement-HWND zurück, den er unter Übergabe des Fensterhandles des Steuerelements mithilfe von <xref:System.Windows.Automation.Provider.AutomationInteropProvider.HostProviderFromHandle%2A>abruft. Abschließend implementiert der Fragmentstammanbieter für die Infoleiste die <xref:System.Windows.Automation.Provider.IRawElementProviderHwndOverride> -Schnittstelle, und gibt in seiner Implementierung von <xref:System.Windows.Automation.Provider.IRawElementProviderHwndOverride.GetOverrideProviderForHwnd%2A> den geeigneten Bandanbieter für das im angegebenen HWND enthaltene Steuerelement zurück.

## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter](ui-automation-providers-overview.md)
- [Verfügbarmachen eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters](expose-a-server-side-ui-automation-provider.md)
- [Zurückgeben von Eigenschaften aus einem Benutzeroberflächenautomatisierungs-Anbieter](return-properties-from-a-ui-automation-provider.md)
- [Auslösen von Ereignissen aus einem Benutzeroberflächenautomatisierungs-Anbieter](raise-events-from-a-ui-automation-provider.md)
- [Aktivieren der Navigation in einem Benutzeroberflächenautomatisierungs-Fragmentanbieter](enable-navigation-in-a-ui-automation-fragment-provider.md)
- [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](support-control-patterns-in-a-ui-automation-provider.md)
