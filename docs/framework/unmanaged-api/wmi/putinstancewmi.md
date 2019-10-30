---
title: Putinstancewmi-Funktion (Referenz zur nicht verwalteten API)
description: Die putinstancewmi-Funktion erstellt oder aktualisiert eine Instanz einer vorhandenen Klasse.
ms.date: 11/06/2017
api_name:
- PutInstanceWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutInstanceWmi
helpviewer_keywords:
- PutInstanceWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: b33f31d69c64ce520580c29f1014c058c78d0953
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127357"
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="ca039-103">Putinstancewmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="ca039-103">PutInstanceWmi function</span></span>

<span data-ttu-id="ca039-104">Erstellt oder aktualisiert eine Instanz einer vorhandenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="ca039-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="ca039-105">Die Instanz wird in das WMI-Repository geschrieben.</span><span class="sxs-lookup"><span data-stu-id="ca039-105">The instance is written to the WMI repository.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ca039-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca039-106">Syntax</span></span>

```cpp
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="ca039-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca039-107">Parameters</span></span>

`pInst`\
<span data-ttu-id="ca039-108">in Ein Zeiger auf die zu schreibende-Instanz.</span><span class="sxs-lookup"><span data-stu-id="ca039-108">[in] A pointer to the instance to be written.</span></span>

`lFlags`\
<span data-ttu-id="ca039-109">in Eine Kombination von Flags, die sich auf das Verhalten dieser Funktion auswirken.</span><span class="sxs-lookup"><span data-stu-id="ca039-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="ca039-110">Die folgenden Werte sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="ca039-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ca039-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="ca039-111">Constant</span></span>  |<span data-ttu-id="ca039-112">Wert</span><span class="sxs-lookup"><span data-stu-id="ca039-112">Value</span></span>  |<span data-ttu-id="ca039-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca039-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="ca039-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="ca039-114">0x20000</span></span> | <span data-ttu-id="ca039-115">Wenn diese Einstellung festgelegt ist, speichert WMI keine Qualifizierer mit der **geänderten** Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ca039-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> <br> <span data-ttu-id="ca039-116">Wenn nicht festgelegt, wird davon ausgegangen, dass dieses Objekt nicht lokalisiert ist, und alle Qualifizierer werden mit dieser Instanz gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ca039-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="ca039-117">0</span><span class="sxs-lookup"><span data-stu-id="ca039-117">0</span></span> | <span data-ttu-id="ca039-118">Erstellen Sie die Instanz, wenn Sie nicht vorhanden ist, oder überschreiben Sie Sie, falls Sie bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ca039-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="ca039-119">1</span><span class="sxs-lookup"><span data-stu-id="ca039-119">1</span></span> | <span data-ttu-id="ca039-120">Aktualisieren Sie die-Instanz.</span><span class="sxs-lookup"><span data-stu-id="ca039-120">Update the instance.</span></span> <span data-ttu-id="ca039-121">Die Instanz muss vorhanden sein, damit der-Befehl erfolgreich ausgeführt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="ca039-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="ca039-122">2</span><span class="sxs-lookup"><span data-stu-id="ca039-122">2</span></span> | <span data-ttu-id="ca039-123">Erstellen Sie die-Instanz.</span><span class="sxs-lookup"><span data-stu-id="ca039-123">Create the instance.</span></span> <span data-ttu-id="ca039-124">Der-Rückruf schlägt fehl, wenn die Instanz bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ca039-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="ca039-125">0x10</span><span class="sxs-lookup"><span data-stu-id="ca039-125">0x10</span></span> | <span data-ttu-id="ca039-126">Das-Flag verursacht einen semisynchronen-Rückruf.</span><span class="sxs-lookup"><span data-stu-id="ca039-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`\
<span data-ttu-id="ca039-127">in In der Regel ist dieser Wert `null`.</span><span class="sxs-lookup"><span data-stu-id="ca039-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="ca039-128">Andernfalls handelt es sich um einen Zeiger auf eine [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, der die angeforderten Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ca039-128">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="ca039-129">vorgenommen Wenn `null`, wird dieser Parameter nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca039-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="ca039-130">Wenn `lFlags` `WBEM_FLAG_RETURN_IMMEDIATELY`enthält, gibt die Funktion sofort mit `WBEM_S_NO_ERROR`zurück.</span><span class="sxs-lookup"><span data-stu-id="ca039-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="ca039-131">Der `ppCallResult`-Parameter empfängt einen Zeiger auf ein neues [iwbemcallresult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="ca039-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="ca039-132">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ca039-132">Return value</span></span>

<span data-ttu-id="ca039-133">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="ca039-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ca039-134">Konstante</span><span class="sxs-lookup"><span data-stu-id="ca039-134">Constant</span></span>  |<span data-ttu-id="ca039-135">Wert</span><span class="sxs-lookup"><span data-stu-id="ca039-135">Value</span></span>  |<span data-ttu-id="ca039-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca039-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="ca039-137">0x80041003</span><span class="sxs-lookup"><span data-stu-id="ca039-137">0x80041003</span></span> | <span data-ttu-id="ca039-138">Der Benutzer verfügt nicht über die Berechtigung zum Aktualisieren einer Instanz der angegebenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="ca039-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="ca039-139">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ca039-139">0x80041001</span></span> | <span data-ttu-id="ca039-140">Ein nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ca039-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="ca039-141">0x80041010</span><span class="sxs-lookup"><span data-stu-id="ca039-141">0x80041010</span></span> | <span data-ttu-id="ca039-142">Die Klasse, die diese Instanz unterstützt, ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="ca039-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="ca039-143">0x80041028</span><span class="sxs-lookup"><span data-stu-id="ca039-143">0x80041028</span></span> | <span data-ttu-id="ca039-144">eine `null` wurde für eine Eigenschaft angegeben, die nicht `null`werden kann, z. b. eine, die durch einen **indizierten** oder **Not_Null** -Qualifizierer gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="ca039-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="ca039-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="ca039-145">0x8004100f</span></span> | <span data-ttu-id="ca039-146">Die angegebene Instanz ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="ca039-146">The specified instance is not valid.</span></span> <span data-ttu-id="ca039-147">(Wenn Sie beispielsweise `PutInstanceWmi` mit einer-Klasse aufrufen, wird dieser Wert zurückgegeben.)</span><span class="sxs-lookup"><span data-stu-id="ca039-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ca039-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ca039-148">0x80041008</span></span> | <span data-ttu-id="ca039-149">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="ca039-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="ca039-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="ca039-150">0x80041019</span></span> | <span data-ttu-id="ca039-151">Das `WBEM_FLAG_CREATE_ONLY`-Flag wurde angegeben, aber die Instanz ist bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ca039-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="ca039-152">0x80041002 angezeigt</span><span class="sxs-lookup"><span data-stu-id="ca039-152">0x80041002</span></span> | <span data-ttu-id="ca039-153">in `lFlags`wurde `WBEM_FLAG_UPDATE_ONLY` angegeben, aber die Instanz ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ca039-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ca039-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ca039-154">0x80041006</span></span> | <span data-ttu-id="ca039-155">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ca039-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="ca039-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="ca039-156">0x80041033</span></span> | <span data-ttu-id="ca039-157">WMI wurde wahrscheinlich angehalten und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="ca039-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="ca039-158">Ruft [connectserverwmi](connectserverwmi.md) erneut auf.</span><span class="sxs-lookup"><span data-stu-id="ca039-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="ca039-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="ca039-159">0x80041015</span></span> | <span data-ttu-id="ca039-160">Fehler beim Remote Prozedur Aufruf (RPC)-Link zwischen dem aktuellen Prozess und WMI.</span><span class="sxs-lookup"><span data-stu-id="ca039-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ca039-161">0</span><span class="sxs-lookup"><span data-stu-id="ca039-161">0</span></span> | <span data-ttu-id="ca039-162">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="ca039-162">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ca039-163">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca039-163">Remarks</span></span>

<span data-ttu-id="ca039-164">Diese Funktion umschließt einen Rückruf für die [IWbemServices::P utinstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) -Methode.</span><span class="sxs-lookup"><span data-stu-id="ca039-164">This function wraps a call to the [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) method.</span></span>

<span data-ttu-id="ca039-165">Die `PutInstanceWmi`-Funktion unterstützt das Erstellen von-Instanzen und das Aktualisieren von Instanzen vorhandener Klassen.</span><span class="sxs-lookup"><span data-stu-id="ca039-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="ca039-166">Abhängig davon, wie der `pCtx`-Parameter festgelegt wird, werden entweder einige oder alle Eigenschaften der-Instanz aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="ca039-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span>

<span data-ttu-id="ca039-167">Wenn die-Instanz, auf die `pInst` verweist, zu einer Unterklasse gehört, ruft die Windows-Verwaltung alle Anbieter auf, die für die Klassen verantwortlich sind, von denen die Unterklasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="ca039-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="ca039-168">Alle diese Anbieter müssen erfolgreich sein, damit die ursprüngliche `PutInstanceWmi` Anforderung erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ca039-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="ca039-169">Der Anbieter, der die oberste Klasse in der Hierarchie unterstützt, wird zuerst aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ca039-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="ca039-170">Die Aufruf Reihenfolge wird mit der Unterklasse der obersten Klasse fortgesetzt und geht von oben nach unten fort, bis die Windows-Verwaltung den Anbieter für die Klasse erreicht hat, auf die `pInst`verweist.</span><span class="sxs-lookup"><span data-stu-id="ca039-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="ca039-171">Die Windows-Verwaltung Ruft die Anbieter für keine der untergeordneten Klassen einer-Instanz auf.</span><span class="sxs-lookup"><span data-stu-id="ca039-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span>

<span data-ttu-id="ca039-172">Wenn eine Anwendung eine Instanz aktualisieren muss, die zu einer Klassenhierarchie gehört, muss der `pInst`-Parameter auf die Instanz verweisen, die die zu ändernden Eigenschaften enthält.</span><span class="sxs-lookup"><span data-stu-id="ca039-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="ca039-173">Das heißt, eine Ziel Instanz, die zu **ClassB**gehört.</span><span class="sxs-lookup"><span data-stu-id="ca039-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="ca039-174">Die **ClassB** -Instanz ist von **ClassA**abgeleitet, und **ClassA** definiert die Eigenschafts **propa**.</span><span class="sxs-lookup"><span data-stu-id="ca039-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="ca039-175">Wenn eine Anwendung eine Änderung am Wert von **propa** in der **ClassB** -Instanz vornehmen möchte, muss `pInst` auf diese Instanz und nicht auf eine Instanz von **ClassA**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ca039-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="ca039-176">Das Aufrufen von `PutInstanceWmi` für eine Instanz einer abstrakten Klasse ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="ca039-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="ca039-177">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, indem Sie die [GetErrorInfo](geterrorinfo.md) -Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ca039-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="ca039-178">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ca039-178">Requirements</span></span>

<span data-ttu-id="ca039-179">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca039-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="ca039-180">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="ca039-180">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="ca039-181">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ca039-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ca039-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca039-182">See also</span></span>

- [<span data-ttu-id="ca039-183">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="ca039-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
