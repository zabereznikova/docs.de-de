---
title: ICorDebugVariableSymbol::GetName-Methode
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: ea414a39e140c74df736764dbbb1bb3934bda78f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397130"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="add01-102">ICorDebugVariableSymbol::GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="add01-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="add01-103">Ruft den Namen einer Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="add01-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="add01-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="add01-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="add01-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="add01-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="add01-106">[in] Die Anzahl der Zeichen im `szName`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="add01-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="add01-107">[out] Ein Zeiger auf die Anzahl der tatsächlich in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="add01-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="add01-108">Ein Zeiger auf ein Zeichenarray, das den Variablennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="add01-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="add01-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="add01-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="add01-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="add01-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="add01-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="add01-111">Requirements</span></span>  
 <span data-ttu-id="add01-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="add01-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="add01-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="add01-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="add01-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="add01-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="add01-115">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="add01-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="add01-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="add01-116">See also</span></span>

- [<span data-ttu-id="add01-117">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="add01-117">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="add01-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="add01-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
