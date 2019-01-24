---
title: Die Next-Funktion (Referenz zur nicht verwalteten API)
description: Die nächste Funktion Retireves die nächste Eigenschaft in einer Enumeration.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aaebf06c63d7022c9798824097cd722a2ffadde5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584609"
---
# <a name="next-function"></a><span data-ttu-id="b4a17-103">Die Next-Funktion</span><span class="sxs-lookup"><span data-stu-id="b4a17-103">Next function</span></span>
<span data-ttu-id="b4a17-104">Ruft die nächste Eigenschaft in einer Enumeration, die mit einem Aufruf von beginnt [BeginEnumeration](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="b4a17-104">Retrieves the next property in an enumeration that begins with a call to [BeginEnumeration](beginenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="b4a17-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4a17-105">Syntax</span></span>  
  
```  
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

## <a name="parameters"></a><span data-ttu-id="b4a17-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4a17-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b4a17-107">[in] Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="b4a17-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b4a17-108">[in] Ein Zeiger auf ein [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) Instanz.</span><span class="sxs-lookup"><span data-stu-id="b4a17-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="b4a17-109">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="b4a17-109">[in] Reserved.</span></span> <span data-ttu-id="b4a17-110">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="b4a17-110">This parameter must be 0.</span></span>

`pstrName`  
<span data-ttu-id="b4a17-111">[out] Ein neues `BSTR` , die den Eigenschaftsnamen enthält.</span><span class="sxs-lookup"><span data-stu-id="b4a17-111">[out] A new `BSTR` that contains the property name.</span></span> <span data-ttu-id="b4a17-112">Sie können diesen Parameter festlegen, um `null` Wenn der Name nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b4a17-112">You can set this parameter to `null` if the name is not required.</span></span>

`pVal`  
<span data-ttu-id="b4a17-113">[out] Ein `VARIANT` mit dem Wert der Eigenschaft gefüllt.</span><span class="sxs-lookup"><span data-stu-id="b4a17-113">[out] A `VARIANT` filled with the value of the property.</span></span> <span data-ttu-id="b4a17-114">Sie können diesen Parameter festlegen, um `null` Wenn der Wert nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b4a17-114">You can set this parameter to `null` if the value is not required.</span></span> <span data-ttu-id="b4a17-115">Wenn die Funktion einen Fehlercode zurückgibt. die `VARIANT` übergeben `pVal` wird links unverändert.</span><span class="sxs-lookup"><span data-stu-id="b4a17-115">If the function returns an error code, the `VARIANT` passed to `pVal` is left unmodified.</span></span> 

`pvtType`  
<span data-ttu-id="b4a17-116">[out] Ein Zeiger auf eine `CIMTYPE` Variable (eine `LONG` in dem der Typ der Eigenschaft befindet).</span><span class="sxs-lookup"><span data-stu-id="b4a17-116">[out] A pointer to a `CIMTYPE` variable (a `LONG` into which the type of the property is placed).</span></span> <span data-ttu-id="b4a17-117">Der Wert dieser Eigenschaft kann sein ein `VT_NULL_VARIANT`, in diesem Fall ist es erforderlich, um zu bestimmen, den tatsächlichen Typ der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b4a17-117">The value of this property can be a `VT_NULL_VARIANT`, in which case it is necessary to determine the actual type of the property.</span></span> <span data-ttu-id="b4a17-118">Dieser Parameter kann auch sein `null`.</span><span class="sxs-lookup"><span data-stu-id="b4a17-118">This parameter can also be `null`.</span></span> 

`plFlavor`  
<span data-ttu-id="b4a17-119">[out] `null`, oder ein Wert, der Informationen auf den Ursprung der Eigenschaft empfängt.</span><span class="sxs-lookup"><span data-stu-id="b4a17-119">[out] `null`, or a value that receives information on the origin of the property.</span></span> <span data-ttu-id="b4a17-120">Finden Sie im Abschnitt "[" Hinweise "]" für die möglichen Werte.</span><span class="sxs-lookup"><span data-stu-id="b4a17-120">See the [Remarks] section for possible values.</span></span> 

## <a name="return-value"></a><span data-ttu-id="b4a17-121">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b4a17-121">Return value</span></span>

<span data-ttu-id="b4a17-122">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="b4a17-122">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b4a17-123">Konstante</span><span class="sxs-lookup"><span data-stu-id="b4a17-123">Constant</span></span>  |<span data-ttu-id="b4a17-124">Wert</span><span class="sxs-lookup"><span data-stu-id="b4a17-124">Value</span></span>  |<span data-ttu-id="b4a17-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4a17-125">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="b4a17-126">0x80041001</span><span class="sxs-lookup"><span data-stu-id="b4a17-126">0x80041001</span></span> | <span data-ttu-id="b4a17-127">Es wurde ein allgemeiner Fehler.</span><span class="sxs-lookup"><span data-stu-id="b4a17-127">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b4a17-128">0x80041008</span><span class="sxs-lookup"><span data-stu-id="b4a17-128">0x80041008</span></span> | <span data-ttu-id="b4a17-129">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="b4a17-129">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="b4a17-130">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="b4a17-130">0x8004101d</span></span> | <span data-ttu-id="b4a17-131">Es wurde kein Aufruf von der [ `BeginEnumeration` ](beginenumeration.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="b4a17-131">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="b4a17-132">0x80041006</span><span class="sxs-lookup"><span data-stu-id="b4a17-132">0x80041006</span></span> | <span data-ttu-id="b4a17-133">Es ist nicht genügend Arbeitsspeicher zur Verfügung, um eine neue Enumeration beginnen.</span><span class="sxs-lookup"><span data-stu-id="b4a17-133">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="b4a17-134">0x80041015</span><span class="sxs-lookup"><span data-stu-id="b4a17-134">0x80041015</span></span> | <span data-ttu-id="b4a17-135">Der Remoteprozeduraufruf zwischen dem aktuellen Prozess und die Windows-Verwaltung ist fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="b4a17-135">The remote procedure call betweeen the current process and Windows Management failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="b4a17-136">0</span><span class="sxs-lookup"><span data-stu-id="b4a17-136">0</span></span> | <span data-ttu-id="b4a17-137">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="b4a17-137">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="b4a17-138">0x40005</span><span class="sxs-lookup"><span data-stu-id="b4a17-138">0x40005</span></span> | <span data-ttu-id="b4a17-139">Es gibt keine weiteren Eigenschaften in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="b4a17-139">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="b4a17-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4a17-140">Remarks</span></span>

<span data-ttu-id="b4a17-141">Diese Funktion umschließt einen Aufruf der [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) Methode.</span><span class="sxs-lookup"><span data-stu-id="b4a17-141">This function wraps a call to the [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) method.</span></span>

<span data-ttu-id="b4a17-142">Diese Methode gibt auch Systemeigenschaften zurück.</span><span class="sxs-lookup"><span data-stu-id="b4a17-142">This method also returns system properties.</span></span>

<span data-ttu-id="b4a17-143">Wenn der zugrunde liegende Typ der Eigenschaft eines Objektpfad, ein Datum oder Uhrzeit oder einen anderen speziellen Typ ist, enthält der zurückgegebene Typ keine ausreichende Informationen.</span><span class="sxs-lookup"><span data-stu-id="b4a17-143">If the underlying type of the property is an object path, a date or time, or another special type, then the returned type does not contain enough information.</span></span> <span data-ttu-id="b4a17-144">Der Aufrufer muss Untersuchen der `CIMTYPE` für die angegebene Eigenschaft aus, um festzustellen, ob die Eigenschaft einen Objektverweis, ein Datum oder Uhrzeit oder einen anderen speziellen Typ ist.</span><span class="sxs-lookup"><span data-stu-id="b4a17-144">The caller must examine the `CIMTYPE` for the specified property to determine if the property is an object reference, a date or time, or another special type.</span></span>

<span data-ttu-id="b4a17-145">Wenn `plFlavor` nicht `null`, `LONG` Wert empfängt Informationen über den Ursprung der Eigenschaft, die wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b4a17-145">If `plFlavor` is not `null`, the `LONG` value receives information about the origin of the property, as follows:</span></span>

|<span data-ttu-id="b4a17-146">Konstante</span><span class="sxs-lookup"><span data-stu-id="b4a17-146">Constant</span></span>  |<span data-ttu-id="b4a17-147">Wert</span><span class="sxs-lookup"><span data-stu-id="b4a17-147">Value</span></span>  |<span data-ttu-id="b4a17-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4a17-148">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="b4a17-149">0x40</span><span class="sxs-lookup"><span data-stu-id="b4a17-149">0x40</span></span> | <span data-ttu-id="b4a17-150">Die Eigenschaft ist eine standard-Systemeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b4a17-150">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="b4a17-151">0x20</span><span class="sxs-lookup"><span data-stu-id="b4a17-151">0x20</span></span> | <span data-ttu-id="b4a17-152">Für eine Klasse: Die Eigenschaft wird von der übergeordneten Klasse geerbt.</span><span class="sxs-lookup"><span data-stu-id="b4a17-152">For a class: The property is inherited from the parent class.</span></span> </br> <span data-ttu-id="b4a17-153">Für eine Instanz: Die Eigenschaft wurde während der von der übergeordneten Klasse geerbt nicht von der Instanz geändert.</span><span class="sxs-lookup"><span data-stu-id="b4a17-153">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="b4a17-154">0</span><span class="sxs-lookup"><span data-stu-id="b4a17-154">0</span></span> | <span data-ttu-id="b4a17-155">Für eine Klasse: Die Eigenschaft gehört der abgeleiteten Klasse.</span><span class="sxs-lookup"><span data-stu-id="b4a17-155">For a class: The property belongs to the derived class.</span></span> </br> <span data-ttu-id="b4a17-156">Für eine Instanz: Die Eigenschaft wird von der Instanz geändert werden. d. h. ein Wert angegeben wurde, oder ein Qualifizierer hinzugefügt oder geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="b4a17-156">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="requirements"></a><span data-ttu-id="b4a17-157">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b4a17-157">Requirements</span></span>  
 <span data-ttu-id="b4a17-158">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4a17-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4a17-159">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b4a17-159">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b4a17-160">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b4a17-160">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4a17-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4a17-161">See also</span></span>
- [<span data-ttu-id="b4a17-162">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="b4a17-162">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
