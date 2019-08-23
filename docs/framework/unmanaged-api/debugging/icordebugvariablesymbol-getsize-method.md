---
title: 'Icordebugvariablesymbol:: GetSize-Methode'
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 782073968030d3dcdbbe49e0ed7732fe15c4a3bb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968166"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="26a13-102">Icordebugvariablesymbol:: GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="26a13-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="26a13-103">Ruft die Größe einer Variablen in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="26a13-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26a13-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="26a13-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26a13-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="26a13-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="26a13-106">Ein Zeiger auf eine 32-Bit-Ganzzahl ohne Vorzeichen, die die Größe der Variablen enthält.</span><span class="sxs-lookup"><span data-stu-id="26a13-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26a13-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="26a13-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26a13-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="26a13-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26a13-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="26a13-109">Requirements</span></span>  
 <span data-ttu-id="26a13-110">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26a13-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26a13-111">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="26a13-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26a13-112">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26a13-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26a13-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26a13-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26a13-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26a13-114">See also</span></span>

- [<span data-ttu-id="26a13-115">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="26a13-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="26a13-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="26a13-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
