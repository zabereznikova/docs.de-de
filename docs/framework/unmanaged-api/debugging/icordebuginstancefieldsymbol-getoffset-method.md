---
title: ICorDebugInstanceFieldSymbol::GetOffset-Methode
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8e78a7358f62ab83c7ecba63eac9f021fc4932d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636373"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="35849-102">ICorDebugInstanceFieldSymbol::GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="35849-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>
<span data-ttu-id="35849-103">Ruft den Offset dieses Instanzenfelds in der übergeordneten Klasse in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="35849-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35849-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35849-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35849-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="35849-105">Parameters</span></span>  
 `pcbOffset`  
 <span data-ttu-id="35849-106">Ein Zeiger auf die Anzahl der Bytes, die der Offset dieses Instanzenfelds in der übergeordneten Klasse aufweist.</span><span class="sxs-lookup"><span data-stu-id="35849-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35849-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="35849-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35849-108">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="35849-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35849-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="35849-109">Requirements</span></span>  
 <span data-ttu-id="35849-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35849-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35849-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35849-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35849-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35849-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35849-113">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35849-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35849-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35849-114">See also</span></span>
- [<span data-ttu-id="35849-115">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35849-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="35849-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="35849-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
