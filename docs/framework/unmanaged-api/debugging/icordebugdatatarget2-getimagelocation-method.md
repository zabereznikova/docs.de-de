---
title: ICorDebugDataTarget2::GetImageLocation-Methode
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: c909b46a9bb70d23d1cd3a769ac24fcf58479308
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713794"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="86a01-102">ICorDebugDataTarget2::GetImageLocation-Methode</span><span class="sxs-lookup"><span data-stu-id="86a01-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>

<span data-ttu-id="86a01-103">Gibt den Pfad eines Moduls aus der Basisadresse des Moduls zurück.</span><span class="sxs-lookup"><span data-stu-id="86a01-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86a01-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="86a01-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86a01-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="86a01-105">Parameters</span></span>  

 `baseAddress`  
 <span data-ttu-id="86a01-106">in Ein [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) Wert, der die Basisadresse des Moduls darstellt.</span><span class="sxs-lookup"><span data-stu-id="86a01-106">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="86a01-107">[in] Die Anzahl der Zeichen im Puffer, die den Modulpfad erhalten sollen.</span><span class="sxs-lookup"><span data-stu-id="86a01-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="86a01-108">[out] Ein Zeiger auf die Anzahl der in den `szName`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="86a01-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="86a01-109">[out] Der Pfad des Moduls.</span><span class="sxs-lookup"><span data-stu-id="86a01-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86a01-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="86a01-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="86a01-111">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="86a01-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86a01-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="86a01-112">Requirements</span></span>  

 <span data-ttu-id="86a01-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86a01-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86a01-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86a01-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86a01-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86a01-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86a01-116">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86a01-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86a01-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="86a01-117">See also</span></span>

- [<span data-ttu-id="86a01-118">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="86a01-118">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="86a01-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="86a01-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
