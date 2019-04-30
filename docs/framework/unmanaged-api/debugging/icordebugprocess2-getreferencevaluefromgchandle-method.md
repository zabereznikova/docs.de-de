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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08bf4022f7cd7f85ffe7939c16fd47950e131a77
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948901"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a><span data-ttu-id="5e616-102">ICorDebugProcess2::GetReferenceValueFromGCHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="5e616-102">ICorDebugProcess2::GetReferenceValueFromGCHandle Method</span></span>
<span data-ttu-id="5e616-103">Ruft einen Verweiszeiger auf das angegebene verwaltete Objekt, das eine Garbagecollection verarbeitet hat.</span><span class="sxs-lookup"><span data-stu-id="5e616-103">Gets a reference pointer to the specified managed object that has a garbage collection handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e616-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e616-104">Syntax</span></span>  
  
```  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e616-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5e616-105">Parameters</span></span>  
 `handle`  
 <span data-ttu-id="5e616-106">[in] Ein Zeiger auf ein verwaltetes Objekt, das eine Garbage Collection-Handle verfügt.</span><span class="sxs-lookup"><span data-stu-id="5e616-106">[in] A pointer to a managed object that has a garbage collection handle.</span></span> <span data-ttu-id="5e616-107">Dieser Wert ist eine <xref:System.IntPtr> Objekt abgerufen werden können, und wählen Sie die <xref:System.Runtime.InteropServices.GCHandle> für das verwaltete Objekt.</span><span class="sxs-lookup"><span data-stu-id="5e616-107">This value is a <xref:System.IntPtr> object and can be retrieved from the <xref:System.Runtime.InteropServices.GCHandle> for the managed object.</span></span>  
  
 `pOutValue`  
 <span data-ttu-id="5e616-108">[out] Ein Zeiger auf die Adresse des ein ICorDebugReferenceValue-Objekt, das einen Verweis auf das angegebene verwaltete Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="5e616-108">[out] A pointer to the address of an ICorDebugReferenceValue object that represents a reference to the specified managed object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e616-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e616-109">Remarks</span></span>  
 <span data-ttu-id="5e616-110">Verwechseln Sie nicht den Wert der zurückgegebene Verweis mit einem Garbage Collection-Verweis-Wert.</span><span class="sxs-lookup"><span data-stu-id="5e616-110">Do not confuse the returned reference value with a garbage collection reference value.</span></span>  
  
 <span data-ttu-id="5e616-111">Der zurückgegebene Verweis verhält sich wie ein normaler Verweis.</span><span class="sxs-lookup"><span data-stu-id="5e616-111">The returned reference behaves like a normal reference.</span></span> <span data-ttu-id="5e616-112">Es ist deaktiviert, wenn die Ausführung von Code nach einem Haltepunkt fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="5e616-112">It is disabled when code execution continues after a breakpoint.</span></span> <span data-ttu-id="5e616-113">Die Lebensdauer des Zielobjekts ist von der Lebensdauer der Verweiswert nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="5e616-113">The lifetime of the target object is not affected by the lifetime of the reference value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e616-114">Die `GetReferenceValueFromGCHandle` Methode überprüft nicht das Handle.</span><span class="sxs-lookup"><span data-stu-id="5e616-114">The `GetReferenceValueFromGCHandle` method does not validate the handle.</span></span> <span data-ttu-id="5e616-115">Aus diesem Grund die `GetReferenceValueFromGCHandle` Methode kann möglicherweise beschädigt, den Debugger und der Code gedebuggt wird, wenn ein ungültiges Handle übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="5e616-115">Therefore, the `GetReferenceValueFromGCHandle` method can potentially corrupt both the debugger and the code being debugged if an invalid handle is passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e616-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5e616-116">Requirements</span></span>  
 <span data-ttu-id="5e616-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e616-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e616-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e616-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e616-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e616-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e616-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e616-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
