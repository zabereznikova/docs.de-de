---
title: Exception. prepforremoting-Methode (System)
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: ce1c24578690a1643b7f5af0e44eaae95ed7b0a2
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214897"
---
# <a name="exceptionprepforremoting-method"></a><span data-ttu-id="20f08-102">Exception.PrepForRemoting-Methode</span><span class="sxs-lookup"><span data-stu-id="20f08-102">Exception.PrepForRemoting Method</span></span>

<span data-ttu-id="20f08-103">Behält die serverseitige Stapel Überwachung bei, indem Sie an die Nachricht angehängt wird, bevor die Ausnahme erneut an der Client aufrufssite ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="20f08-103">Preserves the server-side stack trace by appending it to the message before the exception is rethrown at the client call site.</span></span>

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a><span data-ttu-id="20f08-104">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="20f08-104">Returns</span></span>

<xref:System.Exception>  
<span data-ttu-id="20f08-105">Diese <xref:System.Exception>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="20f08-105">This <xref:System.Exception> instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="20f08-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="20f08-106">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="20f08-107">Die `Exception.PrepForRemoting`-Methode ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="20f08-107">The `Exception.PrepForRemoting` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="20f08-108">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="20f08-108">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="20f08-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="20f08-109">Requirements</span></span>

<span data-ttu-id="20f08-110">**Namespace:** <xref:System></span><span class="sxs-lookup"><span data-stu-id="20f08-110">**Namespace:** <xref:System></span></span>

<span data-ttu-id="20f08-111">**Assembly:** mscorlib. dll (in "mscorlib. dll")</span><span class="sxs-lookup"><span data-stu-id="20f08-111">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="20f08-112">**.NET Framework Versionen:** Verfügbar seit 1,0.</span><span class="sxs-lookup"><span data-stu-id="20f08-112">**.NET Framework versions:** Available since 1.0.</span></span>
