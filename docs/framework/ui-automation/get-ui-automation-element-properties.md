---
title: "Abrufen von Elementeigenschaften der Benutzeroberflächenautomatisierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
caps.latest.revision: "5"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 2b9e1f24a6384cd052dd7b15c7afb3facac05c57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="get-ui-automation-element-properties"></a>Abrufen von Elementeigenschaften der Benutzeroberflächenautomatisierung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In diesem Thema wird gezeigt, wie zum Abrufen der Eigenschaften einer [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Element.  
  
### <a name="get-a-current-property-value"></a>Abrufen von einem aktuellen Eigenschaftswert  
  
1.  Abrufen der <xref:System.Windows.Automation.AutomationElement> , deren Eigenschaft, die Sie abrufen möchten.  
  
2.  Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, oder Abrufen der <xref:System.Windows.Automation.AutomationElement.Current%2A> Eigenschaftsstruktur und beziehen Sie den Wert von einem seiner Member.  
  
### <a name="get-a-cached-property-value"></a>Abrufen eines zwischengespeicherten Werts  
  
1.  Abrufen der <xref:System.Windows.Automation.AutomationElement> , deren Eigenschaft, die Sie abrufen möchten. Die Eigenschaft muss angegeben wurde der <xref:System.Windows.Automation.CacheRequest>.  
  
2.  Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, oder Abrufen der <xref:System.Windows.Automation.AutomationElement.Cached%2A> Eigenschaftsstruktur und beziehen Sie den Wert von einem seiner Member.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt verschiedene Möglichkeiten zum Abrufen der aktuellen Eigenschaften des ein <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a>Siehe auch  
 [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [Verwenden der Zwischenspeicherung in der UI-Automatisierung](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)  
 [Zwischenspeichern in Benutzeroberflächenautomatisierungs-Clients](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
