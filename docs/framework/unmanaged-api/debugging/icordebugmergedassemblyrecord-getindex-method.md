---
title: ICorDebugMergedAssemblyRecord::GetIndex-Methode
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8ba470325098125aee8ef7de01fa6aa70596d42
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202598"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="73e46-102">ICorDebugMergedAssemblyRecord::GetIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="73e46-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="73e46-103">Ruft den Präfixindex der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="73e46-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73e46-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="73e46-104">Syntax</span></span>  
  
```  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73e46-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="73e46-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="73e46-106">[out] Ein Zeiger auf den Präfixindex.</span><span class="sxs-lookup"><span data-stu-id="73e46-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73e46-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="73e46-107">Remarks</span></span>  
 <span data-ttu-id="73e46-108">Der Präfixindex wird verwendet, um Namenskonflikte in den zusammengeführten Namen der Metadatentypen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="73e46-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73e46-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="73e46-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73e46-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="73e46-110">Requirements</span></span>  
 <span data-ttu-id="73e46-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73e46-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73e46-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73e46-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73e46-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73e46-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="73e46-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="73e46-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="73e46-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73e46-115">See also</span></span>

- [<span data-ttu-id="73e46-116">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="73e46-116">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="73e46-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="73e46-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
