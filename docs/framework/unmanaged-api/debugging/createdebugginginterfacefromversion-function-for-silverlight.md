---
title: CreateDebuggingInterfaceFromVersion-Funktion für Silverlight
ms.date: 03/30/2017
f1_keywords:
- CreateDebuggingInterfaceFromVersion
helpviewer_keywords:
- CreateDebuggingInterfaceFromVersion function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 35c7a18f-133a-4584-bd25-bb338568b0c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53571268391011cc1dc0ff112d484e1fa140057f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407713"
---
# <a name="createdebugginginterfacefromversion-function-for-silverlight"></a><span data-ttu-id="3e960-102">CreateDebuggingInterfaceFromVersion-Funktion für Silverlight</span><span class="sxs-lookup"><span data-stu-id="3e960-102">CreateDebuggingInterfaceFromVersion Function for Silverlight</span></span>
<span data-ttu-id="3e960-103">Akzeptiert eine common Language Runtime (CLR) Version-Zeichenfolge, die von zurückgegeben wird das [CreateVersionStringFromModule-Funktion](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md), und gibt eine entsprechende Debuggerschnittstelle zurück (in der Regel [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)).</span><span class="sxs-lookup"><span data-stu-id="3e960-103">Accepts a common language runtime (CLR) version string that is returned from the [CreateVersionStringFromModule function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md), and returns a corresponding debugger interface (typically, [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e960-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e960-104">Syntax</span></span>  
  
```  
HRESULT CreateDebuggingInterfaceFromVersion (  
    [in]  LPCWSTR      szDebuggeeVersion,  
    [out] IUnknown**   ppCordb,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e960-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3e960-105">Parameters</span></span>  
 `szDebuggeeVersion`  
 <span data-ttu-id="3e960-106">[in] Die Versionszeichenfolge der CLR in der zu debuggenden Zielkomponente, die von zurückgegeben wird das [CreateVersionStringFromModule-Funktion](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md).</span><span class="sxs-lookup"><span data-stu-id="3e960-106">[in] Version string of the CLR in the target debuggee, which is returned by the [CreateVersionStringFromModule function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md).</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="3e960-107">Zeiger auf einen Zeiger auf ein COM-Objekt (`IUnknown`).</span><span class="sxs-lookup"><span data-stu-id="3e960-107">[out] Pointer to a pointer to a COM object (`IUnknown`).</span></span> <span data-ttu-id="3e960-108">Dieses Objekt wird umgewandelt werden, um eine [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Objekt, bevor sie zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3e960-108">This object will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object before it is returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e960-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3e960-109">Return Value</span></span>  
 <span data-ttu-id="3e960-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e960-110">S_OK</span></span>  
 <span data-ttu-id="3e960-111">`ppCordb` verweist auf ein gültiges Objekt, das die [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3e960-111">`ppCordb` references a valid object that implements the [ICorDebug interface](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface.</span></span>  
  
 <span data-ttu-id="3e960-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3e960-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="3e960-113">Entweder `szDebuggeeVersion` oder `ppCordb` ist null.</span><span class="sxs-lookup"><span data-stu-id="3e960-113">Either `szDebuggeeVersion` or `ppCordb` is null.</span></span>  
  
 <span data-ttu-id="3e960-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span><span class="sxs-lookup"><span data-stu-id="3e960-114">CORDBG_E_DEBUG_COMPONENT_MISSING</span></span>  
 <span data-ttu-id="3e960-115">Eine für das CLR-Debuggen erforderliche Komponente kann nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="3e960-115">A component that is necessary for CLR debugging cannot be located.</span></span> <span data-ttu-id="3e960-116">Dies bedeutet, dass entweder mscordbi.dll oder mscordaccore.dll nicht im selben Verzeichnis wie die Ziel-CoreCLR.dll gefunden wurde.
</span><span class="sxs-lookup"><span data-stu-id="3e960-116">This means that either mscordbi.dll or mscordaccore.dll was not found in the same directory as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="3e960-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span><span class="sxs-lookup"><span data-stu-id="3e960-117">CORDBG_E_INCOMPATIBLE_PROTOCOL</span></span>  
 <span data-ttu-id="3e960-118">Entweder mscordbi.dll oder mscordaccore.dll haben nicht dieselbe Version wie die Ziel-CoreCLR.dll.</span><span class="sxs-lookup"><span data-stu-id="3e960-118">Either mscordbi.dll or mscordaccore.dll is not the same version as the target CoreCLR.dll.</span></span>  
  
 <span data-ttu-id="3e960-119">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="3e960-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="3e960-120">Zurückgeben kann ein [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md).</span><span class="sxs-lookup"><span data-stu-id="3e960-120">Unable to return an [ICorDebug interface](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e960-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3e960-121">Remarks</span></span>  
 <span data-ttu-id="3e960-122">Die zurückgegebene Schnittstelle stellt die Funktionen zum Anfügen an eine CLR in einem Zielprozess und zum Debuggen von verwaltetem Code bereit, der von der CLR ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3e960-122">The interface that is returned provides the facilities for attaching to a CLR in a target process and debugging the managed code that the CLR is running.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e960-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3e960-123">Requirements</span></span>  
 <span data-ttu-id="3e960-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e960-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e960-125">**Header:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="3e960-125">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="3e960-126">**Bibliothek:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="3e960-126">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="3e960-127">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="3e960-127">**.NET Framework Versions:** 3.5 SP1</span></span>
