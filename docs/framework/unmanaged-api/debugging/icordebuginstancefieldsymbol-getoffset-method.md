---
title: ICorDebugInstanceFieldSymbol::GetOffset-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 534e3238a4b20e390c4f2168629e0ba93620f55a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="c8b75-102">ICorDebugInstanceFieldSymbol::GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="c8b75-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="c8b75-103">Ruft den Offset dieses Instanzenfelds in der übergeordneten Klasse in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="c8b75-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8b75-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8b75-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8b75-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c8b75-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="c8b75-106">Ein Zeiger auf die Anzahl der Bytes, die der Offset dieses Instanzenfelds in der übergeordneten Klasse aufweist.</span><span class="sxs-lookup"><span data-stu-id="c8b75-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8b75-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8b75-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8b75-108">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c8b75-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8b75-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c8b75-109">Requirements</span></span>  
 <span data-ttu-id="c8b75-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8b75-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8b75-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8b75-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8b75-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8b75-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8b75-113">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8b75-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8b75-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8b75-114">See Also</span></span>  
 [<span data-ttu-id="c8b75-115">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8b75-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="c8b75-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c8b75-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
