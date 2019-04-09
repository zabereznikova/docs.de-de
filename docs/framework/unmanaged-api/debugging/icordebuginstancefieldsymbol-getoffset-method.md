---
title: ICorDebugInstanceFieldSymbol::GetOffset-Methode
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8ea777755aebb59f3e865df26c38c74ef68ae31
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203872"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="db412-102">ICorDebugInstanceFieldSymbol::GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="db412-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="db412-103">Ruft den Offset dieses Instanzenfelds in der übergeordneten Klasse in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="db412-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db412-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="db412-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db412-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="db412-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="db412-106">Ein Zeiger auf die Anzahl der Bytes, die der Offset dieses Instanzenfelds in der übergeordneten Klasse aufweist.</span><span class="sxs-lookup"><span data-stu-id="db412-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db412-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="db412-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db412-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="db412-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db412-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="db412-109">Requirements</span></span>  
 <span data-ttu-id="db412-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db412-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db412-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db412-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db412-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db412-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="db412-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="db412-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="db412-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db412-114">See also</span></span>

- [<span data-ttu-id="db412-115">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db412-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="db412-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="db412-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
