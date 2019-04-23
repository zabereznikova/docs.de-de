---
title: ICorDebugProcess6::GetExportStepInfo-Methode
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44a891e6d65d159875f5607ac33b0668414cb380
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137214"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="5fa9e-102">ICorDebugProcess6::GetExportStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="5fa9e-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="5fa9e-103">Enthält Informationen über die exportierten Laufzeitfunktionen, welche dabei helfen, den verwaltetem Code schrittweise durchzugehen.</span><span class="sxs-lookup"><span data-stu-id="5fa9e-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fa9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5fa9e-104">Syntax</span></span>  
  
```  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fa9e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5fa9e-105">Parameters</span></span>  
 <span data-ttu-id="5fa9e-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="5fa9e-106">pszExportName</span></span>  
 <span data-ttu-id="5fa9e-107">[in] Der Name einer Laufzeit-Exportfunktion wie in der PE-Exporttabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="5fa9e-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="5fa9e-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="5fa9e-108">invokeKind</span></span>  
 <span data-ttu-id="5fa9e-109">[out] Ein Zeiger auf ein Mitglied der [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) Enumeration, die beschreibt, wie die exportierte Funktion verwalteter Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5fa9e-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="5fa9e-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="5fa9e-110">invokePurpose</span></span>  
 <span data-ttu-id="5fa9e-111">[out] Ein Zeiger auf ein Mitglied der [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) Enumeration, die beschreibt, warum die exportierte Funktion verwalteter Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5fa9e-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5fa9e-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5fa9e-112">Return Value</span></span>  
 <span data-ttu-id="5fa9e-113">Diese Methode kann die in der folgenden Tabelle aufgeführten Werte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="5fa9e-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="5fa9e-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5fa9e-114">Return value</span></span>|<span data-ttu-id="5fa9e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5fa9e-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="5fa9e-116">Der Methodenaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="5fa9e-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="5fa9e-117">`pInvokeKind` oder `pInvokePurpose` ist **null**.</span><span class="sxs-lookup"><span data-stu-id="5fa9e-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="5fa9e-118">Andere fehlerhafte `HRESULT`-Werte.</span><span class="sxs-lookup"><span data-stu-id="5fa9e-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="5fa9e-119">Gegebenenfalls.</span><span class="sxs-lookup"><span data-stu-id="5fa9e-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fa9e-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5fa9e-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fa9e-121">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5fa9e-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fa9e-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5fa9e-122">Requirements</span></span>  
 <span data-ttu-id="5fa9e-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fa9e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fa9e-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fa9e-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fa9e-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fa9e-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fa9e-126">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fa9e-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fa9e-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fa9e-127">See also</span></span>

- [<span data-ttu-id="5fa9e-128">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5fa9e-128">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="5fa9e-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5fa9e-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
