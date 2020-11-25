---
title: ICorDebugProcess2::GetReferenceValueFromGCHandle-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
ms.openlocfilehash: a5b9d57aab834ba3ca72a2ea8576ec70cd88eb77
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713573"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="bae61-102">ICorDebugProcess2::GetReferenceValueFromGCHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="bae61-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>

<span data-ttu-id="bae61-103">Ruft einen Verweis Zeiger auf das angegebene verwaltete Objekt ab, das über ein Garbage Collection Handle verfügt.</span><span class="sxs-lookup"><span data-stu-id="bae61-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bae61-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bae61-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bae61-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bae61-105">Parameters</span></span>  

 `handle`  
 <span data-ttu-id="bae61-106">in Ein Zeiger auf ein verwaltetes Objekt, das über ein Garbage Collection Handle verfügt.</span><span class="sxs-lookup"><span data-stu-id="bae61-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="bae61-107">Dieser Wert ist ein <xref:System.IntPtr> -Objekt und kann vom <xref:System.Runtime.InteropServices.GCHandle> für das verwaltete Objekt abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bae61-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="bae61-108">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugReferenceValue-Objekts, das einen Verweis auf das angegebene verwaltete Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="bae61-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bae61-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bae61-109">Remarks</span></span>  

 <span data-ttu-id="bae61-110">Verwechseln Sie den zurückgegebenen Verweis Wert nicht mit einem Garbage Collection Verweis Wert.</span><span class="sxs-lookup"><span data-stu-id="bae61-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="bae61-111">Der zurückgegebene Verweis verhält sich wie ein normaler Verweis.</span><span class="sxs-lookup"><span data-stu-id="bae61-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="bae61-112">Diese Option ist deaktiviert, wenn die Codeausführung nach einem Breakpoint fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="bae61-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="bae61-113">Die Lebensdauer des Zielobjekts wird von der Lebensdauer des Verweis Werts nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="bae61-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bae61-114">Die- `GetReferenceValueFromGCHandle` Methode validiert das Handle nicht.</span><span class="sxs-lookup"><span data-stu-id="bae61-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="bae61-115">Daher kann die `GetReferenceValueFromGCHandle` -Methode den Debugger und den Code, der debuggt wird, potenziell beschädigen, wenn ein ungültiges Handle übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="bae61-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bae61-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bae61-116">Requirements</span></span>  

 <span data-ttu-id="bae61-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bae61-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bae61-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bae61-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bae61-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bae61-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bae61-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bae61-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
