---
title: 'Vorgehensweise: Abrufen von Typ- und Memberinformationen mithilfe von Reflektion'
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
author: rpetrusha
ms.author: ronpet
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: da71845ea276267220636cfd661465ea02b2b50d
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972858"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a><span data-ttu-id="57460-102">Vorgehensweise: Abrufen von Typ- und Memberinformationen mithilfe von Reflektion</span><span class="sxs-lookup"><span data-stu-id="57460-102">How to: Get type and member information by using reflection</span></span>
<span data-ttu-id="57460-103">Der <xref:System.Reflection>-Namespace enthält viele Methoden zum Abrufen von Informationen zu Typen und deren Membern.</span><span class="sxs-lookup"><span data-stu-id="57460-103">The <xref:System.Reflection> namespace contains many methods for obtaining information about types and their members.</span></span> <span data-ttu-id="57460-104">In diesem Artikel wird eine dieser Methoden, nämlich <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>, veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="57460-104">This article demonstrates one of these methods, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="57460-105">Weitere Informationen finden Sie unter [Übersicht über Reflektion](reflection.md).</span><span class="sxs-lookup"><span data-stu-id="57460-105">For additional information, see [Reflection overview](reflection.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="57460-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="57460-106">Example</span></span>

<span data-ttu-id="57460-107">In folgendem Beispiel werden mithilfe von Reflektion Typ- und Memberinformationen aus einer Assembly abgerufen:</span><span class="sxs-lookup"><span data-stu-id="57460-107">The following example obtains type and member information by using reflection:</span></span>

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a><span data-ttu-id="57460-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57460-108">See also</span></span>

- [<span data-ttu-id="57460-109">Programmieren mit Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="57460-109">Program with application domains</span></span>](../app-domains/application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="57460-110">Reflexion</span><span class="sxs-lookup"><span data-stu-id="57460-110">Reflection</span></span>](reflection.md)
- [<span data-ttu-id="57460-111">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="57460-111">Use application domains</span></span>](../app-domains/use.md)
