---
title: ICorDebugDataTarget2::GetImageFromPointer-Methode
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5dab9183075f563f52a4fc982eda5cb172556554
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154374"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="0414d-102">ICorDebugDataTarget2::GetImageFromPointer-Methode</span><span class="sxs-lookup"><span data-stu-id="0414d-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="0414d-103">Gibt die Basisadresse des Moduls und die Größe von einer Adresse in diesem Modul aus.</span><span class="sxs-lookup"><span data-stu-id="0414d-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0414d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0414d-104">Syntax</span></span>  
  
```  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0414d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0414d-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="0414d-106">Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) -Wert, der eine Adresse in einem Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="0414d-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="0414d-107">[out] Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) -Wert, der Basisadresse des Moduls darstellt.</span><span class="sxs-lookup"><span data-stu-id="0414d-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="0414d-108">Ein Zeiger auf die Modulgröße.</span><span class="sxs-lookup"><span data-stu-id="0414d-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0414d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0414d-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0414d-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0414d-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0414d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0414d-111">Requirements</span></span>  
 <span data-ttu-id="0414d-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0414d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0414d-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0414d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0414d-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0414d-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0414d-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="0414d-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0414d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0414d-116">See also</span></span>

- [<span data-ttu-id="0414d-117">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0414d-117">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="0414d-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="0414d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
