---
title: ICorDebugMergedAssemblyRecord::GetIndex-Methode
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: 3056d22f5ddc1b11b79ee072aba68ce3ad40e8da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710635"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="429f7-102">ICorDebugMergedAssemblyRecord::GetIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="429f7-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>

<span data-ttu-id="429f7-103">Ruft den Präfixindex der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="429f7-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="429f7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="429f7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="429f7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="429f7-105">Parameters</span></span>  

 `pIndex`  
 <span data-ttu-id="429f7-106">[out] Ein Zeiger auf den Präfixindex.</span><span class="sxs-lookup"><span data-stu-id="429f7-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="429f7-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="429f7-107">Remarks</span></span>  

 <span data-ttu-id="429f7-108">Der Präfixindex wird verwendet, um Namenskonflikte in den zusammengeführten Namen der Metadatentypen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="429f7-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="429f7-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="429f7-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="429f7-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="429f7-110">Requirements</span></span>  

 <span data-ttu-id="429f7-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="429f7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="429f7-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="429f7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="429f7-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="429f7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="429f7-114">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="429f7-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="429f7-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="429f7-115">See also</span></span>

- [<span data-ttu-id="429f7-116">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="429f7-116">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="429f7-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="429f7-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
