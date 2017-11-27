---
title: ICorDebugProcess6::GetCode-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c69ce290a486960978ddaf87203328df4f392b48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="c0c3c-102">ICorDebugProcess6::GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="c0c3c-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="c0c3c-103">Ruft Informationen über den verwalteten Code an einer bestimmten Codeadresse ab.</span><span class="sxs-lookup"><span data-stu-id="c0c3c-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0c3c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0c3c-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0c3c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c0c3c-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="c0c3c-106">[in] Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) Wert, der die Startadresse des verwalteten Codesegments angibt.</span><span class="sxs-lookup"><span data-stu-id="c0c3c-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="c0c3c-107">[out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugCode", das ein Segment von verwaltetem Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="c0c3c-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0c3c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c0c3c-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0c3c-109">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c0c3c-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0c3c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c0c3c-110">Requirements</span></span>  
 <span data-ttu-id="c0c3c-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0c3c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0c3c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0c3c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0c3c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0c3c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0c3c-114">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0c3c-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0c3c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0c3c-115">See Also</span></span>  
 [<span data-ttu-id="c0c3c-116">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0c3c-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="c0c3c-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c0c3c-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
