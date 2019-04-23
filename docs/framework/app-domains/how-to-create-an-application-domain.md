---
title: 'Vorgehensweise: Erstellen einer Anwendungsdomäne'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff85f5737babb73d87f4918ca0f4981263f7dadc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166750"
---
# <a name="how-to-create-an-application-domain"></a><span data-ttu-id="cdd96-102">Vorgehensweise: Erstellen einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="cdd96-102">How to: Create an Application Domain</span></span>
<span data-ttu-id="cdd96-103">Ein Common Language Runtime-Host erstellt automatisch Anwendungsdomänen, wenn sie gebraucht werden.</span><span class="sxs-lookup"><span data-stu-id="cdd96-103">A common language runtime host creates application domains automatically when they are needed.</span></span> <span data-ttu-id="cdd96-104">Jedoch können Sie eigene Anwendungsdomänen erstellen und sie in die Assemblys laden, die Sie persönlich verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="cdd96-104">However, you can create your own application domains and load into them those assemblies that you want to manage personally.</span></span> <span data-ttu-id="cdd96-105">Sie können auch Anwendungsdomänen erstellen, in denen Sie Code ausführen.</span><span class="sxs-lookup"><span data-stu-id="cdd96-105">You can also create application domains from which you execute code.</span></span>  
  
 <span data-ttu-id="cdd96-106">Sie erstellen eine neue Anwendungsdomäne mit einer der überladenen **CreateDomain**-Methoden in der <xref:System.AppDomain?displayProperty=nameWithType>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="cdd96-106">You create a new application domain using one of the overloaded **CreateDomain** methods in the <xref:System.AppDomain?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="cdd96-107">Sie können der Anwendungsdomäne einen Namen geben und auf sie mit diesem Namen verweisen.</span><span class="sxs-lookup"><span data-stu-id="cdd96-107">You can give the application domain a name and reference it by that name.</span></span>  
  
 <span data-ttu-id="cdd96-108">In folgendem Beispiel wird eine neue Anwendungsdomäne erstellt, weist ihr den Namen `MyDomain` zu, und gibt dann den Namen der Hostdomäne und der neu erstellte untergeordneten Anwendungsdomäne in der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="cdd96-108">The following example creates a new application domain, assigns it the name `MyDomain`, and then prints the name of the host domain and the newly created child application domain to the console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdd96-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cdd96-109">Example</span></span>  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="cdd96-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cdd96-110">See also</span></span>

- [<span data-ttu-id="cdd96-111">Programming with Application Domains (Programmieren mit Anwendungsdomänen)</span><span class="sxs-lookup"><span data-stu-id="cdd96-111">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="cdd96-112">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="cdd96-112">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
