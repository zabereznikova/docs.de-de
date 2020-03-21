---
title: Übersicht über die Benutzeroberflächenautomatisierungs-Eigenschaften
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, properties
- properties, UI Automation
ms.assetid: a6c31d7b-b33e-49b3-b5c1-31a345f9b7c8
ms.openlocfilehash: 8a44fd89017002ae51d9b15a22bac97668d0ff90
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179866"
---
# <a name="ui-automation-properties-overview"></a>Übersicht über die Benutzeroberflächenautomatisierungs-Eigenschaften
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Benutzeroberflächenautomatisierungs-Anbieter machen Eigenschaften von [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Elementen verfügbar. Diese Eigenschaften ermöglichen es Benutzeroberflächenautomatisierungs-Clientanwendungen, Informationen zu Bestandteilen der [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)](insbesondere Steuerelemente) zu ermitteln, wobei diese Informationen sowohl statische als auch dynamische Daten umfassen können.  
  
 In diesem Abschnitt finden Sie eine allgemeine Übersicht über [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Eigenschaften. Speziellere Informationen finden Sie in folgenden Themen:  
  
- [Benutzeroberflächenautomatisierungs-Eigenschaften für Clients](ui-automation-properties-for-clients.md)  
  
- [Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters](server-side-ui-automation-provider-implementation.md)  
  
<a name="Property_Identifiers"></a>
## <a name="property-identifiers"></a>Eigenschaftsbezeichner  
 Jede Eigenschaft wird mit einer Zahl und einem Namen bezeichnet. Die Namen von Eigenschaften werden nur zum Debuggen und zu Diagnosezwecken verwendet. Anbieter verwenden die numerischen IDs, um eingehende Eigenschaftsanforderungen zu identifizieren. Clientanwendungen verwenden dagegen, um die abzurufenden Eigenschaften zu kennzeichnen, nur <xref:System.Windows.Automation.AutomationProperty>-Objekte, in denen die Zahl und der Name gekapselt werden.  
  
 <xref:System.Windows.Automation.AutomationProperty> -Objekte, die bestimmte Eigenschaften darstellen, sind als Felder in verschiedenen Klassen verfügbar. Aus Sicherheitsgründen rufen Benutzeroberflächenautomatisierungs-Anbieter diese Objekte aus einem separaten Satz von Klassen ab, die in „Uiautomationtypes.dll“ enthalten sind.  
  
 In der folgenden Tabelle werden Eigenschaften nach <xref:System.Windows.Automation.AutomationProperty>den Klassen kategorisiert, die die IDs enthalten.  
  
|Arten von Eigenschaften|Clients rufen IDs ab von|Anbieter rufen IDs ab von|  
|-------------------------|--------------------------|----------------------------|  
|Eigenschaften, die jedes der Elemente hat (siehe folgende Tabellen)|<xref:System.Windows.Automation.AutomationElement>|<xref:System.Windows.Automation.AutomationElementIdentifiers>|  
|Position eines andockbaren Fensters|<xref:System.Windows.Automation.DockPattern>|<xref:System.Windows.Automation.DockPatternIdentifiers>|  
|Zustand eines Elements, das erweitert und reduziert werden kann|<xref:System.Windows.Automation.ExpandCollapsePattern>|<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers>|  
|Eigenschaften eines Elements in einem Raster|<xref:System.Windows.Automation.GridItemPattern>|<xref:System.Windows.Automation.GridItemPatternIdentifiers>|  
|Eigenschaften eines Rasters|<xref:System.Windows.Automation.GridPattern>|<xref:System.Windows.Automation.GridPatternIdentifiers>|  
|Aktuelle und unterstützte Ansicht eines Elements, das mehrere Ansichten hat|<xref:System.Windows.Automation.MultipleViewPattern>|<xref:System.Windows.Automation.MultipleViewPatternIdentifiers>|  
|Eigenschaften eines Elements, das innerhalb eines Wertebereichs verschoben werden kann, etwa ein Schieberegler|<xref:System.Windows.Automation.RangeValuePattern>|<xref:System.Windows.Automation.RangeValuePatternIdentifiers>|  
|Eigenschaften eines scrollbaren Fensters|<xref:System.Windows.Automation.ScrollPattern>|<xref:System.Windows.Automation.ScrollPatternIdentifiers>|  
|Status und Container eines Elements, das ausgewählt werden kann, z. B. in einer Liste|<xref:System.Windows.Automation.SelectionItemPattern>|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers>|  
|Eigenschaften eines Steuerelements, das Auswahlelemente enthält|<xref:System.Windows.Automation.SelectionPattern>|<xref:System.Windows.Automation.SelectionPatternIdentifiers>|  
|Spalten- und Zeilenüberschriften eines Elements in einer Tabelle|<xref:System.Windows.Automation.TableItemPattern>|<xref:System.Windows.Automation.TableItemPatternIdentifiers>|  
|Spalten- und Zeilenüberschriften sowie Ausrichtung einer Tabelle|<xref:System.Windows.Automation.TablePattern>|<xref:System.Windows.Automation.TablePatternIdentifiers>|  
|Zustand eines umschaltbaren Steuerelements|<xref:System.Windows.Automation.TogglePattern>|<xref:System.Windows.Automation.TogglePatternIdentifiers>|  
|Funktionen eines Elements, das verschoben, gedreht oder in der Größe geändert werden kann|<xref:System.Windows.Automation.TransformPattern>|<xref:System.Windows.Automation.TransformPatternIdentifiers>|  
|Wert und Lese-/Schreibfunktionen eines Elements, das einen Wert hat|<xref:System.Windows.Automation.ValuePattern>|<xref:System.Windows.Automation.ValuePatternIdentifiers>|  
|Funktionen und Status eines Fensters|<xref:System.Windows.Automation.WindowPattern>|<xref:System.Windows.Automation.WindowPatternIdentifiers>|  
  
<a name="Properties_by_Category"></a>
## <a name="properties-by-category"></a>Eigenschaften nach Kategorie  
 In den folgenden Tabellen werden die Eigenschaften kategorisiert, deren IDs in <xref:System.Windows.Automation.AutomationElement> und <xref:System.Windows.Automation.AutomationElementIdentifiers>gefunden werden. Diese Eigenschaften hat jedes der Steuerelemente. Bis auf einige Ausnahmen sind wahrscheinlich alle diese Eigenschaften während der gesamten Lebensdauer der Anbieteranwendung statisch. Die meisten dynamischen Eigenschaften sind mit Steuerelementmustern verknüpft.  
  
 In der Spalte **Eigenschaftenzugriff** werden zusätzlich zu <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> und <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>alle weiteren Accessoren für jede Eigenschaft aufgeführt. Weitere Informationen zum Abrufen von Eigenschaften in einer Clientanwendung finden Sie unter [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
> [!NOTE]
> Spezielle Informationen zu jeder Eigenschaft finden Sie über den Link in der Spalte **Eigenschaftenzugriff** .  
  
### <a name="display-characteristics"></a>Anzeigen von Merkmalen  
  
|Eigenschaftsbezeichner|Eigenschaftenzugriff|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.BoundingRectangleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>|  
|<xref:System.Windows.Automation.AutomationElement.CultureProperty>|–|  
|<xref:System.Windows.Automation.AutomationElement.HelpTextProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HelpText%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsOffscreenProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsOffscreen%2A>|  
|<xref:System.Windows.Automation.AutomationElement.OrientationProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Orientation%2A>|  
  
### <a name="element-type"></a>Elementtyp  
  
|Eigenschaftsbezeichner|Eigenschaftenzugriff|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.ControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ControlType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsContentElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsContentElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsControlElementProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsControlElement%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemType%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LocalizedControlTypeProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LocalizedControlType%2A>|  
  
### <a name="identification"></a>Identifikation  
  
|Eigenschaftsbezeichner|Eigenschaftenzugriff|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AutomationId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClassNameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ClassName%2A>|  
|<xref:System.Windows.Automation.AutomationElement.FrameworkIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.FrameworkId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.LabeledByProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.LabeledBy%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NameProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ProcessIdProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ProcessId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.RuntimeIdProperty>|<xref:System.Windows.Automation.AutomationElement.GetRuntimeId%2A>|  
|<xref:System.Windows.Automation.AutomationElement.NativeWindowHandleProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.NativeWindowHandle%2A>|  
  
### <a name="interaction"></a>Interaktion  
  
|Eigenschaftsbezeichner|Eigenschaftenzugriff|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.AcceleratorKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AcceleratorKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.AccessKeyProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.AccessKey%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>|<xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>|  
|<xref:System.Windows.Automation.AutomationElement.HasKeyboardFocusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.HasKeyboardFocus%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsEnabled%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsKeyboardFocusableProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsKeyboardFocusable%2A>|  
  
### <a name="support-for-patterns"></a>Unterstützung für Muster  
  
|Eigenschaftsbezeichner|Eigenschaftenzugriff|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsDockPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsExpandCollapsePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsGridPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsInvokePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsMultipleViewPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsRangeValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsScrollPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsSelectionPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTableItemPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTablePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTogglePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsTransformPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsValuePatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsWindowPatternAvailableProperty>|<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>|  
  
### <a name="miscellaneous"></a>Sonstiges  
  
|Eigenschaftsbezeichner|Eigenschaftenzugriff|  
|-------------------------|---------------------|  
|<xref:System.Windows.Automation.AutomationElement.IsRequiredForFormProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsRequiredForForm%2A>|  
|<xref:System.Windows.Automation.AutomationElement.IsPasswordProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.IsPassword%2A>|  
|<xref:System.Windows.Automation.AutomationElement.ItemStatusProperty>|<xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.ItemStatus%2A>|  
  
<a name="Localization"></a>
## <a name="localization"></a>Lokalisierung  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anbieter sollten folgende Eigenschaften in der Sprache des Betriebssystems zur Verfügung stellen:  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AcceleratorKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.AccessKeyProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>  
  
- <xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>  
  
<a name="Properties_and_Events"></a>
## <a name="properties-and-events"></a>Eigenschaften und Ereignisse  
 Direkt verknüpft mit den Eigenschaften in [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ist das Konzept von Ereignissen aufgrund von geänderten Eigenschaften. Bei dynamischen Eigenschaften muss die Clientanwendung feststellen können, ob ein Eigenschaftswert geändert wurde. Nur dann kann sie die Informationen in ihrem Cache aktualisieren oder auf andere Weise auf die neuen Informationen reagieren.  
  
 Anbieter lösen Ereignisse aus, wenn irgendetwas in der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] geändert wurde. Wird zum Beispiel ein Kontrollkästchen aktiviert oder deaktiviert, wird von dem Umschaltmuster, das für den Anbieter implementiert ist, ein Ereignis entsprechend der Eigenschaftenänderung ausgelöst. Anbieter können abhängig davon, ob Clients Ereignissen oder bestimmten Ereignissen lauschen, selektiv Ereignisse auslösen.  
  
 Es werden nicht für alle Eigenschaftenänderung Ereignisse ausgelöst. Dies ist vollständig von der Implementierung des Benutzeroberflächenautomatisierungs-Anbieters für das Element abhängig. Die Standardproxyanbieter für Listenfelder lösen beispielsweise kein Ereignis aus, wenn <xref:System.Windows.Automation.SelectionPattern.SelectionProperty> geändert wird. In diesem Fall muss die Anwendung einem <xref:System.Windows.Automation.SelectionItemPattern.ElementSelectedEvent>lauschen.  
  
 Clients lauschen Ereignissen, indem sie diese abonnieren. Abonnieren von Ereignissen bedeutet, dass Delegatenmethoden erstellt werden, die Ereignisse verarbeiten können, und dass die Methoden anschließend zusammen mit den Ereignissen, die von diesen Methoden verarbeitet werden, an [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] übergeben werden. Insbesondere für Ereignisse wegen geänderter Eigenschaften müssen Clients <xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>implementieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Zwischenspeichern in Benutzeroberflächenautomatisierungs-Clients](caching-in-ui-automation-clients.md)
- [Benutzeroberflächenautomatisierungs-Eigenschaften für Clients](ui-automation-properties-for-clients.md)
- [Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters](server-side-ui-automation-provider-implementation.md)
- [Suchen eines Benutzeroberflächenautomatisierungs-Elements anhand einer Eigenschaftenbedingung](find-a-ui-automation-element-based-on-a-property-condition.md)
- [Zurückgeben von Eigenschaften aus einem Benutzeroberflächenautomatisierungs-Anbieter](return-properties-from-a-ui-automation-provider.md)
- [Auslösen von Ereignissen aus einem Benutzeroberflächenautomatisierungs-Anbieter](raise-events-from-a-ui-automation-provider.md)
