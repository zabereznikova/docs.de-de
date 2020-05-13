---
title: ICorDebugMemoryBuffer::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 1bef2e2d0e1a1cef74c7568fdd2e9b7986500488
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212604"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="28a55-102">ICorDebugMemoryBuffer::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="28a55-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="28a55-103">Ruft die Größe des Speicherpuffers in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="28a55-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28a55-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="28a55-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28a55-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="28a55-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="28a55-106">[out] Ein Zeiger auf die Größe des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="28a55-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28a55-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="28a55-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="28a55-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="28a55-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28a55-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="28a55-109">Requirements</span></span>  
 <span data-ttu-id="28a55-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28a55-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28a55-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28a55-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28a55-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28a55-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28a55-113">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28a55-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28a55-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28a55-114">See also</span></span>

- [<span data-ttu-id="28a55-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28a55-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="28a55-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="28a55-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
