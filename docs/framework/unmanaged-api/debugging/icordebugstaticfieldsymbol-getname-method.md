---
title: ICorDebugStaticFieldSymbol::GetName-Methode
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
ms.openlocfilehash: b1f5ca266f51df730dfb840c7bf003c47f31ece9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178514"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="e5bd6-102">ICorDebugStaticFieldSymbol::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="e5bd6-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="e5bd6-103">Ruft den Namen des statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="e5bd6-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5bd6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5bd6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5bd6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e5bd6-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="e5bd6-106">[in] Die Anzahl der Zeichen im `szName`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="e5bd6-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="e5bd6-107">[out] Ein Zeiger auf die Anzahl der tatsächlich in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="e5bd6-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="e5bd6-108">[out] Ein Array von Zeichen, das den zurückgegebenen Namen speichert.</span><span class="sxs-lookup"><span data-stu-id="e5bd6-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5bd6-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e5bd6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5bd6-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e5bd6-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5bd6-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e5bd6-111">Requirements</span></span>  
 <span data-ttu-id="e5bd6-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5bd6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5bd6-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5bd6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5bd6-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5bd6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5bd6-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5bd6-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5bd6-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e5bd6-116">See also</span></span>

- [<span data-ttu-id="e5bd6-117">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5bd6-117">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="e5bd6-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e5bd6-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
