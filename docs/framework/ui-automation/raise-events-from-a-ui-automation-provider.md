---
title: "Auslösen von Ereignissen aus einem Benutzeroberflächenautomatisierungs-Anbieter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
caps.latest.revision: "13"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 323c748a8d40158e51a776e4493975c55b117885
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="raise-events-from-a-ui-automation-provider"></a>Auslösen von Ereignissen aus einem Benutzeroberflächenautomatisierungs-Anbieter
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Beispielcode, in dem gezeigt wird, wie ein Ereignis aus einem Benutzeroberflächenautomatisierungs-Anbieter ausgelöst wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird in der Implementierung eines benutzerdefinierten Schaltflächen-Steuerelements ein [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis ausgelöst. Die Implementierung ermöglicht für eine Benutzeroberflächenautomatisierungs-Client-Anwendung, einen Klick auf die Schaltfläche zu simulieren.  
  
 Um unnötige Verarbeitungsvorgänge zu vermeiden, wird im Beispiel anhand von <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> überprüft, ob Ereignisse ausgelöst werden sollen.  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
