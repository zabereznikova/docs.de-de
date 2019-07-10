---
title: ICorDebugProcess::ModifyLogSwitch-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ModifyLogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ModifyLogSwitch
helpviewer_keywords:
- ICorDebugProcess::ModifyLogSwitch method [.NET Framework debugging]
- ModifyLogSwitch method [.NET Framework debugging]
ms.assetid: 5fd30875-555e-4e96-877b-5dd266cde7c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96db1ca115ffed47b5eb8eadd9c3d2f620060c4a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755450"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="eed1a-102">ICorDebugProcess::ModifyLogSwitch-Methode</span><span class="sxs-lookup"><span data-stu-id="eed1a-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="eed1a-103">Legt den Schweregrad der angegebenen Log-Schalter fest.</span><span class="sxs-lookup"><span data-stu-id="eed1a-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eed1a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eed1a-104">Syntax</span></span>  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eed1a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eed1a-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="eed1a-106">[in] Ein Zeiger auf eine Zeichenfolge, die den Namen der Log-Schalter angibt.</span><span class="sxs-lookup"><span data-stu-id="eed1a-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="eed1a-107">[in] Der Schweregrad für die angegebene Log-Schalter festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="eed1a-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eed1a-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eed1a-108">Remarks</span></span>  
 <span data-ttu-id="eed1a-109">Diese Methode ist nur gültig, nachdem die [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) Rückruf ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="eed1a-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eed1a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eed1a-110">Requirements</span></span>  
 <span data-ttu-id="eed1a-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eed1a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eed1a-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eed1a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eed1a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eed1a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eed1a-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eed1a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
