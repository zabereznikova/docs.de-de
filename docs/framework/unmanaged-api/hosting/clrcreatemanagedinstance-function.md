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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1ae530b8488dcd375e91058a227316dd38cf4ab
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779162"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="71042-102">ClrCreateManagedInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="71042-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="71042-103">Erstellt eine Instanz des angegebenen verwalteten Typs.</span><span class="sxs-lookup"><span data-stu-id="71042-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="71042-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="71042-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="71042-105">Verwenden Sie COM-Aktivierung zum Erstellen einer Instanz des verwalteten Typs oder -hosting (finden Sie unter [CLR Hosten von Schnittstellen hinzugefügt, in .NET Framework 4 und 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span><span class="sxs-lookup"><span data-stu-id="71042-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71042-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="71042-106">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71042-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="71042-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="71042-108">[in] Ein Zeiger auf den Namen des Instanztyps angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="71042-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="71042-109">[in] Die `IID` des Instanztyps angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="71042-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="71042-110">[out] Ein Zeiger auf einen Zeiger auf eine Instanz des verwalteten Typs, der vom Aufrufer angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="71042-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71042-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71042-111">Remarks</span></span>  
 <span data-ttu-id="71042-112">Die common Language Runtime sollte bereits in einen Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="71042-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="71042-113">Sie können z. B. geladen werden, mithilfe eines Aufrufs an die [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) funktionieren, bevor Sie die `ClrCreateManagedInstance` Funktion wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="71042-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="71042-114">Wenn die Laufzeit nicht geladen wurde, `ClrCreateManagedInstance` versucht zuerst, Version 1.0.3705 der Laufzeit zu laden.</span><span class="sxs-lookup"><span data-stu-id="71042-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="71042-115">Wenn dies fehlschlägt, versucht, die neueste Version der Laufzeit zu laden.</span><span class="sxs-lookup"><span data-stu-id="71042-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71042-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="71042-116">Requirements</span></span>  
 <span data-ttu-id="71042-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71042-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71042-118">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="71042-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71042-119">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="71042-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71042-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71042-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71042-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71042-121">See also</span></span>

- [<span data-ttu-id="71042-122">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="71042-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="71042-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="71042-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
