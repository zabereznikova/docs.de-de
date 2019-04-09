---
title: ICorDebugDataTarget2::GetSymbolProviderForImage-Methode
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cda49084c9453f79727f7f57ef152577cb4d7c5d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171963"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="e8d62-102">ICorDebugDataTarget2::GetSymbolProviderForImage-Methode</span><span class="sxs-lookup"><span data-stu-id="e8d62-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="e8d62-103">Gibt anhand der Basisadresse des Moduls den Symbol-Anbieter für ein Modul aus.</span><span class="sxs-lookup"><span data-stu-id="e8d62-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8d62-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8d62-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,   
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8d62-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e8d62-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="e8d62-106">[in] Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) Wert, der die Basisadresse eines Moduls darstellt.</span><span class="sxs-lookup"><span data-stu-id="e8d62-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="e8d62-107">[out] Ein Zeiger auf die Adresse einer [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="e8d62-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8d62-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8d62-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8d62-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e8d62-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8d62-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8d62-110">Requirements</span></span>  
 <span data-ttu-id="e8d62-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8d62-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8d62-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8d62-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8d62-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8d62-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e8d62-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e8d62-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e8d62-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8d62-115">See also</span></span>

- [<span data-ttu-id="e8d62-116">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8d62-116">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="e8d62-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e8d62-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
