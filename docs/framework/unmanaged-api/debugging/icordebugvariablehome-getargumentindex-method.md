---
title: ICorDebugVariableHome::GetArgumentIndex-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentiIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 163704bf9a71ceda04bdfd73f9ca676c19d8a62c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526639"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="45296-102">ICorDebugVariableHome::GetArgumentIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="45296-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>
<span data-ttu-id="45296-103">Ruft den Index ein Funktionsargument ab.</span><span class="sxs-lookup"><span data-stu-id="45296-103">Gets the index of a function argument.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45296-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45296-104">Syntax</span></span>  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45296-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="45296-105">Parameters</span></span>  
 `pArgumentIndex`  
 <span data-ttu-id="45296-106">[out] Ein Zeiger auf den Argumentindex.</span><span class="sxs-lookup"><span data-stu-id="45296-106">[out] A pointer to the argument index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45296-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="45296-107">Return Value</span></span>  
 <span data-ttu-id="45296-108">Die Methode gibt die folgenden Werte an.</span><span class="sxs-lookup"><span data-stu-id="45296-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="45296-109">Wert</span><span class="sxs-lookup"><span data-stu-id="45296-109">Value</span></span>|<span data-ttu-id="45296-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45296-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="45296-111">Aufruf der Methode wurde einen gültiges Argument-Index.</span><span class="sxs-lookup"><span data-stu-id="45296-111">The method call returned a valid argument index.</span></span>|  
|`E_FAIL`|<span data-ttu-id="45296-112">Die aktuelle [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Instanz stellt eine lokale Variable dar.</span><span class="sxs-lookup"><span data-stu-id="45296-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45296-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="45296-113">Remarks</span></span>  
 <span data-ttu-id="45296-114">Der Argumentindex kann zum Abrufen von Metadaten für dieses Argument verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="45296-114">The argument index can be used to retrieve metadata for this argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45296-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="45296-115">Requirements</span></span>  
 <span data-ttu-id="45296-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45296-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45296-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45296-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45296-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45296-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45296-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45296-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45296-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45296-120">See also</span></span>
- [<span data-ttu-id="45296-121">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45296-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
