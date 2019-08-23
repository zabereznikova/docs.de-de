---
title: ICorDebugDataTarget2::GetSymbolProviderForImage-Methode
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e5a6e70d5148756a5ed8d17c56577da920d1b69
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69911449"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="c18dd-102">ICorDebugDataTarget2::GetSymbolProviderForImage-Methode</span><span class="sxs-lookup"><span data-stu-id="c18dd-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="c18dd-103">Gibt anhand der Basisadresse des Moduls den Symbol-Anbieter für ein Modul aus.</span><span class="sxs-lookup"><span data-stu-id="c18dd-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c18dd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c18dd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,   
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c18dd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c18dd-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="c18dd-106">in Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) -Wert, der die Basisadresse eines Moduls darstellt.</span><span class="sxs-lookup"><span data-stu-id="c18dd-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="c18dd-107">vorgenommen Ein Zeiger auf die Adresse eines [icorentbugsymbolprovider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) -Objekts.</span><span class="sxs-lookup"><span data-stu-id="c18dd-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c18dd-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c18dd-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c18dd-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c18dd-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c18dd-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c18dd-110">Requirements</span></span>  
 <span data-ttu-id="c18dd-111">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c18dd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c18dd-112">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="c18dd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c18dd-113">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c18dd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c18dd-114">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c18dd-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c18dd-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c18dd-115">See also</span></span>

- [<span data-ttu-id="c18dd-116">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c18dd-116">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="c18dd-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c18dd-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
