---
title: ICorDebugProcess::EnableLogMessages-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnableLogMessages
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnableLogMessages
helpviewer_keywords:
- ICorDebugProcess::EnableLogMessages method [.NET Framework debugging]
- EnableLogMessages method [.NET Framework debugging]
ms.assetid: 14a4e5a3-3eaf-4f53-9dd1-762726963a23
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d0dbac6570fc0af0452a0e44f838124afbf6a4fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419883"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="0d675-102">ICorDebugProcess::EnableLogMessages-Methode</span><span class="sxs-lookup"><span data-stu-id="0d675-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="0d675-103">Aktiviert und deaktiviert die Übertragung von Meldungen an den Debugger.</span><span class="sxs-lookup"><span data-stu-id="0d675-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d675-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d675-104">Syntax</span></span>  
  
```  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d675-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0d675-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="0d675-106">[in] `true` ermöglicht die Übertragung von Nachrichten protokollieren; `false` deaktiviert die Übertragung.</span><span class="sxs-lookup"><span data-stu-id="0d675-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d675-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0d675-107">Remarks</span></span>  
 <span data-ttu-id="0d675-108">Diese Methode ist nur gültig, nachdem die [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) Rückruf auftritt.</span><span class="sxs-lookup"><span data-stu-id="0d675-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d675-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0d675-109">Requirements</span></span>  
 <span data-ttu-id="0d675-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d675-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d675-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d675-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d675-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d675-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d675-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d675-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
