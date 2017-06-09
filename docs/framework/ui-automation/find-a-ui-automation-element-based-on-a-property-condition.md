---
title: "Find a UI Automation Element Based on a Property Condition | Microsoft Docs"
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
  - "elements, finding by property conditions"
  - "UI Automation, finding elements by property conditions"
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
caps.latest.revision: 19
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 19
---
# Find a UI Automation Element Based on a Property Condition
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework\-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Klassen verwenden möchten, die im <xref:System.Windows.Automation>\-Namespace definiert sind.  Aktuelle Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] finden Sie unter [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In diesem Thema finden Sie Beispielcode, der das Suchen eines Elements in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Struktur auf Grundlage mindestens einer bestimmten Eigenschaft veranschaulicht.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Reihe von Eigenschaftenbedingungen angegeben, die ein bestimmtes relevantes Element \(bzw. bestimmte Elemente\) in der <xref:System.Windows.Automation.AutomationElement>\-Struktur identifizieren.  Anschließend wird mit der <xref:System.Windows.Automation.AutomationElement.FindAll%2A>\-Methode eine Suche nach allen übereinstimmenden Elementen ausgeführt. Diese Methode verwendet eine Reihe boolescher Operatoren aus <xref:System.Windows.Automation.AndCondition>, um die Anzahl der übereinstimmenden Elemente einzuschränken.  
  
> [!NOTE]
>  Bei einer Suche in <xref:System.Windows.Automation.AutomationElement.RootElement%2A> sollte versucht werden, nur direkt untergeordnete Elemente zu erhalten.  Eine Suche nach nachfolgenden Elementen kann hunderte oder sogar tausende Elemente durchlaufen und möglicherweise einen Stapelüberlauf verursachen.  Wenn ein bestimmtes Element auf einer niedrigeren Ebene abgerufen werden soll, sollten Sie die Suche im Anwendungsfenster oder in einem Container auf niedrigerer Ebene starten.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## Siehe auch  
 [InvokePattern and ExpandCollapsePattern Menu Item Sample](http://msdn.microsoft.com/de-de/b7fa141c-e2d1-4da2-a27f-81a7d1172210)   
 [Obtaining UI Automation Elements](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)   
 [Use the AutomationID Property](../../../docs/framework/ui-automation/use-the-automationid-property.md)