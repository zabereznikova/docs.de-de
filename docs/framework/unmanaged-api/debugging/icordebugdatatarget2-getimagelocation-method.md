---
title: ICorDebugDataTarget2::GetImageLocation-Methode
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7acf08262c73df00a96cfb5c244cdfc352e51ea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080475"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="00853-102">ICorDebugDataTarget2::GetImageLocation-Methode</span><span class="sxs-lookup"><span data-stu-id="00853-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="00853-103">Gibt den Pfad eines Moduls aus der Basisadresse des Moduls zurück.</span><span class="sxs-lookup"><span data-stu-id="00853-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00853-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="00853-104">Syntax</span></span>  
  
```  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00853-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="00853-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="00853-106">[in] Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) -Wert, der Basisadresse des Moduls darstellt.</span><span class="sxs-lookup"><span data-stu-id="00853-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="00853-107">[in] Die Anzahl der Zeichen im Puffer, die den Modulpfad erhalten sollen.</span><span class="sxs-lookup"><span data-stu-id="00853-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="00853-108">[out] Ein Zeiger auf die Anzahl der in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="00853-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="00853-109">[out] Der Pfad des Moduls.</span><span class="sxs-lookup"><span data-stu-id="00853-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00853-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00853-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00853-111">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="00853-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00853-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00853-112">Requirements</span></span>  
 <span data-ttu-id="00853-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00853-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00853-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00853-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00853-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00853-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="00853-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="00853-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="00853-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00853-117">See also</span></span>

- [<span data-ttu-id="00853-118">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="00853-118">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="00853-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="00853-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
