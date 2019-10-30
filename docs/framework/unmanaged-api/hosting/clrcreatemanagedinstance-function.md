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
ms.openlocfilehash: 4e672030ae83b57da6f9ab66630513d79f28b8f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131990"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="86ea6-102">ClrCreateManagedInstance-Funktion</span><span class="sxs-lookup"><span data-stu-id="86ea6-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="86ea6-103">Erstellt eine Instanz des angegebenen verwalteten Typs.</span><span class="sxs-lookup"><span data-stu-id="86ea6-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="86ea6-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="86ea6-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="86ea6-105">Verwenden Sie die COM-Aktivierung, um eine Instanz des verwalteten Typs zu erstellen, oder verwenden Sie das Hosting (siehe [CLR-Hostingschnittstellen, die im .NET Framework 4 und 4,5 hinzugefügt](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)wurden)</span><span class="sxs-lookup"><span data-stu-id="86ea6-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86ea6-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="86ea6-106">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86ea6-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="86ea6-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="86ea6-108">in Ein Zeiger auf den Namen des angeforderten Instanztyps.</span><span class="sxs-lookup"><span data-stu-id="86ea6-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="86ea6-109">in Die `IID` des angeforderten Instanztyps.</span><span class="sxs-lookup"><span data-stu-id="86ea6-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="86ea6-110">vorgenommen Ein Zeiger auf einen Zeiger auf eine Instanz des verwalteten Typs, der vom Aufrufer angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="86ea6-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86ea6-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="86ea6-111">Remarks</span></span>  
 <span data-ttu-id="86ea6-112">Die Common Language Runtime sollte bereits in einen Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="86ea6-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="86ea6-113">Beispielsweise kann Sie mithilfe eines Aufrufs der [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) -Funktion geladen werden, bevor die `ClrCreateManagedInstance`-Funktion aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="86ea6-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="86ea6-114">Wenn die Laufzeit nicht geladen wird, versucht `ClrCreateManagedInstance` zuerst, die v-1.0.3705 der Laufzeit zu laden.</span><span class="sxs-lookup"><span data-stu-id="86ea6-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="86ea6-115">Wenn dies nicht möglich ist, wird versucht, die neueste Version der Laufzeit zu laden.</span><span class="sxs-lookup"><span data-stu-id="86ea6-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86ea6-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="86ea6-116">Requirements</span></span>  
 <span data-ttu-id="86ea6-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86ea6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86ea6-118">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="86ea6-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="86ea6-119">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="86ea6-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86ea6-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86ea6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86ea6-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86ea6-121">See also</span></span>

- [<span data-ttu-id="86ea6-122">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="86ea6-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="86ea6-123">Hosting</span><span class="sxs-lookup"><span data-stu-id="86ea6-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
