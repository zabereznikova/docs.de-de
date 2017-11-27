---
title: ICorDebugVariableHome::GetArgumentIndex-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetArgumentIndex
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentiIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 175e45758d26d8168279c825d41ee58d049edf0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="ef915-102">ICorDebugVariableHome::GetArgumentIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="ef915-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>
<span data-ttu-id="ef915-103">Ruft den Index ein Funktionsargument ab.</span><span class="sxs-lookup"><span data-stu-id="ef915-103">Gets the index of a function argument.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef915-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef915-104">Syntax</span></span>  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef915-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ef915-105">Parameters</span></span>  
 `pArgumentIndex`  
 <span data-ttu-id="ef915-106">[out] Ein Zeiger auf den Argumentindex.</span><span class="sxs-lookup"><span data-stu-id="ef915-106">[out] A pointer to the argument index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef915-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ef915-107">Return Value</span></span>  
 <span data-ttu-id="ef915-108">Die Methode gibt die folgenden Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="ef915-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="ef915-109">Wert</span><span class="sxs-lookup"><span data-stu-id="ef915-109">Value</span></span>|<span data-ttu-id="ef915-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef915-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="ef915-111">Der Methodenaufruf zurückgegebene einen gültiges Argumentindex.</span><span class="sxs-lookup"><span data-stu-id="ef915-111">The method call returned a valid argument index.</span></span>|  
|`E_FAIL`|<span data-ttu-id="ef915-112">Die aktuelle [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Instanz darstellt, eine lokale Variable.</span><span class="sxs-lookup"><span data-stu-id="ef915-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef915-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef915-113">Remarks</span></span>  
 <span data-ttu-id="ef915-114">Der Argumentindex kann zum Abrufen von Metadaten für dieses Argument verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ef915-114">The argument index can be used to retrieve metadata for this argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef915-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ef915-115">Requirements</span></span>  
 <span data-ttu-id="ef915-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef915-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef915-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef915-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef915-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef915-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef915-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef915-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef915-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef915-120">See Also</span></span>  
 [<span data-ttu-id="ef915-121">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ef915-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
