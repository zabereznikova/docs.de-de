---
title: "Erstellen eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters"
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
- UI Automation, creating client-side provider
- client-side UI Automation provider, creating
ms.assetid: d91edaf2-be28-41ec-a508-af421cb43c3d
caps.latest.revision: "11"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 5ff3723e016e01b7c249dc7533f2657ea607cd0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="create-a-client-side-ui-automation-provider"></a><span data-ttu-id="f9848-102">Erstellen eines clientseitigen Benutzeroberflächenautomatisierungs-Anbieters</span><span class="sxs-lookup"><span data-stu-id="f9848-102">Create a Client-Side UI Automation Provider</span></span>
> [!NOTE]
>  <span data-ttu-id="f9848-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="f9848-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="f9848-104">Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="f9848-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="f9848-105">Dieses Thema enthält Beispielcode, in dem gezeigt wird, wie ein clientseitiger Benutzeroberflächenautomatisierungs-Anbieter implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="f9848-105">This topic contains example code that shows how to implement a client-side UI Automation provider.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9848-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9848-106">Example</span></span>  
 <span data-ttu-id="f9848-107">Der folgende Beispielcode kann in eine [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] integriert werden, die einen sehr einfachen clientseitigen Anbieter für ein Konsolenfenster implementiert.</span><span class="sxs-lookup"><span data-stu-id="f9848-107">The following example code can be built into a [!INCLUDE[TLA#tla_dll](../../../includes/tlasharptla-dll-md.md)] that implements a very simple client-side provider for a console window.</span></span> <span data-ttu-id="f9848-108">Der Code enthält keine nützliche Funktionalität, sondern soll die grundlegenden Schritte bei der Einrichtung einer Anbieterassembly veranschaulichen, die über eine Benutzeroberflächenautomatisierungs-Clientanwendung registriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9848-108">The code does not have any useful functionality, but is intended to demonstrate the basic steps in setting up a provider assembly that can be registered by a UI Automation client application.</span></span>  
  
 [!code-csharp[UIAClientSideProvider_snip#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClientSideProvider_snip/CSharp/CSProviderProgram.cs#101)]
 [!code-vb[UIAClientSideProvider_snip#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClientSideProvider_snip/visualbasic/csproviderprogram.vb#101)]  
  
## <a name="see-also"></a><span data-ttu-id="f9848-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9848-109">See Also</span></span>  
 [<span data-ttu-id="f9848-110">Übersicht über die Benutzeroberflächenautomatisierungs-Anbieter</span><span class="sxs-lookup"><span data-stu-id="f9848-110">UI Automation Providers Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [<span data-ttu-id="f9848-111">Registrieren einer clientseitigen Anbieterassembly</span><span class="sxs-lookup"><span data-stu-id="f9848-111">Register a Client-Side Provider Assembly</span></span>](../../../docs/framework/ui-automation/register-a-client-side-provider-assembly.md)
