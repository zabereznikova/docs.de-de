---
title: "Get UI Automation Element Properties | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "properties, retrieving"
  - "UI Automation, retrieving properties of elements"
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
caps.latest.revision: 5
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 5
---
# Get UI Automation Element Properties
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework\-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Klassen verwenden möchten, die im <xref:System.Windows.Automation>\-Namespace definiert sind.  Aktuelle Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] finden Sie unter [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In diesem Thema wird veranschaulicht, wie Eigenschaften eines [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Elements abgerufen werden.  
  
### Abrufen eines aktuellen Eigenschaftswerts  
  
1.  Rufen Sie das <xref:System.Windows.Automation.AutomationElement> ab, dessen Eigenschaft Sie ermitteln möchten.  
  
2.  Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A> auf, oder rufen Sie die <xref:System.Windows.Automation.AutomationElement.Current%2A>\-Eigenschaftsstruktur ab, und beziehen Sie den Wert von einem seiner Member.  
  
### Abrufen eines zwischengespeicherten Eigenschaftswerts  
  
1.  Rufen Sie das <xref:System.Windows.Automation.AutomationElement> ab, dessen Eigenschaft Sie ermitteln möchten.  Die Eigenschaft musste in der <xref:System.Windows.Automation.CacheRequest> angegeben werden.  
  
2.  Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> auf, oder rufen Sie die <xref:System.Windows.Automation.AutomationElement.Cached%2A>\-Eigenschaftsstruktur ab, und beziehen Sie den Wert von einem seiner Member.  
  
## Beispiel  
 Im folgenden Beispiel werden verschiedene Möglichkeiten veranschaulicht, aktuelle Eigenschaften eines <xref:System.Windows.Automation.AutomationElement> abzurufen.  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## Siehe auch  
 [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)   
 [Use Caching in UI Automation](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)   
 [Caching in UI Automation Clients](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)