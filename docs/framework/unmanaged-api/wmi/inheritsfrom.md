---
title: Verersfrom-Funktion (Referenz zur nicht verwalteten API)
description: Die verersfrom-Funktion bestimmt, ob eine Klasse oder eine Instanz von einer bestimmten übergeordneten Klasse abgeleitet ist.
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
ms.openlocfilehash: 6bda63377251e3a208dfb1620896535ccdf8ccd8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127428"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="f382e-103">Verersfrom-Funktion</span><span class="sxs-lookup"><span data-stu-id="f382e-103">InheritsFrom function</span></span>
<span data-ttu-id="f382e-104">Bestimmt, ob die aktuelle Klasse oder Instanz aus einer angegebenen übergeordneten Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="f382e-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="f382e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f382e-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="f382e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f382e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f382e-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f382e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f382e-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="f382e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="f382e-109">in Der Name der Klasse.</span><span class="sxs-lookup"><span data-stu-id="f382e-109">[in] The name of the class.</span></span> <span data-ttu-id="f382e-110">`wszAncestor` muss auf einen gültigen `LPCWSTR`zeigen.</span><span class="sxs-lookup"><span data-stu-id="f382e-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="f382e-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f382e-111">Return value</span></span>

<span data-ttu-id="f382e-112">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="f382e-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f382e-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="f382e-113">Constant</span></span>  |<span data-ttu-id="f382e-114">Wert</span><span class="sxs-lookup"><span data-stu-id="f382e-114">Value</span></span>  |<span data-ttu-id="f382e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f382e-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f382e-116">0</span><span class="sxs-lookup"><span data-stu-id="f382e-116">0</span></span> | <span data-ttu-id="f382e-117">Das aktuelle-Objekt erbt von `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="f382e-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="f382e-118">1</span><span class="sxs-lookup"><span data-stu-id="f382e-118">1</span></span> | <span data-ttu-id="f382e-119">Das aktuelle-Objekt erbt nicht von `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="f382e-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f382e-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f382e-120">0x80041008</span></span> | <span data-ttu-id="f382e-121">`wszAncestor` ist `null`.</span><span class="sxs-lookup"><span data-stu-id="f382e-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="f382e-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f382e-122">Remarks</span></span>

<span data-ttu-id="f382e-123">Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: verersfrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) -Methode.</span><span class="sxs-lookup"><span data-stu-id="f382e-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f382e-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f382e-124">Requirements</span></span>  
 <span data-ttu-id="f382e-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f382e-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f382e-126">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="f382e-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f382e-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f382e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f382e-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f382e-128">See also</span></span>

- [<span data-ttu-id="f382e-129">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="f382e-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
