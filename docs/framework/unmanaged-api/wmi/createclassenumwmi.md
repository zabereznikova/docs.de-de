---
title: CreateClassEnumWmi-Funktion (Referenz zur nicht verwalteten API)
description: "Die CreateClassEnumWmi-Funktion gibt einen Enumerator für alle Klassen, die bestimmte Kriterien erfüllen."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CreateClassEnumWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CreateClassEnumWmi
helpviewer_keywords: CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2058bad61af79244d211afb6a7661ca1642db070
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="createclassenumwmi-function"></a><span data-ttu-id="898d9-103">CreateClassEnumWmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="898d9-103">CreateClassEnumWmi function</span></span>
<span data-ttu-id="898d9-104">Gibt einen Enumerator für alle Klassen, die die angegebenen Auswahlkriterien entsprechen.</span><span class="sxs-lookup"><span data-stu-id="898d9-104">Returns an enumerator for all classes that satisfy the specified selection criteria.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="898d9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="898d9-105">Syntax</span></span>  
  
```  
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
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

## <a name="parameters"></a><span data-ttu-id="898d9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="898d9-106">Parameters</span></span>

`strSuperclass`    
<span data-ttu-id="898d9-107">[in] Wenn dies nicht der `null` oder leer ist, gibt den Namen einer übergeordneten Klasse; der Enumerator gibt nur Unterklassen dieser Klasse zurück.</span><span class="sxs-lookup"><span data-stu-id="898d9-107">[in] If not `null` or blank, specifies the name of a parent class; the enumerator returns only subclasses of this class.</span></span> <span data-ttu-id="898d9-108">Ist er `null` oder leer und `lFlags` WBEM_FLAG_SHALLOW ist, wird nur auf oberster Ebene Klassen (mit keinen übergeordneten Klasse).</span><span class="sxs-lookup"><span data-stu-id="898d9-108">If it is `null` or blank and `lFlags` is WBEM_FLAG_SHALLOW, returns only top-level classes (classes with no parent class).</span></span> <span data-ttu-id="898d9-109">Ist er `null` oder leer und `lFlags` ist `WBEM_FLAG_DEEP`, alle Klassen im Namespace zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="898d9-109">If it is `null` or blank and `lFlags` is `WBEM_FLAG_DEEP`, returns all classes in the namespace.</span></span>

`lFlags`   
<span data-ttu-id="898d9-110">[in] Eine Kombination von Flags, die das Verhalten dieser Funktion beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="898d9-110">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="898d9-111">Die folgenden Werte werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="898d9-111">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

|<span data-ttu-id="898d9-112">Konstante</span><span class="sxs-lookup"><span data-stu-id="898d9-112">Constant</span></span>  |<span data-ttu-id="898d9-113">Wert</span><span class="sxs-lookup"><span data-stu-id="898d9-113">Value</span></span>  |<span data-ttu-id="898d9-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="898d9-114">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="898d9-115">0 x 20000</span><span class="sxs-lookup"><span data-stu-id="898d9-115">0x20000</span></span> | <span data-ttu-id="898d9-116">Wenn festgelegt ist, die Funktion ruft die Qualifizierern in den lokalisierten Namespace des Gebietsschemas für die aktuelle Verbindung gespeichert ab.</span><span class="sxs-lookup"><span data-stu-id="898d9-116">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="898d9-117">Wenn dies nicht festgelegt ist, die Funktion ruft nur die Qualifizierer, die in den unmittelbaren Namespace gespeichert.</span><span class="sxs-lookup"><span data-stu-id="898d9-117">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="898d9-118">0</span><span class="sxs-lookup"><span data-stu-id="898d9-118">0</span></span> | <span data-ttu-id="898d9-119">Die Enumeration enthält alle Unterklassen in der Hierarchie, aber nicht für diese Klasse.</span><span class="sxs-lookup"><span data-stu-id="898d9-119">The enumeration includes all subclasses in the hierarchy, but not this class.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="898d9-120">1</span><span class="sxs-lookup"><span data-stu-id="898d9-120">1</span></span> | <span data-ttu-id="898d9-121">Die Enumeration schließt nur reine Instanzen dieser Klasse und schließt alle Instanzen von Unterklassen, die Eigenschaften, die nicht in dieser Klasse angeben.</span><span class="sxs-lookup"><span data-stu-id="898d9-121">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="898d9-122">0 x 10</span><span class="sxs-lookup"><span data-stu-id="898d9-122">0x10</span></span> | <span data-ttu-id="898d9-123">Das Flag wird halbsynchrone aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="898d9-123">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="898d9-124">0 x 20</span><span class="sxs-lookup"><span data-stu-id="898d9-124">0x20</span></span> | <span data-ttu-id="898d9-125">Die Funktion gibt einen Enumerator Vorwärtscursor.</span><span class="sxs-lookup"><span data-stu-id="898d9-125">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="898d9-126">In der Regel nur vorwärts Enumeratoren werden schneller ausgeführt und belegen weniger Speicher als konventionelle Enumeratoren, aber es nicht möglich, dass Aufrufe [Klon](clone.md).</span><span class="sxs-lookup"><span data-stu-id="898d9-126">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="898d9-127">0</span><span class="sxs-lookup"><span data-stu-id="898d9-127">0</span></span> | <span data-ttu-id="898d9-128">WMI behält Zeiger auf Objekte in der Enumration, bis sie veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="898d9-128">WMI retains pointers to objects in the enumration until they are released.</span></span> | 

<span data-ttu-id="898d9-129">Die empfohlene Flags sind `WBEM_FLAG_RETURN_IMMEDIATELY` und `WBEM_FLAG_FORWARD_ONLY` für optimale Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="898d9-129">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="898d9-130">[in] In der Regel wird dieser Wert ist `null`.</span><span class="sxs-lookup"><span data-stu-id="898d9-130">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="898d9-131">Andernfalls ist ein Zeiger auf ein ["IWbemContext"](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) -Instanz, die vom Anbieter verwendet werden kann, das die angeforderte Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="898d9-131">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppEnum`  
<span data-ttu-id="898d9-132">[out] Erhält der Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="898d9-132">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`  
<span data-ttu-id="898d9-133">[in] Die Autorisierungsebene.</span><span class="sxs-lookup"><span data-stu-id="898d9-133">[in] The authorization level.</span></span>

<span data-ttu-id="898d9-134">`impLevel`[in] Die Ebene des Identitätswechsels.</span><span class="sxs-lookup"><span data-stu-id="898d9-134">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="898d9-135">[in] Ein Zeiger auf ein [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) -Objekt, das den aktuellen Namespace darstellt.</span><span class="sxs-lookup"><span data-stu-id="898d9-135">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="898d9-136">[in] Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="898d9-136">[in] The user name.</span></span> <span data-ttu-id="898d9-137">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="898d9-137">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="898d9-138">[in] Das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="898d9-138">[in] The password.</span></span> <span data-ttu-id="898d9-139">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="898d9-139">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="898d9-140">[in] Der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="898d9-140">[in] The domain name of the user.</span></span> <span data-ttu-id="898d9-141">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="898d9-141">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="898d9-142">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="898d9-142">Return value</span></span>

<span data-ttu-id="898d9-143">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="898d9-143">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="898d9-144">Konstante</span><span class="sxs-lookup"><span data-stu-id="898d9-144">Constant</span></span>  |<span data-ttu-id="898d9-145">Wert</span><span class="sxs-lookup"><span data-stu-id="898d9-145">Value</span></span>  |<span data-ttu-id="898d9-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="898d9-146">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="898d9-147">0 x 80041003</span><span class="sxs-lookup"><span data-stu-id="898d9-147">0x80041003</span></span> | <span data-ttu-id="898d9-148">Der Benutzer keine Berechtigung zum Anzeigen, eine oder mehrere Klassen, die die Funktion zurückgeben kann.</span><span class="sxs-lookup"><span data-stu-id="898d9-148">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="898d9-149">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="898d9-149">0x80041001</span></span> | <span data-ttu-id="898d9-150">Nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="898d9-150">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="898d9-151">0 x 80041010</span><span class="sxs-lookup"><span data-stu-id="898d9-151">0x80041010</span></span> | <span data-ttu-id="898d9-152">`strSuperClass` existiert nicht.</span><span class="sxs-lookup"><span data-stu-id="898d9-152">`strSuperClass` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="898d9-153">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="898d9-153">0x80041008</span></span> | <span data-ttu-id="898d9-154">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="898d9-154">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="898d9-155">0x80041006</span><span class="sxs-lookup"><span data-stu-id="898d9-155">0x80041006</span></span> | <span data-ttu-id="898d9-156">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="898d9-156">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="898d9-157">0x80041033</span><span class="sxs-lookup"><span data-stu-id="898d9-157">0x80041033</span></span> | <span data-ttu-id="898d9-158">WMI wurde wahrscheinlich beendet und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="898d9-158">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="898d9-159">Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus.</span><span class="sxs-lookup"><span data-stu-id="898d9-159">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="898d9-160">0x80041015</span><span class="sxs-lookup"><span data-stu-id="898d9-160">0x80041015</span></span> | <span data-ttu-id="898d9-161">Der Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-ausgefallen ist.</span><span class="sxs-lookup"><span data-stu-id="898d9-161">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="898d9-162">0</span><span class="sxs-lookup"><span data-stu-id="898d9-162">0</span></span> | <span data-ttu-id="898d9-163">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="898d9-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="898d9-164">Hinweise</span><span class="sxs-lookup"><span data-stu-id="898d9-164">Remarks</span></span>

<span data-ttu-id="898d9-165">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392095(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="898d9-165">This function wraps a call to the [IWbemServices::CreateClassEnum](https://msdn.microsoft.com/library/aa392095(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="898d9-166">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch Aufrufen der [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="898d9-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="898d9-167">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="898d9-167">Requirements</span></span>  
 <span data-ttu-id="898d9-168">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="898d9-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="898d9-169">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="898d9-169">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="898d9-170">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="898d9-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="898d9-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="898d9-171">See also</span></span>  
[<span data-ttu-id="898d9-172">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="898d9-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
