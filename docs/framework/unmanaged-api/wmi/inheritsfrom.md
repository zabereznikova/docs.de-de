---
title: InheritsFrom-Funktion (Referenz zur nicht verwalteten API)
description: Die InheritsFrom-Funktion bestimmt, ob eine Klasse oder Instanz aus einer bestimmten übergeordneten Klasse abgeleitet ist.
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4784e22d5a3eec031fbee00441958a62d66b52df
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930921"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="8a809-103">InheritsFrom-Funktion</span><span class="sxs-lookup"><span data-stu-id="8a809-103">InheritsFrom function</span></span>
<span data-ttu-id="8a809-104">Bestimmt, ob die aktuelle Klasse oder Instanz aus einer angegebenen übergeordneten Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="8a809-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="8a809-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a809-105">Syntax</span></span>  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="8a809-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8a809-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8a809-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="8a809-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="8a809-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="8a809-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="8a809-109">[in] Der Name der Klasse.</span><span class="sxs-lookup"><span data-stu-id="8a809-109">[in] The name of the class.</span></span> <span data-ttu-id="8a809-110">`wszAncestor` muss auf einen gültigen zeigen `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="8a809-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="8a809-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8a809-111">Return value</span></span>

<span data-ttu-id="8a809-112">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="8a809-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8a809-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="8a809-113">Constant</span></span>  |<span data-ttu-id="8a809-114">Wert</span><span class="sxs-lookup"><span data-stu-id="8a809-114">Value</span></span>  |<span data-ttu-id="8a809-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a809-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="8a809-116">0</span><span class="sxs-lookup"><span data-stu-id="8a809-116">0</span></span> | <span data-ttu-id="8a809-117">Das aktuelle Objekt erbt `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="8a809-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="8a809-118">1</span><span class="sxs-lookup"><span data-stu-id="8a809-118">1</span></span> | <span data-ttu-id="8a809-119">Das aktuelle Objekt erbt nicht von `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="8a809-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8a809-120">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="8a809-120">0x80041008</span></span> | <span data-ttu-id="8a809-121">`wszAncestor` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="8a809-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="8a809-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a809-122">Remarks</span></span>

<span data-ttu-id="8a809-123">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) Methode.</span><span class="sxs-lookup"><span data-stu-id="8a809-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8a809-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8a809-124">Requirements</span></span>  
 <span data-ttu-id="8a809-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a809-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a809-126">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8a809-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8a809-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8a809-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a809-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a809-128">See also</span></span>  
[<span data-ttu-id="8a809-129">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="8a809-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
