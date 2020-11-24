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
ms.openlocfilehash: 575e194cf952f02a3fe4fce9e955e45e1bc3653d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673912"
---
# <a name="closeclrenumeration-function"></a><span data-ttu-id="6dc49-102">CloseCLREnumeration-Funktion</span><span class="sxs-lookup"><span data-stu-id="6dc49-102">CloseCLREnumeration Function</span></span>

<span data-ttu-id="6dc49-103">Schließt alle gültigen Common Language Runtime (CLR) Continue-Startup-Ereignisse in einem Array von Handles, die von der [enumerateclrs-Funktion](enumerateclrs-function.md)zurückgegeben werden, und gibt den Arbeitsspeicher für das Handle und die Zeichen folgen Pfad Arrays frei.</span><span class="sxs-lookup"><span data-stu-id="6dc49-103">Closes any valid common language runtime (CLR) continue-startup events located in an array of handles returned by the [EnumerateCLRs function](enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dc49-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6dc49-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6dc49-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6dc49-105">Parameters</span></span>  

 `pHandleArray`  
 <span data-ttu-id="6dc49-106">in Ein Zeiger auf das Array von Ereignis Handles, die von der [enumerateclrs-Funktion](enumerateclrs-function.md)zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6dc49-106">[in] Pointer to the array of event handles returned from the [EnumerateCLRs function](enumerateclrs-function.md).</span></span>  
  
 `pStringArray`  
 <span data-ttu-id="6dc49-107">in Ein Zeiger auf das Array von CLR-Zeichen folgen Pfaden, die von der [enumerateclrs-Funktion](enumerateclrs-function.md)zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6dc49-107">[in] Pointer to the array of CLR string paths returned from the [EnumerateCLRs function](enumerateclrs-function.md).</span></span>  
  
 `dwArrayLength`  
 <span data-ttu-id="6dc49-108">[in] DWORD, das die Größe (Länge) von `pHandleArray` oder `pStringArray` enthält (diese sind identisch).</span><span class="sxs-lookup"><span data-stu-id="6dc49-108">[in] DWORD that contains the size (length) of either `pHandleArray` or `pStringArray` (they are the same).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6dc49-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6dc49-109">Return Value</span></span>  

 <span data-ttu-id="6dc49-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6dc49-110">S_OK</span></span>  
 <span data-ttu-id="6dc49-111">Handles, die von der [enumerateclrs-Funktion](enumerateclrs-function.md) geöffnet werden, werden geschlossen, und für das Handle-und Zeichen folgen Arrays zugeordnete Arbeitsspeicher wird freigegeben</span><span class="sxs-lookup"><span data-stu-id="6dc49-111">Handles opened by the [EnumerateCLRs function](enumerateclrs-function.md) are closed, and memory allocated for the handle and string arrays is freed.</span></span>  
  
 <span data-ttu-id="6dc49-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6dc49-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="6dc49-113">Die Länge von `pHandleArray` stimmt nicht mit der Länge überein, die in `dwArrayLength` übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="6dc49-113">The length of `pHandleArray` does not match the length that is passed in `dwArrayLength`.</span></span>  
  
 <span data-ttu-id="6dc49-114">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="6dc49-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="6dc49-115">Die Funktion kann den Arbeitsspeicher für `pHandleArray` und `pStringArray` nicht freigeben.</span><span class="sxs-lookup"><span data-stu-id="6dc49-115">The function is unable to free the memory for `pHandleArray` and `pStringArray`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dc49-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6dc49-116">Requirements</span></span>  

 <span data-ttu-id="6dc49-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dc49-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dc49-118">**Header:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="6dc49-118">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="6dc49-119">**Bibliothek:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="6dc49-119">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="6dc49-120">**.NET Framework Versionen:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="6dc49-120">**.NET Framework Versions:** 3.5 SP1</span></span>
