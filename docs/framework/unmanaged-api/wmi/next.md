---
title: Next-Funktion (Referenz zur nicht verwalteten API)
description: Die Next-Funktion Ruft die Next-Eigenschaft in einer Enumeration ab.
ms.date: 11/06/2017
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 587e085f6fe9f6c19d3605c673cd3bd6f68162f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127382"
---
# <a name="next-function"></a><span data-ttu-id="15b4f-103">Next-Funktion</span><span class="sxs-lookup"><span data-stu-id="15b4f-103">Next function</span></span>
<span data-ttu-id="15b4f-104">Ruft die Next-Eigenschaft in einer Enumeration ab, die mit einem Aufrufen von [beginenumeration](beginenumeration.md)beginnt.</span><span class="sxs-lookup"><span data-stu-id="15b4f-104">Retrieves the next property in an enumeration that begins with a call to [BeginEnumeration](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="15b4f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="15b4f-105">Syntax</span></span>

```cpp
HRESULT Next (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="15b4f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="15b4f-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="15b4f-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="15b4f-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="15b4f-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="15b4f-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`\
<span data-ttu-id="15b4f-109">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="15b4f-109">[in] Reserved.</span></span> <span data-ttu-id="15b4f-110">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="15b4f-110">This parameter must be 0.</span></span>

`pstrName`\
<span data-ttu-id="15b4f-111">vorgenommen Ein neues `BSTR`, das den Eigenschaftsnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="15b4f-111">[out] A new `BSTR` that contains the property name.</span></span> <span data-ttu-id="15b4f-112">Sie können diesen Parameter auf `null` festlegen, wenn der Name nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="15b4f-112">You can set this parameter to `null` if the name is not required.</span></span>

`pVal`\
<span data-ttu-id="15b4f-113">vorgenommen Ein `VARIANT` mit dem Wert der-Eigenschaft aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="15b4f-113">[out] A `VARIANT` filled with the value of the property.</span></span> <span data-ttu-id="15b4f-114">Sie können diesen Parameter auf `null` festlegen, wenn der Wert nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="15b4f-114">You can set this parameter to `null` if the value is not required.</span></span> <span data-ttu-id="15b4f-115">Wenn die Funktion einen Fehlercode zurückgibt, bleibt die an `pVal` übergebenen `VARIANT` unverändert.</span><span class="sxs-lookup"><span data-stu-id="15b4f-115">If the function returns an error code, the `VARIANT` passed to `pVal` is left unmodified.</span></span>

`pvtType`\
<span data-ttu-id="15b4f-116">vorgenommen Ein Zeiger auf eine `CIMTYPE` Variable (ein `LONG`, in den der Typ der Eigenschaft eingefügt wird).</span><span class="sxs-lookup"><span data-stu-id="15b4f-116">[out] A pointer to a `CIMTYPE` variable (a `LONG` into which the type of the property is placed).</span></span> <span data-ttu-id="15b4f-117">Der Wert dieser Eigenschaft kann ein `VT_NULL_VARIANT`sein. in diesem Fall muss der tatsächliche Typ der Eigenschaft bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="15b4f-117">The value of this property can be a `VT_NULL_VARIANT`, in which case it is necessary to determine the actual type of the property.</span></span> <span data-ttu-id="15b4f-118">Dieser Parameter kann auch `null`werden.</span><span class="sxs-lookup"><span data-stu-id="15b4f-118">This parameter can also be `null`.</span></span>

`plFlavor`\
<span data-ttu-id="15b4f-119">[out] `null`oder ein Wert, der Informationen über den Ursprung der Eigenschaft empfängt.</span><span class="sxs-lookup"><span data-stu-id="15b4f-119">[out] `null`, or a value that receives information on the origin of the property.</span></span> <span data-ttu-id="15b4f-120">Mögliche Werte finden Sie im Abschnitt [Hinweise].</span><span class="sxs-lookup"><span data-stu-id="15b4f-120">See the [Remarks] section for possible values.</span></span>

## <a name="return-value"></a><span data-ttu-id="15b4f-121">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="15b4f-121">Return value</span></span>

<span data-ttu-id="15b4f-122">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="15b4f-122">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="15b4f-123">Konstante</span><span class="sxs-lookup"><span data-stu-id="15b4f-123">Constant</span></span>  |<span data-ttu-id="15b4f-124">Wert</span><span class="sxs-lookup"><span data-stu-id="15b4f-124">Value</span></span>  |<span data-ttu-id="15b4f-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15b4f-125">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="15b4f-126">0x80041001</span><span class="sxs-lookup"><span data-stu-id="15b4f-126">0x80041001</span></span> | <span data-ttu-id="15b4f-127">Es ist ein allgemeiner Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="15b4f-127">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="15b4f-128">0x80041008</span><span class="sxs-lookup"><span data-stu-id="15b4f-128">0x80041008</span></span> | <span data-ttu-id="15b4f-129">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="15b4f-129">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="15b4f-130">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="15b4f-130">0x8004101d</span></span> | <span data-ttu-id="15b4f-131">Die [`BeginEnumeration`](beginenumeration.md) Funktion wurde nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="15b4f-131">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="15b4f-132">0x80041006</span><span class="sxs-lookup"><span data-stu-id="15b4f-132">0x80041006</span></span> | <span data-ttu-id="15b4f-133">Es ist nicht genügend Arbeitsspeicher verfügbar, um eine neue Enumeration zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="15b4f-133">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="15b4f-134">0x80041015</span><span class="sxs-lookup"><span data-stu-id="15b4f-134">0x80041015</span></span> | <span data-ttu-id="15b4f-135">Der Remote Prozedur Aufrufe zwischen dem aktuellen Prozess und der Windows-Verwaltung ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="15b4f-135">The remote procedure call between the current process and Windows Management failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="15b4f-136">0</span><span class="sxs-lookup"><span data-stu-id="15b4f-136">0</span></span> | <span data-ttu-id="15b4f-137">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="15b4f-137">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="15b4f-138">0x40005</span><span class="sxs-lookup"><span data-stu-id="15b4f-138">0x40005</span></span> | <span data-ttu-id="15b4f-139">In der-Enumeration sind keine weiteren Eigenschaften vorhanden.</span><span class="sxs-lookup"><span data-stu-id="15b4f-139">There are no more properties in the enumeration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="15b4f-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15b4f-140">Remarks</span></span>

<span data-ttu-id="15b4f-141">Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) -Methode.</span><span class="sxs-lookup"><span data-stu-id="15b4f-141">This function wraps a call to the [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) method.</span></span>

<span data-ttu-id="15b4f-142">Diese Methode gibt auch Systemeigenschaften zurück.</span><span class="sxs-lookup"><span data-stu-id="15b4f-142">This method also returns system properties.</span></span>

<span data-ttu-id="15b4f-143">Wenn der zugrunde liegende Typ der Eigenschaft ein Objekt Pfad, ein Datum oder eine Uhrzeit oder ein anderer spezieller Typ ist, enthält der zurückgegebene Typ nicht genügend Informationen.</span><span class="sxs-lookup"><span data-stu-id="15b4f-143">If the underlying type of the property is an object path, a date or time, or another special type, then the returned type does not contain enough information.</span></span> <span data-ttu-id="15b4f-144">Der Aufrufer muss die `CIMTYPE` für die angegebene Eigenschaft überprüfen, um zu bestimmen, ob die Eigenschaft ein Objekt Verweis, ein Datum oder eine Uhrzeit oder ein anderer spezieller Typ ist.</span><span class="sxs-lookup"><span data-stu-id="15b4f-144">The caller must examine the `CIMTYPE` for the specified property to determine if the property is an object reference, a date or time, or another special type.</span></span>

<span data-ttu-id="15b4f-145">Wenn `plFlavor` nicht `null`ist, erhält der `LONG` Wert Informationen zum Ursprung der Eigenschaft wie folgt:</span><span class="sxs-lookup"><span data-stu-id="15b4f-145">If `plFlavor` is not `null`, the `LONG` value receives information about the origin of the property, as follows:</span></span>

|<span data-ttu-id="15b4f-146">Konstante</span><span class="sxs-lookup"><span data-stu-id="15b4f-146">Constant</span></span>  |<span data-ttu-id="15b4f-147">Wert</span><span class="sxs-lookup"><span data-stu-id="15b4f-147">Value</span></span>  |<span data-ttu-id="15b4f-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15b4f-148">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="15b4f-149">0x40</span><span class="sxs-lookup"><span data-stu-id="15b4f-149">0x40</span></span> | <span data-ttu-id="15b4f-150">Die-Eigenschaft ist eine Standardsystem Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="15b4f-150">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="15b4f-151">0x20</span><span class="sxs-lookup"><span data-stu-id="15b4f-151">0x20</span></span> | <span data-ttu-id="15b4f-152">Für eine Klasse: die Eigenschaft wird von der übergeordneten Klasse geerbt.</span><span class="sxs-lookup"><span data-stu-id="15b4f-152">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="15b4f-153">Für eine-Instanz: die-Eigenschaft wurde von der-Instanz nicht geändert, während Sie von der übergeordneten Klasse geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="15b4f-153">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="15b4f-154">0</span><span class="sxs-lookup"><span data-stu-id="15b4f-154">0</span></span> | <span data-ttu-id="15b4f-155">Für eine Klasse: die Eigenschaft gehört zur abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="15b4f-155">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="15b4f-156">Für eine-Instanz: die-Eigenschaft wird von der-Instanz geändert. Das heißt, es wurde ein Wert angegeben, oder es wurde ein Qualifizierer hinzugefügt oder geändert.</span><span class="sxs-lookup"><span data-stu-id="15b4f-156">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="requirements"></a><span data-ttu-id="15b4f-157">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15b4f-157">Requirements</span></span>

<span data-ttu-id="15b4f-158">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15b4f-158">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="15b4f-159">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="15b4f-159">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="15b4f-160">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="15b4f-160">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="15b4f-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15b4f-161">See also</span></span>

- [<span data-ttu-id="15b4f-162">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="15b4f-162">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
