---
title: Getobjecttext-Funktion (Referenz zur nicht verwalteten API)
description: Die getobjecttext-Funktion gibt ein Text Rendering eines Objekts in der MOF-Syntax zurück.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6ad2b29202222d594cc7976a13929002164314a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718370"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="4078d-103">GetObjectText-Funktion</span><span class="sxs-lookup"><span data-stu-id="4078d-103">GetObjectText function</span></span>

<span data-ttu-id="4078d-104">Gibt ein Text Rendering des-Objekts in der MOF-Syntax (Managed Object Format) zurück.</span><span class="sxs-lookup"><span data-stu-id="4078d-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="4078d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4078d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a><span data-ttu-id="4078d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4078d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4078d-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="4078d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="4078d-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="4078d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="4078d-109">in Normalerweise 0.</span><span class="sxs-lookup"><span data-stu-id="4078d-109">[in] Normally 0.</span></span> <span data-ttu-id="4078d-110">Wenn `WBEM_FLAG_NO_FLAVORS` (oder 0x1) angegeben ist, werden Qualifizierer ohne Weitergabeinformationen oder Informationen zur Konfiguration eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4078d-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

<span data-ttu-id="4078d-111">`pstrObjectText` vorgenommen Ein Zeiger auf einen `null` bei Eintrag.</span><span class="sxs-lookup"><span data-stu-id="4078d-111">`pstrObjectText` [out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="4078d-112">Bei Rückgabe ein neu zugeordneter `BSTR` , das ein MOF-Syntax Rendering des-Objekts enthält.</span><span class="sxs-lookup"><span data-stu-id="4078d-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="4078d-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4078d-113">Return value</span></span>

<span data-ttu-id="4078d-114">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="4078d-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4078d-115">Konstante</span><span class="sxs-lookup"><span data-stu-id="4078d-115">Constant</span></span>  |<span data-ttu-id="4078d-116">Wert</span><span class="sxs-lookup"><span data-stu-id="4078d-116">Value</span></span>  |<span data-ttu-id="4078d-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4078d-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="4078d-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="4078d-118">0x80041001</span></span> | <span data-ttu-id="4078d-119">Es ist ein allgemeiner Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4078d-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4078d-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4078d-120">0x80041008</span></span> | <span data-ttu-id="4078d-121">Ein Parameter ist nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="4078d-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4078d-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4078d-122">0x80041006</span></span> | <span data-ttu-id="4078d-123">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4078d-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4078d-124">0</span><span class="sxs-lookup"><span data-stu-id="4078d-124">0</span></span> | <span data-ttu-id="4078d-125">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="4078d-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4078d-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4078d-126">Remarks</span></span>

<span data-ttu-id="4078d-127">Diese Funktion umschließt einen [aufzurufenden Befehl der IWbemClassObject:: getobjecttext](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) -Methode.</span><span class="sxs-lookup"><span data-stu-id="4078d-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="4078d-128">Der zurückgegebene MOF-Text enthält nicht alle Informationen über das Objekt, sondern nur genügend Informationen, damit der MOF-Compiler das ursprüngliche Objekt neu erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="4078d-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="4078d-129">Beispielsweise sind keine propagierten Qualifizierer oder Eigenschaften der übergeordneten Klasse enthalten.</span><span class="sxs-lookup"><span data-stu-id="4078d-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="4078d-130">Der folgende Algorithmus wird verwendet, um den Text der Parameter einer Methode zu rekonstruieren:</span><span class="sxs-lookup"><span data-stu-id="4078d-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="4078d-131">Parameter werden in der Reihenfolge ihrer Bezeichnerwerte neu sequenziert.</span><span class="sxs-lookup"><span data-stu-id="4078d-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="4078d-132">Parameter, die als und angegeben werden, `[in]` `[out]` werden in einem einzelnen Parameter kombiniert.</span><span class="sxs-lookup"><span data-stu-id="4078d-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>

<span data-ttu-id="4078d-133">`pstrObjectText` muss ein Zeiger auf einen sein, `null` Wenn die-Funktion aufgerufen wird. Sie darf nicht auf eine Zeichenfolge verweisen, die vor dem Methodenaufruf gültig ist, da die Zuordnung des Zeigers nicht aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="4078d-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="4078d-134">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4078d-134">Requirements</span></span>  

<span data-ttu-id="4078d-135">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4078d-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4078d-136">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="4078d-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4078d-137">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4078d-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4078d-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4078d-138">See also</span></span>

- [<span data-ttu-id="4078d-139">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="4078d-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
