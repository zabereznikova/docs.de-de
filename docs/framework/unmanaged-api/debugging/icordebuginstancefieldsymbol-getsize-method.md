---
title: ICorDebugInstanceFieldSymbol::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: 3d3c6881ecd54fc48be92e5ea0dc74a5cfdabd8f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209952"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="05d70-102">ICorDebugInstanceFieldSymbol::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="05d70-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="05d70-103">Ruft die Größe des Instanzfelds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="05d70-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05d70-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05d70-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05d70-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="05d70-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="05d70-106">[out] Ein Zeiger auf die Länge des Felds.</span><span class="sxs-lookup"><span data-stu-id="05d70-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05d70-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="05d70-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="05d70-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="05d70-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05d70-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="05d70-109">Requirements</span></span>  
 <span data-ttu-id="05d70-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05d70-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05d70-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05d70-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05d70-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05d70-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05d70-113">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05d70-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d70-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05d70-114">See also</span></span>

- [<span data-ttu-id="05d70-115">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05d70-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="05d70-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="05d70-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
