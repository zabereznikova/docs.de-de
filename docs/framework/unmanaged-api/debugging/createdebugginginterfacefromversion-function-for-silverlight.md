---
title: "CreateDebuggingInterfaceFromVersion-Funktion für Silverlight"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c38171c5887bb207b3692e9fa92aa2be2bc72a27
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="dd0c9-102">CreateDebuggingInterfaceFromVersion-Funktion für Silverlight</span><span class="sxs-lookup"><span data-stu-id="dd0c9-102">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>
<span data-ttu-id="dd0c9-103">Akzeptiert eine common Language Runtime (CLR) Version-Zeichenfolge, die von zurückgegeben wird das [CreateVersionStringFromModule-Funktion](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md), und gibt eine entsprechende Debuggerschnittstelle zurück (in der Regel [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="dd0c9-103">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd0c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd0c9-104">Syntax</span></span>  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dd0c9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dd0c9-105">Parameters</span></span>  
 `szDebuggeeVersion`  
 <span data-ttu-id="dd0c9-106">[in] Die Versionszeichenfolge der CLR in der zu debuggenden Zielkomponente, die von zurückgegeben wird das [CreateVersionStringFromModule-Funktion](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md).</span><span class="sxs-lookup"><span data-stu-id="dd0c9-106">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="dd0c9-107">Zeiger auf einen Zeiger auf ein COM-Objekt (`IUnknown`).</span><span class="sxs-lookup"><span data-stu-id="dd0c9-107">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="dd0c9-108">Dieses Objekt wird umgewandelt werden, um eine [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Objekt, bevor sie zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-108">This object will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd0c9-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dd0c9-109">Return Value</span></span>  
 <span data-ttu-id="dd0c9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd0c9-110">S_OK</span></span>  
 <span data-ttu-id="dd0c9-111">`ppCordb`verweist auf ein gültiges Objekt, das die [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-111">`ppCordb` references a valid object that implements the [ICorDebug interface](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface.</span></span>  
  
 <span data-ttu-id="dd0c9-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="dd0c9-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="dd0c9-113">Entweder `szDebuggeeVersion` oder `ppCordb` ist null.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-113">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 <span data-ttu-id="dd0c9-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span><span class="sxs-lookup"><span data-stu-id="dd0c9-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span></span>  
 <span data-ttu-id="dd0c9-115">Eine für das CLR-Debuggen erforderliche Komponente kann nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-115">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="dd0c9-116">Dies bedeutet, dass entweder mscordbi.dll oder mscordaccore.dll nicht im selben Verzeichnis wie die Ziel-CoreCLR.dll gefunden wurde.
</span><span class="sxs-lookup"><span data-stu-id="dd0c9-116">This means that either mscordbi.dll or mscordaccore.dll was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="dd0c9-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span><span class="sxs-lookup"><span data-stu-id="dd0c9-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span></span>  
 <span data-ttu-id="dd0c9-118">Entweder mscordbi.dll oder mscordaccore.dll haben nicht dieselbe Version wie die Ziel-CoreCLR.dll.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-118">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="dd0c9-119">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="dd0c9-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="dd0c9-120">Zurückgeben kann ein [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md).</span><span class="sxs-lookup"><span data-stu-id="dd0c9-120">Unable to return an [ICorDebug interface](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd0c9-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dd0c9-121">Remarks</span></span>  
 <span data-ttu-id="dd0c9-122">Die zurückgegebene Schnittstelle stellt die Funktionen zum Anfügen an eine CLR in einem Zielprozess und zum Debuggen von verwaltetem Code bereit, der von der CLR ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dd0c9-122">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd0c9-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dd0c9-123">Requirements</span></span>  
 <span data-ttu-id="dd0c9-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd0c9-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd0c9-125">**Header:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="dd0c9-125">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="dd0c9-126">**Bibliothek:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="dd0c9-126">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="dd0c9-127">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="dd0c9-127">**.NET Framework Versions:** 3.5 SP1</span></span>
