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
ms.openlocfilehash: 1b82302ff89d2e8407871cbfba6c10e8322ac4e7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435502"
---
# <a name="get-ui-automation-element-properties"></a>Abrufen von Elementeigenschaften der Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In diesem Thema wird gezeigt, wie Eigenschaften eines [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Elements abgerufen werden.  
  
### <a name="get-a-current-property-value"></a>Aktuellen Eigenschafts Wert erhalten  
  
1. Rufen Sie den <xref:System.Windows.Automation.AutomationElement> ab, dessen Eigenschaft abgerufen werden soll.  
  
2. Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>auf, oder rufen Sie die <xref:System.Windows.Automation.AutomationElement.Current%2A> Eigenschafts Struktur ab, und rufen Sie den Wert von einem der Member ab.  
  
### <a name="get-a-cached-property-value"></a>Erhalten eines zwischengespeicherten Eigenschafts Werts  
  
1. Rufen Sie den <xref:System.Windows.Automation.AutomationElement> ab, dessen Eigenschaft abgerufen werden soll. Die-Eigenschaft muss in der <xref:System.Windows.Automation.CacheRequest>angegeben werden.  
  
2. Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>auf, oder rufen Sie die <xref:System.Windows.Automation.AutomationElement.Cached%2A> Eigenschafts Struktur ab, und rufen Sie den Wert von einem der Member ab.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt verschiedene Möglichkeiten, die aktuellen Eigenschaften eines <xref:System.Windows.Automation.AutomationElement>abzurufen.  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a>Siehe auch

- [UI Automation Properties for Clients](ui-automation-properties-for-clients.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](use-caching-in-ui-automation.md)
- [Caching in UI Automation Clients](caching-in-ui-automation-clients.md)
