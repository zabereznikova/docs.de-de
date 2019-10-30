---
title: ICorDebugDataTarget2::GetImageLocation-Methode
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: 8b873e28bfab31ea18924f471f916475efd345d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122126"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="ee150-102">ICorDebugDataTarget2::GetImageLocation-Methode</span><span class="sxs-lookup"><span data-stu-id="ee150-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="ee150-103">Gibt den Pfad eines Moduls aus der Basisadresse des Moduls zurück.</span><span class="sxs-lookup"><span data-stu-id="ee150-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee150-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee150-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee150-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ee150-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="ee150-106">in Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) -Wert, der die Basisadresse des Moduls darstellt.</span><span class="sxs-lookup"><span data-stu-id="ee150-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ee150-107">[in] Die Anzahl der Zeichen im Puffer, die den Modulpfad erhalten sollen.</span><span class="sxs-lookup"><span data-stu-id="ee150-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="ee150-108">[out] Ein Zeiger auf die Anzahl der in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ee150-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="ee150-109">[out] Der Pfad des Moduls.</span><span class="sxs-lookup"><span data-stu-id="ee150-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee150-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee150-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee150-111">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ee150-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee150-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee150-112">Requirements</span></span>  
 <span data-ttu-id="ee150-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee150-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee150-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee150-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee150-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee150-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee150-116">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee150-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee150-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee150-117">See also</span></span>

- [<span data-ttu-id="ee150-118">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ee150-118">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="ee150-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ee150-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
