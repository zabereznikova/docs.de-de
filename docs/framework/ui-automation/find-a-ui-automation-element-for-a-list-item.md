---
title: "Find a UI Automation Element for a List Item | Microsoft Docs"
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
  - "list items, finding elements for"
  - "elements, finding for list items"
  - "UI Automation, finding elements for List items"
ms.assetid: c326ad2b-2144-4f64-ae4c-d850c74f95c5
caps.latest.revision: 5
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 5
---
# Find a UI Automation Element for a List Item
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework\-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Klassen verwenden möchten, die im <xref:System.Windows.Automation>\-Namespace definiert sind.  Aktuelle Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] finden Sie unter [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Im folgenden Beispiel wird veranschaulicht, wie ein <xref:System.Windows.Automation.AutomationElement> für ein Listenelement abgerufen werden kann, dessen Index bekannt ist.  
  
## Beispiel  
 Im folgenden Beispiel werden zwei Möglichkeiten zum Abrufen eines bestimmten Elements veranschaulicht. Verwendet wird bei einer Möglichkeit <xref:System.Windows.Automation.TreeWalker>, bei der anderen <xref:System.Windows.Automation.AutomationElement.FindAll%2A>.  
  
 Das erste Verfahren ist bei [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]\-Steuerelementen schneller, das zweite ist jedoch schneller bei [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)]\-Steuerelementen.  
  
 [!code-csharp[UIAClient_snip#184](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#184)]
 [!code-vb[UIAClient_snip#184](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#184)]  
  
## Siehe auch  
 [Obtaining UI Automation Elements](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)