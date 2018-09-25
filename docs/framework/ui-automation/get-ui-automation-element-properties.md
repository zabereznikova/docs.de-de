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
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: cb9e37c80c7bc32a29022ede0bffc06a0f6ac5b1
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47078031"
---
# <a name="get-ui-automation-element-properties"></a>Abrufen von Elementeigenschaften der Benutzeroberflächenautomatisierung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In diesem Thema wird gezeigt, wie zum Abrufen der Eigenschaften einer [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Element.  
  
### <a name="get-a-current-property-value"></a>Erhalten Sie einen aktuellen Eigenschaftswert  
  
1.  Abrufen der <xref:System.Windows.Automation.AutomationElement> , dessen Eigenschaft, die Sie abrufen möchten.  
  
2.  Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, oder Abrufen der <xref:System.Windows.Automation.AutomationElement.Current%2A> Struktur der Eigenschaft an, und erhalten den Wert von eins ihrer Elemente.  
  
### <a name="get-a-cached-property-value"></a>Abrufen eines Werts für die zwischengespeicherten Eigenschaftswerte  
  
1.  Abrufen der <xref:System.Windows.Automation.AutomationElement> , dessen Eigenschaft, die Sie abrufen möchten. Die Eigenschaft muss angegeben wurden die <xref:System.Windows.Automation.CacheRequest>.  
  
2.  Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, oder Abrufen der <xref:System.Windows.Automation.AutomationElement.Cached%2A> Struktur der Eigenschaft an, und erhalten den Wert von eins ihrer Elemente.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt verschiedene Möglichkeiten zum Abrufen der aktuellen Eigenschaften des ein <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenautomatisierungs-Eigenschaften für Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)  
 [Zwischenspeichern in Benutzeroberflächenautomatisierungs-Clients](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
