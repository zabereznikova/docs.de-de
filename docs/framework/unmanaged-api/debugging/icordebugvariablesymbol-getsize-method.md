---
title: ICorDebugVariableSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01349b6418008db51c432d5c49f8491a44ab60d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419405"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="22c5a-102">ICorDebugVariableSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="22c5a-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="22c5a-103">Ruft die Größe einer Variablen in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="22c5a-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22c5a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="22c5a-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22c5a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="22c5a-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="22c5a-106">Ein Zeiger auf eine 32-Bit-Ganzzahl ohne Vorzeichen, die die Größe der Variablen enthält.</span><span class="sxs-lookup"><span data-stu-id="22c5a-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22c5a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22c5a-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22c5a-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="22c5a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22c5a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="22c5a-109">Requirements</span></span>  
 <span data-ttu-id="22c5a-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22c5a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22c5a-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22c5a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22c5a-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22c5a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22c5a-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22c5a-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22c5a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22c5a-114">See Also</span></span>  
 [<span data-ttu-id="22c5a-115">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="22c5a-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="22c5a-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="22c5a-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
