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
ms.openlocfilehash: ed45b7e5d60e42f03bce8b9dc4abbf8226916304
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966357"
---
# <a name="register-a-client-side-provider-assembly"></a><span data-ttu-id="db2d1-102">Registrieren einer clientseitigen Anbieterassembly</span><span class="sxs-lookup"><span data-stu-id="db2d1-102">Register a Client-Side Provider Assembly</span></span>
> [!NOTE]
> <span data-ttu-id="db2d1-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="db2d1-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="db2d1-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="db2d1-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="db2d1-105">In diesem Thema wird gezeigt, wie Sie eine DLL registrieren, die clientseitige Benutzeroberflächenautomatisierungs-Anbieter enthält.</span><span class="sxs-lookup"><span data-stu-id="db2d1-105">This topic shows how to register a DLL that contains client-side UI Automation providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db2d1-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="db2d1-106">Example</span></span>  
 <span data-ttu-id="db2d1-107">Im folgenden Beispiel wird gezeigt, wie eine Assembly registriert wird, die einen Anbieter für ein Konsolenfenster enthält.</span><span class="sxs-lookup"><span data-stu-id="db2d1-107">The following example shows how to register an assembly that contains a provider for a console window.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#102](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSClientProgram.cs#102)]
 [!code-vb[UIAClientSideProvider_snip#102](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csclientprogram.vb#102)]  
  
## <a name="see-also"></a><span data-ttu-id="db2d1-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db2d1-108">See also</span></span>

- [<span data-ttu-id="db2d1-109">Erstellen eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters</span><span class="sxs-lookup"><span data-stu-id="db2d1-109">Create a Client-Side UI Automation Provider</span></span>](../../../docs/framework/ui-automation/create-a-client-side-ui-automation-provider.md)
