---
title: CorDebugInternalFrameType-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugInternalFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInternalFrameType
helpviewer_keywords:
- CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type:
- apiref
ms.openlocfilehash: 2be827e12db765485ee889d6a4a19a982dad5d54
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778368"
---
# <a name="cordebuginternalframetype-enumeration"></a><span data-ttu-id="5e88b-102">CorDebugInternalFrameType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5e88b-102">CorDebugInternalFrameType Enumeration</span></span>
<span data-ttu-id="5e88b-103">Identifiziert den Stapelrahmentyp.</span><span class="sxs-lookup"><span data-stu-id="5e88b-103">Identifies the type of stack frame.</span></span> <span data-ttu-id="5e88b-104">Diese Enumeration wird von der [ICorDebugInternalFrame:: GetFrameType](icordebuginternalframe-getframetype-method.md) -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e88b-104">This enumeration is used by the [ICorDebugInternalFrame::GetFrameType](icordebuginternalframe-getframetype-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e88b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e88b-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="5e88b-106">Member</span><span class="sxs-lookup"><span data-stu-id="5e88b-106">Members</span></span>  
  
|<span data-ttu-id="5e88b-107">Member</span><span class="sxs-lookup"><span data-stu-id="5e88b-107">Member</span></span>|<span data-ttu-id="5e88b-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e88b-108">Description</span></span>|  
|------------|-----------------|  
|`STUBFRAME_NONE`|<span data-ttu-id="5e88b-109">Ein NULL-Wert.</span><span class="sxs-lookup"><span data-stu-id="5e88b-109">A null value.</span></span> <span data-ttu-id="5e88b-110">Die `ICorDebugInternalFrame::GetFrameType`-Methode gibt diesen Wert nie zurück.</span><span class="sxs-lookup"><span data-stu-id="5e88b-110">The `ICorDebugInternalFrame::GetFrameType` method never returns this value.</span></span>|  
|`STUBFRAME_M2U`|<span data-ttu-id="5e88b-111">Ein verwalteter-zu-nicht verwalteter Stub-Frame.</span><span class="sxs-lookup"><span data-stu-id="5e88b-111">A managed-to-unmanaged stub frame.</span></span>|  
|`STUBFRAME_U2M`|<span data-ttu-id="5e88b-112">Ein nicht verwalteter zu verwalteter Stub-Frame.</span><span class="sxs-lookup"><span data-stu-id="5e88b-112">An unmanaged-to-managed stub frame.</span></span>|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|<span data-ttu-id="5e88b-113">Ein Übergang zwischen Anwendungs Domänen.</span><span class="sxs-lookup"><span data-stu-id="5e88b-113">A transition between application domains.</span></span>|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|<span data-ttu-id="5e88b-114">Ein Lightweight-Methoden Aufruf.</span><span class="sxs-lookup"><span data-stu-id="5e88b-114">A lightweight method call.</span></span>|  
|`STUBFRAME_FUNC_EVAL`|<span data-ttu-id="5e88b-115">Der Anfang der Funktions Auswertung.</span><span class="sxs-lookup"><span data-stu-id="5e88b-115">The start of function evaluation.</span></span>|  
|`STUBFRAME_INTERNALCALL`|<span data-ttu-id="5e88b-116">Ein interner-Rückruf für die Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="5e88b-116">An internal call into the common language runtime.</span></span>|  
|`STUBFRAME_CLASS_INIT`|<span data-ttu-id="5e88b-117">Der Anfang einer Klassen Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="5e88b-117">The start of a class initialization.</span></span>|  
|`STUBFRAME_EXCEPTION`|<span data-ttu-id="5e88b-118">Eine Ausnahme, die ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="5e88b-118">An exception that is thrown.</span></span>|  
|`STUBFRAME_SECURITY`|<span data-ttu-id="5e88b-119">Ein Frame, der für die Code Zugriffssicherheit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5e88b-119">A frame used for code access security.</span></span>|  
|`STUBFRAME_JIT_COMPILATION`|<span data-ttu-id="5e88b-120">Die Laufzeit ist eine JIT-Kompilierung einer Methode.</span><span class="sxs-lookup"><span data-stu-id="5e88b-120">The runtime is JIT-compiling a method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5e88b-121">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5e88b-121">Requirements</span></span>  
 <span data-ttu-id="5e88b-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e88b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e88b-123">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e88b-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e88b-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e88b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e88b-125">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e88b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e88b-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e88b-126">See also</span></span>

- [<span data-ttu-id="5e88b-127">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="5e88b-127">Debugging Enumerations</span></span>](debugging-enumerations.md)
