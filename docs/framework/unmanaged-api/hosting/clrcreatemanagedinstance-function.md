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
ms.openlocfilehash: 7fbe0cf3e93d75749fa3f463f3f97dbd1bfe27a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176538"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="fc6cb-102">ClrCreateManagedInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="fc6cb-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="fc6cb-103">Erstellt eine Instanz des angegebenen verwalteten Typs.</span><span class="sxs-lookup"><span data-stu-id="fc6cb-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="fc6cb-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="fc6cb-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="fc6cb-105">Verwenden Sie die COM-Aktivierung, um eine Instanz des verwalteten Typs zu erstellen oder Das Hosting zu verwenden (siehe [CLR-Hostingschnittstellen, die in .NET Framework 4 und 4.5 hinzugefügt](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)wurden).</span><span class="sxs-lookup"><span data-stu-id="fc6cb-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc6cb-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc6cb-106">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc6cb-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="fc6cb-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="fc6cb-108">[in] Ein Zeiger auf den Namen des angeforderten Instanztyps.</span><span class="sxs-lookup"><span data-stu-id="fc6cb-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="fc6cb-109">[in] Der `IID` des angeforderten Instanztyps.</span><span class="sxs-lookup"><span data-stu-id="fc6cb-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="fc6cb-110">[out] Ein Zeiger auf einen Zeiger auf eine Instanz des verwalteten Typs, die vom Aufrufer angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="fc6cb-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc6cb-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fc6cb-111">Remarks</span></span>  
 <span data-ttu-id="fc6cb-112">Die Common Language Runtime sollte bereits in einen Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="fc6cb-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="fc6cb-113">Beispielsweise kann es über einen Aufruf der [CorBindToRuntimeEx-Funktion](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) geladen werden, bevor die `ClrCreateManagedInstance` Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fc6cb-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="fc6cb-114">Wenn die Laufzeit nicht `ClrCreateManagedInstance` geladen ist, versucht zuerst, v1.0.3705 der Laufzeit zu laden.</span><span class="sxs-lookup"><span data-stu-id="fc6cb-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="fc6cb-115">Wenn dies fehlschlägt, wird versucht, die neueste Version der Laufzeit zu laden.</span><span class="sxs-lookup"><span data-stu-id="fc6cb-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc6cb-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fc6cb-116">Requirements</span></span>  
 <span data-ttu-id="fc6cb-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc6cb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc6cb-118">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fc6cb-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fc6cb-119">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fc6cb-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fc6cb-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc6cb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc6cb-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc6cb-121">See also</span></span>

- [<span data-ttu-id="fc6cb-122">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="fc6cb-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="fc6cb-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="fc6cb-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
