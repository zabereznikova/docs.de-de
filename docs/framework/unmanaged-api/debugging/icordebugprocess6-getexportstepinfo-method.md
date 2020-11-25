---
title: ICorDebugProcess6::GetExportStepInfo-Methode
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: e2c04672e51ffb16043b14735cd5375073194c27
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732618"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="40627-102">ICorDebugProcess6::GetExportStepInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="40627-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>

<span data-ttu-id="40627-103">Enthält Informationen über die exportierten Laufzeitfunktionen, welche dabei helfen, den verwaltetem Code schrittweise durchzugehen.</span><span class="sxs-lookup"><span data-stu-id="40627-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40627-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40627-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,
    [out] CorDebugCodeInvokeKind* pInvokeKind,
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40627-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="40627-105">Parameters</span></span>  

 <span data-ttu-id="40627-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="40627-106">pszExportName</span></span>  
 <span data-ttu-id="40627-107">[in] Der Name einer Laufzeit-Exportfunktion wie in der PE-Exporttabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="40627-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="40627-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="40627-108">invokeKind</span></span>  
 <span data-ttu-id="40627-109">vorgenommen Ein Zeiger auf einen Member der [cordebugcodeinvokekind](cordebugcodeinvokekind-enumeration.md) -Enumeration, der beschreibt, wie die exportierte Funktion verwalteten Code aufruft.</span><span class="sxs-lookup"><span data-stu-id="40627-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="40627-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="40627-110">invokePurpose</span></span>  
 <span data-ttu-id="40627-111">vorgenommen Ein Zeiger auf einen Member der [cordebugcodeinvokepurpose](cordebugcodeinvokepurpose-enumeration.md) -Enumeration, der beschreibt, warum die exportierte Funktion verwalteten Code aufruft.</span><span class="sxs-lookup"><span data-stu-id="40627-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40627-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="40627-112">Return Value</span></span>  

 <span data-ttu-id="40627-113">Diese Methode kann die in der folgenden Tabelle aufgeführten Werte zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="40627-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="40627-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="40627-114">Return value</span></span>|<span data-ttu-id="40627-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="40627-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="40627-116">Der Methodenaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="40627-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="40627-117">`pInvokeKind` oder `pInvokePurpose` ist **null**.</span><span class="sxs-lookup"><span data-stu-id="40627-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="40627-118">Andere fehlerhafte `HRESULT`-Werte.</span><span class="sxs-lookup"><span data-stu-id="40627-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="40627-119">Gegebenenfalls.</span><span class="sxs-lookup"><span data-stu-id="40627-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40627-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40627-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40627-121">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="40627-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40627-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="40627-122">Requirements</span></span>  

 <span data-ttu-id="40627-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40627-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40627-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40627-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40627-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40627-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40627-126">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40627-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40627-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="40627-127">See also</span></span>

- [<span data-ttu-id="40627-128">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="40627-128">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="40627-129">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="40627-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
