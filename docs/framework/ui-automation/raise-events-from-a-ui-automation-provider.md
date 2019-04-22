---
title: Auslösen von Ereignissen aus einem Benutzeroberflächenautomatisierungs-Anbieter
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, raising events
- raising UI Automation events
ms.assetid: 9fe2f01b-f7d8-49a8-a185-d4472b9976c0
ms.openlocfilehash: 3deb4c6716d83af4b05e15b5b8a4b89e28317406
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138696"
---
# <a name="raise-events-from-a-ui-automation-provider"></a><span data-ttu-id="de608-102">Auslösen von Ereignissen aus einem Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="de608-102">Raise Events from a UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="de608-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="de608-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="de608-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="de608-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="de608-105">Dieses Thema enthält Beispielcode, in dem gezeigt wird, wie ein Ereignis aus einem Benutzeroberflächenautomatisierungs-Anbieter ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="de608-105">This topic contains example code that shows how to raise an event from a UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de608-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de608-106">Example</span></span>  
 <span data-ttu-id="de608-107">Im folgenden Beispiel wird in der Implementierung eines benutzerdefinierten Schaltflächen-Steuerelements ein [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="de608-107">In the following example, a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event is raised in the implementation of a custom button control.</span></span> <span data-ttu-id="de608-108">Die Implementierung ermöglicht für eine Benutzeroberflächenautomatisierungs-Client-Anwendung, einen Klick auf die Schaltfläche zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="de608-108">The implementation enables a UI Automation client application to simulate a button click.</span></span>  
  
 <span data-ttu-id="de608-109">Um unnötige Verarbeitungsvorgänge zu vermeiden, wird im Beispiel anhand von <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> überprüft, ob Ereignisse ausgelöst werden sollen.</span><span class="sxs-lookup"><span data-stu-id="de608-109">To avoid unnecessary processing, the example checks <xref:System.Windows.Automation.Provider.AutomationInteropProvider.ClientsAreListening%2A> to see whether events should be raised.</span></span>  
  
 [!code-csharp[UIAProvider_snip#150](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAProvider_snip/CSharp/FragmentRoot.cs#150)]  
  
## <a name="see-also"></a><span data-ttu-id="de608-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de608-110">See also</span></span>

- [<span data-ttu-id="de608-111">Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="de608-111">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
