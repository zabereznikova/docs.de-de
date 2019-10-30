---
title: Putclasswmi-Funktion (Referenz zur nicht verwalteten API)
description: Die putclasswmi-Funktion erstellt eine neue Klasse oder aktualisiert eine vorhandene.
ms.date: 11/06/2017
api_name:
- PutClassWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutClassWmi
helpviewer_keywords:
- PutClassWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 95a5e1f6339bde9dfe5c5ad9f989fc06e10fa7f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73101789"
---
# <a name="putclasswmi-function"></a><span data-ttu-id="3ea97-103">Putclasswmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="3ea97-103">PutClassWmi function</span></span>

<span data-ttu-id="3ea97-104">Erstellt eine neue Klasse oder aktualisiert eine vorhandene Klasse.</span><span class="sxs-lookup"><span data-stu-id="3ea97-104">Creates a new class or updates an existing one.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="3ea97-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ea97-105">Syntax</span></span>

```cpp
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="3ea97-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ea97-106">Parameters</span></span>

`pObject`\
<span data-ttu-id="3ea97-107">in Ein Zeiger auf eine gültige Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="3ea97-107">[in] A pointer to a valid class definition.</span></span> <span data-ttu-id="3ea97-108">Er muss mit allen erforderlichen Eigenschafts Werten ordnungsgemäß initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3ea97-108">It must be correctly initialized with all the required property values.</span></span>

`lFlags`\
<span data-ttu-id="3ea97-109">in Eine Kombination von Flags, die sich auf das Verhalten dieser Funktion auswirken.</span><span class="sxs-lookup"><span data-stu-id="3ea97-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="3ea97-110">Die folgenden Werte sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="3ea97-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3ea97-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="3ea97-111">Constant</span></span>  |<span data-ttu-id="3ea97-112">Wert</span><span class="sxs-lookup"><span data-stu-id="3ea97-112">Value</span></span>  |<span data-ttu-id="3ea97-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ea97-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="3ea97-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="3ea97-114">0x20000</span></span> | <span data-ttu-id="3ea97-115">Wenn diese Einstellung festgelegt ist, speichert WMI keine Qualifizierer mit der geänderten Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="3ea97-115">If set, WMI does not store any qualifiers with the amended flavor.</span></span> <br> <span data-ttu-id="3ea97-116">Wenn nicht festgelegt, wird davon ausgegangen, dass dieses Objekt nicht lokalisiert ist, und alle Qualifizierer werden mit dieser Instanz gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3ea97-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="3ea97-117">0</span><span class="sxs-lookup"><span data-stu-id="3ea97-117">0</span></span> | <span data-ttu-id="3ea97-118">Erstellen Sie die Klasse, wenn Sie nicht vorhanden ist, oder überschreiben Sie Sie, falls Sie bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3ea97-118">Create the class if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="3ea97-119">1</span><span class="sxs-lookup"><span data-stu-id="3ea97-119">1</span></span> | <span data-ttu-id="3ea97-120">Aktualisieren Sie die-Klasse.</span><span class="sxs-lookup"><span data-stu-id="3ea97-120">Update the class.</span></span> <span data-ttu-id="3ea97-121">Die Klasse muss vorhanden sein, damit der-Befehl erfolgreich ausgeführt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="3ea97-121">The class must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="3ea97-122">2</span><span class="sxs-lookup"><span data-stu-id="3ea97-122">2</span></span> | <span data-ttu-id="3ea97-123">Erstellen Sie die-Klasse.</span><span class="sxs-lookup"><span data-stu-id="3ea97-123">Create the class.</span></span> <span data-ttu-id="3ea97-124">Der-Rückruf schlägt fehl, wenn die Klasse bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3ea97-124">The call fails if the class already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="3ea97-125">0x10</span><span class="sxs-lookup"><span data-stu-id="3ea97-125">0x10</span></span> | <span data-ttu-id="3ea97-126">Das-Flag verursacht einen semisynchronen-Rückruf.</span><span class="sxs-lookup"><span data-stu-id="3ea97-126">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_OWNER_UPDATE` | <span data-ttu-id="3ea97-127">0x10000</span><span class="sxs-lookup"><span data-stu-id="3ea97-127">0x10000</span></span> | <span data-ttu-id="3ea97-128">Pushanbieter müssen dieses Flag angeben, wenn Sie `PutClassWmi` aufrufen, um anzugeben, dass sich diese Klasse geändert hat.</span><span class="sxs-lookup"><span data-stu-id="3ea97-128">Push providers must specify this flag when calling `PutClassWmi` to indicate that this class has changed.</span></span> |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | <span data-ttu-id="3ea97-129">0</span><span class="sxs-lookup"><span data-stu-id="3ea97-129">0</span></span> | <span data-ttu-id="3ea97-130">Ermöglicht es, eine Klasse zu aktualisieren, wenn keine abgeleiteten Klassen und keine Instanzen dieser Klasse vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3ea97-130">Allows a class to be updated if there are no derived classes and no instances of that class.</span></span> <span data-ttu-id="3ea97-131">Sie ermöglicht auch Updates in allen Fällen, wenn die Änderung nur an wichtigen Qualifizierern wie dem Beschreibungs Qualifizierer vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="3ea97-131">It also allows updates in all cases if the change is just to unimportant qualifiers, such as the Description qualifier.</span></span> <span data-ttu-id="3ea97-132">Wenn die Klasse über Instanzen oder Änderungen an wichtigen Qualifizierern verfügt, schlägt die Aktualisierung fehl.</span><span class="sxs-lookup"><span data-stu-id="3ea97-132">If the class has instances or changes are to important qualifiers, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | <span data-ttu-id="3ea97-133">0x20</span><span class="sxs-lookup"><span data-stu-id="3ea97-133">0x20</span></span> | <span data-ttu-id="3ea97-134">Ermöglicht das Aktualisieren von Klassen auch dann, wenn untergeordnete Klassen vorhanden sind, wenn die Änderung keine Konflikte mit untergeordneten Klassen verursacht.</span><span class="sxs-lookup"><span data-stu-id="3ea97-134">Allows updates of classes even if there are child classes as long as the change does not cause any conflicts with child classes.</span></span> <span data-ttu-id="3ea97-135">Beispielsweise kann mit diesem Flag eine neue Eigenschaft zur Basisklasse hinzugefügt werden, die nicht zuvor in einer der untergeordneten Klassen erwähnt wurde.</span><span class="sxs-lookup"><span data-stu-id="3ea97-135">For example, this flag allows a new property to be added to the base class that was not previously mentioned in any of the child classes.</span></span> <span data-ttu-id="3ea97-136">Wenn die Klasse über Instanzen verfügt, tritt bei der Aktualisierung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="3ea97-136">If the class has instances, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | <span data-ttu-id="3ea97-137">0x40</span><span class="sxs-lookup"><span data-stu-id="3ea97-137">0x40</span></span> | <span data-ttu-id="3ea97-138">erzwingt das Aktualisieren von Klassen, wenn widersprüchliche untergeordnete Klassen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3ea97-138">forces updates of classes when conflicting child classes exist.</span></span> <span data-ttu-id="3ea97-139">Beispielsweise erzwingt dieses Flag ein Update, wenn ein Klassen Qualifizierer in einer untergeordneten Klasse definiert ist, und die Basisklasse versucht, denselben Qualifizierer hinzuzufügen, der einen Konflikt mit dem vorhandenen Qualifizierer verursacht.</span><span class="sxs-lookup"><span data-stu-id="3ea97-139">For example, this flag forces an update if a class qualifier is defined in a child class, and the base class tries to add the same qualifier which conflicts with the existing one.</span></span> <span data-ttu-id="3ea97-140">Im Force-Modus wird der Konflikt von TIS behoben, indem der widersprüchliche Qualifizierer in der untergeordneten Klasse gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="3ea97-140">In force mode, tis conflict is resolved by deleting the conflicting qualifier in the child class.</span></span> |

`pCtx`\
<span data-ttu-id="3ea97-141">in In der Regel ist dieser Wert `null`.</span><span class="sxs-lookup"><span data-stu-id="3ea97-141">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="3ea97-142">Andernfalls handelt es sich um einen Zeiger auf eine [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, der die angeforderten Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="3ea97-142">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="3ea97-143">vorgenommen Wenn `null`, wird dieser Parameter nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ea97-143">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="3ea97-144">Wenn `lFlags` `WBEM_FLAG_RETURN_IMMEDIATELY`enthält, gibt die Funktion sofort mit `WBEM_S_NO_ERROR`zurück.</span><span class="sxs-lookup"><span data-stu-id="3ea97-144">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="3ea97-145">Der `ppCallResult`-Parameter empfängt einen Zeiger auf ein neues [iwbemcallresult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="3ea97-145">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="3ea97-146">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3ea97-146">Return value</span></span>

<span data-ttu-id="3ea97-147">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="3ea97-147">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3ea97-148">Konstante</span><span class="sxs-lookup"><span data-stu-id="3ea97-148">Constant</span></span>  |<span data-ttu-id="3ea97-149">Wert</span><span class="sxs-lookup"><span data-stu-id="3ea97-149">Value</span></span>  |<span data-ttu-id="3ea97-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ea97-150">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="3ea97-151">0x80041003</span><span class="sxs-lookup"><span data-stu-id="3ea97-151">0x80041003</span></span> | <span data-ttu-id="3ea97-152">Der Benutzer verfügt nicht über die Berechtigung, Klassen zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3ea97-152">The user does not have permission to create or modify classes.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="3ea97-153">0x80041001</span><span class="sxs-lookup"><span data-stu-id="3ea97-153">0x80041001</span></span> | <span data-ttu-id="3ea97-154">Ein nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3ea97-154">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="3ea97-155">0x80041010</span><span class="sxs-lookup"><span data-stu-id="3ea97-155">0x80041010</span></span> | <span data-ttu-id="3ea97-156">Die angegebene Klasse ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="3ea97-156">The specified class is not valid.</span></span> <span data-ttu-id="3ea97-157">Dies weist in der Regel darauf hin, dass `pObject` ein Instanzobjekt angibt.</span><span class="sxs-lookup"><span data-stu-id="3ea97-157">Typically, this indicates that `pObject` specifies an instance object.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3ea97-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3ea97-158">0x80041008</span></span> | <span data-ttu-id="3ea97-159">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="3ea97-159">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID OPERATION` | <span data-ttu-id="3ea97-160">0x80041016</span><span class="sxs-lookup"><span data-stu-id="3ea97-160">0x80041016</span></span> | <span data-ttu-id="3ea97-161">Der angegebene Klassenname ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="3ea97-161">The specified class name is not valid.</span></span> |
| `WBEM_E_CLASS_HAS_CHILDREN` | <span data-ttu-id="3ea97-162">0x80041025</span><span class="sxs-lookup"><span data-stu-id="3ea97-162">0x80041025</span></span> | <span data-ttu-id="3ea97-163">Es wurde versucht, eine Änderung vorzunehmen, durch die eine Unterklasse ungültig wird.</span><span class="sxs-lookup"><span data-stu-id="3ea97-163">An attempt was made to make a change that would invalidate a subclass.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="3ea97-164">0x80041019</span><span class="sxs-lookup"><span data-stu-id="3ea97-164">0x80041019</span></span> | <span data-ttu-id="3ea97-165">Das `WBEM_FLAG_CREATE_ONLY`-Flag wurde angegeben, aber die Klasse ist bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3ea97-165">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the class already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="3ea97-166">0x80041002 angezeigt</span><span class="sxs-lookup"><span data-stu-id="3ea97-166">0x80041002</span></span> | <span data-ttu-id="3ea97-167">`WBEM_FLAG_UPDATE_ONLY` wurde in `lFlags`angegeben, und die Klasse wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="3ea97-167">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, and the class was not found.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="3ea97-168">0x80041020</span><span class="sxs-lookup"><span data-stu-id="3ea97-168">0x80041020</span></span> | <span data-ttu-id="3ea97-169">Die erforderlichen Eigenschaften für Klassen wurden nicht alle festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3ea97-169">The required properties for classes have not all been set.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="3ea97-170">0x80041006</span><span class="sxs-lookup"><span data-stu-id="3ea97-170">0x80041006</span></span> | <span data-ttu-id="3ea97-171">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="3ea97-171">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="3ea97-172">0x80041033</span><span class="sxs-lookup"><span data-stu-id="3ea97-172">0x80041033</span></span> | <span data-ttu-id="3ea97-173">WMI wurde wahrscheinlich angehalten und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="3ea97-173">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="3ea97-174">Ruft [connectserverwmi](connectserverwmi.md) erneut auf.</span><span class="sxs-lookup"><span data-stu-id="3ea97-174">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="3ea97-175">0x80041015</span><span class="sxs-lookup"><span data-stu-id="3ea97-175">0x80041015</span></span> | <span data-ttu-id="3ea97-176">Fehler beim Remote Prozedur Aufruf (RPC)-Link zwischen dem aktuellen Prozess und WMI.</span><span class="sxs-lookup"><span data-stu-id="3ea97-176">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="3ea97-177">0</span><span class="sxs-lookup"><span data-stu-id="3ea97-177">0</span></span> | <span data-ttu-id="3ea97-178">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="3ea97-178">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="3ea97-179">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ea97-179">Remarks</span></span>

<span data-ttu-id="3ea97-180">Diese Funktion umschließt einen aufzurufenden Befehl der [IWbemServices::P utclass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) -Methode.</span><span class="sxs-lookup"><span data-stu-id="3ea97-180">This function wraps a call to the [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) method.</span></span>

<span data-ttu-id="3ea97-181">Der Benutzer kann keine Klassen erstellen, deren Namen mit einem Unterstrich beginnen oder enden.</span><span class="sxs-lookup"><span data-stu-id="3ea97-181">The user may not create classes with names that begin or end with an underscore character.</span></span>

<span data-ttu-id="3ea97-182">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, indem Sie die [GetErrorInfo](geterrorinfo.md) -Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3ea97-182">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="3ea97-183">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ea97-183">Requirements</span></span>

<span data-ttu-id="3ea97-184">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ea97-184">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="3ea97-185">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="3ea97-185">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="3ea97-186">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3ea97-186">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3ea97-187">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ea97-187">See also</span></span>

- [<span data-ttu-id="3ea97-188">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="3ea97-188">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
