---
title: ICorDebugProcess6::GetExportStepInfo-Methode
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24c3c46a1f347093061983b9185234cc9959b68d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656140"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="c8af2-102">ICorDebugProcess6::GetExportStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="c8af2-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="c8af2-103">Enthält Informationen über die exportierten Laufzeitfunktionen, welche dabei helfen, den verwaltetem Code schrittweise durchzugehen.</span><span class="sxs-lookup"><span data-stu-id="c8af2-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8af2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8af2-104">Syntax</span></span>  
  
```  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8af2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c8af2-105">Parameters</span></span>  
 <span data-ttu-id="c8af2-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="c8af2-106">pszExportName</span></span>  
 <span data-ttu-id="c8af2-107">[in] Der Name einer Laufzeit-Exportfunktion wie in der PE-Exporttabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="c8af2-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="c8af2-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="c8af2-108">invokeKind</span></span>  
 <span data-ttu-id="c8af2-109">[out] Ein Zeiger auf ein Mitglied der [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) Enumeration, die beschreibt, wie die exportierte Funktion verwalteter Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c8af2-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="c8af2-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="c8af2-110">invokePurpose</span></span>  
 <span data-ttu-id="c8af2-111">[out] Ein Zeiger auf ein Mitglied der [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) Enumeration, die beschreibt, warum die exportierte Funktion verwalteter Code aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c8af2-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8af2-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c8af2-112">Return Value</span></span>  
 <span data-ttu-id="c8af2-113">Diese Methode kann die in der folgenden Tabelle aufgeführten Werte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c8af2-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="c8af2-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c8af2-114">Return value</span></span>|<span data-ttu-id="c8af2-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8af2-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="c8af2-116">Der Methodenaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="c8af2-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="c8af2-117">`pInvokeKind` oder `pInvokePurpose` ist **null**.</span><span class="sxs-lookup"><span data-stu-id="c8af2-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="c8af2-118">Andere fehlerhafte `HRESULT`-Werte.</span><span class="sxs-lookup"><span data-stu-id="c8af2-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="c8af2-119">Gegebenenfalls.</span><span class="sxs-lookup"><span data-stu-id="c8af2-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8af2-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8af2-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8af2-121">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c8af2-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8af2-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c8af2-122">Requirements</span></span>  
 <span data-ttu-id="c8af2-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8af2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8af2-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8af2-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8af2-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8af2-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8af2-126">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8af2-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8af2-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8af2-127">See also</span></span>
- [<span data-ttu-id="c8af2-128">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8af2-128">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="c8af2-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c8af2-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
