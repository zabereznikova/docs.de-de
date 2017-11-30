---
title: ICorDebugDataTarget2::GetImageFromPointer-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e56f65aea12c71145c99a9a195b910ef2876aa09
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="0a41b-102">ICorDebugDataTarget2::GetImageFromPointer-Methode</span><span class="sxs-lookup"><span data-stu-id="0a41b-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="0a41b-103">Gibt die Basisadresse des Moduls und die Größe von einer Adresse in diesem Modul aus.</span><span class="sxs-lookup"><span data-stu-id="0a41b-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a41b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a41b-104">Syntax</span></span>  
  
```  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a41b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0a41b-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="0a41b-106">Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) Wert, der eine Adresse in einem Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="0a41b-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="0a41b-107">[out] Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) Wert, der Basisadresse des Moduls darstellt.</span><span class="sxs-lookup"><span data-stu-id="0a41b-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="0a41b-108">Ein Zeiger auf die Modulgröße.</span><span class="sxs-lookup"><span data-stu-id="0a41b-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a41b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0a41b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a41b-110">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0a41b-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a41b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0a41b-111">Requirements</span></span>  
 <span data-ttu-id="0a41b-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a41b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a41b-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a41b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a41b-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a41b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a41b-115">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a41b-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a41b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a41b-116">See Also</span></span>  
 [<span data-ttu-id="0a41b-117">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a41b-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="0a41b-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="0a41b-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
