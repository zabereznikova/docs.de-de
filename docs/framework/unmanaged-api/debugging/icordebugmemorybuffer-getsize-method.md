---
title: ICorDebugMemoryBuffer::GetSize-Methode
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
ms.openlocfilehash: 7f5458dd12ca83c1a5190bbf7fab0f8e5d06a0e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710756"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="cffa5-102">ICorDebugMemoryBuffer::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="cffa5-102">ICorDebugMemoryBuffer::GetSize Method</span></span>

<span data-ttu-id="cffa5-103">Ruft die Größe des Speicherpuffers in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="cffa5-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cffa5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cffa5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cffa5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cffa5-105">Parameters</span></span>  

 `pcbBufferLength`  
 <span data-ttu-id="cffa5-106">[out] Ein Zeiger auf die Größe des Speicherpuffers.</span><span class="sxs-lookup"><span data-stu-id="cffa5-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cffa5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cffa5-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cffa5-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cffa5-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cffa5-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cffa5-109">Requirements</span></span>  

 <span data-ttu-id="cffa5-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cffa5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cffa5-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cffa5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cffa5-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cffa5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cffa5-113">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cffa5-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cffa5-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cffa5-114">See also</span></span>

- [<span data-ttu-id="cffa5-115">ICorDebugMemoryBuffer-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cffa5-115">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="cffa5-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="cffa5-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
