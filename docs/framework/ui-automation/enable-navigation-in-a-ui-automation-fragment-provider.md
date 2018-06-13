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
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 1f4dea321ba4a4242af0766a367731222368372e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401026"
---
# <a name="enable-navigation-in-a-ui-automation-fragment-provider"></a><span data-ttu-id="d0f83-102">Aktivieren der Navigation in einem Benutzeroberflächenautomatisierungs-Fragmentanbieter</span><span class="sxs-lookup"><span data-stu-id="d0f83-102">Enable Navigation in a UI Automation Fragment Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="d0f83-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d0f83-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d0f83-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="d0f83-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="d0f83-105">Dieses Thema enthält Beispielcode, der das Aktivieren der Navigation in einem Benutzeroberflächenautomatisierungs-Anbieter für ein Element veranschaulicht, das sich in einem Fragment befindet.</span><span class="sxs-lookup"><span data-stu-id="d0f83-105">This topic contains example code that shows how to enable navigation in a UI Automation provider for an element that is within a fragment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0f83-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0f83-106">Example</span></span>  
 <span data-ttu-id="d0f83-107">Der folgende Beispielcode implementiert <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> für ein Element in einer Liste.</span><span class="sxs-lookup"><span data-stu-id="d0f83-107">The following example code implements <xref:System.Windows.Automation.Provider.IRawElementProviderFragment.Navigate%2A> for a list item within a list.</span></span> <span data-ttu-id="d0f83-108">Das übergeordnete Element ist das Listenfeldelement und die gleichgeordneten Elemente sind andere Elemente in der Listenauflistung.</span><span class="sxs-lookup"><span data-stu-id="d0f83-108">The parent element is the list box element, and the sibling elements are other items in the list collection.</span></span> <span data-ttu-id="d0f83-109">Die Methode gibt `null` (`Nothing` in Visual Basic) für ungültige Anweisungen zurück. In diesem Fall <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> und <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>, da das Element keine untergeordneten Elemente aufweist.</span><span class="sxs-lookup"><span data-stu-id="d0f83-109">The method returns `null` (`Nothing` in Visual Basic) for directions that are not valid; in this case, <xref:System.Windows.Automation.Provider.NavigateDirection.FirstChild> and <xref:System.Windows.Automation.Provider.NavigateDirection.LastChild>, because the element has no children.</span></span>  
  
 [!code-csharp[UIAFragmentProvider_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListItemFragment.cs#103)]
 [!code-vb[UIAFragmentProvider_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListItemFragment.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="d0f83-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0f83-110">See Also</span></span>  
 [<span data-ttu-id="d0f83-111">Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="d0f83-111">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 <span data-ttu-id="d0f83-112">[Server-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)(Implementierung eines serverseitigen Benutzeroberflächenautomatisierungs-Anbieter)</span><span class="sxs-lookup"><span data-stu-id="d0f83-112">[Server-Side UI Automation Provider Implementation](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)</span></span>
