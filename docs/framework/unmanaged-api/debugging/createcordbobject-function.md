---
title: CreateCordbObject-Funktion
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f546d7707c40f7f26a46177ae972a988e54e1e45
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487862"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="84db4-102">CreateCordbObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="84db4-102">CreateCordbObject Function</span></span>
<span data-ttu-id="84db4-103">Erstellt eine Debugschnittstelle ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)), die Funktionen zum Instanziieren einer verwalteten Debugsitzung für einen Remoteprozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="84db4-103">Creates a debugger interface ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84db4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84db4-104">Syntax</span></span>  
  
```  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84db4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84db4-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="84db4-106">[in] Debuggerversion des Zielprozesses.</span><span class="sxs-lookup"><span data-stu-id="84db4-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="84db4-107">Dieser Parameter muss CorDebugVersion_2_0 für das Remotedebuggen sein.</span><span class="sxs-lookup"><span data-stu-id="84db4-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="84db4-108">[out] Zeiger auf einen Zeiger auf ein Objekt, das in umgewandelt werden, wird ein [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Schnittstelle und zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="84db4-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84db4-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="84db4-109">Return Value</span></span>  
 <span data-ttu-id="84db4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="84db4-110">S_OK</span></span>  
 <span data-ttu-id="84db4-111">Die Anzahl der CLRs im Prozess wurde erfolgreich ermittelt, und das entsprechende Handle und die Pfadarrays wurden ordnungsgemäß aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="84db4-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="84db4-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="84db4-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="84db4-113">`ppCordb` ist NULL, oder `iDebuggerVersion` ist nicht CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="84db4-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="84db4-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="84db4-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="84db4-115">Für `ppCordb` kann nicht genug Arbeitspeicher zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="84db4-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="84db4-116">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="84db4-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="84db4-117">Andere Fehler.</span><span class="sxs-lookup"><span data-stu-id="84db4-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84db4-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="84db4-118">Remarks</span></span>  
 <span data-ttu-id="84db4-119">Die [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) -Schnittstelle, die in zurückgegebenen `ppCordb` ist die Debugschnittstelle auf oberster Ebene, für alle Debugdienste verwalteten.</span><span class="sxs-lookup"><span data-stu-id="84db4-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84db4-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84db4-120">Requirements</span></span>  
 <span data-ttu-id="84db4-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84db4-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84db4-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="84db4-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="84db4-123">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="84db4-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="84db4-124">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="84db4-124">**.NET Framework Versions:** 3.5 SP1</span></span>
