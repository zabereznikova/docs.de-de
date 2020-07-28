---
title: Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients
description: Lesen Sie eine Übersicht über Steuerelement Muster für Benutzeroberflächenautomatisierungs-Clients. Verwenden Sie Steuerelement Muster für den Zugriff auf Informationen über die Benutzeroberfläche (UI).
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control patterns for clients
- control patterns, UI Automation clients
ms.assetid: 571561d8-5f49-43a9-a054-87735194e013
ms.openlocfilehash: f2def328228a30ace6d0edc0661d6e79f237d6f4
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163873"
---
# <a name="ui-automation-control-patterns-for-clients"></a>Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 Diese Übersicht enthält Steuerelementmuster für Benutzeroberflächenautomatisierungs-Clients. Es sind Informationen dazu enthalten, wie ein Benutzeroberflächenautomatisierungs-Client Steuerelementmuster nutzen kann, um auf Informationen über die [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] zugreifen zu können.  
  
 Steuerelementmuster bieten eine Möglichkeit zum Kategorisieren und Verfügbarmachen der Funktionalität eines Steuerelements, unabhängig vom Typ des Steuerelements oder vom Erscheinungsbild des Steuerelements. Benutzeroberflächenautomatisierungs-Clients können ein <xref:System.Windows.Automation.AutomationElement> untersuchen, um festzulegen, welche Steuerelementmuster unterstützt werden und wie das Verhalten des Steuerelements sein wird.  
  
 Eine umfassende Liste mit Steuerelement Mustern finden Sie unter [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
<a name="uiautomation_getting_control_patterns"></a>
## <a name="getting-control-patterns"></a>Abrufen von Steuerelementmustern  
 Clients empfangen ein Steuerelementmuster von einem <xref:System.Windows.Automation.AutomationElement> durch den Aufruf eines <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A?displayProperty=nameWithType> oder <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A?displayProperty=nameWithType>.  
  
 Clients können die <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>-Methode oder eine einzelne `IsPatternAvailable`-Eigenschaft (z. B. <xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>) nutzen, um zu bestimmen, ob ein Muster oder eine Gruppe von Mustern im <xref:System.Windows.Automation.AutomationElement> unterstützt wird. Es ist jedoch effizienter, zu versuchen, das Steuerelementmuster abzurufen und zu prüfen, ob ein `null`-Verweis vorliegt als die unterstützten Eigenschaften zu überprüfen und das Steuerelementmuster abzurufen, da dies zu weniger prozessübergreifenden Aufrufen führt.  
  
 Das folgende Beispiel zeigt den Abruf eines <xref:System.Windows.Automation.TextPattern>-Steuerelementmusters aus einem <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIATextPattern_snip#1037](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#1037)]  
  
<a name="uiautomation_properties_on_control_patterns"></a>
## <a name="retrieving-properties-on-control-patterns"></a>Abrufen von Eigenschaften in Steuerelementmustern  
 Clients können die Eigenschaftswerte in Steuerelementmustern durch Aufrufen von <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType> oder <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType> abrufen und das zurückgegebene Objekt in einen geeigneten Typ umwandeln. Weitere Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Eigenschaften finden Sie unter [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
 Zusätzlich zu den- `GetPropertyValue` Methoden können Eigenschaftswerte über die Common Language Runtime (CLR)-Accessoren abgerufen werden, um [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] auf die Eigenschaften eines Musters zuzugreifen.  
  
<a name="uiautomation_with_variable_patterns"></a>
## <a name="controls-with-variable-patterns"></a>Steuerelemente mit Variablenmustern  
 Einige Steuerelementtypen unterstützen unterschiedliche Muster, abhängig vom entsprechenden Status oder der Art und Weise, wie das Steuerelement verwendet wird. Beispiele für Steuerelemente, die über Variablen Muster verfügen können, sind Listenansichten (Miniaturansichten, Kacheln, Symbole, Liste, Details), Microsoft Excel-Diagramme (Kreis, Linie, Balken, Zellwert mit einer Formel), Microsoft Word-Dokumentbereich (normal, Weblayout, Gliederung, Druck Layout, Druckvorschau) und Microsoft Windows Media Player Skins.  
  
 Steuerelemente, die benutzerdefinierte Steuerelementtypen implementieren, können über einen beliebigen Satz von Steuerelementmustern verfügen, die zur Darstellung der entsprechenden Funktionalität erforderlich sind.  
  
## <a name="see-also"></a>Siehe auch

- [Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns.md)
- [Textmuster zur Benutzeroberflächenautomatisierung](ui-automation-text-pattern.md)
- [Aufrufen eines Steuerelements mithilfe von Benutzeroberflächenautomatisierung](invoke-a-control-using-ui-automation.md)
- [Abrufen des Umschaltstatus eines Kontrollkästchens mithilfe von Benutzeroberflächenautomatisierung](get-the-toggle-state-of-a-check-box-using-ui-automation.md)
- [Zuordnen von Steuerelementmustern für Benutzeroberflächenautomatisierungs-Clients](control-pattern-mapping-for-ui-automation-clients.md)
- [TextPattern-Textbeispiel einfügen](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InsertText)
- [Beispiel für TextPattern-Suche und-Auswahl](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/FindText)
- [InvokePattern, expandredusepattern und TogglePattern (Beispiel)](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InvokePattern)
