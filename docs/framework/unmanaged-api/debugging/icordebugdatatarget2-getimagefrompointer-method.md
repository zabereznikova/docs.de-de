---
title: ICorDebugDataTarget2::GetImageFromPointer-Methode
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 72bad186bc8bb198a8c5b05fffcc0b2b6544482f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472420"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="6f182-102">ICorDebugDataTarget2::GetImageFromPointer-Methode</span><span class="sxs-lookup"><span data-stu-id="6f182-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="6f182-103">Gibt die Basisadresse des Moduls und die Größe von einer Adresse in diesem Modul aus.</span><span class="sxs-lookup"><span data-stu-id="6f182-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f182-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f182-104">Syntax</span></span>  
  
```  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f182-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f182-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="6f182-106">Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) -Wert, der eine Adresse in einem Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="6f182-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="6f182-107">[out] Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) -Wert, der Basisadresse des Moduls darstellt.</span><span class="sxs-lookup"><span data-stu-id="6f182-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="6f182-108">Ein Zeiger auf die Modulgröße.</span><span class="sxs-lookup"><span data-stu-id="6f182-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f182-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6f182-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f182-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6f182-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f182-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6f182-111">Requirements</span></span>  
 <span data-ttu-id="6f182-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f182-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f182-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f182-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f182-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f182-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f182-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f182-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f182-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f182-116">See also</span></span>
- [<span data-ttu-id="6f182-117">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f182-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="6f182-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6f182-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
