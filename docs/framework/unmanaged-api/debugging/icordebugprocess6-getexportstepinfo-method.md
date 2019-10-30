---
title: ICorDebugProcess6::GetExportStepInfo-Methode
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: d92b05e3d84a230e87901378f34ed27ac38286b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123457"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="a965b-102">ICorDebugProcess6::GetExportStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="a965b-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="a965b-103">Enthält Informationen über die exportierten Laufzeitfunktionen, welche dabei helfen, den verwaltetem Code schrittweise durchzugehen.</span><span class="sxs-lookup"><span data-stu-id="a965b-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a965b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a965b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a965b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a965b-105">Parameters</span></span>  
 <span data-ttu-id="a965b-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="a965b-106">pszExportName</span></span>  
 <span data-ttu-id="a965b-107">[in] Der Name einer Laufzeit-Exportfunktion wie in der PE-Exporttabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="a965b-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="a965b-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="a965b-108">invokeKind</span></span>  
 <span data-ttu-id="a965b-109">vorgenommen Ein Zeiger auf einen Member der [cordebugcodeinvokekind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) -Enumeration, der beschreibt, wie die exportierte Funktion verwalteten Code aufruft.</span><span class="sxs-lookup"><span data-stu-id="a965b-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="a965b-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="a965b-110">invokePurpose</span></span>  
 <span data-ttu-id="a965b-111">vorgenommen Ein Zeiger auf einen Member der [cordebugcodeinvokepurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) -Enumeration, der beschreibt, warum die exportierte Funktion verwalteten Code aufruft.</span><span class="sxs-lookup"><span data-stu-id="a965b-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a965b-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a965b-112">Return Value</span></span>  
 <span data-ttu-id="a965b-113">Diese Methode kann die in der folgenden Tabelle aufgeführten Werte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a965b-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="a965b-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a965b-114">Return value</span></span>|<span data-ttu-id="a965b-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a965b-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="a965b-116">Der Methodenaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="a965b-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="a965b-117">`pInvokeKind` oder `pInvokePurpose` ist **null**.</span><span class="sxs-lookup"><span data-stu-id="a965b-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="a965b-118">Andere fehlerhafte `HRESULT`-Werte.</span><span class="sxs-lookup"><span data-stu-id="a965b-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="a965b-119">Gegebenenfalls.</span><span class="sxs-lookup"><span data-stu-id="a965b-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a965b-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a965b-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a965b-121">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a965b-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a965b-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a965b-122">Requirements</span></span>  
 <span data-ttu-id="a965b-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a965b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a965b-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a965b-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a965b-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a965b-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a965b-126">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a965b-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a965b-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a965b-127">See also</span></span>

- [<span data-ttu-id="a965b-128">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a965b-128">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="a965b-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a965b-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
