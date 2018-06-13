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
ms.openlocfilehash: 20f65218928ee07d67ea742154469ac3cbea9241
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421764"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="de442-102">ICorDebugVariableHome::GetArgumentIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="de442-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>
<span data-ttu-id="de442-103">Ruft den Index ein Funktionsargument ab.</span><span class="sxs-lookup"><span data-stu-id="de442-103">Gets the index of a function argument.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de442-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="de442-104">Syntax</span></span>  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de442-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="de442-105">Parameters</span></span>  
 `pArgumentIndex`  
 <span data-ttu-id="de442-106">[out] Ein Zeiger auf den Argumentindex.</span><span class="sxs-lookup"><span data-stu-id="de442-106">[out] A pointer to the argument index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de442-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="de442-107">Return Value</span></span>  
 <span data-ttu-id="de442-108">Die Methode gibt die folgenden Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="de442-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="de442-109">Wert</span><span class="sxs-lookup"><span data-stu-id="de442-109">Value</span></span>|<span data-ttu-id="de442-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de442-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="de442-111">Der Methodenaufruf zurückgegebene einen gültiges Argumentindex.</span><span class="sxs-lookup"><span data-stu-id="de442-111">The method call returned a valid argument index.</span></span>|  
|`E_FAIL`|<span data-ttu-id="de442-112">Die aktuelle [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Instanz darstellt, eine lokale Variable.</span><span class="sxs-lookup"><span data-stu-id="de442-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de442-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de442-113">Remarks</span></span>  
 <span data-ttu-id="de442-114">Der Argumentindex kann zum Abrufen von Metadaten für dieses Argument verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="de442-114">The argument index can be used to retrieve metadata for this argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de442-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="de442-115">Requirements</span></span>  
 <span data-ttu-id="de442-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de442-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de442-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de442-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de442-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de442-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de442-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de442-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de442-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de442-120">See Also</span></span>  
 [<span data-ttu-id="de442-121">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de442-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
