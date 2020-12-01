---
title: 'Vorgehensweise: Abrufen von Typ- und Memberinformationen mithilfe von Reflektion'
description: Hier erfahren Sie, wie Sie mit der Reflexion mithilfe des System.Reflection-Namespace Informationen zum Typ und Member erhalten.
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: 771917bb2ae5cae56c775ae23119d5eda9701df1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266323"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a><span data-ttu-id="de1ac-103">Vorgehensweise: Abrufen von Typ- und Memberinformationen mithilfe von Reflektion</span><span class="sxs-lookup"><span data-stu-id="de1ac-103">How to: Get type and member information by using reflection</span></span>

<span data-ttu-id="de1ac-104">Der <xref:System.Reflection>-Namespace enthält viele Methoden zum Abrufen von Informationen zu Typen und deren Membern.</span><span class="sxs-lookup"><span data-stu-id="de1ac-104">The <xref:System.Reflection> namespace contains many methods for obtaining information about types and their members.</span></span> <span data-ttu-id="de1ac-105">In diesem Artikel wird eine dieser Methoden, nämlich <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>, veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="de1ac-105">This article demonstrates one of these methods, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="de1ac-106">Weitere Informationen finden Sie unter [Übersicht über Reflektion](reflection.md).</span><span class="sxs-lookup"><span data-stu-id="de1ac-106">For additional information, see [Reflection overview](reflection.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="de1ac-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="de1ac-107">Example</span></span>

<span data-ttu-id="de1ac-108">In folgendem Beispiel werden mithilfe von Reflektion Typ- und Memberinformationen aus einer Assembly abgerufen:</span><span class="sxs-lookup"><span data-stu-id="de1ac-108">The following example obtains type and member information by using reflection:</span></span>

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a><span data-ttu-id="de1ac-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de1ac-109">See also</span></span>

- [<span data-ttu-id="de1ac-110">Programmieren mit Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="de1ac-110">Program with application domains</span></span>](../app-domains/application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="de1ac-111">Reflexion</span><span class="sxs-lookup"><span data-stu-id="de1ac-111">Reflection</span></span>](reflection.md)
- [<span data-ttu-id="de1ac-112">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="de1ac-112">Use application domains</span></span>](../app-domains/use.md)
