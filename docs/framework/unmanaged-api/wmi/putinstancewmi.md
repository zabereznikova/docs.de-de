---
title: PutInstanceWmi-Funktion (Referenz zur nicht verwalteten API)
description: Die Funktion PutInstanceWmi erstellt oder aktualisiert eine Instanz einer vorhandenen Klasse.
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
ms.openlocfilehash: 0db08ef4938a88ee657e2d65dda70edac09df8ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462159"
---
# <a name="putinstancewmi-function"></a><span data-ttu-id="a3996-103">PutInstanceWmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="a3996-103">PutInstanceWmi function</span></span>
<span data-ttu-id="a3996-104">Erstellt oder aktualisiert eine Instanz einer vorhandenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="a3996-104">Creates or updates an instance of an existing class.</span></span> <span data-ttu-id="a3996-105">Die Instanz wird in das WMI-Repository geschrieben.</span><span class="sxs-lookup"><span data-stu-id="a3996-105">The instance is written to the WMI repository.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="a3996-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3996-106">Syntax</span></span>  
  
```  
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a><span data-ttu-id="a3996-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="a3996-107">Parameters</span></span>

`pInst`    
<span data-ttu-id="a3996-108">[in] Ein Zeiger auf die Instanz Writen sein.</span><span class="sxs-lookup"><span data-stu-id="a3996-108">[in] A pointer to the instance to be writen.</span></span>

`lFlags`   
<span data-ttu-id="a3996-109">[in] Eine Kombination von Flags, die das Verhalten dieser Funktion beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="a3996-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="a3996-110">Die folgenden Werte werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="a3996-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="a3996-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="a3996-111">Constant</span></span>  |<span data-ttu-id="a3996-112">Wert</span><span class="sxs-lookup"><span data-stu-id="a3996-112">Value</span></span>  |<span data-ttu-id="a3996-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3996-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="a3996-114">0 x 20000</span><span class="sxs-lookup"><span data-stu-id="a3996-114">0x20000</span></span> | <span data-ttu-id="a3996-115">Wenn festgelegt, WMI keine Qualifizierer mit speichert die **Amended** Flavor.</span><span class="sxs-lookup"><span data-stu-id="a3996-115">If set, WMI does not store any qualifiers with the **Amended** flavor.</span></span> </br> <span data-ttu-id="a3996-116">Wenn dies nicht festgelegt ist, wird davon ausgegangen, dass dieses Objekt nicht lokalisiert ist und alle Qualifizierer Storedwith dieser Instanz.</span><span class="sxs-lookup"><span data-stu-id="a3996-116">If not set, it is assumed that this object is not localized, and all qualifiers are storedwith this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="a3996-117">0</span><span class="sxs-lookup"><span data-stu-id="a3996-117">0</span></span> | <span data-ttu-id="a3996-118">Erstellen Sie die Instanz aus, wenn sie nicht vorhanden, oder sie zu überschreiben, wenn sie bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a3996-118">Create the instance if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="a3996-119">1</span><span class="sxs-lookup"><span data-stu-id="a3996-119">1</span></span> | <span data-ttu-id="a3996-120">Aktualisieren Sie die Instanz.</span><span class="sxs-lookup"><span data-stu-id="a3996-120">Update the instance.</span></span> <span data-ttu-id="a3996-121">Die Instanz muss vorhanden sein, der Aufruf erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="a3996-121">The instance must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="a3996-122">2</span><span class="sxs-lookup"><span data-stu-id="a3996-122">2</span></span> | <span data-ttu-id="a3996-123">Erstellen Sie die Instanz.</span><span class="sxs-lookup"><span data-stu-id="a3996-123">Create the instance.</span></span> <span data-ttu-id="a3996-124">Der Aufruf fehlschlägt, wenn die Instanz bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a3996-124">The call fails if the instance already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="a3996-125">0x10</span><span class="sxs-lookup"><span data-stu-id="a3996-125">0x10</span></span> | <span data-ttu-id="a3996-126">Das Flag wird halbsynchrone aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a3996-126">The flag causes a semisynchronous call.</span></span> |

`pCtx`  
<span data-ttu-id="a3996-127">[in] In der Regel wird dieser Wert ist `null`.</span><span class="sxs-lookup"><span data-stu-id="a3996-127">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="a3996-128">Andernfalls ist ein Zeiger auf ein ["IWbemContext"](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) -Instanz, die vom Anbieter verwendet werden kann, das die angeforderte Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a3996-128">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppCallResult`  
<span data-ttu-id="a3996-129">[out] Wenn `null`, dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="a3996-129">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="a3996-130">Wenn `lFlags` enthält `WBEM_FLAG_RETURN_IMMEDIATELY`, die Funktion gibt sofort mit `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="a3996-130">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="a3996-131">Die `ppCallResult` Parameter erhält einen Zeiger auf ein neues [IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx) Objekt.</span><span class="sxs-lookup"><span data-stu-id="a3996-131">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="a3996-132">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a3996-132">Return value</span></span>

<span data-ttu-id="a3996-133">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="a3996-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a3996-134">Konstante</span><span class="sxs-lookup"><span data-stu-id="a3996-134">Constant</span></span>  |<span data-ttu-id="a3996-135">Wert</span><span class="sxs-lookup"><span data-stu-id="a3996-135">Value</span></span>  |<span data-ttu-id="a3996-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3996-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="a3996-137">0 x 80041003</span><span class="sxs-lookup"><span data-stu-id="a3996-137">0x80041003</span></span> | <span data-ttu-id="a3996-138">Der Benutzer nicht über die Berechtigung zum Aktualisieren einer Instanz der angegebenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="a3996-138">The user does not have permission to update an instance of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="a3996-139">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="a3996-139">0x80041001</span></span> | <span data-ttu-id="a3996-140">Nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a3996-140">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="a3996-141">0 x 80041010</span><span class="sxs-lookup"><span data-stu-id="a3996-141">0x80041010</span></span> | <span data-ttu-id="a3996-142">Die Klasse, die Unterstützung dieser Instanz ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="a3996-142">The class supporting this instance is not valid.</span></span> |
| `WBEM_E_ILLEGAL_NULL` | <span data-ttu-id="a3996-143">0x80041028</span><span class="sxs-lookup"><span data-stu-id="a3996-143">0x80041028</span></span> | <span data-ttu-id="a3996-144">eine `null` Zielsätzen für eine Eigenschaft, die nicht möglich `null`, z. B. die von markiert ist ein **indiziert** oder **Not_Null** Qualifizierer.</span><span class="sxs-lookup"><span data-stu-id="a3996-144">a `null` was specified for a property that cannot be `null`, such as one that is marked by an **Indexed** or **Not_Null** qualifier.</span></span> |
| `WBEM_E_INVALID_OBJECT` | <span data-ttu-id="a3996-145">0x8004100f</span><span class="sxs-lookup"><span data-stu-id="a3996-145">0x8004100f</span></span> | <span data-ttu-id="a3996-146">Die angegebene Instanz ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="a3996-146">The specified instance is not valid.</span></span> <span data-ttu-id="a3996-147">(Z. B. durch Aufruf von `PutInstanceWmi` mit einer Klasse gibt diesen Wert zurück.)</span><span class="sxs-lookup"><span data-stu-id="a3996-147">(For example, calling `PutInstanceWmi` with a class returns this value.)</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a3996-148">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="a3996-148">0x80041008</span></span> | <span data-ttu-id="a3996-149">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="a3996-149">A parameter is not valid.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="a3996-150">0x80041019</span><span class="sxs-lookup"><span data-stu-id="a3996-150">0x80041019</span></span> | <span data-ttu-id="a3996-151">Die `WBEM_FLAG_CREATE_ONLY` -Flag angegeben wurde, aber die Instanz ist bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a3996-151">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the instance already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="a3996-152">0x80041002</span><span class="sxs-lookup"><span data-stu-id="a3996-152">0x80041002</span></span> | <span data-ttu-id="a3996-153">`WBEM_FLAG_UPDATE_ONLY` wurde im angegebenen `lFlags`, aber die Instanz ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a3996-153">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, but the instance does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="a3996-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="a3996-154">0x80041006</span></span> | <span data-ttu-id="a3996-155">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="a3996-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="a3996-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="a3996-156">0x80041033</span></span> | <span data-ttu-id="a3996-157">WMI wurde wahrscheinlich beendet und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="a3996-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="a3996-158">Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus.</span><span class="sxs-lookup"><span data-stu-id="a3996-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="a3996-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="a3996-159">0x80041015</span></span> | <span data-ttu-id="a3996-160">Der Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-ausgefallen ist.</span><span class="sxs-lookup"><span data-stu-id="a3996-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="a3996-161">0</span><span class="sxs-lookup"><span data-stu-id="a3996-161">0</span></span> | <span data-ttu-id="a3996-162">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="a3996-162">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="a3996-163">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a3996-163">Remarks</span></span>

<span data-ttu-id="a3996-164">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemServices::PutInstance](https://msdn.microsoft.com/library/aa392115(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="a3996-164">This function wraps a call to the [IWbemServices::PutInstance](https://msdn.microsoft.com/library/aa392115(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="a3996-165">Die `PutInstanceWmi` -Funktion unterstützt das Erstellen von Instanzen und Instanzen von vorhandenen Klassen nur aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a3996-165">The `PutInstanceWmi` function supports creating instances and updating instances of existing classes only.</span></span>  <span data-ttu-id="a3996-166">Je nachdem, wie der `pCtx` Parameter festgelegt ist, einige oder alle Eigenschaften der Instanz aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="a3996-166">Depending on how the `pCtx` parameter is set, either some or all of the properties of the instance are updated.</span></span> 

<span data-ttu-id="a3996-167">Wenn die Instanz verweist, zu `pInst` gehört zu einer Unterklasse, die Verwaltung von Windows ruft alle Anbieter, die verantwortlich für die Klassen, die von der Unterklasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="a3996-167">When the instance pointed to by `pInst` belongs to a subclass, Windows Management calls all the providers responsible for the classes from which the subclass derives.</span></span> <span data-ttu-id="a3996-168">Alle diese Anbieter muss erfolgreich sein, für die ursprüngliche `PutInstanceWmi` Anforderung erfolgreich verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a3996-168">All of these providers must succeed for the original `PutInstanceWmi` request to succeed.</span></span> <span data-ttu-id="a3996-169">Der Anbieter unterstützt die oberste Klasse in der Hierarchie wird zuerst aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a3996-169">The provider supporting the topmost class in the hierarchy is called first.</span></span> <span data-ttu-id="a3996-170">Die Reihenfolge des Aufrufs angezeigt mit die Unterklasse der obersten Klasse fortgesetzt und von oben nach unten verläuft wird, bis Windows Management den Anbieter für die Klasse, die Besitzer der Instanz verweist erreicht `pInst`.</span><span class="sxs-lookup"><span data-stu-id="a3996-170">The calling order continues with the subclass of the topmost class and proceeds from top to bottom until Windows Management reaches the provider for the class owning the instance pointed to by `pInst`.</span></span>
<span data-ttu-id="a3996-171">Verwaltung von Windows wird die Anbieter für alle untergeordneten Klassen einer Instanz nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a3996-171">Windows Management does not call the providers for any of the child classes of an instance.</span></span> 

<span data-ttu-id="a3996-172">Wenn eine Anwendung eine Instanz aktualisieren muss, die zu einer Klassenhierarchie gehört die `pInst` Parameter muss mit der Instanz, die mit den zu ändernden Eigenschaften verweisen.</span><span class="sxs-lookup"><span data-stu-id="a3996-172">When an application must update an instance that belongs to a class hierarchy, the `pInst` parameter must point to the instance containing the properties to be modified.</span></span> <span data-ttu-id="a3996-173">Betrachten Sie also eine Zielinstanz, die zu gehört **ClassB**.</span><span class="sxs-lookup"><span data-stu-id="a3996-173">That is, consider a target instance that belongs to **ClassB**.</span></span> <span data-ttu-id="a3996-174">Die **ClassB** Instanz leitet sich von **ClassA**, und **ClassA** definiert die Eigenschaft **PropA**.</span><span class="sxs-lookup"><span data-stu-id="a3996-174">The **ClassB** instance derives from **ClassA**, and **ClassA** defines the property **PropA**.</span></span> <span data-ttu-id="a3996-175">Wenn eine Anwendung eine Änderung an den Wert der vornehmen möchte **PropA** in der **ClassB** Instanz müssen sie festlegen `pInst` auf diese Instanz statt mit einer Instanz von **ClassA** .</span><span class="sxs-lookup"><span data-stu-id="a3996-175">If an application wants to make a change to the value of **PropA** in the **ClassB** instance, it must set `pInst` to that instance rather than an instance of **ClassA**.</span></span>

<span data-ttu-id="a3996-176">Aufrufen von `PutInstanceWmi` auf einer Instanz einer abstrakten Klasse ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="a3996-176">Calling `PutInstanceWmi` on an instance of an abstract class is not allowed.</span></span>

<span data-ttu-id="a3996-177">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch Aufrufen der [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="a3996-177">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="a3996-178">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3996-178">Requirements</span></span>  
 <span data-ttu-id="a3996-179">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3996-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3996-180">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a3996-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a3996-181">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a3996-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3996-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3996-182">See also</span></span>  
[<span data-ttu-id="a3996-183">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="a3996-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
