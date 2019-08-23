---
title: Zurückgeben von Eigenschaften aus einem Benutzeroberflächenautomatisierungs-Anbieter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- providers, UI Automation, returning properties
- properties, returned by UI Automation providers
- UI Automation, providers returning properties
ms.assetid: 5eba950e-b9e1-48eb-ab8e-b69db76bf589
ms.openlocfilehash: 7a637f759c952751c0472c51afa42a2c67c58624
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969103"
---
# <a name="return-properties-from-a-ui-automation-provider"></a><span data-ttu-id="435d8-102">Zurückgeben von Eigenschaften aus einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="435d8-102">Return Properties from a UI Automation Provider</span></span>
> [!NOTE]
> <span data-ttu-id="435d8-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="435d8-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="435d8-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="435d8-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="435d8-105">Dieses Thema enthält Beispielcode, der veranschaulicht, wie ein Benutzeroberflächenautomatisierungs-Anbieter Eigenschaften eines Elements an Clientanwendungen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="435d8-105">This topic contains sample code that shows how a UI Automation provider can return properties of an element to client applications.</span></span>  
  
 <span data-ttu-id="435d8-106">Für jede nicht explizit unterstützte Eigenschaft muss der Anbieter `null` zurückgeben (`Nothing` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="435d8-106">For any property it does not explicitly support, the provider must return `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="435d8-107">Dadurch wird sichergestellt, dass [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] versucht, die Eigenschaft aus einer anderen Quelle abzurufen, z. B. vom Hostfensteranbieter.</span><span class="sxs-lookup"><span data-stu-id="435d8-107">This ensures that [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] attempts to obtain the property from another source, such as the host window provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="435d8-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="435d8-108">Example</span></span>  
 [!code-csharp[UIAFragmentProvider_snip#117](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#117)]
 [!code-vb[UIAFragmentProvider_snip#117](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#117)]  
  
## <a name="see-also"></a><span data-ttu-id="435d8-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="435d8-109">See also</span></span>

- [<span data-ttu-id="435d8-110">Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="435d8-110">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- <span data-ttu-id="435d8-111">[Server-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)(Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieter)</span><span class="sxs-lookup"><span data-stu-id="435d8-111">[Server-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)</span></span>
