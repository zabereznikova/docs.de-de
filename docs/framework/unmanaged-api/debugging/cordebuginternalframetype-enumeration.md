---
title: CorDebugInternalFrameType-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugInternalFrameType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugInternalFrameType
helpviewer_keywords: CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65e970563ec3958deddb0aa1d89e10b0da70f0a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="cordebuginternalframetype-enumeration"></a><span data-ttu-id="b68f1-102">CorDebugInternalFrameType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b68f1-102">CorDebugInternalFrameType Enumeration</span></span>
<span data-ttu-id="b68f1-103">Identifiziert den Stapelrahmentyp.</span><span class="sxs-lookup"><span data-stu-id="b68f1-103">Identifies the type of stack frame.</span></span> <span data-ttu-id="b68f1-104">Diese Enumeration wird verwendet, durch die [ICorDebugInternalFrame:: GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="b68f1-104">This enumeration is used by the [ICorDebugInternalFrame::GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b68f1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b68f1-105">Syntax</span></span>  
  
```  
typedef enum CorDebugInternalFrameType {  
  
    STUBFRAME_NONE                 = 0x00000000,  
    STUBFRAME_M2U                  = 0x00000001,  
    STUBFRAME_U2M                  = 0x00000002,  
    STUBFRAME_APPDOMAIN_TRANSITION = 0x00000003,  
    STUBFRAME_LIGHTWEIGHT_FUNCTION = 0x00000004,  
    STUBFRAME_FUNC_EVAL            = 0x00000005,  
    STUBFRAME_INTERNALCALL         = 0x00000006,  
    STUBFRAME_CLASS_INIT           = 0x00000007,  
    STUBFRAME_EXCEPTION            = 0x00000008,  
    STUBFRAME_SECURITY             = 0x00000009,  
    STUBFRAME_JIT_COMPILATION     = 0x0000000a,  
} CorDebugInternalFrameType;  
```  
  
## <a name="members"></a><span data-ttu-id="b68f1-106">Member</span><span class="sxs-lookup"><span data-stu-id="b68f1-106">Members</span></span>  
  
|<span data-ttu-id="b68f1-107">Member</span><span class="sxs-lookup"><span data-stu-id="b68f1-107">Member</span></span>|<span data-ttu-id="b68f1-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b68f1-108">Description</span></span>|  
|------------|-----------------|  
|`STUBFRAME_NONE`|<span data-ttu-id="b68f1-109">Ein NULL-Wert.</span><span class="sxs-lookup"><span data-stu-id="b68f1-109">A null value.</span></span> <span data-ttu-id="b68f1-110">Die `ICorDebugInternalFrame::GetFrameType` Methode gibt diesen Wert nie zurück.</span><span class="sxs-lookup"><span data-stu-id="b68f1-110">The `ICorDebugInternalFrame::GetFrameType` method never returns this value.</span></span>|  
|`STUBFRAME_M2U`|<span data-ttu-id="b68f1-111">Ein Stub verwaltet, nicht verwaltete-Frame.</span><span class="sxs-lookup"><span data-stu-id="b68f1-111">A managed-to-unmanaged stub frame.</span></span>|  
|`STUBFRAME_U2M`|<span data-ttu-id="b68f1-112">Einen nicht verwalteten zum verwalteten Stub-Frame.</span><span class="sxs-lookup"><span data-stu-id="b68f1-112">An unmanaged-to-managed stub frame.</span></span>|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|<span data-ttu-id="b68f1-113">Ein Übergang zwischen Anwendungsdomänen.</span><span class="sxs-lookup"><span data-stu-id="b68f1-113">A transition between application domains.</span></span>|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|<span data-ttu-id="b68f1-114">Ein lightweight-Methodenaufruf.</span><span class="sxs-lookup"><span data-stu-id="b68f1-114">A lightweight method call.</span></span>|  
|`STUBFRAME_FUNC_EVAL`|<span data-ttu-id="b68f1-115">Der Beginn des funktionsauswertung.</span><span class="sxs-lookup"><span data-stu-id="b68f1-115">The start of function evaluation.</span></span>|  
|`STUBFRAME_INTERNALCALL`|<span data-ttu-id="b68f1-116">Ein interner Aufruf in der common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="b68f1-116">An internal call into the common language runtime.</span></span>|  
|`STUBFRAME_CLASS_INIT`|<span data-ttu-id="b68f1-117">Der Anfang der Initialisierung einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="b68f1-117">The start of a class initialization.</span></span>|  
|`STUBFRAME_EXCEPTION`|<span data-ttu-id="b68f1-118">Eine Ausnahme, die ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="b68f1-118">An exception that is thrown.</span></span>|  
|`STUBFRAME_SECURITY`|<span data-ttu-id="b68f1-119">Ein Frame, der für die Codezugriffssicherheit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b68f1-119">A frame used for code access security.</span></span>|  
|`STUBFRAME_JIT_COMPILATION`|<span data-ttu-id="b68f1-120">Die Common Language Runtime ist eine Methode JIT-Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="b68f1-120">The runtime is JIT-compiling a method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b68f1-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b68f1-121">Requirements</span></span>  
 <span data-ttu-id="b68f1-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b68f1-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b68f1-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b68f1-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b68f1-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b68f1-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b68f1-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b68f1-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b68f1-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b68f1-126">See Also</span></span>  
 [<span data-ttu-id="b68f1-127">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="b68f1-127">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
