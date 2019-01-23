---
title: Registrieren einer clientseitigen Anbieterassembly
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- registering client-side provider assemblies
- client-side provider assemblies, registering
- UI Automation, registering provider assemblies
- provider assemblies, registering
ms.assetid: a03af4d9-2771-43cc-b07b-d468dca23190
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 2e5b5fcdf5ae0eead5da42d5c4a7f826d2a3aecb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511851"
---
# <a name="register-a-client-side-provider-assembly"></a><span data-ttu-id="ba93c-102">Registrieren einer clientseitigen Anbieterassembly</span><span class="sxs-lookup"><span data-stu-id="ba93c-102">Register a Client-Side Provider Assembly</span></span>
> [!NOTE]
>  <span data-ttu-id="ba93c-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ba93c-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="ba93c-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="ba93c-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="ba93c-105">In diesem Thema wird gezeigt, wie Sie eine DLL registrieren, die clientseitige Benutzeroberflächenautomatisierungs-Anbieter enthält.</span><span class="sxs-lookup"><span data-stu-id="ba93c-105">This topic shows how to register a DLL that contains client-side UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba93c-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ba93c-106">Example</span></span>  
 <span data-ttu-id="ba93c-107">Im folgenden Beispiel wird gezeigt, wie eine Assembly registriert wird, die einen Anbieter für ein Konsolenfenster enthält.</span><span class="sxs-lookup"><span data-stu-id="ba93c-107">The following example shows how to register an assembly that contains a provider for a console window.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSClientProgram.cs#102)]
 [!code-vb[UIAClientSideProvider_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csclientprogram.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="ba93c-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba93c-108">See also</span></span>
- [<span data-ttu-id="ba93c-109">Erstellen eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters</span><span class="sxs-lookup"><span data-stu-id="ba93c-109">Create a Client-Side UI Automation Provider</span></span>](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)
