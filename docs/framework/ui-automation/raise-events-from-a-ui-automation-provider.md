---
title: "Raise Events from a UI Automation Provider | Microsoft Docs"
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
  - "UI Automation, raising events"
  - "raising UI Automation events"
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
caps.latest.revision: 13
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 13
---
# Raise Events from a UI Automation Provider
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework\-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Klassen verwenden möchten, die im <xref:System.Windows.Automation>\-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] finden Sie auf der Seite zur [Windows\-Automatisierungs\-API: UI\-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Beispielcode, in dem gezeigt wird, wie ein Ereignis aus einem Benutzeroberflächenautomatisierungs\-Anbieter ausgelöst wird.  
  
## Beispiel  
 Im folgenden Beispiel wird in der Implementierung eines benutzerdefinierten Schaltflächen\-Steuerelements ein [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]\-Ereignis ausgelöst. Die Implementierung ermöglicht für eine Benutzeroberflächenautomatisierungs\-Client\-Anwendung, einen Klick auf die Schaltfläche zu simulieren.  
  
 Um unnötige Verarbeitungsvorgänge zu vermeiden, wird im Beispiel anhand von <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> überprüft, ob Ereignisse ausgelöst werden sollen.  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## Siehe auch  
 [UI Automation Providers Overview](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)