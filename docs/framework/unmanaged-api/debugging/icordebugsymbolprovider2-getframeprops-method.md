---
title: ICorDebugSymbolProvider2::GetFrameProps-Methode
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b20d78abbfa1db43047872a596289028833de37d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098987"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="e4385-102">ICorDebugSymbolProvider2::GetFrameProps-Methode</span><span class="sxs-lookup"><span data-stu-id="e4385-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>
<span data-ttu-id="e4385-103">Gibt die relative virtuelle Startadresse einer Methode und den übergeordneten Frame zurück, wenn eine coderelative virtuelle Adresse angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e4385-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4385-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4385-104">Syntax</span></span>  
  
```  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4385-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e4385-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="e4385-106">[in] Eine coderelative virtuelle Adresse.</span><span class="sxs-lookup"><span data-stu-id="e4385-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="e4385-107">[out] Ein Zeiger auf die relative virtuelle Startadresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="e4385-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="e4385-108">[out] Ein Zeiger auf die relative virtuelle Startadresse des Frames.</span><span class="sxs-lookup"><span data-stu-id="e4385-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4385-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4385-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4385-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e4385-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4385-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e4385-111">Requirements</span></span>  
 <span data-ttu-id="e4385-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4385-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4385-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4385-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4385-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4385-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e4385-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e4385-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e4385-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4385-116">See also</span></span>

- [<span data-ttu-id="e4385-117">ICorDebugSymbolProvider2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4385-117">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="e4385-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e4385-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
