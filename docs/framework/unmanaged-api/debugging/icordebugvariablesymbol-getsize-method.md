---
title: 'Icordebugvariablesymbol:: GetSize-Methode'
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 027b3f773ff0ed0ca7bf9d193f97a3b060ea8494
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211841"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="1138d-102">Icordebugvariablesymbol:: GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="1138d-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="1138d-103">Ruft die Größe einer Variablen in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="1138d-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1138d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1138d-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1138d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1138d-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="1138d-106">Ein Zeiger auf eine 32-Bit-Ganzzahl ohne Vorzeichen, die die Größe der Variablen enthält.</span><span class="sxs-lookup"><span data-stu-id="1138d-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1138d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1138d-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1138d-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1138d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1138d-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1138d-109">Requirements</span></span>  
 <span data-ttu-id="1138d-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1138d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1138d-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1138d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1138d-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1138d-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1138d-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="1138d-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1138d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1138d-114">See also</span></span>

- [<span data-ttu-id="1138d-115">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1138d-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="1138d-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1138d-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
