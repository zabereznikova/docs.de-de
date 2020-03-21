---
title: ICorDebugDataTarget2::GetImageFromPointer-Methode
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: 3ac1f8ab98583357a3aa622b5032d9ae121ebdf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178922"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="029fa-102">ICorDebugDataTarget2::GetImageFromPointer-Methode</span><span class="sxs-lookup"><span data-stu-id="029fa-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="029fa-103">Gibt die Basisadresse des Moduls und die Größe von einer Adresse in diesem Modul aus.</span><span class="sxs-lookup"><span data-stu-id="029fa-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="029fa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="029fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,
   [out] CORDB_ADDRESS *pImageBase,
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="029fa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="029fa-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="029fa-106">Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) Wert, der eine Adresse in einem Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="029fa-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="029fa-107">[out] Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) Wert, der die Basisadresse des Moduls darstellt.</span><span class="sxs-lookup"><span data-stu-id="029fa-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="029fa-108">Ein Zeiger auf die Modulgröße.</span><span class="sxs-lookup"><span data-stu-id="029fa-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="029fa-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="029fa-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="029fa-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="029fa-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="029fa-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="029fa-111">Requirements</span></span>  
 <span data-ttu-id="029fa-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="029fa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="029fa-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="029fa-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="029fa-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="029fa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="029fa-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="029fa-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="029fa-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="029fa-116">See also</span></span>

- [<span data-ttu-id="029fa-117">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="029fa-117">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="029fa-118">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="029fa-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
