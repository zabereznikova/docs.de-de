---
title: Implementieren des Invoke-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Invoke control pattern
- control patterns, Invoke
- Invoke control pattern
ms.assetid: e5b1e239-49f8-468e-bfec-1fba02ec9ac4
ms.openlocfilehash: 30ae83aa4b73f36afce1251387598ef9b61816d8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435163"
---
# <a name="implementing-the-ui-automation-invoke-control-pattern"></a>Implementieren des Invoke-Steuerelementmusters der Benutzeroberflächenautomatisierung

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).

Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IInvokeProvider>, einschließlich Informationen über Ereignisse und Eigenschaften. Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.

Das <xref:System.Windows.Automation.InvokePattern> -Steuerelementmuster wird dazu verwendet, Steuerelemente zu unterstützen, deren Zustand nicht verwaltet wird, wenn sie aktiviert werden, sondern die nur eine einzelne, eindeutige Aktion initiieren oder ausführen Steuerelemente, deren Zustand verwaltet wird (etwa Kontrollkästchen und Optionsfelder), müssen stattdessen <xref:System.Windows.Automation.Provider.IToggleProvider> bzw. <xref:System.Windows.Automation.Provider.ISelectionItemProvider> implementieren. Beispiele für Steuerelemente, die das Invoke-Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).

<a name="Implementation_Guidelines_and_Conventions"></a>

## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen

Beachten Sie beim Implementieren des Invoke-Steuerelementmusters die folgenden Richtlinien und Konventionen:

- Steuerelemente implementieren <xref:System.Windows.Automation.Provider.IInvokeProvider> , wenn das gleiche Verhalten nicht durch einen anderen Steuerelementmuster-Anbieter verfügbar gemacht wird. Wenn die <xref:System.Windows.Automation.InvokePattern.Invoke%2A> -Methode eines Steuerelements beispielsweise dieselbe Aktion wie die <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> - oder die <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> -Methode ausführt, darf <xref:System.Windows.Automation.Provider.IInvokeProvider>nicht für das Steuerelement implementiert werden.

- Ein Steuerelement wird normalerweise durch Klicken, Doppelklicken, Drücken der EINGABETASTE oder durch eine vordefinierte oder alternative Tastenkombination aufgerufen.

- Für ein Steuerelement, das aktiviert wurde, wird<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent> ausgelöst (als Reaktion auf ein Steuerelement, das seine zugehörige Aktion ausführt). Sofern möglich, sollte das Ereignis ausgelöst werden, nachdem das Steuerelement die Aktion abgeschlossen hat und ohne Blockierung zurückgekehrt ist. In den folgenden Szenarien sollte das Invoked-Ereignis ausgelöst werden, bevor die Invoke-Anforderung verarbeitet wird:

  - Es ist nicht möglich oder zweckmäßig, bis zum Abschluss der Aktion zu warten.

  - Die Aktion erfordert eine Benutzeraktion.

  - Die Aktion ist zeitaufwändig und führt dazu, dass der aufrufende Client für einen längeren Zeitraum blockiert wird.

- Wenn das Aufrufen des Steuerelements größere Nebeneffekte hat, sollten diese Nebeneffekte über die <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A> -Eigenschaft mitgeteilt werden. Beispielsweise kann <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> bewirken, das ein anderes Steuerelement ausgewählt wird, obwohl <xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> nicht mit Auswahlverhalten verknüpft ist.

- Hovereffekte (oder Mouseovereffekte) sind im Allgemeinen kein Grund für ein Invoked-Ereignis. Jedoch sollten Steuerelemente, die auf Basis des Hoverzustands eine Aktion ausführen (im Gegensatz zum Verursachen eines visuellen Effekts), das <xref:System.Windows.Automation.InvokePattern> -Steuerelementmuster unterstützen.

> [!NOTE]
> Diese Implementierung wird als Problem für Barrierefreiheit betrachtet, wenn das Steuerelement nur als Ergebnis eines mausbezogenen Nebeneffekts aufgerufen werden kann.

- Das Aufrufen eines Steuerelements unterscheidet sich vom Auswählen eines Elements. Abhängig vom Steuerelement kann das Aufrufen jedoch möglicherweise den Nebeneffekt haben, dass das Element ausgewählt wird. For example, invoking a Microsoft Word document list item in the My Documents folder both selects the item and opens the document.

- Ein Element kann, wenn es aufgerufen wird, sofort aus der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur ausgeblendet werden. Dies kann zur Folge haben, dass das Anfordern von Informationen von dem Element, die durch den Ereignisrückruf bereitgestellt werden, fehlschlägt. Als Problemlösung wird empfohlen, zwischengespeicherte Informationen vorab abzurufen.

- Steuerelemente können mehrere Steuerelementmuster implementieren. For example, the Fill Color control on the Microsoft Excel toolbar implements both the <xref:System.Windows.Automation.InvokePattern> and the <xref:System.Windows.Automation.ExpandCollapsePattern> control patterns. Das<xref:System.Windows.Automation.ExpandCollapsePattern> macht das Menü verfügbar, und das I <xref:System.Windows.Automation.InvokePattern> füllt die aktive Auswahl mit der ausgewählten Farbe.

<a name="Required_Members_for_the_IValueProvider_Interface"></a>

## <a name="required-members-for-iinvokeprovider"></a>Erforderliche Member für IInvokeProvider

Die folgenden Eigenschaften und Methoden sind für das Implementieren von <xref:System.Windows.Automation.Provider.IInvokeProvider>erforderlich.

|Erforderliche Member|Memberart|Notizen|
|----------------------|-----------------|-----------|
|<xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A>|Methode|<xref:System.Windows.Automation.Provider.IInvokeProvider.Invoke%2A> ist ein asynchroner Aufruf und muss die Kontrolle sofort zurückgeben, ohne zu blockieren.<br /><br /> Dieses Verhalten ist insbesondere für Steuerelemente wichtig, die direkt oder indirekt ein modales Dialogfeld starten, wenn sie aufgerufen werden. Jeder Benutzeroberflächenautomatisierungs-Client, der das Ereignis ausgelöst hat, bleibt blockiert, bis das modale Dialogfeld geschlossen wird.|

<a name="Exceptions"></a>

## <a name="exceptions"></a>Ausnahmen

Anbieter müssen die folgenden Ausnahmen auslösen.

|Ausnahmetyp|Bedingung|
|--------------------|---------------|
|<xref:System.Windows.Automation.ElementNotEnabledException>|Wenn das Steuerelement nicht aktiviert ist.|

## <a name="see-also"></a>Siehe auch

- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns-overview.md)
- [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](support-control-patterns-in-a-ui-automation-provider.md)
- [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](ui-automation-control-patterns-for-clients.md)
- [Aufrufen eines Steuerelements mithilfe von Benutzeroberflächenautomatisierung](invoke-a-control-using-ui-automation.md)
- [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](ui-automation-tree-overview.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](use-caching-in-ui-automation.md)
