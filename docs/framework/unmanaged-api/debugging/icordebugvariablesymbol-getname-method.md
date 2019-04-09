---
title: ICorDebugVariableSymbol::GetName-Methode
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f514acbd772c9d33ec4372cfaccb778d6bb41eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170169"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="41f07-102">ICorDebugVariableSymbol::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="41f07-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="41f07-103">Ruft den Namen einer Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="41f07-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41f07-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41f07-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41f07-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="41f07-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="41f07-106">[in] Die Anzahl der Zeichen im `szName`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="41f07-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="41f07-107">[out] Ein Zeiger auf die Anzahl der tatsächlich in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="41f07-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="41f07-108">Ein Zeiger auf ein Zeichenarray, das den Variablennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="41f07-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41f07-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41f07-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41f07-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="41f07-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41f07-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="41f07-111">Requirements</span></span>  
 <span data-ttu-id="41f07-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41f07-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41f07-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41f07-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41f07-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41f07-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="41f07-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="41f07-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="41f07-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41f07-116">See also</span></span>

- [<span data-ttu-id="41f07-117">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41f07-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="41f07-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="41f07-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
