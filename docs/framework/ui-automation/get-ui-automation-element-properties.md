---
title: Abrufen von Elementeigenschaften der Benutzeroberflächenautomatisierung
description: In den Anweisungen und einem Beispiel wird gezeigt, wie Sie die aktuellen oder zwischengespeicherten Eigenschaften eines Benutzeroberflächenautomatisierungs-Elements abrufen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: 34a42355acce0beafbb9658baf6032e4e7e19fcb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276424"
---
# <a name="get-ui-automation-element-properties"></a>Abrufen von Elementeigenschaften der Benutzeroberflächenautomatisierung

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 In diesem Thema wird gezeigt, wie Eigenschaften eines-Elements abgerufen werden [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
### <a name="get-a-current-property-value"></a>Aktuellen Eigenschafts Wert erhalten  
  
1. Rufen Sie das ab <xref:System.Windows.Automation.AutomationElement> , dessen Eigenschaft abgerufen werden soll.  
  
2. Rufen <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> Sie auf, oder rufen <xref:System.Windows.Automation.AutomationElement.Current%2A> Sie die Eigenschafts Struktur ab, und rufen Sie den Wert von einem ihrer Member ab.  
  
### <a name="get-a-cached-property-value"></a>Erhalten eines zwischengespeicherten Eigenschafts Werts  
  
1. Rufen Sie das ab <xref:System.Windows.Automation.AutomationElement> , dessen Eigenschaft abgerufen werden soll. Die-Eigenschaft muss in angegeben werden <xref:System.Windows.Automation.CacheRequest> .  
  
2. Rufen <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> Sie auf, oder rufen <xref:System.Windows.Automation.AutomationElement.Cached%2A> Sie die Eigenschafts Struktur ab, und rufen Sie den Wert von einem ihrer Member ab.  
  
## <a name="example"></a>Beispiel  

 Das folgende Beispiel zeigt verschiedene Möglichkeiten, die aktuellen Eigenschaften eines abzurufen <xref:System.Windows.Automation.AutomationElement> .  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Benutzeroberflächenautomatisierungs-Eigenschaften für Clients](ui-automation-properties-for-clients.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](use-caching-in-ui-automation.md)
- [Zwischenspeichern in Benutzeroberflächenautomatisierungs-Clients](caching-in-ui-automation-clients.md)
