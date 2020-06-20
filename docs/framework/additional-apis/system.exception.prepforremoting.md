---
title: Exception. prepforremoting-Methode (System)
description: Überprüfen Sie die Exception. prepforremoting-Methode in .net. Die-Methode fügt der Nachricht die serverseitige Stapel Überwachung hinzu, bevor die Ausnahme erneut auf dem Client ausgelöst wird.
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 9ceb73499ae3bb308975e6db5b961bfe40165ba3
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105267"
---
# <a name="exceptionprepforremoting-method"></a><span data-ttu-id="96d3e-104">Exception.PrepForRemoting-Methode</span><span class="sxs-lookup"><span data-stu-id="96d3e-104">Exception.PrepForRemoting Method</span></span>

<span data-ttu-id="96d3e-105">Behält die serverseitige Stapel Überwachung bei, indem Sie an die Nachricht angehängt wird, bevor die Ausnahme erneut an der Client aufrufssite ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="96d3e-105">Preserves the server-side stack trace by appending it to the message before the exception is rethrown at the client call site.</span></span>

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a><span data-ttu-id="96d3e-106">Rückgabe</span><span class="sxs-lookup"><span data-stu-id="96d3e-106">Returns</span></span>

<xref:System.Exception>  
<span data-ttu-id="96d3e-107">Diese <xref:System.Exception>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="96d3e-107">This <xref:System.Exception> instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="96d3e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="96d3e-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="96d3e-109">Die `Exception.PrepForRemoting` Methode ist intern und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="96d3e-109">The `Exception.PrepForRemoting` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="96d3e-110">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="96d3e-110">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="96d3e-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="96d3e-111">Requirements</span></span>

<span data-ttu-id="96d3e-112">**Namespace:** <xref:System></span><span class="sxs-lookup"><span data-stu-id="96d3e-112">**Namespace:** <xref:System></span></span>

<span data-ttu-id="96d3e-113">**Assembly:** mscorlib.dll (in mscorlib.dll)</span><span class="sxs-lookup"><span data-stu-id="96d3e-113">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="96d3e-114">**.NET Framework Versionen:** Verfügbar seit 1,0.</span><span class="sxs-lookup"><span data-stu-id="96d3e-114">**.NET Framework versions:** Available since 1.0.</span></span>
