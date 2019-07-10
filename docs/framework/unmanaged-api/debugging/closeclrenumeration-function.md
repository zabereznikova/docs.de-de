---
title: CloseCLREnumeration-Funktion
ms.date: 03/30/2017
api_name:
- CloseCLREnumeration
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9eb9bb1e4abeb98d8d0ba2b052612d918c45f22
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741085"
---
# <a name="closeclrenumeration-function"></a><span data-ttu-id="d2630-102">CloseCLREnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="d2630-102">CloseCLREnumeration Function</span></span>
<span data-ttu-id="d2630-103">Schließt alle gültigen common Language Runtime (CLR) weiterhin-Starts Ereignisse befindet sich in einem Array von Handles, die vom der [EnumerateCLRs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), und den Speicher für den Pfad von Handle- und Zeichenfolgenarrays freigegeben.</span><span class="sxs-lookup"><span data-stu-id="d2630-103">Closes any valid common language runtime (CLR) continue-startup events located in an array of handles returned by the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2630-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2630-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2630-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2630-105">Parameters</span></span>  
 `pHandleArray`  
 <span data-ttu-id="d2630-106">[in] Zeiger auf das Array von Ereignishandles zurückgegeben wird, aus der [EnumerateCLRs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="d2630-106">[in] Pointer to the array of event handles returned from the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span></span>  
  
 `pStringArray`  
 <span data-ttu-id="d2630-107">[in] Zeiger auf das Array von CLR-Zeichenfolgenpfaden, die zurückgegeben werden, aus der [EnumerateCLRs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="d2630-107">[in] Pointer to the array of CLR string paths returned from the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span></span>  
  
 `dwArrayLength`  
 <span data-ttu-id="d2630-108">[in] DWORD, das die Größe (Länge) von `pHandleArray` oder `pStringArray` enthält (diese sind identisch).</span><span class="sxs-lookup"><span data-stu-id="d2630-108">[in] DWORD that contains the size (length) of either `pHandleArray` or `pStringArray` (they are the same).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2630-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d2630-109">Return Value</span></span>  
 <span data-ttu-id="d2630-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d2630-110">S_OK</span></span>  
 <span data-ttu-id="d2630-111">Handles geöffnet wird, indem die [EnumerateCLRs-Funktion](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) geschlossen werden, und für die Handle- und Zeichenfolgenarrays zugewiesenen Arbeitsspeicher wird freigegeben.</span><span class="sxs-lookup"><span data-stu-id="d2630-111">Handles opened by the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) are closed, and memory allocated for the handle and string arrays is freed.</span></span>  
  
 <span data-ttu-id="d2630-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d2630-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="d2630-113">Die Länge von `pHandleArray` stimmt nicht mit der Länge überein, die in `dwArrayLength` übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="d2630-113">The length of `pHandleArray` does not match the length that is passed in `dwArrayLength`.</span></span>  
  
 <span data-ttu-id="d2630-114">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="d2630-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="d2630-115">Die Funktion kann den Arbeitsspeicher für `pHandleArray` und `pStringArray` nicht freigeben.</span><span class="sxs-lookup"><span data-stu-id="d2630-115">The function is unable to free the memory for `pHandleArray` and `pStringArray`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2630-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2630-116">Requirements</span></span>  
 <span data-ttu-id="d2630-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2630-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2630-118">**Header:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="d2630-118">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="d2630-119">**Bibliothek:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="d2630-119">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="d2630-120">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="d2630-120">**.NET Framework Versions:** 3.5 SP1</span></span>
