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
ms.openlocfilehash: da532ee1b5909a68bedbb9e6f6c96333e88002a8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109729"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="c8057-102">ICorDebugModule::EnableJITDebugging-Methode</span><span class="sxs-lookup"><span data-stu-id="c8057-102">ICorDebugModule::EnableJITDebugging Method</span></span>
<span data-ttu-id="c8057-103">Steuert, ob der JIT-Compiler (Just-in-Time) Debuginformationen für Methoden in diesem Modul beibehält.</span><span class="sxs-lookup"><span data-stu-id="c8057-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8057-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8057-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8057-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c8057-105">Parameters</span></span>  
 `bTrackJITInfo`  
 <span data-ttu-id="c8057-106">in Legen Sie diesen Wert auf `true` fest, damit der JIT-Compiler Zuordnungsinformationen zwischen der MSIL-Version (Microsoft Intermediate Language) und der JIT-kompilierten Version der einzelnen Methoden in diesem Modul beibehalten kann.</span><span class="sxs-lookup"><span data-stu-id="c8057-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="c8057-107">in Legen Sie diesen Wert auf `true` fest, damit der JIT-Compiler Code mit bestimmten JIT-spezifischen Optimierungen für das Debuggen generieren kann.</span><span class="sxs-lookup"><span data-stu-id="c8057-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8057-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8057-108">Remarks</span></span>  
 <span data-ttu-id="c8057-109">Das JIT-Debuggen ist standardmäßig für alle Module aktiviert, die geladen werden, wenn der Debugger aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="c8057-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="c8057-110">Die programmgesteuerte Aktivierung oder Deaktivierung der Einstellungen überschreibt globale Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="c8057-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8057-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c8057-111">Requirements</span></span>  
 <span data-ttu-id="c8057-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8057-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8057-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8057-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8057-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8057-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8057-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8057-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
