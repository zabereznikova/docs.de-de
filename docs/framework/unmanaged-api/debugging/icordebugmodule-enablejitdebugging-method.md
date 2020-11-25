---
title: ICorDebugModule::EnableJITDebugging-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableJITDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type:
- apiref
ms.openlocfilehash: 359db27878ea4adf794bcd6221d4b5387026e5c0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710310"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="160c7-102">ICorDebugModule::EnableJITDebugging-Methode</span><span class="sxs-lookup"><span data-stu-id="160c7-102">ICorDebugModule::EnableJITDebugging Method</span></span>

<span data-ttu-id="160c7-103">Steuert, ob der JIT-Compiler (Just-in-Time) Debuginformationen für Methoden in diesem Modul beibehält.</span><span class="sxs-lookup"><span data-stu-id="160c7-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="160c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="160c7-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="160c7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="160c7-105">Parameters</span></span>  

 `bTrackJITInfo`  
 <span data-ttu-id="160c7-106">in Legen Sie diesen Wert auf fest, `true` um dem JIT-Compiler das Beibehalten von Zuordnungsinformationen zwischen der MSIL-Version (Microsoft Intermediate Language) und der JIT-kompilierten Version der einzelnen Methoden in diesem Modul zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="160c7-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="160c7-107">in Legen Sie diesen Wert auf fest, `true` um dem JIT-Compiler das Generieren von Code mit bestimmten JIT-spezifischen Optimierungen für das Debuggen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="160c7-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="160c7-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="160c7-108">Remarks</span></span>  

 <span data-ttu-id="160c7-109">Das JIT-Debuggen ist standardmäßig für alle Module aktiviert, die geladen werden, wenn der Debugger aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="160c7-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="160c7-110">Die programmgesteuerte Aktivierung oder Deaktivierung der Einstellungen überschreibt globale Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="160c7-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="160c7-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="160c7-111">Requirements</span></span>  

 <span data-ttu-id="160c7-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="160c7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="160c7-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="160c7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="160c7-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="160c7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="160c7-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="160c7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
