---
title: ICorDebugMemoryBuffer::GetStartAddress-Methode
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: f76bf1479db987e4956d8b876f67d629d927f956
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710757"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="4a967-102">ICorDebugMemoryBuffer::GetStartAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="4a967-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>

<span data-ttu-id="4a967-103">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="4a967-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a967-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a967-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a967-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4a967-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="4a967-106">[out] Ein Zeiger auf die Startadresse des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="4a967-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a967-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4a967-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="4a967-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4a967-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a967-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4a967-109">Requirements</span></span>  

 <span data-ttu-id="4a967-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a967-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a967-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a967-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a967-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a967-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a967-113">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a967-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a967-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a967-114">See also</span></span>

- [<span data-ttu-id="4a967-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a967-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="4a967-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4a967-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
