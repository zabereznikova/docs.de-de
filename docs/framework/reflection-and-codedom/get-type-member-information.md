---
title: 'Gewusst wie: Abgleichen von Typ-und Element Informationen mithilfe von Reflektion'
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: 9ffc173bbd0ed12eedea0c191f6d39baf181793a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130213"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a><span data-ttu-id="2ac0b-102">Gewusst wie: Abgleichen von Typ-und Element Informationen mithilfe von Reflektion</span><span class="sxs-lookup"><span data-stu-id="2ac0b-102">How to: Get type and member information by using reflection</span></span>
<span data-ttu-id="2ac0b-103">Der <xref:System.Reflection>-Namespace enthält viele Methoden zum Abrufen von Informationen zu Typen und deren Membern.</span><span class="sxs-lookup"><span data-stu-id="2ac0b-103">The <xref:System.Reflection> namespace contains many methods for obtaining information about types and their members.</span></span> <span data-ttu-id="2ac0b-104">In diesem Artikel wird eine dieser Methoden, nämlich <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>, veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2ac0b-104">This article demonstrates one of these methods, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2ac0b-105">Weitere Informationen finden Sie unter [Übersicht über Reflektion](reflection.md).</span><span class="sxs-lookup"><span data-stu-id="2ac0b-105">For additional information, see [Reflection overview](reflection.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="2ac0b-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ac0b-106">Example</span></span>

<span data-ttu-id="2ac0b-107">In folgendem Beispiel werden mithilfe von Reflektion Typ- und Memberinformationen aus einer Assembly abgerufen:</span><span class="sxs-lookup"><span data-stu-id="2ac0b-107">The following example obtains type and member information by using reflection:</span></span>

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a><span data-ttu-id="2ac0b-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ac0b-108">See also</span></span>

- [<span data-ttu-id="2ac0b-109">Programmieren mit Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="2ac0b-109">Program with application domains</span></span>](../app-domains/application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="2ac0b-110">Reflektion</span><span class="sxs-lookup"><span data-stu-id="2ac0b-110">Reflection</span></span>](reflection.md)
- [<span data-ttu-id="2ac0b-111">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="2ac0b-111">Use application domains</span></span>](../app-domains/use.md)
