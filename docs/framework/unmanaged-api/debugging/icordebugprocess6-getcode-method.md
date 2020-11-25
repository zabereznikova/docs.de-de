---
title: ICorDebugProcess6::GetCode-Methode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
ms.openlocfilehash: cee1556fd7d803765b09a7cbd86ce2ff7be91cc9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732631"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="a7f73-102">ICorDebugProcess6::GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="a7f73-102">ICorDebugProcess6::GetCode Method</span></span>

<span data-ttu-id="a7f73-103">Ruft Informationen über den verwalteten Code an einer bestimmten Codeadresse ab.</span><span class="sxs-lookup"><span data-stu-id="a7f73-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7f73-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7f73-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7f73-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a7f73-105">Parameters</span></span>  

 `codeAddress`  
 <span data-ttu-id="a7f73-106">in Ein [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) -Wert, der die Startadresse des verwalteten Code Segments angibt.</span><span class="sxs-lookup"><span data-stu-id="a7f73-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="a7f73-107">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugCode-Objekts, das ein Segment von verwaltetem Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="a7f73-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7f73-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7f73-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a7f73-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a7f73-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7f73-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a7f73-110">Requirements</span></span>  

 <span data-ttu-id="a7f73-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7f73-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7f73-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7f73-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7f73-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7f73-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7f73-114">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7f73-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7f73-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a7f73-115">See also</span></span>

- [<span data-ttu-id="a7f73-116">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7f73-116">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="a7f73-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a7f73-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
