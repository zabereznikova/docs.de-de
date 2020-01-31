---
title: ICorDebugDataTarget2::GetImageFromPointer-Methode
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: 55c87731399cf1e7a6747720b8bb33de7e01906c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788845"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="53451-102">ICorDebugDataTarget2::GetImageFromPointer-Methode</span><span class="sxs-lookup"><span data-stu-id="53451-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="53451-103">Gibt die Basisadresse des Moduls und die Größe von einer Adresse in diesem Modul aus.</span><span class="sxs-lookup"><span data-stu-id="53451-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53451-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53451-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,   
   [out] CORDB_ADDRESS *pImageBase,   
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53451-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="53451-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="53451-106">Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) Wert, der eine Adresse in einem Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="53451-106">A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="53451-107">vorgenommen Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) Wert, der die Basisadresse des Moduls darstellt.</span><span class="sxs-lookup"><span data-stu-id="53451-107">[out] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="53451-108">Ein Zeiger auf die Modulgröße.</span><span class="sxs-lookup"><span data-stu-id="53451-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53451-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="53451-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53451-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="53451-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53451-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="53451-111">Requirements</span></span>  
 <span data-ttu-id="53451-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53451-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53451-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53451-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53451-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53451-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53451-115">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53451-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53451-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53451-116">See also</span></span>

- [<span data-ttu-id="53451-117">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53451-117">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="53451-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="53451-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
