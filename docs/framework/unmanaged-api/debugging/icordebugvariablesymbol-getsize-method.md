---
title: ICorDebugVariableSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: 1079351e75ec9c48a9657f514ee56e2e6a4b0920
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731370"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="69e66-102">ICorDebugVariableSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="69e66-102">ICorDebugVariableSymbol::GetSize Method</span></span>

<span data-ttu-id="69e66-103">Ruft die Größe einer Variablen in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="69e66-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69e66-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="69e66-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69e66-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="69e66-105">Parameters</span></span>  

 `pcbValue`  
 <span data-ttu-id="69e66-106">Ein Zeiger auf eine 32-Bit-Ganzzahl ohne Vorzeichen, die die Größe der Variablen enthält.</span><span class="sxs-lookup"><span data-stu-id="69e66-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69e66-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="69e66-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69e66-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="69e66-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69e66-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="69e66-109">Requirements</span></span>  

 <span data-ttu-id="69e66-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69e66-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69e66-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69e66-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69e66-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69e66-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69e66-113">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69e66-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e66-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69e66-114">See also</span></span>

- [<span data-ttu-id="69e66-115">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="69e66-115">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="69e66-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="69e66-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
