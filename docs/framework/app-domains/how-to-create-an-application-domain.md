---
title: 'Vorgehensweise: Erstellen einer Anwendungsdomäne'
description: Hier erfahren Sie, wie Sie eine Anwendungsdomäne in .NET erstellen. Sie können eine Anwendungsdomäne zum Laden von Assemblys erstellen, die persönlich verwaltet werden, oder Sie erstellen eine Anwendungsdomäne, um Code auszuführen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
ms.openlocfilehash: 8e44e682f64854dbc0181b26f6ed3fa2905b7814
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104800"
---
# <a name="how-to-create-an-application-domain"></a><span data-ttu-id="8a662-104">Vorgehensweise: Erstellen einer Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="8a662-104">How to: Create an Application Domain</span></span>
<span data-ttu-id="8a662-105">Ein Common Language Runtime-Host erstellt automatisch Anwendungsdomänen, wenn sie gebraucht werden.</span><span class="sxs-lookup"><span data-stu-id="8a662-105">A common language runtime host creates application domains automatically when they are needed.</span></span> <span data-ttu-id="8a662-106">Jedoch können Sie eigene Anwendungsdomänen erstellen und sie in die Assemblys laden, die Sie persönlich verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="8a662-106">However, you can create your own application domains and load into them those assemblies that you want to manage personally.</span></span> <span data-ttu-id="8a662-107">Sie können auch Anwendungsdomänen erstellen, in denen Sie Code ausführen.</span><span class="sxs-lookup"><span data-stu-id="8a662-107">You can also create application domains from which you execute code.</span></span>  
  
 <span data-ttu-id="8a662-108">Sie erstellen eine neue Anwendungsdomäne mit einer der überladenen **CreateDomain**-Methoden in der <xref:System.AppDomain?displayProperty=nameWithType>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="8a662-108">You create a new application domain using one of the overloaded **CreateDomain** methods in the <xref:System.AppDomain?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="8a662-109">Sie können der Anwendungsdomäne einen Namen geben und auf sie mit diesem Namen verweisen.</span><span class="sxs-lookup"><span data-stu-id="8a662-109">You can give the application domain a name and reference it by that name.</span></span>  
  
 <span data-ttu-id="8a662-110">In folgendem Beispiel wird eine neue Anwendungsdomäne erstellt, weist ihr den Namen `MyDomain` zu, und gibt dann den Namen der Hostdomäne und der neu erstellte untergeordneten Anwendungsdomäne in der Konsole aus.</span><span class="sxs-lookup"><span data-stu-id="8a662-110">The following example creates a new application domain, assigns it the name `MyDomain`, and then prints the name of the host domain and the newly created child application domain to the console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a662-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8a662-111">Example</span></span>  
 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="8a662-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a662-112">See also</span></span>

- [<span data-ttu-id="8a662-113">Programming with Application Domains (Programmieren mit Anwendungsdomänen)</span><span class="sxs-lookup"><span data-stu-id="8a662-113">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="8a662-114">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="8a662-114">Using Application Domains</span></span>](use.md)
