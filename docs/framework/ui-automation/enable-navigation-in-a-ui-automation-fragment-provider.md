---
title: "Enable Navigation in a UI Automation Fragment Provider | Microsoft Docs"
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
  - "UI Automation, enabling navigation in provider"
  - "navigation, enabling in UI Automation provider"
ms.assetid: 3cb6092a-58c9-4ca0-84a5-0e54d5d00a0d
caps.latest.revision: 16
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 16
---
# Enable Navigation in a UI Automation Fragment Provider
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework\-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Klassen verwenden möchten, die im <xref:System.Windows.Automation>\-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] finden Sie auf der Seite zur [Windows\-Automatisierungs\-API: UI\-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Beispielcode, der das Aktivieren der Navigation in einem Benutzeroberflächenautomatisierungs\-Anbieter für ein Element veranschaulicht, das sich in einem Fragment befindet.  
  
## Beispiel  
 Der folgende Beispielcode implementiert <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> für ein Element in einer Liste. Das übergeordnete Element ist das Listenfeldelement und die gleichgeordneten Elemente sind andere Elemente in der Listenauflistung. Die Methode gibt `null` \(`Nothing` in Visual Basic\) für ungültige Anweisungen zurück. In diesem Fall <xref:System.Windows.Automation.Provider.NavigateDirection> und <xref:System.Windows.Automation.Provider.NavigateDirection>, da das Element keine untergeordneten Elemente aufweist.  
  
 [!code-csharp[UIAFragmentProvider_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListItemFragment.cs#103)]
 [!code-vb[UIAFragmentProvider_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListItemFragment.vb#103)]  
  
## Siehe auch  
 [UI Automation Providers Overview](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)   
 [Server\-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)