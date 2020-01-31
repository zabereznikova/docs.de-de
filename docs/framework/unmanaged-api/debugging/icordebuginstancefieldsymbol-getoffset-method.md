---
title: ICorDebugInstanceFieldSymbol::GetOffset-Methode
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: f7c13d397b39698bdf1a22f14820680e1fd0a25f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782289"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="dcfed-102">ICorDebugInstanceFieldSymbol::GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="dcfed-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="dcfed-103">Ruft den Offset dieses Instanzenfelds in der übergeordneten Klasse in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="dcfed-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcfed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dcfed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcfed-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="dcfed-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="dcfed-106">Ein Zeiger auf die Anzahl der Bytes, die der Offset dieses Instanzenfelds in der übergeordneten Klasse aufweist.</span><span class="sxs-lookup"><span data-stu-id="dcfed-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcfed-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dcfed-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dcfed-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dcfed-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcfed-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dcfed-109">Requirements</span></span>  
 <span data-ttu-id="dcfed-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcfed-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcfed-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcfed-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcfed-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcfed-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcfed-113">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcfed-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcfed-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dcfed-114">See also</span></span>

- [<span data-ttu-id="dcfed-115">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dcfed-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="dcfed-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="dcfed-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
