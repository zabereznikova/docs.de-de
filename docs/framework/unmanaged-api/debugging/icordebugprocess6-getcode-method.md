---
title: ICorDebugProcess6::GetCode-Methode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d896cc4316c2de6fa1cb0bacc9ff8b1f3713129
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967555"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="dce19-102">ICorDebugProcess6::GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="dce19-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="dce19-103">Ruft Informationen über den verwalteten Code an einer bestimmten Codeadresse ab.</span><span class="sxs-lookup"><span data-stu-id="dce19-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dce19-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dce19-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dce19-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dce19-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="dce19-106">in Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) -Wert, der die Startadresse des verwalteten Code Segments angibt.</span><span class="sxs-lookup"><span data-stu-id="dce19-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="dce19-107">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugCode-Objekts, das ein Segment von verwaltetem Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="dce19-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dce19-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dce19-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dce19-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dce19-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dce19-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dce19-110">Requirements</span></span>  
 <span data-ttu-id="dce19-111">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dce19-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dce19-112">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="dce19-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dce19-113">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dce19-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dce19-114">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dce19-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dce19-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dce19-115">See also</span></span>

- [<span data-ttu-id="dce19-116">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dce19-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="dce19-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="dce19-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
