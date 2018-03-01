---
title: CreateCordbObject-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7007e541e9999e0cb14a83845eb28d71336b3ff6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="createcordbobject-function"></a><span data-ttu-id="ff3ea-102">CreateCordbObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="ff3ea-102">CreateCordbObject Function</span></span>
<span data-ttu-id="ff3ea-103">Erstellt eine Debugschnittstelle ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)), die Funktionen zum Instanziieren einer verwalteten Debugsitzung für einen Remoteprozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ff3ea-103">Creates a debugger interface ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff3ea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff3ea-104">Syntax</span></span>  
  
```  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff3ea-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ff3ea-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="ff3ea-106">[in] Debuggerversion des Zielprozesses.</span><span class="sxs-lookup"><span data-stu-id="ff3ea-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="ff3ea-107">Dieser Parameter muss CorDebugVersion_2_0 für das Remotedebuggen sein.</span><span class="sxs-lookup"><span data-stu-id="ff3ea-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="ff3ea-108">[out] Zeiger auf einen Zeiger auf ein Objekt, das in umgewandelt werden, wird ein [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Schnittstelle und zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ff3ea-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff3ea-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ff3ea-109">Return Value</span></span>  
 <span data-ttu-id="ff3ea-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff3ea-110">S_OK</span></span>  
 <span data-ttu-id="ff3ea-111">Die Anzahl der CLRs im Prozess wurde erfolgreich ermittelt, und das entsprechende Handle und die Pfadarrays wurden ordnungsgemäß aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="ff3ea-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="ff3ea-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ff3ea-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="ff3ea-113">`ppCordb` ist NULL, oder `iDebuggerVersion` ist nicht CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="ff3ea-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="ff3ea-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ff3ea-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="ff3ea-115">Für `ppCordb` kann nicht genug Arbeitspeicher zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="ff3ea-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="ff3ea-116">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="ff3ea-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="ff3ea-117">Andere Fehler.</span><span class="sxs-lookup"><span data-stu-id="ff3ea-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff3ea-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff3ea-118">Remarks</span></span>  
 <span data-ttu-id="ff3ea-119">Die [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) -Schnittstelle, die im zurückgegebenen `ppCordb` ist die Debugschnittstelle auf oberster Ebene für alle Debugdienste verwalteten.</span><span class="sxs-lookup"><span data-stu-id="ff3ea-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff3ea-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ff3ea-120">Requirements</span></span>  
 <span data-ttu-id="ff3ea-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff3ea-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff3ea-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="ff3ea-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="ff3ea-123">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="ff3ea-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="ff3ea-124">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ff3ea-124">**.NET Framework Versions:** 3.5 SP1</span></span>
