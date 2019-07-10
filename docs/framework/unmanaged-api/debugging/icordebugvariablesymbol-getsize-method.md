---
title: 'Icordebugvariablesymbol:: GetSize-Methode'
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e963e655c933c9191953bb32ba0b73adf0ae86d7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774867"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="6334b-102">Icordebugvariablesymbol:: GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="6334b-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="6334b-103">Ruft die Größe einer Variablen in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="6334b-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6334b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6334b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6334b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6334b-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="6334b-106">Ein Zeiger auf eine 32-Bit-Ganzzahl ohne Vorzeichen, die die Größe der Variablen enthält.</span><span class="sxs-lookup"><span data-stu-id="6334b-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6334b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6334b-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6334b-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6334b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6334b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6334b-109">Requirements</span></span>  
 <span data-ttu-id="6334b-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6334b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6334b-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6334b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6334b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6334b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6334b-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6334b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6334b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6334b-114">See also</span></span>

- [<span data-ttu-id="6334b-115">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6334b-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="6334b-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6334b-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
