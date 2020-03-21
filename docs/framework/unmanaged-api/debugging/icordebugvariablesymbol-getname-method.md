---
title: ICorDebugVariableSymbol::GetName-Methode
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: abc0e368f259df1a3542b0fc8e7fbfd7e06cf6eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178455"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="19352-102">ICorDebugVariableSymbol::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="19352-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="19352-103">Ruft den Namen einer Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="19352-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19352-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="19352-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19352-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="19352-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="19352-106">[in] Die Anzahl der Zeichen im `szName`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="19352-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="19352-107">[out] Ein Zeiger auf die Anzahl der tatsächlich in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="19352-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="19352-108">Ein Zeiger auf ein Zeichenarray, das den Variablennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="19352-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19352-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="19352-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="19352-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="19352-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19352-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="19352-111">Requirements</span></span>  
 <span data-ttu-id="19352-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19352-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19352-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19352-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19352-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19352-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19352-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19352-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19352-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19352-116">See also</span></span>

- [<span data-ttu-id="19352-117">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19352-117">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="19352-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="19352-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
