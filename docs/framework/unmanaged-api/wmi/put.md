---
title: Put-Funktion (Referenz zur nicht verwalteten API)
description: Die Put-Funktion weist einer benannten Eigenschaft einen neuen Wert zu.
ms.date: 11/06/2017
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f1bb8aa09a269e3b8fd23f393d63a275d308a77c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127400"
---
# <a name="put-function"></a><span data-ttu-id="00642-103">Put-Funktion</span><span class="sxs-lookup"><span data-stu-id="00642-103">Put function</span></span>

<span data-ttu-id="00642-104">Legt eine benannte Eigenschaft auf einen neuen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="00642-104">Sets a named property to a new value.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="00642-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="00642-105">Syntax</span></span>

```cpp
HRESULT Put (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
);
```

## <a name="parameters"></a><span data-ttu-id="00642-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="00642-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="00642-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="00642-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="00642-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="00642-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="00642-109">in Der Name der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="00642-109">[in] The name of the property.</span></span> <span data-ttu-id="00642-110">Dieser Parameter kann nicht `null`werden.</span><span class="sxs-lookup"><span data-stu-id="00642-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="00642-111">[in]: Reserviert</span><span class="sxs-lookup"><span data-stu-id="00642-111">[in] Reserved.</span></span> <span data-ttu-id="00642-112">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="00642-112">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="00642-113">in Ein Zeiger auf einen gültigen `VARIANT`, der zum neuen Eigenschafts Wert wird.</span><span class="sxs-lookup"><span data-stu-id="00642-113">[in] A pointer to a valid `VARIANT` that becomes the new property value.</span></span> <span data-ttu-id="00642-114">Wenn `pVal` `null` oder auf eine `VARIANT` vom Typ `VT_NULL`verweist, wird die-Eigenschaft auf `null`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="00642-114">If `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`, the property is set to `null`.</span></span>

`vtType`\
<span data-ttu-id="00642-115">in Der Typ der `VARIANT` auf die von `pVal`verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="00642-115">[in] The type of `VARIANT` pointed to by `pVal`.</span></span> <span data-ttu-id="00642-116">Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="00642-116">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="00642-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="00642-117">Return value</span></span>

<span data-ttu-id="00642-118">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="00642-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="00642-119">Konstante</span><span class="sxs-lookup"><span data-stu-id="00642-119">Constant</span></span>  |<span data-ttu-id="00642-120">Wert</span><span class="sxs-lookup"><span data-stu-id="00642-120">Value</span></span>  |<span data-ttu-id="00642-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00642-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="00642-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="00642-122">0x80041001</span></span> | <span data-ttu-id="00642-123">Es ist ein allgemeiner Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="00642-123">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="00642-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="00642-124">0x80041008</span></span> | <span data-ttu-id="00642-125">Mindestens ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="00642-125">One or more parameters are not valid.</span></span> |
|`WBEM_E_INVALID_PROPERTY_TYPE` | <span data-ttu-id="00642-126">0x8004102a</span><span class="sxs-lookup"><span data-stu-id="00642-126">0x8004102a</span></span> | <span data-ttu-id="00642-127">Der Eigenschaftentyp wird nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="00642-127">The property type is not recognized.</span></span> <span data-ttu-id="00642-128">Dieser Wert wird zurückgegeben, wenn Klassen Instanzen erstellt werden, wenn die Klasse bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="00642-128">This value is returned when creating class instances if the class already exists.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="00642-129">0x80041006</span><span class="sxs-lookup"><span data-stu-id="00642-129">0x80041006</span></span> | <span data-ttu-id="00642-130">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="00642-130">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="00642-131">0x80041005 beim</span><span class="sxs-lookup"><span data-stu-id="00642-131">0x80041005</span></span> | <span data-ttu-id="00642-132">Für-Instanzen: gibt an, dass `pVal` auf eine `VARIANT` eines falschen Typs für die-Eigenschaft verweist.</span><span class="sxs-lookup"><span data-stu-id="00642-132">For instances: Indicates that `pVal` points to a `VARIANT` of an incorrect type for the property.</span></span> <br/> <span data-ttu-id="00642-133">Für Klassendefinitionen: die Eigenschaft ist bereits in der übergeordneten Klasse vorhanden, und der neue com-Typ unterscheidet sich vom alten com-Typ.</span><span class="sxs-lookup"><span data-stu-id="00642-133">For class definitions: The property already exists in the parent class, and the new COM type is different from the old COM type.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="00642-134">0</span><span class="sxs-lookup"><span data-stu-id="00642-134">0</span></span> | <span data-ttu-id="00642-135">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="00642-135">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="00642-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00642-136">Remarks</span></span>

<span data-ttu-id="00642-137">Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) -Methode.</span><span class="sxs-lookup"><span data-stu-id="00642-137">This function wraps a call to the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

<span data-ttu-id="00642-138">Diese Funktion überschreibt immer den aktuellen-Eigenschafts Wert mit einem neuen.</span><span class="sxs-lookup"><span data-stu-id="00642-138">This function always overwrites the current property value with a new one.</span></span> <span data-ttu-id="00642-139">Wenn [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) auf eine Klassendefinition zeigt, `Put` den Eigenschafts Wert erstellt oder aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="00642-139">If the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a class definition, `Put` creates or updates the property value.</span></span> <span data-ttu-id="00642-140">Wenn [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) auf eine CIM-Instanz verweist, `Put` nur den Eigenschafts Wert aktualisiert. ein Eigenschafts Wert `Put` kann nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="00642-140">When [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a CIM instance, `Put` updates the property value only; `Put` cannot create a property value.</span></span>

<span data-ttu-id="00642-141">Die `__CLASS` System Eigenschaft ist während der Klassen Erstellung nur beschreibbar, wenn Sie möglicherweise nicht leer bleibt.</span><span class="sxs-lookup"><span data-stu-id="00642-141">The `__CLASS` system property is only writable during class creation, when it may not be left blank.</span></span> <span data-ttu-id="00642-142">Alle anderen Systemeigenschaften sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="00642-142">All other system properties are read-only.</span></span>

<span data-ttu-id="00642-143">Ein Benutzer kann keine Eigenschaften erstellen, deren Namen mit einem Unterstrich ("_") beginnen oder enden.</span><span class="sxs-lookup"><span data-stu-id="00642-143">A user cannot create properties with names that begin or end with an underscore ("_").</span></span> <span data-ttu-id="00642-144">Dies ist für System Klassen und-Eigenschaften reserviert.</span><span class="sxs-lookup"><span data-stu-id="00642-144">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="00642-145">Wenn die von der `Put`-Funktion festgelegte Eigenschaft in der übergeordneten Klasse vorhanden ist, wird der Standardwert der Eigenschaft geändert, es sei denn, der Eigenschaftentyp stimmt nicht mit dem übergeordneten Klassentyp.</span><span class="sxs-lookup"><span data-stu-id="00642-145">If the property set by the `Put` function exists in the parent class, the default value of the property is changed unless the property type does not match the parent class type.</span></span> <span data-ttu-id="00642-146">Wenn die Eigenschaft nicht vorhanden ist und es sich nicht um einen Typen Konflikt handelt, wird die-Eigenschaft erstellt.</span><span class="sxs-lookup"><span data-stu-id="00642-146">If the property does not exist and it is not a type mismatch, the property is created.</span></span>

<span data-ttu-id="00642-147">Verwenden Sie den `vtType`-Parameter nur, wenn Sie neue Eigenschaften in einer CIM-Klassendefinition erstellen und `pVal` `null` oder auf eine `VARIANT` vom Typ `VT_NULL`verweist.</span><span class="sxs-lookup"><span data-stu-id="00642-147">Use the `vtType` parameter only when creating new properties in a CIM class definition and `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`.</span></span> <span data-ttu-id="00642-148">In diesem Fall gibt der `vType`-Parameter den CIM-Typ der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="00642-148">In this case, the `vType` parameter specifies the CIM type of the property.</span></span> <span data-ttu-id="00642-149">In allen anderen Fällen muss `vtType` 0 sein.</span><span class="sxs-lookup"><span data-stu-id="00642-149">In every other case, `vtType` must be 0.</span></span> <span data-ttu-id="00642-150">`vtType` muss auch 0 sein, wenn das zugrunde liegende Objekt eine Instanz ist (auch wenn `Val` `null`ist), da der Typ der Eigenschaft korrigiert ist und nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="00642-150">`vtType` must also be 0 if the underlying object is an instance (even if `Val` is `null`) because the type of the property is fixed and cannot be changed.</span></span>

## <a name="example"></a><span data-ttu-id="00642-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00642-151">Example</span></span>

<span data-ttu-id="00642-152">Ein Beispiel finden Sie in der [IWbemClassObject::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) -Methode.</span><span class="sxs-lookup"><span data-stu-id="00642-152">For an example, see the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="00642-153">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00642-153">Requirements</span></span>

<span data-ttu-id="00642-154">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00642-154">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="00642-155">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="00642-155">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="00642-156">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="00642-156">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="00642-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00642-157">See also</span></span>

- [<span data-ttu-id="00642-158">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="00642-158">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
