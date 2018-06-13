---
title: 'Gewusst wie: Abrufen von Typ- und Memberinformationen aus einer Assembly'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- obtaining assembly information
- assemblies [.NET Framework], obtaining information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fb06555f18c13f87347a5a76e6f4a3060777f02
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744066"
---
# <a name="how-to-obtain-type-and-member-information-from-an-assembly"></a><span data-ttu-id="21edd-102">Gewusst wie: Abrufen von Typ- und Memberinformationen aus einer Assembly</span><span class="sxs-lookup"><span data-stu-id="21edd-102">How to: Obtain Type and Member Information from an Assembly</span></span>
<span data-ttu-id="21edd-103">Der <xref:System.Reflection>-Namespace enthält viele Methoden zum Abrufen von Informationen aus einer Assembly.</span><span class="sxs-lookup"><span data-stu-id="21edd-103">The <xref:System.Reflection> namespace contains many methods for obtaining information from an assembly.</span></span> <span data-ttu-id="21edd-104">In diesem Abschnitt wird eine dieser Methoden veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="21edd-104">This section demonstrates one of these methods.</span></span> <span data-ttu-id="21edd-105">Weitere Informationen finden Sie unter [Reflection Overview (Übersicht über Reflektion)](../../../docs/framework/reflection-and-codedom/reflection.md).</span><span class="sxs-lookup"><span data-stu-id="21edd-105">For additional information, see [Reflection Overview](../../../docs/framework/reflection-and-codedom/reflection.md).</span></span>  
  
 <span data-ttu-id="21edd-106">In folgendem Beispiel werden Typ- und Memberinformationen aus einer Assembly abgerufen.</span><span class="sxs-lookup"><span data-stu-id="21edd-106">The following example obtains type and member information from an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21edd-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21edd-107">Example</span></span>  
 [!code-cpp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source6.cpp#8)]
 [!code-csharp[Conceptual.Types.ViewInfo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source6.cs#8)]
 [!code-vb[Conceptual.Types.ViewInfo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source6.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="21edd-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21edd-108">See Also</span></span>  
 <span data-ttu-id="21edd-109">[Programming with Application Domains (Programmieren mit Anwendungsdomänen)](./application-domains.md#programming-with-application-domains) [Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md)</span><span class="sxs-lookup"><span data-stu-id="21edd-109">[Programming with Application Domains](./application-domains.md#programming-with-application-domains) [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md)</span></span>  
 [<span data-ttu-id="21edd-110">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="21edd-110">Using Application Domains</span></span>](../../../docs/framework/app-domains/use.md)
