---
title: ICorDebugInstanceFieldSymbol::GetSize-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 364144dcef21e7e9c058cb0317970a273aa8ecac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="e1bc6-102">ICorDebugInstanceFieldSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="e1bc6-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="e1bc6-103">Ruft die Größe des Instanzfelds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="e1bc6-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1bc6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1bc6-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1bc6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e1bc6-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="e1bc6-106">[out] Ein Zeiger auf die Länge des Felds.</span><span class="sxs-lookup"><span data-stu-id="e1bc6-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1bc6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e1bc6-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e1bc6-108">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e1bc6-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1bc6-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e1bc6-109">Requirements</span></span>  
 <span data-ttu-id="e1bc6-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1bc6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1bc6-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1bc6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1bc6-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1bc6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1bc6-113">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1bc6-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1bc6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1bc6-114">See Also</span></span>  
 [<span data-ttu-id="e1bc6-115">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e1bc6-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="e1bc6-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e1bc6-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
