---
title: "Gewusst wie: Erstellen einer Anwendungsdomäne"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cdbab5e43d2af7608c4d8322eb071baf591e18d5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-an-application-domain"></a><span data-ttu-id="46761-102">Gewusst wie: Erstellen einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="46761-102">How to: Create an Application Domain</span></span>
<span data-ttu-id="46761-103">Ein Common Language Runtime-Host erstellt automatisch Anwendungsdomänen, wenn sie gebraucht werden.</span><span class="sxs-lookup"><span data-stu-id="46761-103">A common language runtime host creates application domains automatically when they are needed.</span></span> <span data-ttu-id="46761-104">Jedoch können Sie eigene Anwendungsdomänen erstellen und sie in die Assemblys laden, die Sie persönlich verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="46761-104">However, you can create your own application domains and load into them those assemblies that you want to manage personally.</span></span> <span data-ttu-id="46761-105">Sie können auch Anwendungsdomänen erstellen, in denen Sie Code ausführen.</span><span class="sxs-lookup"><span data-stu-id="46761-105">You can also create application domains from which you execute code.</span></span>  
  
 <span data-ttu-id="46761-106">Sie erstellen eine neue Anwendungsdomäne mit einer der überladenen **CreateDomain**-Methoden in der <xref:System.AppDomain?displayProperty=nameWithType>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="46761-106">You create a new application domain using one of the overloaded **CreateDomain** methods in the <xref:System.AppDomain?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="46761-107">Sie können der Anwendungsdomäne einen Namen geben und auf sie mit diesem Namen verweisen.</span><span class="sxs-lookup"><span data-stu-id="46761-107">You can give the application domain a name and reference it by that name.</span></span>  
  
 <span data-ttu-id="46761-108">In folgendem Beispiel wird eine neue Anwendungsdomäne erstellt, weist ihr den Namen `MyDomain` zu, und gibt dann den Namen der Hostdomäne und der neu erstellte untergeordneten Anwendungsdomäne in der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="46761-108">The following example creates a new application domain, assigns it the name `MyDomain`, and then prints the name of the host domain and the newly created child application domain to the console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46761-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46761-109">Example</span></span>  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="46761-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46761-110">See Also</span></span>  
 [<span data-ttu-id="46761-111">Programming with Application Domains (Programmieren mit Anwendungsdomänen)</span><span class="sxs-lookup"><span data-stu-id="46761-111">Programming with Application Domains</span></span>](http://msdn.microsoft.com/library/bd36055b-56bd-43eb-b4d8-820c37172131)  
 [<span data-ttu-id="46761-112">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="46761-112">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
