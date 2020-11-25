---
title: ICorDebugInstanceFieldSymbol::GetOffset-Methode
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: 2d73de46bbb1023f20dd9023076630611c74be5d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724922"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="e9b76-102">ICorDebugInstanceFieldSymbol::GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="e9b76-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>

<span data-ttu-id="e9b76-103">Ruft den Offset dieses Instanzenfelds in der übergeordneten Klasse in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="e9b76-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9b76-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9b76-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9b76-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9b76-105">Parameters</span></span>  

 `pcbOffset`  
 <span data-ttu-id="e9b76-106">Ein Zeiger auf die Anzahl der Bytes, die der Offset dieses Instanzenfelds in der übergeordneten Klasse aufweist.</span><span class="sxs-lookup"><span data-stu-id="e9b76-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9b76-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9b76-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9b76-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e9b76-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9b76-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e9b76-109">Requirements</span></span>  

 <span data-ttu-id="e9b76-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9b76-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9b76-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9b76-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9b76-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9b76-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9b76-113">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9b76-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9b76-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9b76-114">See also</span></span>

- [<span data-ttu-id="e9b76-115">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9b76-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="e9b76-116">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e9b76-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
