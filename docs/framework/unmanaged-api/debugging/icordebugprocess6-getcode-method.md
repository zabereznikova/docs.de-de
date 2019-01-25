---
title: ICorDebugProcess6::GetCode-Methode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30464956adf09ee4cc55db183c34396beacf070e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720453"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="c9a1b-102">ICorDebugProcess6::GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="c9a1b-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="c9a1b-103">Ruft Informationen über den verwalteten Code an einer bestimmten Codeadresse ab.</span><span class="sxs-lookup"><span data-stu-id="c9a1b-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9a1b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9a1b-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9a1b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c9a1b-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="c9a1b-106">[in] Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) Wert, der die Startadresse des verwalteten Codesegments angibt.</span><span class="sxs-lookup"><span data-stu-id="c9a1b-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="c9a1b-107">[out] Ein Zeiger auf die Adresse ein "ICorDebugCode"-Objekt, das ein Segment von verwaltetem Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="c9a1b-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9a1b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c9a1b-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9a1b-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c9a1b-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9a1b-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c9a1b-110">Requirements</span></span>  
 <span data-ttu-id="c9a1b-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9a1b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9a1b-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9a1b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9a1b-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9a1b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9a1b-114">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9a1b-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9a1b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9a1b-115">See also</span></span>
- [<span data-ttu-id="c9a1b-116">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c9a1b-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="c9a1b-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c9a1b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
