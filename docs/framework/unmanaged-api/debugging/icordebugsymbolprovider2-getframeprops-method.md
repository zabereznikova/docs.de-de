---
title: 'ICorDebugSymbolProvider2:: getframerequismethode'
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
ms.openlocfilehash: 39bdb93fcb48da6667d982ca2d511ee5e499ae32
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133646"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="e0429-102">ICorDebugSymbolProvider2:: getframerequismethode</span><span class="sxs-lookup"><span data-stu-id="e0429-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>
<span data-ttu-id="e0429-103">Gibt die relative virtuelle Startadresse einer Methode und den übergeordneten Frame zurück, wenn eine coderelative virtuelle Adresse angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e0429-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0429-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0429-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0429-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e0429-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="e0429-106">[in] Eine coderelative virtuelle Adresse.</span><span class="sxs-lookup"><span data-stu-id="e0429-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="e0429-107">[out] Ein Zeiger auf die relative virtuelle Startadresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="e0429-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="e0429-108">[out] Ein Zeiger auf die relative virtuelle Startadresse des Frames.</span><span class="sxs-lookup"><span data-stu-id="e0429-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0429-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0429-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0429-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e0429-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0429-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e0429-111">Requirements</span></span>  
 <span data-ttu-id="e0429-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0429-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0429-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0429-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0429-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0429-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0429-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0429-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0429-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0429-116">See also</span></span>

- [<span data-ttu-id="e0429-117">ICorDebugSymbolProvider2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0429-117">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="e0429-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e0429-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
