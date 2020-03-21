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
ms.openlocfilehash: 2716adcc8c79c8003202561ea2011c2469a6bc5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179232"
---
# <a name="createcordbobject-function"></a><span data-ttu-id="a06ca-102">CreateCordbObject-Funktion</span><span class="sxs-lookup"><span data-stu-id="a06ca-102">CreateCordbObject Function</span></span>
<span data-ttu-id="a06ca-103">Erstellt eine Debuggerschnittstelle ([ICorDebug](icordebug-interface.md)), die Funktionen zum Instanziieren einer verwalteten Debugsitzung für einen Remoteprozess bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a06ca-103">Creates a debugger interface ([ICorDebug](icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a06ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a06ca-104">Syntax</span></span>  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a06ca-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a06ca-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="a06ca-106">[in] Debuggerversion des Zielprozesses.</span><span class="sxs-lookup"><span data-stu-id="a06ca-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="a06ca-107">Dieser Parameter muss CorDebugVersion_2_0 für das Remotedebuggen sein.</span><span class="sxs-lookup"><span data-stu-id="a06ca-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="a06ca-108">[out] Zeiger auf einen Zeiger auf ein Objekt, das in eine [ICorDebug-Schnittstelle](icordebug-interface.md) zurückgeworfen und zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a06ca-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a06ca-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a06ca-109">Return Value</span></span>  
 <span data-ttu-id="a06ca-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a06ca-110">S_OK</span></span>  
 <span data-ttu-id="a06ca-111">Die Anzahl der CLRs im Prozess wurde erfolgreich ermittelt, und das entsprechende Handle und die Pfadarrays wurden ordnungsgemäß aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="a06ca-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="a06ca-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a06ca-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="a06ca-113">`ppCordb` ist NULL, oder `iDebuggerVersion` ist nicht CorDebugVersion_2_0.</span><span class="sxs-lookup"><span data-stu-id="a06ca-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="a06ca-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a06ca-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="a06ca-115">Für `ppCordb` kann nicht genug Arbeitspeicher zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a06ca-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="a06ca-116">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="a06ca-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="a06ca-117">Andere Fehler.</span><span class="sxs-lookup"><span data-stu-id="a06ca-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a06ca-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a06ca-118">Remarks</span></span>  
 <span data-ttu-id="a06ca-119">Die [ICorDebug-Schnittstelle,](icordebug-interface.md) `ppCordb` die zurückgegeben wird, ist die Debugging-Schnittstelle der obersten Ebene für alle verwalteten Debugdienstdienste.</span><span class="sxs-lookup"><span data-stu-id="a06ca-119">The [ICorDebug](icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a06ca-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a06ca-120">Requirements</span></span>  
 <span data-ttu-id="a06ca-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a06ca-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a06ca-122">**Kopfzeile:** CoreClrRemoteDebuggingSchnittstellen.h</span><span class="sxs-lookup"><span data-stu-id="a06ca-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="a06ca-123">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="a06ca-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="a06ca-124">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="a06ca-124">**.NET Framework Versions:** 3.5 SP1</span></span>
