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
ms.openlocfilehash: 3ac1b3606131f534195df9b6b59bf72b1bff27fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724532"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="0ae31-102">ICorDebugProcess::ModifyLogSwitch-Methode</span><span class="sxs-lookup"><span data-stu-id="0ae31-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>

<span data-ttu-id="0ae31-103">Legt den Schweregrad des angegebenen Protokoll Schalters fest.</span><span class="sxs-lookup"><span data-stu-id="0ae31-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ae31-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ae31-104">Syntax</span></span>  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ae31-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ae31-105">Parameters</span></span>  

 `pLogSwitchName`  
 <span data-ttu-id="0ae31-106">in Ein Zeiger auf eine Zeichenfolge, die den Namen des Protokoll Schalters angibt.</span><span class="sxs-lookup"><span data-stu-id="0ae31-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="0ae31-107">in Der Schweregrad, der für den angegebenen Protokoll Schalter festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0ae31-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ae31-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ae31-108">Remarks</span></span>  

 <span data-ttu-id="0ae31-109">Diese Methode ist nur gültig, nachdem der [ICorDebugManagedCallback::](icordebugmanagedcallback-createprocess-method.md) up-Rückruf aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="0ae31-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ae31-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0ae31-110">Requirements</span></span>  

 <span data-ttu-id="0ae31-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ae31-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ae31-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ae31-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ae31-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ae31-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ae31-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ae31-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
