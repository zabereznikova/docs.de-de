---
title: ICorDebugInstanceFieldSymbol::GetName-Methode
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
ms.openlocfilehash: 05914863dfbc2aca608a5d74f298f81c64345fe8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782390"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="b34b0-102">ICorDebugInstanceFieldSymbol::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="b34b0-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="b34b0-103">Ruft den Namen des Instanzfelds ab.</span><span class="sxs-lookup"><span data-stu-id="b34b0-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b34b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b34b0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b34b0-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b34b0-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="b34b0-106">[in] Die Anzahl der Zeichen im `szName`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="b34b0-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b34b0-107">[out] Ein Zeiger auf die Anzahl der tatsächlich in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b34b0-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="b34b0-108">[out] Ein Array von Zeichen, das den zurückgegebenen Namen speichert.</span><span class="sxs-lookup"><span data-stu-id="b34b0-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b34b0-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b34b0-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b34b0-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b34b0-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b34b0-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b34b0-111">Requirements</span></span>  
 <span data-ttu-id="b34b0-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b34b0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b34b0-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b34b0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b34b0-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b34b0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b34b0-115">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b34b0-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b34b0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b34b0-116">See also</span></span>

- [<span data-ttu-id="b34b0-117">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b34b0-117">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="b34b0-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b34b0-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
