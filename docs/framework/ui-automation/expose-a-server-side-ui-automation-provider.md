---
title: Verfügbarmachen eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- expose a server-side UI Automation provider
- UI Automation, server-side provider, exposing
- server-side UI Automation provider, exposing
ms.assetid: 55d419c0-2201-4101-90c9-2888df4dbb47
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 675d9c02503cd69c425a95cffabde053dd5cca59
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568815"
---
# <a name="expose-a-server-side-ui-automation-provider"></a>Verfügbarmachen eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Beispielcode, der die Offenlegung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters veranschaulicht, der in einem <xref:System.Windows.Forms.Control?displayProperty=nameWithType> -Fenster gehostet wird.  
  
 Das Beispiel setzt die Fensterprozedur außer Kraft, um WM_GETOBJECT, abzufangen. Dies ist die vom [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Kerndienst gesendete Nachricht, wenn eine Clientanwendung Informationen zum Fenster anfordert.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[UIAFragmentProvider_snip#116](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#116)]
 [!code-vb[UIAFragmentProvider_snip#116](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#116)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [Server-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)(Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieter)
