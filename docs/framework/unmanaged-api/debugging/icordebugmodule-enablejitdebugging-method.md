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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8aeb6ed448539db2720fee0d42cfcc344fd3bbf7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762766"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="09a6e-102">ICorDebugModule::EnableJITDebugging-Methode</span><span class="sxs-lookup"><span data-stu-id="09a6e-102">ICorDebugModule::EnableJITDebugging Method</span></span>
<span data-ttu-id="09a6e-103">Steuert, ob der just-in-Time (JIT)-Compiler Debuginformationen für Methoden in diesem Modul werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="09a6e-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09a6e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="09a6e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09a6e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="09a6e-105">Parameters</span></span>  
 `bTrackJITInfo`  
 <span data-ttu-id="09a6e-106">[in] Legen Sie diesen Wert auf `true` zum Aktivieren des JIT-Compilers, um Informationen über die Zuordnung zwischen der Microsoft intermediate Language (MSIL)-Version und der JIT-kompilierten Version der einzelnen Methoden in diesem Modul zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="09a6e-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="09a6e-107">[in] Legen Sie diesen Wert auf `true` den JIT-Compiler zum Generieren von Code mit bestimmten JIT-spezifischen Optimierungen für das Debuggen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="09a6e-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09a6e-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="09a6e-108">Remarks</span></span>  
 <span data-ttu-id="09a6e-109">JIT-Debuggen ist für alle Module in der Standardeinstellung aktiviert, die geladen werden, wenn der Debugger aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="09a6e-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="09a6e-110">Programmgesteuertes aktivieren oder deaktivieren die Einstellungen überschreibt globale Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="09a6e-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09a6e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="09a6e-111">Requirements</span></span>  
 <span data-ttu-id="09a6e-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09a6e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09a6e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09a6e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09a6e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09a6e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09a6e-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09a6e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
