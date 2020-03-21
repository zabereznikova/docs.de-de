---
title: ICorDebugInstanceFieldSymbol::GetName-Methode
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
ms.openlocfilehash: dd925cc213ed8a6c5d1def85b3e6335751c1b594
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178760"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="c0abd-102">ICorDebugInstanceFieldSymbol::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="c0abd-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="c0abd-103">Ruft den Namen des Instanzfelds ab.</span><span class="sxs-lookup"><span data-stu-id="c0abd-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0abd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0abd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0abd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c0abd-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="c0abd-106">[in] Die Anzahl der Zeichen im `szName`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="c0abd-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c0abd-107">[out] Ein Zeiger auf die Anzahl der tatsächlich in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c0abd-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="c0abd-108">[out] Ein Array von Zeichen, das den zurückgegebenen Namen speichert.</span><span class="sxs-lookup"><span data-stu-id="c0abd-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0abd-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c0abd-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c0abd-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c0abd-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0abd-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c0abd-111">Requirements</span></span>  
 <span data-ttu-id="c0abd-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0abd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0abd-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0abd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0abd-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0abd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0abd-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0abd-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0abd-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c0abd-116">See also</span></span>

- [<span data-ttu-id="c0abd-117">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0abd-117">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="c0abd-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c0abd-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
