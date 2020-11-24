---
title: ICorDebugStaticFieldSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: 34567247935588363d96b141717d7ec07bb76546
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677209"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="20064-102">ICorDebugStaticFieldSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="20064-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>

<span data-ttu-id="20064-103">Ruft die Größe des statischen Felds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="20064-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20064-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20064-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20064-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="20064-105">Parameters</span></span>  

 `pcbSize`  
 <span data-ttu-id="20064-106">[out] Ein Zeiger auf die Länge des Felds.</span><span class="sxs-lookup"><span data-stu-id="20064-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20064-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20064-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20064-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="20064-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20064-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="20064-109">Requirements</span></span>  

 <span data-ttu-id="20064-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20064-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20064-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20064-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20064-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20064-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20064-113">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20064-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20064-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20064-114">See also</span></span>

- [<span data-ttu-id="20064-115">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20064-115">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="20064-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="20064-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
