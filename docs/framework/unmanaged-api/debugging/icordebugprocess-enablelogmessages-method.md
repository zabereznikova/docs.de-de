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
ms.openlocfilehash: 86cb1a2eb18840419d2a4e8ee4f6475edafe8397
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724623"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="2a17b-102">ICorDebugProcess::EnableLogMessages-Methode</span><span class="sxs-lookup"><span data-stu-id="2a17b-102">ICorDebugProcess::EnableLogMessages Method</span></span>

<span data-ttu-id="2a17b-103">Aktiviert und deaktiviert die Übertragung von Protokollmeldungen an den Debugger.</span><span class="sxs-lookup"><span data-stu-id="2a17b-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a17b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a17b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a17b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a17b-105">Parameters</span></span>  

 `fOnOff`  
 <span data-ttu-id="2a17b-106">[in] `true` ermöglicht die Übertragung von Protokollmeldungen. `false` deaktiviert die Übertragung.</span><span class="sxs-lookup"><span data-stu-id="2a17b-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2a17b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2a17b-107">Remarks</span></span>  

 <span data-ttu-id="2a17b-108">Diese Methode ist nur gültig, wenn der [ICorDebugManagedCallback::](icordebugmanagedcallback-createprocess-method.md) up-Prozess-Rückruf auftritt.</span><span class="sxs-lookup"><span data-stu-id="2a17b-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a17b-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2a17b-109">Requirements</span></span>  

 <span data-ttu-id="2a17b-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a17b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a17b-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a17b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a17b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a17b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a17b-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a17b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
