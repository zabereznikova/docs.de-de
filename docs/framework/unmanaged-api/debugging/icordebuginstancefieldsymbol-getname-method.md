---
title: ICorDebugInstanceFieldSymbol::GetName-Methode
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
ms.openlocfilehash: e466a62761cc6dd1f1fc0a54f05d54f85c190d07
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724935"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="a992e-102">ICorDebugInstanceFieldSymbol::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="a992e-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>

<span data-ttu-id="a992e-103">Ruft den Namen des Instanzfelds ab.</span><span class="sxs-lookup"><span data-stu-id="a992e-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a992e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a992e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a992e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a992e-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="a992e-106">[in] Die Anzahl der Zeichen im `szName`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="a992e-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a992e-107">[out] Ein Zeiger auf die Anzahl der tatsächlich in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="a992e-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="a992e-108">[out] Ein Array von Zeichen, das den zurückgegebenen Namen speichert.</span><span class="sxs-lookup"><span data-stu-id="a992e-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a992e-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a992e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a992e-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a992e-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a992e-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a992e-111">Requirements</span></span>  

 <span data-ttu-id="a992e-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a992e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a992e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a992e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a992e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a992e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a992e-115">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a992e-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a992e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a992e-116">See also</span></span>

- [<span data-ttu-id="a992e-117">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a992e-117">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="a992e-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a992e-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
