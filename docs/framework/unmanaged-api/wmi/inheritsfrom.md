---
title: InheritsFrom-Funktion (Nicht verwaltete API-Referenz)
description: Die Funktion InheritsFrom bestimmt, ob eine Klasse oder Instanz von einer bestimmten übergeordneten Klasse stammt.
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
ms.openlocfilehash: c735c01c45beda8a1ba988a5c580e6b04ae46312
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174939"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="f4e7d-103">InheritsFrom-Funktion</span><span class="sxs-lookup"><span data-stu-id="f4e7d-103">InheritsFrom function</span></span>
<span data-ttu-id="f4e7d-104">Bestimmt, ob die aktuelle Klasse oder Instanz aus einer angegebenen übergeordneten Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="f4e7d-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="f4e7d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4e7d-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszAncestor
);
```  

## <a name="parameters"></a><span data-ttu-id="f4e7d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f4e7d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f4e7d-107">[in] Dieser Parameter ist nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4e7d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f4e7d-108">[in] Ein Zeiger auf eine [IWbemClassObject-Instanz.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="f4e7d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="f4e7d-109">[in] Der Name der Klasse.</span><span class="sxs-lookup"><span data-stu-id="f4e7d-109">[in] The name of the class.</span></span> <span data-ttu-id="f4e7d-110">`wszAncestor`muss auf eine `LPCWSTR`gültige zeigen.</span><span class="sxs-lookup"><span data-stu-id="f4e7d-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="f4e7d-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f4e7d-111">Return value</span></span>

<span data-ttu-id="f4e7d-112">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *PseCli.h-Headerdatei* definiert, oder Sie können sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="f4e7d-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f4e7d-113">Dauerhaft</span><span class="sxs-lookup"><span data-stu-id="f4e7d-113">Constant</span></span>  |<span data-ttu-id="f4e7d-114">value</span><span class="sxs-lookup"><span data-stu-id="f4e7d-114">Value</span></span>  |<span data-ttu-id="f4e7d-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4e7d-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f4e7d-116">0</span><span class="sxs-lookup"><span data-stu-id="f4e7d-116">0</span></span> | <span data-ttu-id="f4e7d-117">Das aktuelle Objekt erbt von `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="f4e7d-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="f4e7d-118">1</span><span class="sxs-lookup"><span data-stu-id="f4e7d-118">1</span></span> | <span data-ttu-id="f4e7d-119">Das aktuelle Objekt erbt `wszAncestor`nicht von .</span><span class="sxs-lookup"><span data-stu-id="f4e7d-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f4e7d-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f4e7d-120">0x80041008</span></span> | <span data-ttu-id="f4e7d-121">`wszAncestor` ist `null`</span><span class="sxs-lookup"><span data-stu-id="f4e7d-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="f4e7d-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f4e7d-122">Remarks</span></span>

<span data-ttu-id="f4e7d-123">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::InheritsFrom-Methode.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom)</span><span class="sxs-lookup"><span data-stu-id="f4e7d-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f4e7d-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f4e7d-124">Requirements</span></span>  
 <span data-ttu-id="f4e7d-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4e7d-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4e7d-126">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f4e7d-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f4e7d-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f4e7d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4e7d-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f4e7d-128">See also</span></span>

- [<span data-ttu-id="f4e7d-129">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="f4e7d-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
