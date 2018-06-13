---
title: CreateInstanceEnumWmi-Funktion (Referenz zur nicht verwalteten API)
description: Die CreateInstanceEnumWmi-Funktion gibt einen Enumerator mit Instanzen einer bestimmten Klasse, die Auswahlkriterien erfüllt.
ms.date: 11/06/2017
api_name:
- CreateInstanceEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstanceEnumWmi
helpviewer_keywords:
- CreateInstanceEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f9297d34b01c03075db67bd904a81e589bfcc10
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461375"
---
# <a name="createinstanceenumwmi-function"></a><span data-ttu-id="99c74-103">CreateInstanceEnumWmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="99c74-103">CreateInstanceEnumWmi function</span></span>
<span data-ttu-id="99c74-104">Gibt einen Enumerator, der die Instanzen einer bestimmten Klasse zurückgibt, die angegebenen Auswahlkriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="99c74-104">Returns an enumerator that returns the instances of a specified class that meet specified selection criteria.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="99c74-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="99c74-105">Syntax</span></span>  
  
```  
HRESULT CreateInstanceEnumWmi (
   [in] BSTR                    strFilter,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
); 
```  

## <a name="parameters"></a><span data-ttu-id="99c74-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="99c74-106">Parameters</span></span>

`strFilter`    
<span data-ttu-id="99c74-107">[in] Der Name der Klasse für die Instanzen gewünscht werden.</span><span class="sxs-lookup"><span data-stu-id="99c74-107">[in] The name of the class for which instances are desired.</span></span> <span data-ttu-id="99c74-108">Dieser Parameter darf nicht sein `null`.</span><span class="sxs-lookup"><span data-stu-id="99c74-108">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="99c74-109">[in] Eine Kombination von Flags, die das Verhalten dieser Funktion beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="99c74-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="99c74-110">Die folgenden Werte werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="99c74-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="99c74-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="99c74-111">Constant</span></span>  |<span data-ttu-id="99c74-112">Wert</span><span class="sxs-lookup"><span data-stu-id="99c74-112">Value</span></span>  |<span data-ttu-id="99c74-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99c74-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="99c74-114">0 x 20000</span><span class="sxs-lookup"><span data-stu-id="99c74-114">0x20000</span></span> | <span data-ttu-id="99c74-115">Wenn festgelegt ist, die Funktion ruft die Qualifizierern in den lokalisierten Namespace des Gebietsschemas für die aktuelle Verbindung gespeichert ab.</span><span class="sxs-lookup"><span data-stu-id="99c74-115">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="99c74-116">Wenn dies nicht festgelegt ist, die Funktion ruft nur die Qualifizierer, die in den unmittelbaren Namespace gespeichert.</span><span class="sxs-lookup"><span data-stu-id="99c74-116">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="99c74-117">0</span><span class="sxs-lookup"><span data-stu-id="99c74-117">0</span></span> | <span data-ttu-id="99c74-118">Die Enumeration enthält auch alle Unterklassen in der Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="99c74-118">The enumeration includes this and all subclasses in the hierarchy.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="99c74-119">1</span><span class="sxs-lookup"><span data-stu-id="99c74-119">1</span></span> | <span data-ttu-id="99c74-120">Die Enumeration schließt nur reine Instanzen dieser Klasse und schließt alle Instanzen von Unterklassen, die Eigenschaften, die nicht in dieser Klasse angeben.</span><span class="sxs-lookup"><span data-stu-id="99c74-120">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="99c74-121">0x10</span><span class="sxs-lookup"><span data-stu-id="99c74-121">0x10</span></span> | <span data-ttu-id="99c74-122">Das Flag wird halbsynchrone aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="99c74-122">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="99c74-123">0x20</span><span class="sxs-lookup"><span data-stu-id="99c74-123">0x20</span></span> | <span data-ttu-id="99c74-124">Die Funktion gibt einen Enumerator Vorwärtscursor.</span><span class="sxs-lookup"><span data-stu-id="99c74-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="99c74-125">In der Regel nur vorwärts Enumeratoren werden schneller ausgeführt und belegen weniger Speicher als konventionelle Enumeratoren, aber es nicht möglich, dass Aufrufe [Klon](clone.md).</span><span class="sxs-lookup"><span data-stu-id="99c74-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="99c74-126">0</span><span class="sxs-lookup"><span data-stu-id="99c74-126">0</span></span> | <span data-ttu-id="99c74-127">WMI behält Zeiger auf Objekte in der Enumration, bis sie veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="99c74-127">WMI retains pointers to objects in the enumration until they are released.</span></span> | 

<span data-ttu-id="99c74-128">Die empfohlene Flags sind `WBEM_FLAG_RETURN_IMMEDIATELY` und `WBEM_FLAG_FORWARD_ONLY` für optimale Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="99c74-128">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="99c74-129">[in] In der Regel wird dieser Wert ist `null`.</span><span class="sxs-lookup"><span data-stu-id="99c74-129">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="99c74-130">Andernfalls ist ein Zeiger auf ein ["IWbemContext"](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) -Instanz, die vom Anbieter verwendet werden kann, das die angeforderte Instanzen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="99c74-130">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that may be used by the provider that is providing the requested instances.</span></span>

`ppEnum`  
<span data-ttu-id="99c74-131">[out] Erhält der Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="99c74-131">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`  
<span data-ttu-id="99c74-132">[in] Die Autorisierungsebene.</span><span class="sxs-lookup"><span data-stu-id="99c74-132">[in] The authorization level.</span></span>

<span data-ttu-id="99c74-133">`impLevel` [in] Die Ebene des Identitätswechsels.</span><span class="sxs-lookup"><span data-stu-id="99c74-133">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="99c74-134">[in] Ein Zeiger auf ein [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) -Objekt, das den aktuellen Namespace darstellt.</span><span class="sxs-lookup"><span data-stu-id="99c74-134">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="99c74-135">[in] Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="99c74-135">[in] The user name.</span></span> <span data-ttu-id="99c74-136">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="99c74-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="99c74-137">[in] Das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="99c74-137">[in] The password.</span></span> <span data-ttu-id="99c74-138">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="99c74-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="99c74-139">[in] Der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="99c74-139">[in] The domain name of the user.</span></span> <span data-ttu-id="99c74-140">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="99c74-140">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="99c74-141">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="99c74-141">Return value</span></span>

<span data-ttu-id="99c74-142">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="99c74-142">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="99c74-143">Konstante</span><span class="sxs-lookup"><span data-stu-id="99c74-143">Constant</span></span>  |<span data-ttu-id="99c74-144">Wert</span><span class="sxs-lookup"><span data-stu-id="99c74-144">Value</span></span>  |<span data-ttu-id="99c74-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99c74-145">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="99c74-146">0 x 80041003</span><span class="sxs-lookup"><span data-stu-id="99c74-146">0x80041003</span></span> | <span data-ttu-id="99c74-147">Der Benutzer keine Berechtigung zum Anzeigen von Instanzen der angegebenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="99c74-147">The user does not have permission to view instances of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="99c74-148">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="99c74-148">0x80041001</span></span> | <span data-ttu-id="99c74-149">Nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="99c74-149">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="99c74-150">0 x 80041010</span><span class="sxs-lookup"><span data-stu-id="99c74-150">0x80041010</span></span> | <span data-ttu-id="99c74-151">`strFilter` existiert nicht.</span><span class="sxs-lookup"><span data-stu-id="99c74-151">`strFilter` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="99c74-152">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="99c74-152">0x80041008</span></span> | <span data-ttu-id="99c74-153">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="99c74-153">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="99c74-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="99c74-154">0x80041006</span></span> | <span data-ttu-id="99c74-155">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="99c74-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="99c74-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="99c74-156">0x80041033</span></span> | <span data-ttu-id="99c74-157">WMI wurde wahrscheinlich beendet und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="99c74-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="99c74-158">Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus.</span><span class="sxs-lookup"><span data-stu-id="99c74-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="99c74-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="99c74-159">0x80041015</span></span> | <span data-ttu-id="99c74-160">Der Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-ausgefallen ist.</span><span class="sxs-lookup"><span data-stu-id="99c74-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="99c74-161">0</span><span class="sxs-lookup"><span data-stu-id="99c74-161">0</span></span> | <span data-ttu-id="99c74-162">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="99c74-162">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="99c74-163">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99c74-163">Remarks</span></span>

<span data-ttu-id="99c74-164">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392097(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="99c74-164">This function wraps a call to the [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392097(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="99c74-165">Beachten Sie, dass der zurückgegebene Enumerator 0 (null) Elemente verfügen kann.</span><span class="sxs-lookup"><span data-stu-id="99c74-165">Note that the returned enumerator can have zero elements.</span></span>

<span data-ttu-id="99c74-166">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch Aufrufen der [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="99c74-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="99c74-167">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99c74-167">Requirements</span></span>  
 <span data-ttu-id="99c74-168">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99c74-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99c74-169">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="99c74-169">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="99c74-170">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="99c74-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c74-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99c74-171">See also</span></span>  
[<span data-ttu-id="99c74-172">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="99c74-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
