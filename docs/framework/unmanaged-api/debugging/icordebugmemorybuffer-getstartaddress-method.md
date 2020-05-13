---
title: ICorDebugMemoryBuffer::GetStartAddress-Methode
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: 47369c744ee42fb03857a3e69063a04e4f509d0d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212346"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="eac29-102">ICorDebugMemoryBuffer::GetStartAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="eac29-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="eac29-103">Ruft die Startadresse des Speicherpuffers ab.</span><span class="sxs-lookup"><span data-stu-id="eac29-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eac29-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eac29-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eac29-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eac29-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="eac29-106">[out] Ein Zeiger auf die Startadresse des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="eac29-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eac29-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eac29-107">Remarks</span></span>  
  
> [!WARNING]
> <span data-ttu-id="eac29-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eac29-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eac29-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="eac29-109">Requirements</span></span>  
 <span data-ttu-id="eac29-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eac29-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eac29-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eac29-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eac29-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eac29-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eac29-113">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eac29-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eac29-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eac29-114">See also</span></span>

- [<span data-ttu-id="eac29-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eac29-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="eac29-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="eac29-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
