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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37810ecab2e02d4ec250dd2a4b2657c3b898f714
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798370"
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="11417-103">Putinstancewmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="11417-103">PutInstanceWmi function</span></span>

<span data-ttu-id="11417-104">Erstellt oder aktualisiert eine Instanz einer vorhandenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="11417-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="11417-105">Die Instanz wird in das WMI-Repository geschrieben.</span><span class="sxs-lookup"><span data-stu-id="11417-105">The instance is written to the WMI repository.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="11417-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="11417-106">Syntax</span></span>

```cpp
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a><span data-ttu-id="11417-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="11417-107">Parameters</span></span>

`pInst`\
<span data-ttu-id="11417-108">in Ein Zeiger auf die zu schreibende-Instanz.</span><span class="sxs-lookup"><span data-stu-id="11417-108">[in] A pointer to the instance to be written.</span></span>

`lFlags`\
<span data-ttu-id="11417-109">in Eine Kombination von Flags, die sich auf das Verhalten dieser Funktion auswirken.</span><span class="sxs-lookup"><span data-stu-id="11417-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="11417-110">Die folgenden Werte sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="11417-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="11417-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="11417-111">Constant</span></span>  |<span data-ttu-id="11417-112">Wert</span><span class="sxs-lookup"><span data-stu-id="11417-112">Value</span></span>  |<span data-ttu-id="11417-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11417-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="11417-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="11417-114">0x20000</span></span> | <span data-ttu-id="11417-115">Wenn diese Einstellung festgelegt ist, speichert WMI keine Qualifizierer mit der **geänderten** Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="11417-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> <br> <span data-ttu-id="11417-116">Wenn nicht festgelegt, wird davon ausgegangen, dass dieses Objekt nicht lokalisiert ist, und alle Qualifizierer werden mit dieser Instanz gespeichert.</span><span class="sxs-lookup"><span data-stu-id="11417-116">If not set, it is assumed that this object is not localized, and all qualifiers are stored with this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="11417-117">0</span><span class="sxs-lookup"><span data-stu-id="11417-117">0</span></span> | <span data-ttu-id="11417-118">Erstellen Sie die Instanz, wenn Sie nicht vorhanden ist, oder überschreiben Sie Sie, falls Sie bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="11417-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="11417-119">1</span><span class="sxs-lookup"><span data-stu-id="11417-119">1</span></span> | <span data-ttu-id="11417-120">Aktualisieren Sie die-Instanz.</span><span class="sxs-lookup"><span data-stu-id="11417-120">Update the instance.</span></span> <span data-ttu-id="11417-121">Die Instanz muss vorhanden sein, damit der-Befehl erfolgreich ausgeführt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="11417-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="11417-122">2</span><span class="sxs-lookup"><span data-stu-id="11417-122">2</span></span> | <span data-ttu-id="11417-123">Erstellen Sie die-Instanz.</span><span class="sxs-lookup"><span data-stu-id="11417-123">Create the instance.</span></span> <span data-ttu-id="11417-124">Der-Rückruf schlägt fehl, wenn die Instanz bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="11417-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="11417-125">0x10</span><span class="sxs-lookup"><span data-stu-id="11417-125">0x10</span></span> | <span data-ttu-id="11417-126">Das-Flag verursacht einen semisynchronen-Rückruf.</span><span class="sxs-lookup"><span data-stu-id="11417-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`\
<span data-ttu-id="11417-127">in Normalerweise ist `null`dieser Wert.</span><span class="sxs-lookup"><span data-stu-id="11417-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="11417-128">Andernfalls handelt es sich um einen Zeiger auf eine [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, der die angeforderten Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="11417-128">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppCallResult`\
<span data-ttu-id="11417-129">vorgenommen Wenn `null`der Wert ist, wird dieser Parameter nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="11417-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="11417-130">Wenn `lFlags` `WBEM_S_NO_ERROR`enthält `WBEM_FLAG_RETURN_IMMEDIATELY`, gibt die Funktion sofort mit zurück.</span><span class="sxs-lookup"><span data-stu-id="11417-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="11417-131">Der `ppCallResult` -Parameter empfängt einen Zeiger auf ein neues [iwbemcallresult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="11417-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="11417-132">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="11417-132">Return value</span></span>

<span data-ttu-id="11417-133">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="11417-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="11417-134">Konstante</span><span class="sxs-lookup"><span data-stu-id="11417-134">Constant</span></span>  |<span data-ttu-id="11417-135">Wert</span><span class="sxs-lookup"><span data-stu-id="11417-135">Value</span></span>  |<span data-ttu-id="11417-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="11417-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="11417-137">0x80041003</span><span class="sxs-lookup"><span data-stu-id="11417-137">0x80041003</span></span> | <span data-ttu-id="11417-138">Der Benutzer verfügt nicht über die Berechtigung zum Aktualisieren einer Instanz der angegebenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="11417-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="11417-139">0x80041001</span><span class="sxs-lookup"><span data-stu-id="11417-139">0x80041001</span></span> | <span data-ttu-id="11417-140">Ein nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="11417-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="11417-141">0x80041010</span><span class="sxs-lookup"><span data-stu-id="11417-141">0x80041010</span></span> | <span data-ttu-id="11417-142">Die Klasse, die diese Instanz unterstützt, ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="11417-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="11417-143">0x80041028</span><span class="sxs-lookup"><span data-stu-id="11417-143">0x80041028</span></span> | <span data-ttu-id="11417-144">eine `null` wurde für eine Eigenschaft angegeben, die nicht `null`sein kann, z. b. eine, die durch einen **indizierten** oder **Not_Null** -Qualifizierer gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="11417-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="11417-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="11417-145">0x8004100f</span></span> | <span data-ttu-id="11417-146">Die angegebene Instanz ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="11417-146">The specified instance is not valid.</span></span> <span data-ttu-id="11417-147">(Wenn z. b `PutInstanceWmi` . mit einer Klasse aufgerufen wird, wird dieser Wert zurückgegeben.)</span><span class="sxs-lookup"><span data-stu-id="11417-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="11417-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="11417-148">0x80041008</span></span> | <span data-ttu-id="11417-149">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="11417-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="11417-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="11417-150">0x80041019</span></span> | <span data-ttu-id="11417-151">Das `WBEM_FLAG_CREATE_ONLY` Flag wurde angegeben, aber die Instanz ist bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="11417-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="11417-152">0x80041002</span><span class="sxs-lookup"><span data-stu-id="11417-152">0x80041002</span></span> | <span data-ttu-id="11417-153">`WBEM_FLAG_UPDATE_ONLY`wurde in `lFlags`angegeben, aber die Instanz ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="11417-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="11417-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="11417-154">0x80041006</span></span> | <span data-ttu-id="11417-155">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="11417-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="11417-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="11417-156">0x80041033</span></span> | <span data-ttu-id="11417-157">WMI wurde wahrscheinlich angehalten und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="11417-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="11417-158">Ruft [connectserverwmi](connectserverwmi.md) erneut auf.</span><span class="sxs-lookup"><span data-stu-id="11417-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="11417-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="11417-159">0x80041015</span></span> | <span data-ttu-id="11417-160">Fehler beim Remote Prozedur Aufruf (RPC)-Link zwischen dem aktuellen Prozess und WMI.</span><span class="sxs-lookup"><span data-stu-id="11417-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="11417-161">0</span><span class="sxs-lookup"><span data-stu-id="11417-161">0</span></span> | <span data-ttu-id="11417-162">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="11417-162">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="11417-163">Hinweise</span><span class="sxs-lookup"><span data-stu-id="11417-163">Remarks</span></span>

<span data-ttu-id="11417-164">Diese Funktion umschließt einen Rückruf für die [IWbemServices::P utinstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) -Methode.</span><span class="sxs-lookup"><span data-stu-id="11417-164">This function wraps a call to the [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) method.</span></span>

<span data-ttu-id="11417-165">Die `PutInstanceWmi` -Funktion unterstützt das Erstellen von-Instanzen und das Aktualisieren von Instanzen vorhandener Klassen.</span><span class="sxs-lookup"><span data-stu-id="11417-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="11417-166">Abhängig davon, wie `pCtx` der-Parameter festgelegt wird, werden entweder einige oder alle Eigenschaften der-Instanz aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="11417-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span>

<span data-ttu-id="11417-167">Wenn die-Instanz, auf `pInst` die von verwiesen wird, zu einer-Unterklasse gehört, ruft die Windows-Verwaltung alle für die Klassen verantwortlichen Anbieter auf, von denen die Unterklasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="11417-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="11417-168">Alle diese Anbieter müssen erfolgreich sein, damit die `PutInstanceWmi` ursprüngliche Anforderung erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="11417-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="11417-169">Der Anbieter, der die oberste Klasse in der Hierarchie unterstützt, wird zuerst aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="11417-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="11417-170">Die Aufruf Reihenfolge setzt mit der Unterklasse der obersten Klasse fort und geht von oben nach unten fort, bis die Windows-Verwaltung den Anbieter für die Klasse erreicht hat `pInst`, auf die die Instanz verweist.</span><span class="sxs-lookup"><span data-stu-id="11417-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="11417-171">Die Windows-Verwaltung Ruft die Anbieter für keine der untergeordneten Klassen einer-Instanz auf.</span><span class="sxs-lookup"><span data-stu-id="11417-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span>

<span data-ttu-id="11417-172">Wenn eine Anwendung eine Instanz aktualisieren muss, die zu einer Klassenhierarchie gehört `pInst` , muss der Parameter auf die Instanz verweisen, die die zu ändernden Eigenschaften enthält.</span><span class="sxs-lookup"><span data-stu-id="11417-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="11417-173">Das heißt, eine Ziel Instanz, die zu **ClassB**gehört.</span><span class="sxs-lookup"><span data-stu-id="11417-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="11417-174">Die **ClassB** -Instanz ist von **ClassA**abgeleitet, und **ClassA** definiert die Eigenschafts **propa**.</span><span class="sxs-lookup"><span data-stu-id="11417-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="11417-175">Wenn eine Anwendung eine Änderung an dem Wert von **propa** in der **ClassB** -Instanz vornehmen möchte, muss Sie auf `pInst` diese Instanz und nicht auf eine Instanz von **ClassA**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="11417-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="11417-176">Das `PutInstanceWmi` Aufrufen von für eine Instanz einer abstrakten Klasse ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="11417-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="11417-177">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, indem Sie die [GetErrorInfo](geterrorinfo.md) -Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="11417-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="11417-178">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="11417-178">Requirements</span></span>

<span data-ttu-id="11417-179">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11417-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="11417-180">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="11417-180">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="11417-181">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="11417-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="11417-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11417-182">See also</span></span>

- [<span data-ttu-id="11417-183">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="11417-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
