---
title: ExecQueryWmi-Funktion (Referenz zur nicht verwalteten API)
description: "Die ExecQueryWmi-Funktion führt eine Abfrage zum Abrufen von Objekten."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- ExecQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecQueryWmi
helpviewer_keywords:
- ExecQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 872109cb0472a8404c492c2867429fe783f898eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="execquerywmi-function"></a><span data-ttu-id="ac239-103">ExecQueryWmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="ac239-103">ExecQueryWmi function</span></span>
<span data-ttu-id="ac239-104">Führt eine Abfrage zum Abrufen von Objekten.</span><span class="sxs-lookup"><span data-stu-id="ac239-104">Executes a query to retrieve objects.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ac239-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac239-105">Syntax</span></span>  
  
```  
HRESULT ExecQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
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

## <a name="parameters"></a><span data-ttu-id="ac239-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ac239-106">Parameters</span></span>

`strQueryLanguage`    
<span data-ttu-id="ac239-107">[in] Eine Zeichenfolge mit der gültigen Abfragesprache, die von der Windows-Verwaltung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac239-107">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="ac239-108">Es muss "WQL", das Akronym für WMI-Abfragesprache.</span><span class="sxs-lookup"><span data-stu-id="ac239-108">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`  
<span data-ttu-id="ac239-109">[in] Der Text der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="ac239-109">[in] The text of the query.</span></span> <span data-ttu-id="ac239-110">Dieser Parameter darf nicht sein `null`.</span><span class="sxs-lookup"><span data-stu-id="ac239-110">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="ac239-111">[in] Eine Kombination von Flags, die das Verhalten dieser Funktion beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="ac239-111">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="ac239-112">Die folgenden Werte werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="ac239-112">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span> 

| <span data-ttu-id="ac239-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="ac239-113">Constant</span></span> | <span data-ttu-id="ac239-114">Wert</span><span class="sxs-lookup"><span data-stu-id="ac239-114">Value</span></span>  | <span data-ttu-id="ac239-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac239-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="ac239-116">0 x 20000</span><span class="sxs-lookup"><span data-stu-id="ac239-116">0x20000</span></span> | <span data-ttu-id="ac239-117">Wenn festgelegt ist, die Funktion ruft die Qualifizierern in den lokalisierten Namespace des Gebietsschemas für die aktuelle Verbindung gespeichert ab.</span><span class="sxs-lookup"><span data-stu-id="ac239-117">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="ac239-118">Wenn dies nicht festgelegt ist, die Funktion ruft nur die Qualifizierer, die in den unmittelbaren Namespace gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ac239-118">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="ac239-119">0 x 10</span><span class="sxs-lookup"><span data-stu-id="ac239-119">0x10</span></span> | <span data-ttu-id="ac239-120">Das Flag wird halbsynchrone aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ac239-120">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="ac239-121">0 x 20</span><span class="sxs-lookup"><span data-stu-id="ac239-121">0x20</span></span> | <span data-ttu-id="ac239-122">Die Funktion gibt einen Enumerator Vorwärtscursor.</span><span class="sxs-lookup"><span data-stu-id="ac239-122">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="ac239-123">In der Regel nur vorwärts Enumeratoren werden schneller ausgeführt und belegen weniger Speicher als konventionelle Enumeratoren, aber es nicht möglich, dass Aufrufe [Klon](clone.md).</span><span class="sxs-lookup"><span data-stu-id="ac239-123">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="ac239-124">0</span><span class="sxs-lookup"><span data-stu-id="ac239-124">0</span></span> | <span data-ttu-id="ac239-125">WMI behält Zeiger auf Objekte in der Enumration, bis sie veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="ac239-125">WMI retains pointers to objects in the enumration until they are released.</span></span> | 
| `WBEM_FLAG_ENSURE_LOCATABLE` | <span data-ttu-id="ac239-126">0 x 100</span><span class="sxs-lookup"><span data-stu-id="ac239-126">0x100</span></span> | <span data-ttu-id="ac239-127">Stellt sicher, dass alle zurückgegebenen Objekte haben genügend Informationen enthalten, Systemeigenschaften wie z. B. **__PATH**, **__RELPATH**, und **__SERVER**, sind nicht `null`.</span><span class="sxs-lookup"><span data-stu-id="ac239-127">Ensures that any returned objects have enough information in them so that system properties, such as **__PATH**, **__RELPATH**, and **__SERVER**, are not `null`.</span></span> |
| `WBEM_FLAG_PROTOTYPE` | <span data-ttu-id="ac239-128">2</span><span class="sxs-lookup"><span data-stu-id="ac239-128">2</span></span> | <span data-ttu-id="ac239-129">Dieses Flag wird für die Erstellung von Prototypen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac239-129">This flag is used for prototyping.</span></span> <span data-ttu-id="ac239-130">Die Abfrage wird nicht ausgeführt, und es wird stattdessen ein Objekt, das aussieht wie ein typisches Ergebnis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ac239-130">It does not execute the query and instead returns an object that looks like a typical result object.</span></span> |
| `WBEM_FLAG_DIRECT_READ` | <span data-ttu-id="ac239-131">0 x 200</span><span class="sxs-lookup"><span data-stu-id="ac239-131">0x200</span></span> | <span data-ttu-id="ac239-132">Ursachen direkten Zugriff auf den Anbieter für die Klasse, die unabhängig von der übergeordneten Klasse oder Unterklassen angegeben.</span><span class="sxs-lookup"><span data-stu-id="ac239-132">Causes direct access to the provider for the class specified without regard to its parent class or any subclasses.</span></span> |

<span data-ttu-id="ac239-133">Die empfohlene Flags sind `WBEM_FLAG_RETURN_IMMEDIATELY` und `WBEM_FLAG_FORWARD_ONLY` für optimale Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="ac239-133">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`  
<span data-ttu-id="ac239-134">[in] In der Regel wird dieser Wert ist `null`.</span><span class="sxs-lookup"><span data-stu-id="ac239-134">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="ac239-135">Andernfalls ist ein Zeiger auf ein ["IWbemContext"](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) -Instanz, die vom Anbieter verwendet werden kann, das die angeforderte Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ac239-135">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested classes.</span></span> 

`ppEnum`  
<span data-ttu-id="ac239-136">[out] Wenn kein Fehler auftritt, empfängt den Zeiger auf den Enumerator, der den Aufrufer beim Abrufen von den Instanzen im Resultset der Abfrage ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="ac239-136">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="ac239-137">Die Abfrage kann ein Resultset mit 0 (null) Instanzen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ac239-137">The query can have a result set with zero instances.</span></span> <span data-ttu-id="ac239-138">Finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="ac239-138">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`  
<span data-ttu-id="ac239-139">[in] Die Autorisierungsebene.</span><span class="sxs-lookup"><span data-stu-id="ac239-139">[in] The authorization level.</span></span>

<span data-ttu-id="ac239-140">`impLevel`[in] Die Ebene des Identitätswechsels.</span><span class="sxs-lookup"><span data-stu-id="ac239-140">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="ac239-141">[in] Ein Zeiger auf ein [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) -Objekt, das den aktuellen Namespace darstellt.</span><span class="sxs-lookup"><span data-stu-id="ac239-141">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="ac239-142">[in] Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="ac239-142">[in] The user name.</span></span> <span data-ttu-id="ac239-143">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="ac239-143">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="ac239-144">[in] Das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="ac239-144">[in] The password.</span></span> <span data-ttu-id="ac239-145">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="ac239-145">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="ac239-146">[in] Der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ac239-146">[in] The domain name of the user.</span></span> <span data-ttu-id="ac239-147">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="ac239-147">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="ac239-148">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ac239-148">Return value</span></span>

<span data-ttu-id="ac239-149">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="ac239-149">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ac239-150">Konstante</span><span class="sxs-lookup"><span data-stu-id="ac239-150">Constant</span></span>  |<span data-ttu-id="ac239-151">Wert</span><span class="sxs-lookup"><span data-stu-id="ac239-151">Value</span></span>  |<span data-ttu-id="ac239-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac239-152">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="ac239-153">0 x 80041003</span><span class="sxs-lookup"><span data-stu-id="ac239-153">0x80041003</span></span> | <span data-ttu-id="ac239-154">Der Benutzer keine Berechtigung zum Anzeigen, eine oder mehrere Klassen, die die Funktion zurückgeben kann.</span><span class="sxs-lookup"><span data-stu-id="ac239-154">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="ac239-155">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="ac239-155">0x80041001</span></span> | <span data-ttu-id="ac239-156">Nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ac239-156">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ac239-157">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="ac239-157">0x80041008</span></span> | <span data-ttu-id="ac239-158">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="ac239-158">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="ac239-159">0x80041017</span><span class="sxs-lookup"><span data-stu-id="ac239-159">0x80041017</span></span> | <span data-ttu-id="ac239-160">Die Abfrage hat einen Syntaxfehler.</span><span class="sxs-lookup"><span data-stu-id="ac239-160">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="ac239-161">0x80041018</span><span class="sxs-lookup"><span data-stu-id="ac239-161">0x80041018</span></span> | <span data-ttu-id="ac239-162">Die angeforderte Abfragesprache wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac239-162">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="ac239-163">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="ac239-163">0x8004106c</span></span> | <span data-ttu-id="ac239-164">Die Abfrage ist zu komplex.</span><span class="sxs-lookup"><span data-stu-id="ac239-164">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ac239-165">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ac239-165">0x80041006</span></span> | <span data-ttu-id="ac239-166">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ac239-166">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="ac239-167">0x80041033</span><span class="sxs-lookup"><span data-stu-id="ac239-167">0x80041033</span></span> | <span data-ttu-id="ac239-168">WMI wurde wahrscheinlich beendet und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="ac239-168">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="ac239-169">Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus.</span><span class="sxs-lookup"><span data-stu-id="ac239-169">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="ac239-170">0x80041015</span><span class="sxs-lookup"><span data-stu-id="ac239-170">0x80041015</span></span> | <span data-ttu-id="ac239-171">Der Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-ausgefallen ist.</span><span class="sxs-lookup"><span data-stu-id="ac239-171">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="ac239-172">0x80041002</span><span class="sxs-lookup"><span data-stu-id="ac239-172">0x80041002</span></span> | <span data-ttu-id="ac239-173">Die Abfrage gibt eine Klasse, die nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ac239-173">The query specifies a class that does not exist.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ac239-174">0</span><span class="sxs-lookup"><span data-stu-id="ac239-174">0</span></span> | <span data-ttu-id="ac239-175">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="ac239-175">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ac239-176">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac239-176">Remarks</span></span>

<span data-ttu-id="ac239-177">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemServices::ExecQuery](https://msdn.microsoft.com/library/aa392107(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="ac239-177">This function wraps a call to the [IWbemServices::ExecQuery](https://msdn.microsoft.com/library/aa392107(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="ac239-178">Diese Funktion verarbeitet die Abfrage der `strQuery` Parameter und erstellt einen Enumerator über die der Aufrufer die Ergebnisse der Abfrage zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="ac239-178">This function processes the query specified in the `strQuery` parameter and creates an enumerator through which the caller can access the query results.</span></span> <span data-ttu-id="ac239-179">Der Enumerator ist ein Zeiger auf ein [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) Schnittstelle; die Abfrage Ergebnisse sind Instanzen von Klassenobjekten bis zur Verfügung gestellt der [IWbemClassObject](https://msdn.microsoft.com/library/aa391433(v=vs.85).aspx) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ac239-179">The enumerator is a pointer to an [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) interface; the query results are instances of class objects made available through the [IWbemClassObject](https://msdn.microsoft.com/library/aa391433(v=vs.85).aspx) interface.</span></span>

<span data-ttu-id="ac239-180">Begrenzt die Anzahl der `AND` und `OR` Schlüsselwörter, die in der WQL-Abfragen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ac239-180">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="ac239-181">Große Anzahl von WQL Schlüsselwörter in eine komplexe Abfrage kann dazu führen, dass WMI zurückzugebenden der `WBEM_E_QUOTA_VIOLATION` (oder 0x8004106c) Fehlercode als ein `HRESULT` Wert.</span><span class="sxs-lookup"><span data-stu-id="ac239-181">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="ac239-182">Das Limit von WQL-Schlüsselwörter, hängt davon ab, wie komplex die Abfrage ist.</span><span class="sxs-lookup"><span data-stu-id="ac239-182">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="ac239-183">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch Aufrufen der [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="ac239-183">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="ac239-184">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ac239-184">Requirements</span></span>  
 <span data-ttu-id="ac239-185">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac239-185">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac239-186">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ac239-186">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ac239-187">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ac239-187">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac239-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac239-188">See also</span></span>  
[<span data-ttu-id="ac239-189">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="ac239-189">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
