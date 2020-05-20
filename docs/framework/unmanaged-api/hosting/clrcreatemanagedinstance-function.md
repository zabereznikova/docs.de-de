---
title: ClrCreateManagedInstance-Funktion
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
ms.openlocfilehash: ecd618ecf08836ea5e38ce738f97fc91ee6426f4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616813"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="3c0e0-102">ClrCreateManagedInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="3c0e0-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="3c0e0-103">Erstellt eine Instanz des angegebenen verwalteten Typs.</span><span class="sxs-lookup"><span data-stu-id="3c0e0-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="3c0e0-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="3c0e0-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="3c0e0-105">Verwenden Sie die COM-Aktivierung, um eine Instanz des verwalteten Typs zu erstellen, oder verwenden Sie das Hosting (siehe [CLR-Hostingschnittstellen, die im .NET Framework 4 und 4,5 hinzugefügt](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)wurden)</span><span class="sxs-lookup"><span data-stu-id="3c0e0-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c0e0-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c0e0-106">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c0e0-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="3c0e0-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="3c0e0-108">in Ein Zeiger auf den Namen des angeforderten Instanztyps.</span><span class="sxs-lookup"><span data-stu-id="3c0e0-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="3c0e0-109">in Der `IID` des angefragten Instanztyps.</span><span class="sxs-lookup"><span data-stu-id="3c0e0-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="3c0e0-110">vorgenommen Ein Zeiger auf einen Zeiger auf eine Instanz des verwalteten Typs, der vom Aufrufer angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="3c0e0-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c0e0-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c0e0-111">Remarks</span></span>  
 <span data-ttu-id="3c0e0-112">Die Common Language Runtime sollte bereits in einen Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="3c0e0-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="3c0e0-113">Beispielsweise kann Sie mithilfe eines Aufrufs der [CorBindToRuntimeEx](corbindtoruntimeex-function.md) -Funktion geladen werden, bevor die- `ClrCreateManagedInstance` Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="3c0e0-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="3c0e0-114">Wenn die Laufzeit nicht geladen ist, `ClrCreateManagedInstance` versucht zuerst, die v-1.0.3705 der Laufzeit zu laden.</span><span class="sxs-lookup"><span data-stu-id="3c0e0-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="3c0e0-115">Wenn dies nicht möglich ist, wird versucht, die neueste Version der Laufzeit zu laden.</span><span class="sxs-lookup"><span data-stu-id="3c0e0-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c0e0-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3c0e0-116">Requirements</span></span>  
 <span data-ttu-id="3c0e0-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c0e0-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c0e0-118">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="3c0e0-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3c0e0-119">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3c0e0-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c0e0-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c0e0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c0e0-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c0e0-121">See also</span></span>

- [<span data-ttu-id="3c0e0-122">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="3c0e0-122">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="3c0e0-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="3c0e0-123">Hosting</span></span>](index.md)
