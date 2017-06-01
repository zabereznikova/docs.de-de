---
title: "Abrufen von unterst&#252;tzten Steuerelementmustern f&#252;r Benutzeroberfl&#228;chenautomatisierung | Microsoft Docs"
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
  - "Steuerelementmuster abrufen"
  - "Abrufen von Steuerelementmustern UI-Automatisierung"
  - "Abrufen von Steuerelementmustern"
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
caps.latest.revision: 10
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 10
---
# Abrufen von unterst&#252;tzten Steuerelementmustern f&#252;r Benutzeroberfl&#228;chenautomatisierung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler, die die verwaltete verwenden möchten vorgesehen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Klassen, die in der <xref:System.Windows.Automation> Namespace. Die neuesten Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows Automation API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In diesem Thema veranschaulicht, wie Muster von Objekten aus abrufen [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Elemente.  
  
### <a name="obtain-all-control-patterns"></a>Abrufen aller Steuerelementmuster  
  
1.  Abrufen der <xref:System.Windows.Automation.AutomationElement> , deren Steuerelementmustern interessiert sind.  
  
2.  Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> auf alle Steuerelementmuster aus dem Element abzurufen.  
  
> [!CAUTION]
>  Es wird dringend empfohlen, dass ein Client nicht verwendet <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>. Leistung kann schwerwiegend beeinträchtigt werden, wie diese Methode ruft <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> intern für jedes vorhandene Steuerelementmuster. Wenn möglich, ein Client aufrufen sollten <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> für die Muster von Interesse sind.  
  
### <a name="obtain-a-specific-control-pattern"></a>Abrufen eines bestimmten Steuerelementmusters  
  
1.  Abrufen der <xref:System.Windows.Automation.AutomationElement> , deren Steuerelementmustern interessiert sind.  
  
2.  Rufen Sie <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> oder <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> Abfrage für ein bestimmtes Muster. Diese Methoden ähneln sich, wenn das Muster nicht gefunden wird, aber <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> löst eine Ausnahme aus und <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> gibt `false`.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein <xref:System.Windows.Automation.AutomationElement> für ein Listenelement und erhält eine <xref:System.Windows.Automation.SelectionItemPattern> von diesem Element.  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)