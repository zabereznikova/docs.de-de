---
title: Implementierung von Benutzeroberflächenautomatisierungs-Anbietern in einer Clientanwendung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client-side UI Automation provider, implementation within applications
- UI Automation, implementing client-side provider within application
ms.assetid: f325f0d8-1715-41ea-85ca-45b82ffea8bc
ms.openlocfilehash: ef3d03bee412b97ed88ec76e81ad2fd19a9595eb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968948"
---
# <a name="implement-ui-automation-providers-in-a-client-application"></a><span data-ttu-id="ae31d-102">Implementierung von Benutzeroberflächenautomatisierungs-Anbietern in einer Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="ae31d-102">Implement UI Automation Providers in a Client Application</span></span>
> [!NOTE]
> <span data-ttu-id="ae31d-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ae31d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ae31d-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="ae31d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="ae31d-105">Dieses Thema enthält Beispielcode, in dem gezeigt wird, wie ein clientseitiger Benutzeroberflächenautomatisierungs-Anbieter in einer Anwendung implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="ae31d-105">This topic contains example code that shows how to implement a client-side UI Automation provider within an application.</span></span>  
  
 <span data-ttu-id="ae31d-106">Dies ist ein ungewöhnliches Szenario.</span><span class="sxs-lookup"><span data-stu-id="ae31d-106">This is an uncommon scenario.</span></span> <span data-ttu-id="ae31d-107">In der Regel verwendet eine Benutzeroberflächenautomatisierungs-Clientanwendung serverseitige oder clientseitige Anbieter, die sich in einer DLL befinden.</span><span class="sxs-lookup"><span data-stu-id="ae31d-107">Most often, a UI Automation client application uses server-side providers, or client-side providers that reside in a DLL.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae31d-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ae31d-108">Example</span></span>  
 <span data-ttu-id="ae31d-109">Im folgenden Beispielcode wird ein einfacher Anbieter für ein Konsolenfenster implementiert.</span><span class="sxs-lookup"><span data-stu-id="ae31d-109">The following example code implements a simple provider for a console window.</span></span> <span data-ttu-id="ae31d-110">Dieser Code ist nicht auf Funktionalität ausgerichtet, sondern soll die grundlegenden Schritte beim Einrichten eines Anbieters in Clientcode und dessen Registrierung durch <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="ae31d-110">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider within client code and registering it by using <xref:System.Windows.Automation.ClientSettings.RegisterClientSideProviders%2A>.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#201](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/ClientImplementationProgram.cs#201)]
 [!code-vb[UIAClientSideProvider_snip#201](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/clientimplementationprogram.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="ae31d-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae31d-111">See also</span></span>

- [<span data-ttu-id="ae31d-112">Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="ae31d-112">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)
- [<span data-ttu-id="ae31d-113">Registrieren einer clientseitigen Anbieterassembly</span><span class="sxs-lookup"><span data-stu-id="ae31d-113">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
- [<span data-ttu-id="ae31d-114">Erstellen eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters</span><span class="sxs-lookup"><span data-stu-id="ae31d-114">Create a Client-Side UI Automation Provider</span></span>](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)
- [<span data-ttu-id="ae31d-115">Implementierung eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters</span><span class="sxs-lookup"><span data-stu-id="ae31d-115">Client-Side UI Automation Provider Implementation</span></span>](../../../docs/framework/ui-automation/client-side-ui-automation-provider-implementation.md)
