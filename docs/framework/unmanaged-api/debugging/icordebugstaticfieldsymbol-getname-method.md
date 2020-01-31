---
title: ICorDebugStaticFieldSymbol::GetName-Methode
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
ms.openlocfilehash: 0e4c52ff1ae6113ee2c3990a9d91682e10141902
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791831"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="52311-102">ICorDebugStaticFieldSymbol::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="52311-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="52311-103">Ruft den Namen des statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="52311-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52311-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="52311-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52311-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="52311-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="52311-106">[in] Die Anzahl der Zeichen im `szName`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="52311-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="52311-107">[out] Ein Zeiger auf die Anzahl der tatsächlich in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="52311-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="52311-108">[out] Ein Array von Zeichen, das den zurückgegebenen Namen speichert.</span><span class="sxs-lookup"><span data-stu-id="52311-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52311-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="52311-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52311-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="52311-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52311-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="52311-111">Requirements</span></span>  
 <span data-ttu-id="52311-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52311-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52311-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52311-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52311-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52311-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52311-115">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52311-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52311-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52311-116">See also</span></span>

- [<span data-ttu-id="52311-117">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52311-117">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="52311-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="52311-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
