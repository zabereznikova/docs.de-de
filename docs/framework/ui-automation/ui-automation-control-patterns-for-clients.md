---
title: "Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, control patterns for clients
- control patterns, UI Automation clients
ms.assetid: 571561d8-5f49-43a9-a054-87735194e013
caps.latest.revision: "24"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 1d556b3da13b70a0a5e69eb72905e04a01dffa9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ui-automation-control-patterns-for-clients"></a>Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Diese Übersicht enthält Steuerelementmuster für Benutzeroberflächenautomatisierungs-Clients. Es enthält Informationen, wie ein Benutzeroberflächenautomatisierungs-Client Steuerelementmuster nutzen kann, Informationen über den Zugriff auf die [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)].  
  
 Steuerelementmuster bieten eine Möglichkeit zum Kategorisieren und Verfügbarmachen der Funktionalität eines Steuerelements, unabhängig vom Typ des Steuerelements oder vom Erscheinungsbild des Steuerelements. Benutzeroberflächenautomatisierungs-Clients können überprüfen, ein <xref:System.Windows.Automation.AutomationElement> um festzulegen, welche Steuerelementmuster unterstützt werden und wie das Verhalten des Steuerelements sein.  
  
 Eine vollständige Liste der verfügbaren Steuerelementmuster, finden Sie unter [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
<a name="uiautomation_getting_control_patterns"></a>   
## <a name="getting-control-patterns"></a>Abrufen von Steuerelementmustern  
 Clients empfangen ein Steuerelementmuster von einem <xref:System.Windows.Automation.AutomationElement> durch den Aufruf eines <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A?displayProperty=nameWithType> oder <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A?displayProperty=nameWithType>.  
  
 Clients können die <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>-Methode oder eine einzelne `IsPatternAvailable`-Eigenschaft (z. B. <xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>) nutzen, um zu bestimmen, ob ein Muster oder eine Gruppe von Mustern im <xref:System.Windows.Automation.AutomationElement> unterstützt wird. Es ist jedoch effizienter, zu versuchen, das Steuerelementmuster abzurufen und zu prüfen, ob ein `null`-Verweis vorliegt als die unterstützten Eigenschaften zu überprüfen und das Steuerelementmuster abzurufen, da dies zu weniger prozessübergreifenden Aufrufen führt.  
  
 Das folgende Beispiel zeigt den Abruf eines <xref:System.Windows.Automation.TextPattern>-Steuerelementmusters aus einem <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIATextPattern_snip#1037](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#1037)]  
  
<a name="uiautomation_properties_on_control_patterns"></a>   
## <a name="retrieving-properties-on-control-patterns"></a>Abrufen von Eigenschaften in Steuerelementmustern  
 Clients können die Eigenschaftswerte in Steuerelementmustern durch Aufrufen von <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType> oder <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType> abrufen und das zurückgegebene Objekt in einen geeigneten Typ umwandeln. Weitere Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Eigenschaften finden Sie in [Benutzeroberflächenautomatisierungs-Eigenschaften für Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
 Zusätzlich zu den `GetPropertyValue`-Methoden können Eigenschaftswerte über die [!INCLUDE[TLA#tla_clr](../../../includes/tlasharptla-clr-md.md)]-Accessoren abgerufen werden, um auf die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Eigenschaften in einem Muster zuzugreifen.  
  
<a name="uiautomation_with_variable_patterns"></a>   
## <a name="controls-with-variable-patterns"></a>Steuerelemente mit Variablenmustern  
 Einige Steuerelementtypen unterstützen unterschiedliche Muster, abhängig vom entsprechenden Status oder der Art und Weise, wie das Steuerelement verwendet wird. Beispiele für Steuerelemente mit Variablenmustern sind Listenansichten (Miniaturansichten, Kacheln, Symbole, Liste, Details), [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)]-Diagramme (Kreisdiagramm, Liniendiagramm, Balkendiagramm, Zellwert mit einer Formel), [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)]-Dokumentbereich (Normal, Weblayout, Gliederung, Seitenlayout, Seitenansicht) und [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)]-Designs.  
  
 Steuerelemente, die benutzerdefinierte Steuerelementtypen implementieren, können über einen beliebigen Satz von Steuerelementmustern verfügen, die zur Darstellung der entsprechenden Funktionalität erforderlich sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelementmuster für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-patterns.md)  
 [Textmuster zur Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-text-pattern.md)  
 [Aufrufen eines Steuerelements mithilfe von Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/invoke-a-control-using-ui-automation.md)  
 [Abrufen des Umschaltstatus eines Kontrollkästchens mithilfe von Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/get-the-toggle-state-of-a-check-box-using-ui-automation.md)  
 [Zuordnen von Steuerelementmustern für Benutzeroberflächenautomatisierungs-Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)  
 [Einfügen von TextPattern-Text (Beispiel)](http://msdn.microsoft.com/en-us/67353f93-7ee2-42f2-ab76-5c078cf6ca16)  
 [TextPattern-Suche und Auswahl-Beispiel](http://msdn.microsoft.com/en-us/0a3bca57-8b72-489d-a57c-da85b7a22c7f)  
 ["InvokePattern" und ExpandCollapsePattern-Menü-Element-Beispiel](http://msdn.microsoft.com/en-us/b7fa141c-e2d1-4da2-a27f-81a7d1172210)
