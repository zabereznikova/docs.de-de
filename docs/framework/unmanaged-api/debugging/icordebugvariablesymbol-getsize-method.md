---
title: ICorDebugVariableSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: 6d60dbdefd09770fd5a18653c5118469323581e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790902"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="71897-102">ICorDebugVariableSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="71897-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="71897-103">Ruft die Größe einer Variablen in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="71897-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71897-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71897-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71897-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="71897-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="71897-106">Ein Zeiger auf eine 32-Bit-Ganzzahl ohne Vorzeichen, die die Größe der Variablen enthält.</span><span class="sxs-lookup"><span data-stu-id="71897-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71897-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71897-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71897-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="71897-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71897-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="71897-109">Requirements</span></span>  
 <span data-ttu-id="71897-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71897-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71897-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71897-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71897-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71897-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71897-113">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71897-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71897-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71897-114">See also</span></span>

- [<span data-ttu-id="71897-115">ICorDebugVariableSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71897-115">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="71897-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="71897-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
