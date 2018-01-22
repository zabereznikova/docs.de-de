---
title: 'Gewusst wie: Abrufen von Typ- und Memberinformationen aus einer Assembly'
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
- cpp
helpviewer_keywords:
- obtaining assembly information
- assemblies [.NET Framework], obtaining information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1c3112b7484e4d03eaacd218ff8e8ac34e77745b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-obtain-type-and-member-information-from-an-assembly"></a><span data-ttu-id="9687e-102">Gewusst wie: Abrufen von Typ- und Memberinformationen aus einer Assembly</span><span class="sxs-lookup"><span data-stu-id="9687e-102">How to: Obtain Type and Member Information from an Assembly</span></span>
<span data-ttu-id="9687e-103">Der <xref:System.Reflection>-Namespace enthält viele Methoden zum Abrufen von Informationen aus einer Assembly.</span><span class="sxs-lookup"><span data-stu-id="9687e-103">The <xref:System.Reflection> namespace contains many methods for obtaining information from an assembly.</span></span> <span data-ttu-id="9687e-104">In diesem Abschnitt wird eine dieser Methoden veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9687e-104">This section demonstrates one of these methods.</span></span> <span data-ttu-id="9687e-105">Weitere Informationen finden Sie unter [Reflection Overview (Übersicht über Reflektion)](../../../docs/framework/reflection-and-codedom/reflection.md).</span><span class="sxs-lookup"><span data-stu-id="9687e-105">For additional information, see [Reflection Overview](../../../docs/framework/reflection-and-codedom/reflection.md).</span></span>  
  
 <span data-ttu-id="9687e-106">In folgendem Beispiel werden Typ- und Memberinformationen aus einer Assembly abgerufen.</span><span class="sxs-lookup"><span data-stu-id="9687e-106">The following example obtains type and member information from an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9687e-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9687e-107">Example</span></span>  
 [!code-cpp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source6.cpp#8)]
 [!code-csharp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source6.cs#8)]
 [!code-vb[Conceptual.Types.ViewInfo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source6.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="9687e-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9687e-108">See Also</span></span>  
 [<span data-ttu-id="9687e-109">Programming with Application Domains (Programmieren mit Anwendungsdomänen)</span><span class="sxs-lookup"><span data-stu-id="9687e-109">Programming with Application Domains</span></span>](http://msdn.microsoft.com/library/bd36055b-56bd-43eb-b4d8-820c37172131)  
 [<span data-ttu-id="9687e-110">Reflektion</span><span class="sxs-lookup"><span data-stu-id="9687e-110">Reflection</span></span>](../../../docs/framework/reflection-and-codedom/reflection.md)  
 [<span data-ttu-id="9687e-111">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="9687e-111">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
