---
title: ICorDebugSymbolProvider2::GetFrameProps-Methode
ms.date: 03/30/2017
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
ms.openlocfilehash: ba1fd104c35b6e6dfdfd771f71eb19f8d532a1d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672010"
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="3f5db-102">ICorDebugSymbolProvider2::GetFrameProps-Methode</span><span class="sxs-lookup"><span data-stu-id="3f5db-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>

<span data-ttu-id="3f5db-103">Gibt die relative virtuelle Startadresse einer Methode und den übergeordneten Frame zurück, wenn eine coderelative virtuelle Adresse angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3f5db-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f5db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f5db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f5db-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3f5db-105">Parameters</span></span>  

 `codeRva`  
 <span data-ttu-id="3f5db-106">[in] Eine coderelative virtuelle Adresse.</span><span class="sxs-lookup"><span data-stu-id="3f5db-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="3f5db-107">[out] Ein Zeiger auf die relative virtuelle Startadresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="3f5db-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="3f5db-108">[out] Ein Zeiger auf die relative virtuelle Startadresse des Frames.</span><span class="sxs-lookup"><span data-stu-id="3f5db-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f5db-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3f5db-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f5db-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3f5db-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f5db-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3f5db-111">Requirements</span></span>  

 <span data-ttu-id="3f5db-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f5db-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f5db-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f5db-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f5db-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f5db-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f5db-115">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f5db-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f5db-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f5db-116">See also</span></span>

- [<span data-ttu-id="3f5db-117">ICorDebugSymbolProvider2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f5db-117">ICorDebugSymbolProvider2 Interface</span></span>](icordebugsymbolprovider2-interface.md)
- [<span data-ttu-id="3f5db-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3f5db-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
