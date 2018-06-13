---
title: ICorDebugInstanceFieldSymbol::GetOffset-Methode
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c77ac2eac1022fa591066901f48eaf609b5367af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413562"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="b35fd-102">ICorDebugInstanceFieldSymbol::GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="b35fd-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="b35fd-103">Ruft den Offset dieses Instanzenfelds in der übergeordneten Klasse in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="b35fd-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b35fd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b35fd-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b35fd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b35fd-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="b35fd-106">Ein Zeiger auf die Anzahl der Bytes, die der Offset dieses Instanzenfelds in der übergeordneten Klasse aufweist.</span><span class="sxs-lookup"><span data-stu-id="b35fd-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b35fd-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b35fd-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b35fd-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b35fd-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b35fd-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b35fd-109">Requirements</span></span>  
 <span data-ttu-id="b35fd-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b35fd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b35fd-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b35fd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b35fd-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b35fd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b35fd-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b35fd-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b35fd-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b35fd-114">See Also</span></span>  
 [<span data-ttu-id="b35fd-115">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b35fd-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="b35fd-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b35fd-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
