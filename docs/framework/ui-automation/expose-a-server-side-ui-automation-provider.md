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
ms.openlocfilehash: 247a353a3f68289a85e581fd9b9c308e442a9412
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2018
ms.locfileid: "47455486"
---
# <a name="expose-a-server-side-ui-automation-provider"></a><span data-ttu-id="62d75-102">Verfügbarmachen eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieters</span><span class="sxs-lookup"><span data-stu-id="62d75-102">Expose a Server-side UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="62d75-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="62d75-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="62d75-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: UI-Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="62d75-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="62d75-105">Dieses Thema enthält Beispielcode, der zeigt, wie serverseitige Benutzeroberflächenautomatisierungs-Anbieter verfügbar zu machen, die in gehostet ist eine <xref:System.Windows.Forms.Control?displayProperty=nameWithType> Fenster.</span><span class="sxs-lookup"><span data-stu-id="62d75-105">This topic contains example code that shows how to expose a server-side UI Automation provider that is hosted in a <xref:System.Windows.Forms.Control?displayProperty=nameWithType> window.</span></span>  
  
 <span data-ttu-id="62d75-106">Das Beispiel setzt die Fensterprozedur außer Kraft, um WM_GETOBJECT, abzufangen. Dies ist die vom [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Kerndienst gesendete Nachricht, wenn eine Clientanwendung Informationen zum Fenster anfordert.</span><span class="sxs-lookup"><span data-stu-id="62d75-106">The example overrides the window procedure to trap WM_GETOBJECT, which is the message sent by the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] core service when a client application requests information about the window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62d75-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="62d75-107">Example</span></span>  
 [!code-csharp[UIAFragmentProvider_snip#116](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#116)]
 [!code-vb[UIAFragmentProvider_snip#116](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#116)]  
  
## <a name="see-also"></a><span data-ttu-id="62d75-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62d75-108">See Also</span></span>  
 [<span data-ttu-id="62d75-109">Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="62d75-109">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 <span data-ttu-id="62d75-110">[Server-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)(Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieter)</span><span class="sxs-lookup"><span data-stu-id="62d75-110">[Server-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)</span></span>
