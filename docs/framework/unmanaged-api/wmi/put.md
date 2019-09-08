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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5aa629c2d07fb25db035cd80aba3c74413070e6e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798402"
---
# <a name="put-function"></a><span data-ttu-id="913da-103">Put-Funktion</span><span class="sxs-lookup"><span data-stu-id="913da-103">Put function</span></span>

<span data-ttu-id="913da-104">Legt eine benannte Eigenschaft auf einen neuen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="913da-104">Sets a named property to a new value.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="913da-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="913da-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="913da-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="913da-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="913da-107">in Dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="913da-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="913da-108">in Ein Zeiger auf eine [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="913da-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="913da-109">in Der Name der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="913da-109">[in] The name of the property.</span></span> <span data-ttu-id="913da-110">Dieser Parameter darf nicht `null`sein.</span><span class="sxs-lookup"><span data-stu-id="913da-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="913da-111">[in] Reserviert.</span><span class="sxs-lookup"><span data-stu-id="913da-111">[in] Reserved.</span></span> <span data-ttu-id="913da-112">Dieser Parameter muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="913da-112">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="913da-113">in Ein Zeiger auf einen gültigen `VARIANT` , der zum neuen Eigenschafts Wert wird.</span><span class="sxs-lookup"><span data-stu-id="913da-113">[in] A pointer to a valid `VARIANT` that becomes the new property value.</span></span> <span data-ttu-id="913da-114">Wenn `pVal` `VARIANT` ist `null` oder auf einen des Typs `VT_NULL`verweist, wird die-Eigenschaft auf `null`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="913da-114">If `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`, the property is set to `null`.</span></span>

`vtType`\
<span data-ttu-id="913da-115">in Der Typ von `VARIANT` `pVal`, auf den verweist.</span><span class="sxs-lookup"><span data-stu-id="913da-115">[in] The type of `VARIANT` pointed to by `pVal`.</span></span> <span data-ttu-id="913da-116">Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="913da-116">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="913da-117">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="913da-117">Return value</span></span>

<span data-ttu-id="913da-118">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="913da-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="913da-119">Konstante</span><span class="sxs-lookup"><span data-stu-id="913da-119">Constant</span></span>  |<span data-ttu-id="913da-120">Wert</span><span class="sxs-lookup"><span data-stu-id="913da-120">Value</span></span>  |<span data-ttu-id="913da-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="913da-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="913da-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="913da-122">0x80041001</span></span> | <span data-ttu-id="913da-123">Es ist ein allgemeiner Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="913da-123">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="913da-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="913da-124">0x80041008</span></span> | <span data-ttu-id="913da-125">Mindestens ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="913da-125">One or more parameters are not valid.</span></span> |
|`WBEM_E_INVALID_PROPERTY_TYPE` | <span data-ttu-id="913da-126">0x8004102a</span><span class="sxs-lookup"><span data-stu-id="913da-126">0x8004102a</span></span> | <span data-ttu-id="913da-127">Der Eigenschaftentyp wird nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="913da-127">The property type is not recognized.</span></span> <span data-ttu-id="913da-128">Dieser Wert wird zurückgegeben, wenn Klassen Instanzen erstellt werden, wenn die Klasse bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="913da-128">This value is returned when creating class instances if the class already exists.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="913da-129">0x80041006</span><span class="sxs-lookup"><span data-stu-id="913da-129">0x80041006</span></span> | <span data-ttu-id="913da-130">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="913da-130">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="913da-131">0x80041005</span><span class="sxs-lookup"><span data-stu-id="913da-131">0x80041005</span></span> | <span data-ttu-id="913da-132">Für-Instanzen: Gibt an `pVal` , dass auf `VARIANT` einen von einem falschen Typ für die Eigenschaft verweist.</span><span class="sxs-lookup"><span data-stu-id="913da-132">For instances: Indicates that `pVal` points to a `VARIANT` of an incorrect type for the property.</span></span> <br/> <span data-ttu-id="913da-133">Für Klassendefinitionen: Die Eigenschaft ist in der übergeordneten Klasse bereits vorhanden, und der neue com-Typ unterscheidet sich vom alten com-Typ.</span><span class="sxs-lookup"><span data-stu-id="913da-133">For class definitions: The property already exists in the parent class, and the new COM type is different from the old COM type.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="913da-134">0</span><span class="sxs-lookup"><span data-stu-id="913da-134">0</span></span> | <span data-ttu-id="913da-135">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="913da-135">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="913da-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="913da-136">Remarks</span></span>

<span data-ttu-id="913da-137">Diese Funktion umschließt einen aufrufsbefehl an die [IWbemClassObject::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) -Methode.</span><span class="sxs-lookup"><span data-stu-id="913da-137">This function wraps a call to the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

<span data-ttu-id="913da-138">Diese Funktion überschreibt immer den aktuellen-Eigenschafts Wert mit einem neuen.</span><span class="sxs-lookup"><span data-stu-id="913da-138">This function always overwrites the current property value with a new one.</span></span> <span data-ttu-id="913da-139">Wenn [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) auf eine Klassendefinition zeigt, `Put` erstellt oder aktualisiert den Eigenschafts Wert.</span><span class="sxs-lookup"><span data-stu-id="913da-139">If the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a class definition, `Put` creates or updates the property value.</span></span> <span data-ttu-id="913da-140">Wenn [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) auf eine CIM-Instanz verweist `Put` , aktualisiert nur den Eigenschafts Wert. `Put` ein Eigenschafts Wert kann nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="913da-140">When [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a CIM instance, `Put` updates the property value only; `Put` cannot create a property value.</span></span>

<span data-ttu-id="913da-141">Die `__CLASS` System Eigenschaft ist nur während der Klassen Erstellung beschreibbar, wenn Sie möglicherweise nicht leer ist.</span><span class="sxs-lookup"><span data-stu-id="913da-141">The `__CLASS` system property is only writable during class creation, when it may not be left blank.</span></span> <span data-ttu-id="913da-142">Alle anderen Systemeigenschaften sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="913da-142">All other system properties are read-only.</span></span>

<span data-ttu-id="913da-143">Ein Benutzer kann keine Eigenschaften erstellen, deren Namen mit einem Unterstrich ("_") beginnen oder enden.</span><span class="sxs-lookup"><span data-stu-id="913da-143">A user cannot create properties with names that begin or end with an underscore ("_").</span></span> <span data-ttu-id="913da-144">Dies ist für System Klassen und-Eigenschaften reserviert.</span><span class="sxs-lookup"><span data-stu-id="913da-144">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="913da-145">Wenn die von der `Put` Funktion festgelegte Eigenschaft in der übergeordneten Klasse vorhanden ist, wird der Standardwert der Eigenschaft geändert, es sei denn, der Eigenschaftentyp stimmt nicht mit dem Typ der übergeordneten Klasse identisch.</span><span class="sxs-lookup"><span data-stu-id="913da-145">If the property set by the `Put` function exists in the parent class, the default value of the property is changed unless the property type does not match the parent class type.</span></span> <span data-ttu-id="913da-146">Wenn die Eigenschaft nicht vorhanden ist und es sich nicht um einen Typen Konflikt handelt, wird die-Eigenschaft erstellt.</span><span class="sxs-lookup"><span data-stu-id="913da-146">If the property does not exist and it is not a type mismatch, the property is created.</span></span>

<span data-ttu-id="913da-147">Verwenden Sie `vtType` den `pVal` `VARIANT` -Parameter`VT_NULL`nur, wenn neue Eigenschaften in einer CIM-Klassendefinition erstellt werden, oderverweistaufeinenvomTyp.`null`</span><span class="sxs-lookup"><span data-stu-id="913da-147">Use the `vtType` parameter only when creating new properties in a CIM class definition and `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`.</span></span> <span data-ttu-id="913da-148">In diesem Fall gibt der `vType` Parameter den CIM-Typ der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="913da-148">In this case, the `vType` parameter specifies the CIM type of the property.</span></span> <span data-ttu-id="913da-149">In jedem anderen Fall `vtType` muss 0 sein.</span><span class="sxs-lookup"><span data-stu-id="913da-149">In every other case, `vtType` must be 0.</span></span> <span data-ttu-id="913da-150">`vtType`muss auch 0 sein, wenn das zugrunde liegende Objekt eine Instanz ist ( `Val` auch `null`wenn ist), da der Typ der Eigenschaft korrigiert ist und nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="913da-150">`vtType` must also be 0 if the underlying object is an instance (even if `Val` is `null`) because the type of the property is fixed and cannot be changed.</span></span>

## <a name="example"></a><span data-ttu-id="913da-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="913da-151">Example</span></span>

<span data-ttu-id="913da-152">Ein Beispiel finden Sie in der [IWbemClassObject::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) -Methode.</span><span class="sxs-lookup"><span data-stu-id="913da-152">For an example, see the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="913da-153">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="913da-153">Requirements</span></span>

<span data-ttu-id="913da-154">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="913da-154">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="913da-155">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="913da-155">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="913da-156">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="913da-156">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="913da-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="913da-157">See also</span></span>

- [<span data-ttu-id="913da-158">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="913da-158">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
