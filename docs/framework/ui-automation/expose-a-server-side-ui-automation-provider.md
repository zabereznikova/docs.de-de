---
title: "Verfügbarmachen eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters"
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
- expose a server-side UI Automation provider
- UI Automation, server-side provider, exposing
- server-side UI Automation provider, exposing
ms.assetid: 55d419c0-2201-4101-90c9-2888df4dbb47
caps.latest.revision: "20"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b18bf705c0aefcc8d10575b8b4648d2e2bcaccb7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="expose-a-server-side-ui-automation-provider"></a>Verfügbarmachen eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Beispielcode, der zeigt, wie einen serverseitiger Benutzeroberflächenautomatisierungs-Anbieter verfügbar machen, die in gehostet wird eine <xref:System.Windows.Forms.Control?displayProperty=nameWithType> Fenster.  
  
 Das Beispiel setzt die Fensterprozedur außer Kraft, um WM_GETOBJECT, abzufangen. Dies ist die vom [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Kerndienst gesendete Nachricht, wenn eine Clientanwendung Informationen zum Fenster anfordert.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[UIAFragmentProvider_snip#116](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#116)]
 [!code-vb[UIAFragmentProvider_snip#116](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#116)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [Server-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)(Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieter)
