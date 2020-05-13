---
title: ICorDebugMergedAssemblyRecord::GetCulture-Methode
ms.date: 03/30/2017
ms.assetid: 030b2f8c-8c21-40b7-855d-3afa78975a17
ms.openlocfilehash: f73aac169cc048a87aca3bfc325cf8c6243012e9
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207860"
---
# <a name="icordebugmergedassemblyrecordgetculture-method"></a><span data-ttu-id="c5b00-102">ICorDebugMergedAssemblyRecord::GetCulture-Methode</span><span class="sxs-lookup"><span data-stu-id="c5b00-102">ICorDebugMergedAssemblyRecord::GetCulture Method</span></span>
<span data-ttu-id="c5b00-103">Ruft die Kulturnamen-Zeichenfolge der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="c5b00-103">Gets the culture name string of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5b00-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5b00-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCulture(  
   [in] ULONG32 cchCulture,
   [out] ULONG32 *pcchCulture,
   [out, size_is(cchCulture), length_is(*pcchCulture)] WCHAR szCulture[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5b00-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c5b00-105">Parameters</span></span>  
 `cchCulture`  
 <span data-ttu-id="c5b00-106">[in] Die Anzahl der Zeichen im `szCulture`-Puffer.</span><span class="sxs-lookup"><span data-stu-id="c5b00-106">[in] The number of characters in the `szCulture` buffer.</span></span>  
  
 `pcchCulture`  
 <span data-ttu-id="c5b00-107">[out] Die Anzahl der tatsächlich in den `szCulture`-Puffer geschriebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="c5b00-107">[out] The number of characters actually written to the `szCulture` buffer.</span></span>  
  
 `szCulture`  
 <span data-ttu-id="c5b00-108">[out] Ein Zeichenarray, das den Kulturnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="c5b00-108">[out] A character array that contains the culture name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5b00-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5b00-109">Remarks</span></span>  
 <span data-ttu-id="c5b00-110">Der Kulturname ist eine eindeutige Zeichenfolge, die eine Kultur identifiziert, z. B. "en-US" (für die Kultur Englisch (USA)), oder "neutral" (für eine neutrale Kultur).</span><span class="sxs-lookup"><span data-stu-id="c5b00-110">The culture name is a unique string that identifies a culture, such as "en-US" (for the English (United States) culture), or "neutral" (for a neutral culture).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c5b00-111">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c5b00-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5b00-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c5b00-112">Requirements</span></span>  
 <span data-ttu-id="c5b00-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5b00-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5b00-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5b00-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5b00-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5b00-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5b00-116">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5b00-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b00-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5b00-117">See also</span></span>

- [<span data-ttu-id="c5b00-118">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c5b00-118">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="c5b00-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c5b00-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
