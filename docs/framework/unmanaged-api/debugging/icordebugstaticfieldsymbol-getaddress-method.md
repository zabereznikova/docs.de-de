---
title: ICorDebugStaticFieldSymbol::GetAddress-Methode
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: 7b8072234df172eeafd77db90287ea3319c08ec7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378764"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="334f3-102">ICorDebugStaticFieldSymbol::GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="334f3-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="334f3-103">Ruft die Adresse eines statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="334f3-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="334f3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="334f3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="334f3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="334f3-105">Parameters</span></span>  
 <span data-ttu-id="334f3-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="334f3-106">pRVA</span></span>  
 <span data-ttu-id="334f3-107">[out] Ein Zeiger auf die relative virtuelle Adresse (RVA) des statischen Felds.</span><span class="sxs-lookup"><span data-stu-id="334f3-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="334f3-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="334f3-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="334f3-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="334f3-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="334f3-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="334f3-110">Requirements</span></span>  
 <span data-ttu-id="334f3-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="334f3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="334f3-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="334f3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="334f3-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="334f3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="334f3-114">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="334f3-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="334f3-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="334f3-115">See also</span></span>

- [<span data-ttu-id="334f3-116">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="334f3-116">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="334f3-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="334f3-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
