---
title: ICorDebugStaticFieldSymbol::GetSize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 256a15952cd52c5a096e1f0b8c7fc2086cde226c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="2cf2a-102">ICorDebugStaticFieldSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="2cf2a-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="2cf2a-103">Ruft die Größe des statischen Felds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="2cf2a-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cf2a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cf2a-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2cf2a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2cf2a-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="2cf2a-106">[out] Ein Zeiger auf die Länge des Felds.</span><span class="sxs-lookup"><span data-stu-id="2cf2a-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cf2a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2cf2a-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2cf2a-108">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2cf2a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cf2a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2cf2a-109">Requirements</span></span>  
 <span data-ttu-id="2cf2a-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cf2a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cf2a-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cf2a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cf2a-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cf2a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cf2a-113">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cf2a-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cf2a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cf2a-114">See Also</span></span>  
 [<span data-ttu-id="2cf2a-115">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cf2a-115">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="2cf2a-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="2cf2a-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
