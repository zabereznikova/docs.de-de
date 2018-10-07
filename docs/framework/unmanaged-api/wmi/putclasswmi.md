---
title: PutClassWmi-Funktion (Referenz zur nicht verwalteten API)
description: Die PutClassWmi-Funktion wird eine neue Klasse erstellt oder aktualisiert eine bereits vorhandene.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de08662a825a84f19a40863cf73481d89364ebd0
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836205"
---
# <a name="putclasswmi-function"></a><span data-ttu-id="8c524-103">PutClassWmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="8c524-103">PutClassWmi function</span></span>
<span data-ttu-id="8c524-104">Erstellt eine neue Klasse oder aktualisiert eine vorhandene Klasse.</span><span class="sxs-lookup"><span data-stu-id="8c524-104">Creates a new class or updates an existing one.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="8c524-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c524-105">Syntax</span></span>  
  
```  
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a><span data-ttu-id="8c524-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8c524-106">Parameters</span></span>

`pObject`    
<span data-ttu-id="8c524-107">[in] Ein Zeiger auf eine gültige Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="8c524-107">[in] A pointer to a valid class definition.</span></span> <span data-ttu-id="8c524-108">Es muss ordnungsgemäß mit allen Werten für die erforderliche Eigenschaft initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="8c524-108">It must be correctly initialized with all the required property values.</span></span>

`lFlags`   
<span data-ttu-id="8c524-109">[in] Eine Kombination von Flags, die das Verhalten dieser Funktion zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="8c524-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="8c524-110">Die folgenden Werte werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="8c524-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="8c524-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="8c524-111">Constant</span></span>  |<span data-ttu-id="8c524-112">Wert</span><span class="sxs-lookup"><span data-stu-id="8c524-112">Value</span></span>  |<span data-ttu-id="8c524-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c524-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="8c524-114">0 x 20000</span><span class="sxs-lookup"><span data-stu-id="8c524-114">0x20000</span></span> | <span data-ttu-id="8c524-115">Wenn festgelegt ist, WMI keine keine Qualifizierer mit den geänderten Typ gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="8c524-115">If set, WMI does not store any qualifiers with the amended flavor.</span></span> </br> <span data-ttu-id="8c524-116">Wenn dies nicht festgelegt ist, wird davon ausgegangen, dass dieses Objekt nicht lokalisiert ist und alle Qualifizierer Storedwith dieser Instanz.</span><span class="sxs-lookup"><span data-stu-id="8c524-116">If not set, it is assumed that this object is not localized, and all qualifiers are storedwith this instance.</span></span> |
| `WBEM_FLAG_CREATE_OR_UPDATE` | <span data-ttu-id="8c524-117">0</span><span class="sxs-lookup"><span data-stu-id="8c524-117">0</span></span> | <span data-ttu-id="8c524-118">Erstellen Sie die Klasse aus, wenn er nicht vorhanden ist, oder überschrieben, falls sie bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8c524-118">Create the class if it does not exist, or overwrite it if it exists already.</span></span> |
| `WBEM_FLAG_UPDATE_ONLY` | <span data-ttu-id="8c524-119">1</span><span class="sxs-lookup"><span data-stu-id="8c524-119">1</span></span> | <span data-ttu-id="8c524-120">Aktualisieren Sie die Klasse.</span><span class="sxs-lookup"><span data-stu-id="8c524-120">Update the class.</span></span> <span data-ttu-id="8c524-121">Der Aufruf erfolgreich ausgeführt werden muss die Klasse vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="8c524-121">The class must exist for the call to be successful.</span></span> |
| `WBEM_FLAG_CREATE_ONLY` | <span data-ttu-id="8c524-122">2</span><span class="sxs-lookup"><span data-stu-id="8c524-122">2</span></span> | <span data-ttu-id="8c524-123">Erstellen Sie die Klasse.</span><span class="sxs-lookup"><span data-stu-id="8c524-123">Create the class.</span></span> <span data-ttu-id="8c524-124">Der Aufruf schlägt fehl, wenn die Klasse bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8c524-124">The call fails if the class already exists.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="8c524-125">0x10</span><span class="sxs-lookup"><span data-stu-id="8c524-125">0x10</span></span> | <span data-ttu-id="8c524-126">Das Flag wird halbsynchron aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8c524-126">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_OWNER_UPDATE` | <span data-ttu-id="8c524-127">0 x 10000</span><span class="sxs-lookup"><span data-stu-id="8c524-127">0x10000</span></span> | <span data-ttu-id="8c524-128">Push-Anbieter müssen dieses Flag angeben, beim Aufrufen von `PutClassWmi` , um anzugeben, dass diese Klasse geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="8c524-128">Push providers must specify this flag when calling `PutClassWmi` to indicate that this class has changed.</span></span> |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | <span data-ttu-id="8c524-129">0</span><span class="sxs-lookup"><span data-stu-id="8c524-129">0</span></span> | <span data-ttu-id="8c524-130">Ermöglicht eine Klasse, die aktualisiert werden, wenn keine abgeleiteten Klassen und keine Instanzen dieser Klasse vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="8c524-130">Allows a class to be updated if there are no derived classes and no instances of that class.</span></span> <span data-ttu-id="8c524-131">Darüber hinaus können Updates in allen Fällen ist die Änderung nur auf unwichtig Qualifizierer, z. B. das Description-Qualifizierers.</span><span class="sxs-lookup"><span data-stu-id="8c524-131">It also allows updates in all cases if the change is just to unimportant qualifiers, such as the Description qualifier.</span></span> <span data-ttu-id="8c524-132">Wenn die Klasse verfügt über Instanzen oder Änderungen wichtig, Qualifizierer sind, schlägt die Aktualisierung fehl.</span><span class="sxs-lookup"><span data-stu-id="8c524-132">If the class has instances or changes are to important qualifiers, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | <span data-ttu-id="8c524-133">0x20</span><span class="sxs-lookup"><span data-stu-id="8c524-133">0x20</span></span> | <span data-ttu-id="8c524-134">Können Updates von Klassen aus, auch wenn die untergeordnete Klassen vorhanden sind, solange die Änderung keine Konflikte mit den untergeordneten Klassen verursacht.</span><span class="sxs-lookup"><span data-stu-id="8c524-134">Allows updates of classes even if there are child classes as long as the change does not cause any conflicts with child classes.</span></span> <span data-ttu-id="8c524-135">Dieses Flag ermöglicht beispielsweise eine neue Eigenschaft mit der Basisklasse hinzugefügt werden, die in allen untergeordneten Klassen nicht zuvor erwähnt wurde.</span><span class="sxs-lookup"><span data-stu-id="8c524-135">For example, this flag allows a new property to be added to the base class that was not previously mentioned in any of the child classes.</span></span> <span data-ttu-id="8c524-136">Wenn die Klasse Instanzen verfügt, schlägt die Aktualisierung fehl.</span><span class="sxs-lookup"><span data-stu-id="8c524-136">If the class has instances, the update fails.</span></span> |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | <span data-ttu-id="8c524-137">0 x 40</span><span class="sxs-lookup"><span data-stu-id="8c524-137">0x40</span></span> | <span data-ttu-id="8c524-138">Erzwingt die Aktualisierung von Klassen, wenn konfliktverursachende untergeordnete Klassen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="8c524-138">forces updates of classes when conflicting child classes exist.</span></span> <span data-ttu-id="8c524-139">Dieses Flag erzwingt z. B. ein Update aus, wenn ein Klasse-Qualifizierer in einer untergeordneten Klasse definiert ist und die Basisklasse der Klasse versucht, den gleichen Qualifizierer hinzufügen, die mit des maßgeblichen eine vorhandenen in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="8c524-139">For example, this flag forces an update if a class qualifier is defined in a child class, and the base class tries to add the same qualifier which conflicts with thte existing one.</span></span> <span data-ttu-id="8c524-140">Im Modus "Force" Tis-Konflikt lässt sich durch das Löschen des in Konflikt stehende Qualifizierers in der untergeordneten Klasse.</span><span class="sxs-lookup"><span data-stu-id="8c524-140">In force mode, tis conflict is resolved by deleting the conflicting qualifier in the child class.</span></span> |

`pCtx`  
<span data-ttu-id="8c524-141">[in] Dieser Wert in der Regel ist `null`.</span><span class="sxs-lookup"><span data-stu-id="8c524-141">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="8c524-142">Andernfalls wird ein Zeiger auf ein [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, die die angeforderten Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8c524-142">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppCallResult`  
<span data-ttu-id="8c524-143">[out] Wenn `null`, dieser Parameter wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c524-143">[out] If `null`, this parameter is unused.</span></span> <span data-ttu-id="8c524-144">Wenn `lFlags` enthält `WBEM_FLAG_RETURN_IMMEDIATELY`, die Funktion gibt sofort zurück `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="8c524-144">If `lFlags` contains `WBEM_FLAG_RETURN_IMMEDIATELY`, the function returns immediately with `WBEM_S_NO_ERROR`.</span></span> <span data-ttu-id="8c524-145">Die `ppCallResult` Parameter erhält einen Zeiger auf ein neues [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) Objekt.</span><span class="sxs-lookup"><span data-stu-id="8c524-145">The `ppCallResult` parameter receives a pointer to a new [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) object.</span></span>

## <a name="return-value"></a><span data-ttu-id="8c524-146">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8c524-146">Return value</span></span>

<span data-ttu-id="8c524-147">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="8c524-147">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8c524-148">Konstante</span><span class="sxs-lookup"><span data-stu-id="8c524-148">Constant</span></span>  |<span data-ttu-id="8c524-149">Wert</span><span class="sxs-lookup"><span data-stu-id="8c524-149">Value</span></span>  |<span data-ttu-id="8c524-150">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c524-150">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="8c524-151">0 x 80041003</span><span class="sxs-lookup"><span data-stu-id="8c524-151">0x80041003</span></span> | <span data-ttu-id="8c524-152">Der Benutzer besitzt keine Berechtigung zum Erstellen oder Ändern von Klassen.</span><span class="sxs-lookup"><span data-stu-id="8c524-152">The user does not have permission to create or modify classes.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="8c524-153">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="8c524-153">0x80041001</span></span> | <span data-ttu-id="8c524-154">Ein Unbekannter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8c524-154">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="8c524-155">0 x 80041010</span><span class="sxs-lookup"><span data-stu-id="8c524-155">0x80041010</span></span> | <span data-ttu-id="8c524-156">Die angegebene Klasse ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="8c524-156">The specified class is not valid.</span></span> <span data-ttu-id="8c524-157">In der Regel gibt dies an, dass `pObject` ein Instanzobjekt angibt.</span><span class="sxs-lookup"><span data-stu-id="8c524-157">Typically, this indicates that `pObject` specifies an instance object.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8c524-158">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="8c524-158">0x80041008</span></span> | <span data-ttu-id="8c524-159">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="8c524-159">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID OPERATION` | <span data-ttu-id="8c524-160">0x80041016</span><span class="sxs-lookup"><span data-stu-id="8c524-160">0x80041016</span></span> | <span data-ttu-id="8c524-161">Der Name für die angegebene Klasse ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="8c524-161">The specified class name is not valid.</span></span> |
| `WBEM_E_CLASS_HAS_CHILDREN` | <span data-ttu-id="8c524-162">0x80041025</span><span class="sxs-lookup"><span data-stu-id="8c524-162">0x80041025</span></span> | <span data-ttu-id="8c524-163">Es wurde versucht, eine Änderung vornehmen, die eine Unterklasse ungültig machen würde.</span><span class="sxs-lookup"><span data-stu-id="8c524-163">An attempt was made to make a change that would invalidate a subclass.</span></span> |
| `WBEM_E_ALREADY_EXISTS` | <span data-ttu-id="8c524-164">0x80041019</span><span class="sxs-lookup"><span data-stu-id="8c524-164">0x80041019</span></span> | <span data-ttu-id="8c524-165">Die `WBEM_FLAG_CREATE_ONLY` -Flag angegeben wurde, aber die Klasse bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8c524-165">The `WBEM_FLAG_CREATE_ONLY` flag was specified, but the class already exists.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="8c524-166">0x80041002</span><span class="sxs-lookup"><span data-stu-id="8c524-166">0x80041002</span></span> | <span data-ttu-id="8c524-167">`WBEM_FLAG_UPDATE_ONLY` in wurde angegeben `lFlags`, und die Klasse wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="8c524-167">`WBEM_FLAG_UPDATE_ONLY` was specified in `lFlags`, and the class was not found.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="8c524-168">0x80041020</span><span class="sxs-lookup"><span data-stu-id="8c524-168">0x80041020</span></span> | <span data-ttu-id="8c524-169">Die erforderlichen Eigenschaften für Klassen wurden nicht alle festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8c524-169">The required properties for classes have not all been set.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="8c524-170">0x80041006</span><span class="sxs-lookup"><span data-stu-id="8c524-170">0x80041006</span></span> | <span data-ttu-id="8c524-171">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="8c524-171">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="8c524-172">0x80041033</span><span class="sxs-lookup"><span data-stu-id="8c524-172">0x80041033</span></span> | <span data-ttu-id="8c524-173">WMI wurde wahrscheinlich beendet und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="8c524-173">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="8c524-174">Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus.</span><span class="sxs-lookup"><span data-stu-id="8c524-174">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="8c524-175">0x80041015</span><span class="sxs-lookup"><span data-stu-id="8c524-175">0x80041015</span></span> | <span data-ttu-id="8c524-176">Der Remoteprozeduraufruf-Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-hat Fehler.</span><span class="sxs-lookup"><span data-stu-id="8c524-176">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="8c524-177">0</span><span class="sxs-lookup"><span data-stu-id="8c524-177">0</span></span> | <span data-ttu-id="8c524-178">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="8c524-178">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8c524-179">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8c524-179">Remarks</span></span>

<span data-ttu-id="8c524-180">Diese Funktion umschließt einen Aufruf der [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) Methode.</span><span class="sxs-lookup"><span data-stu-id="8c524-180">This function wraps a call to the [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) method.</span></span>

<span data-ttu-id="8c524-181">Der Benutzer darf keine Klassen mit Namen erstellen, die mit einem Unterstrich Chacater beginnen oder enden</span><span class="sxs-lookup"><span data-stu-id="8c524-181">The user may not create classes with names that begin or end with an underscore chacater</span></span>

<span data-ttu-id="8c524-182">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch den Aufruf der [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="8c524-182">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="8c524-183">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8c524-183">Requirements</span></span>  
 <span data-ttu-id="8c524-184">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c524-184">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c524-185">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8c524-185">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8c524-186">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8c524-186">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c524-187">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c524-187">See also</span></span>  
[<span data-ttu-id="8c524-188">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="8c524-188">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
