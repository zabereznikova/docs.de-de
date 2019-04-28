---
title: Aktivieren der Navigation in einem Benutzeroberflächenautomatisierungs-Fragmentanbieter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, enabling navigation in provider
- navigation, enabling in UI Automation provider
ms.assetid: 3cb6092a-58c9-4ca0-84a5-0e54d5d00a0d
ms.openlocfilehash: e97494e01a81ad75820cd3cffa51b5a508152355
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645915"
---
# <a name="enable-navigation-in-a-ui-automation-fragment-provider"></a><span data-ttu-id="ed1ea-102">Aktivieren der Navigation in einem Benutzeroberflächenautomatisierungs-Fragmentanbieter</span><span class="sxs-lookup"><span data-stu-id="ed1ea-102">Enable Navigation in a UI Automation Fragment Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="ed1ea-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ed1ea-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ed1ea-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="ed1ea-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="ed1ea-105">Dieses Thema enthält Beispielcode, der das Aktivieren der Navigation in einem Benutzeroberflächenautomatisierungs-Anbieter für ein Element veranschaulicht, das sich in einem Fragment befindet.</span><span class="sxs-lookup"><span data-stu-id="ed1ea-105">This topic contains example code that shows how to enable navigation in a UI Automation provider for an element that is within a fragment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed1ea-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed1ea-106">Example</span></span>  
 <span data-ttu-id="ed1ea-107">Der folgende Beispielcode implementiert <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> für ein Element in einer Liste.</span><span class="sxs-lookup"><span data-stu-id="ed1ea-107">The following example code implements <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> for a list item within a list.</span></span> <span data-ttu-id="ed1ea-108">Das übergeordnete Element ist das Listenfeldelement und die gleichgeordneten Elemente sind andere Elemente in der Listenauflistung.</span><span class="sxs-lookup"><span data-stu-id="ed1ea-108">The parent element is the list box element, and the sibling elements are other items in the list collection.</span></span> <span data-ttu-id="ed1ea-109">Die Methode gibt `null` (`Nothing` in Visual Basic) für ungültige Anweisungen zurück. In diesem Fall <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> und <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>, da das Element keine untergeordneten Elemente aufweist.</span><span class="sxs-lookup"><span data-stu-id="ed1ea-109">The method returns `null` (`Nothing` in Visual Basic) for directions that are not valid; in this case, <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> and <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>, because the element has no children.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListItemFragment.cs#103)]
 [!code-vb[UIAFragmentProvider_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListItemFragment.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="ed1ea-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed1ea-110">See also</span></span>

- [<span data-ttu-id="ed1ea-111">Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="ed1ea-111">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- <span data-ttu-id="ed1ea-112">[Server-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)(Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieter)</span><span class="sxs-lookup"><span data-stu-id="ed1ea-112">[Server-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)</span></span>
