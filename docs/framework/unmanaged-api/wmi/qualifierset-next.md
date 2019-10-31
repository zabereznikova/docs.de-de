---
title: QualifierSet_Next-Funktion (Referenz zur nicht verwalteten API)
description: Die QualifierSet_Next-Funktion Ruft den nächsten Qualifizierer in einer Enumeration ab.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c9c824b0158618848c13183d92f88604460d5099
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141723"
---
# <a name="qualifierset_next-function"></a><span data-ttu-id="ca07c-103">QualifierSet_Next-Funktion</span><span class="sxs-lookup"><span data-stu-id="ca07c-103">QualifierSet_Next function</span></span>
<span data-ttu-id="ca07c-104">Ruft den nächsten Qualifizierer in einer Enumeration ab, die durch einen Aufruf der [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)-Funktion gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="ca07c-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ca07c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca07c-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,        
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="ca07c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca07c-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="ca07c-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca07c-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="ca07c-108">in Ein Zeiger auf eine [iwbemqualifierset](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="ca07c-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="ca07c-109">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="ca07c-109">[in] Reserved.</span></span> <span data-ttu-id="ca07c-110">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="ca07c-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="ca07c-111">vorgenommen Der Name des Qualifizierers.</span><span class="sxs-lookup"><span data-stu-id="ca07c-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="ca07c-112">Wenn `null`, wird dieser Parameter ignoriert. Andernfalls sollten `pstrName` nicht auf einen gültigen `BSTR` zeigen, oder es kommt zu einem Speicherfehler.</span><span class="sxs-lookup"><span data-stu-id="ca07c-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="ca07c-113">Wenn der Wert nicht NULL ist, ordnet die Funktion immer eine neue `BSTR` zu, wenn Sie `WBEM_S_NO_ERROR`zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ca07c-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="ca07c-114">vorgenommen Bei Erfolg der Wert für den Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="ca07c-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="ca07c-115">Wenn die Funktion fehlschlägt, wird die `VARIANT`, auf die `pVal` verweist, nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="ca07c-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="ca07c-116">Wenn dieser Parameter `null`ist, wird der-Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ca07c-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="ca07c-117">vorgenommen Ein Zeiger auf einen Long-Wert, der die qualifiziererkonfiguration empfängt.</span><span class="sxs-lookup"><span data-stu-id="ca07c-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="ca07c-118">Wenn keine Informationen zur Konfiguration erwünscht sind, kann dieser Parameter `null`werden.</span><span class="sxs-lookup"><span data-stu-id="ca07c-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="ca07c-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ca07c-119">Return value</span></span>

<span data-ttu-id="ca07c-120">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="ca07c-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ca07c-121">Konstante</span><span class="sxs-lookup"><span data-stu-id="ca07c-121">Constant</span></span>  |<span data-ttu-id="ca07c-122">Wert</span><span class="sxs-lookup"><span data-stu-id="ca07c-122">Value</span></span>  |<span data-ttu-id="ca07c-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca07c-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ca07c-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ca07c-124">0x80041008</span></span> | <span data-ttu-id="ca07c-125">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="ca07c-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="ca07c-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="ca07c-126">0x8004101d</span></span> | <span data-ttu-id="ca07c-127">Der Aufrufer hat [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ca07c-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ca07c-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ca07c-128">0x80041006</span></span> | <span data-ttu-id="ca07c-129">Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="ca07c-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="ca07c-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="ca07c-130">0x40005</span></span> | <span data-ttu-id="ca07c-131">In der-Enumeration verbleiben keine weiteren Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="ca07c-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ca07c-132">0</span><span class="sxs-lookup"><span data-stu-id="ca07c-132">0</span></span> | <span data-ttu-id="ca07c-133">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="ca07c-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ca07c-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca07c-134">Remarks</span></span>

<span data-ttu-id="ca07c-135">Diese Funktion umschließt einen aufzurufenden Befehl der [iwbemqualifierset:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) -Methode.</span><span class="sxs-lookup"><span data-stu-id="ca07c-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="ca07c-136">Sie können die `QualifierSet_Next`-Funktion wiederholt aufzählen, um alle Qualifizierer aufzulisten, bis die Funktion `WBEM_S_NO_MORE_DATA`zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ca07c-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="ca07c-137">Um die Enumeration frühzeitig zu beenden, nennen Sie die [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="ca07c-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="ca07c-138">Die Reihenfolge der während der-Enumeration zurückgegebenen Qualifizierer ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="ca07c-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="ca07c-139">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ca07c-139">Requirements</span></span>  
 <span data-ttu-id="ca07c-140">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca07c-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca07c-141">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="ca07c-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ca07c-142">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ca07c-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca07c-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca07c-143">See also</span></span>

- [<span data-ttu-id="ca07c-144">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="ca07c-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
