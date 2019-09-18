---
title: Abrufen von Elementeigenschaften der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: 158ebf29bb504dd11f9e8416011226fc5846873e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043611"
---
# <a name="get-ui-automation-element-properties"></a>Abrufen von Elementeigenschaften der Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.  
  
 In diesem Thema wird gezeigt, wie Eigenschaften eines [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Elements abgerufen werden.  
  
### <a name="get-a-current-property-value"></a>Aktuellen Eigenschafts Wert erhalten  
  
1. Rufen Sie <xref:System.Windows.Automation.AutomationElement> das ab, dessen Eigenschaft abgerufen werden soll.  
  
2. Rufen <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>Sie auf, oder <xref:System.Windows.Automation.AutomationElement.Current%2A> rufen Sie die Eigenschafts Struktur ab, und rufen Sie den Wert von einem ihrer Member ab.  
  
### <a name="get-a-cached-property-value"></a>Erhalten eines zwischengespeicherten Eigenschafts Werts  
  
1. Rufen Sie <xref:System.Windows.Automation.AutomationElement> das ab, dessen Eigenschaft abgerufen werden soll. Die-Eigenschaft muss in <xref:System.Windows.Automation.CacheRequest>angegeben werden.  
  
2. Rufen <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>Sie auf, oder <xref:System.Windows.Automation.AutomationElement.Cached%2A> rufen Sie die Eigenschafts Struktur ab, und rufen Sie den Wert von einem ihrer Member ab.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt verschiedene Möglichkeiten, die aktuellen Eigenschaften eines <xref:System.Windows.Automation.AutomationElement>abzurufen.  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a>Siehe auch

- [Benutzeroberflächenautomatisierungs-Eigenschaften für Clients](ui-automation-properties-for-clients.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](use-caching-in-ui-automation.md)
- [Zwischenspeichern in Benutzeroberflächenautomatisierungs-Clients](caching-in-ui-automation-clients.md)
