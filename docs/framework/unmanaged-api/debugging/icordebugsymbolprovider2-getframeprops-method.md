---
title: ICorDebugSymbolProvider2::GetFrameProps-Methode
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
ms.openlocfilehash: dc64152938c46945978715251286ecb6c6d8983c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791512"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="b2dc1-102">ICorDebugSymbolProvider2::GetFrameProps-Methode</span><span class="sxs-lookup"><span data-stu-id="b2dc1-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>
<span data-ttu-id="b2dc1-103">Gibt die relative virtuelle Startadresse einer Methode und den übergeordneten Frame zurück, wenn eine coderelative virtuelle Adresse angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b2dc1-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2dc1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2dc1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2dc1-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b2dc1-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="b2dc1-106">[in] Eine coderelative virtuelle Adresse.</span><span class="sxs-lookup"><span data-stu-id="b2dc1-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="b2dc1-107">[out] Ein Zeiger auf die relative virtuelle Startadresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="b2dc1-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="b2dc1-108">[out] Ein Zeiger auf die relative virtuelle Startadresse des Frames.</span><span class="sxs-lookup"><span data-stu-id="b2dc1-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2dc1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b2dc1-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2dc1-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b2dc1-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2dc1-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b2dc1-111">Requirements</span></span>  
 <span data-ttu-id="b2dc1-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2dc1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2dc1-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2dc1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2dc1-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2dc1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2dc1-115">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2dc1-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2dc1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2dc1-116">See also</span></span>

- [<span data-ttu-id="b2dc1-117">ICorDebugSymbolProvider2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b2dc1-117">ICorDebugSymbolProvider2 Interface</span></span>](icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="b2dc1-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b2dc1-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
