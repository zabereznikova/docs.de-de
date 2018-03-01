---
title: ExecNotificationQueryWmi-Funktion (Referenz zur nicht verwalteten API)
description: "Die ExecNotificationQueryWmi-Funktion führt eine Abfrage aus, um Ereignisse zu empfangen."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- ExecNotificationQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecNotificationQueryWmi
helpviewer_keywords:
- ExecNotificationQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d6dd0926d2262f8d0aa125b86755017a65a95a7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="42a34-103">ExecNotificationQueryWmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="42a34-103">ExecNotificationQueryWmi function</span></span>
<span data-ttu-id="42a34-104">Führt eine Abfrage aus, um Ereignisse zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="42a34-104">Executes a query to receive events.</span></span> <span data-ttu-id="42a34-105">Der Aufruf sofort zurückgegeben, und der Aufrufer den zurückgegebenen Enumerator für Ereignisse beim Eintreffen Abfragen kann.</span><span class="sxs-lookup"><span data-stu-id="42a34-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="42a34-106">Den zurückgegebenen Enumerator freigeben, wird die Abfrage abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="42a34-106">Releasing the returned enumerator cancels the query.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="42a34-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="42a34-107">Syntax</span></span>  
  
```  
HRESULT ExecNotificationQueryWmi (
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

## <a name="parameters"></a><span data-ttu-id="42a34-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="42a34-108">Parameters</span></span>

`strQueryLanguage`    
<span data-ttu-id="42a34-109">[in] Eine Zeichenfolge mit der gültigen Abfragesprache, die von der Windows-Verwaltung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="42a34-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="42a34-110">Es muss "WQL", das Akronym für WMI-Abfragesprache.</span><span class="sxs-lookup"><span data-stu-id="42a34-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`  
<span data-ttu-id="42a34-111">[in] Der Text der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="42a34-111">[in] The text of the query.</span></span> <span data-ttu-id="42a34-112">Dieser Parameter darf nicht sein `null`.</span><span class="sxs-lookup"><span data-stu-id="42a34-112">This parameter cannot be `null`.</span></span>

`lFlags`   
<span data-ttu-id="42a34-113">[in] Eine Kombination der folgenden zwei Flags, die das Verhalten dieser Funktion zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="42a34-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="42a34-114">Diese Werte werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="42a34-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> 

| <span data-ttu-id="42a34-115">Konstante</span><span class="sxs-lookup"><span data-stu-id="42a34-115">Constant</span></span> | <span data-ttu-id="42a34-116">Wert</span><span class="sxs-lookup"><span data-stu-id="42a34-116">Value</span></span>  | <span data-ttu-id="42a34-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42a34-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="42a34-118">0 x 10</span><span class="sxs-lookup"><span data-stu-id="42a34-118">0x10</span></span> | <span data-ttu-id="42a34-119">Das Flag wird halbsynchrone aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="42a34-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="42a34-120">Wenn dieses Flag nicht festgelegt ist, schlägt der Aufruf fehl.</span><span class="sxs-lookup"><span data-stu-id="42a34-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="42a34-121">Grund hierfür ist Ereignisse kontinuierlich, stammen, was bedeutet, dass der Benutzer den zurückgegebenen Enumerator abrufen muss.</span><span class="sxs-lookup"><span data-stu-id="42a34-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="42a34-122">Dieser Aufruf auf unbestimmte Zeit blockiert ist, die nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="42a34-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="42a34-123">0 x 20</span><span class="sxs-lookup"><span data-stu-id="42a34-123">0x20</span></span> | <span data-ttu-id="42a34-124">Die Funktion gibt einen Enumerator Vorwärtscursor.</span><span class="sxs-lookup"><span data-stu-id="42a34-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="42a34-125">In der Regel nur vorwärts Enumeratoren werden schneller ausgeführt und belegen weniger Speicher als konventionelle Enumeratoren, aber es nicht möglich, dass Aufrufe [Klon](clone.md).</span><span class="sxs-lookup"><span data-stu-id="42a34-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`  
<span data-ttu-id="42a34-126">[in] In der Regel wird dieser Wert ist `null`.</span><span class="sxs-lookup"><span data-stu-id="42a34-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="42a34-127">Andernfalls ist ein Zeiger auf ein ["IWbemContext"](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) -Instanz, die vom Anbieter verwendet werden kann, das die angeforderte Ereignisse bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="42a34-127">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) instance that can be used by the provider that is providing the requested events.</span></span> 

`ppEnum`  
<span data-ttu-id="42a34-128">[out] Wenn kein Fehler auftritt, empfängt den Zeiger auf den Enumerator, der den Aufrufer beim Abrufen von den Instanzen im Resultset der Abfrage ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="42a34-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="42a34-129">Finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="42a34-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`  
<span data-ttu-id="42a34-130">[in] Die Autorisierungsebene.</span><span class="sxs-lookup"><span data-stu-id="42a34-130">[in] The authorization level.</span></span>

<span data-ttu-id="42a34-131">`impLevel`[in] Die Ebene des Identitätswechsels.</span><span class="sxs-lookup"><span data-stu-id="42a34-131">`impLevel` [in] The impersonation level.</span></span>

`pCurrentNamespace`   
<span data-ttu-id="42a34-132">[in] Ein Zeiger auf ein [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) -Objekt, das den aktuellen Namespace darstellt.</span><span class="sxs-lookup"><span data-stu-id="42a34-132">[in] A pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object that represents the current namespace.</span></span>

`strUser`   
<span data-ttu-id="42a34-133">[in] Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="42a34-133">[in] The user name.</span></span> <span data-ttu-id="42a34-134">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="42a34-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="42a34-135">[in] Das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="42a34-135">[in] The password.</span></span> <span data-ttu-id="42a34-136">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="42a34-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="42a34-137">[in] Der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="42a34-137">[in] The domain name of the user.</span></span> <span data-ttu-id="42a34-138">Finden Sie unter der [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="42a34-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="42a34-139">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="42a34-139">Return value</span></span>

<span data-ttu-id="42a34-140">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="42a34-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="42a34-141">Konstante</span><span class="sxs-lookup"><span data-stu-id="42a34-141">Constant</span></span>  |<span data-ttu-id="42a34-142">Wert</span><span class="sxs-lookup"><span data-stu-id="42a34-142">Value</span></span>  |<span data-ttu-id="42a34-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42a34-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="42a34-144">0 x 80041003</span><span class="sxs-lookup"><span data-stu-id="42a34-144">0x80041003</span></span> | <span data-ttu-id="42a34-145">Der Benutzer keine Berechtigung zum Anzeigen, eine oder mehrere Klassen, die die Funktion zurückgeben kann.</span><span class="sxs-lookup"><span data-stu-id="42a34-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="42a34-146">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="42a34-146">0x80041001</span></span> | <span data-ttu-id="42a34-147">Nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="42a34-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="42a34-148">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="42a34-148">0x80041008</span></span> | <span data-ttu-id="42a34-149">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="42a34-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="42a34-150">0 x 80041010</span><span class="sxs-lookup"><span data-stu-id="42a34-150">0x80041010</span></span> | <span data-ttu-id="42a34-151">Die Abfrage gibt eine Klasse, die nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="42a34-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="42a34-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="42a34-152">0x80042002</span></span> | <span data-ttu-id="42a34-153">Zu viele mit einfacher Genauigkeit in die Übermittlung von Ereignissen wurde angefordert.</span><span class="sxs-lookup"><span data-stu-id="42a34-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="42a34-154">Eine größere Abruf Toleranz muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="42a34-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="42a34-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="42a34-155">0x80042001</span></span> | <span data-ttu-id="42a34-156">Die Abfrage Requess kann mehr Informationen als Windows-Verwaltung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="42a34-156">The query requess more information than Windows Management can provide.</span></span> <span data-ttu-id="42a34-157">Dies `HRESULT` wird zurückgegeben, wenn ein Ereignis in einer Anforderung zum Abrufen aller Objekte in einem Namespace Abfrageergebnisse.</span><span class="sxs-lookup"><span data-stu-id="42a34-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="42a34-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="42a34-158">0x80041017</span></span> | <span data-ttu-id="42a34-159">Die Abfrage hat einen Syntaxfehler.</span><span class="sxs-lookup"><span data-stu-id="42a34-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="42a34-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="42a34-160">0x80041018</span></span> | <span data-ttu-id="42a34-161">Die angeforderte Abfragesprache wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="42a34-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="42a34-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="42a34-162">0x8004106c</span></span> | <span data-ttu-id="42a34-163">Die Abfrage ist zu komplex.</span><span class="sxs-lookup"><span data-stu-id="42a34-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="42a34-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="42a34-164">0x80041006</span></span> | <span data-ttu-id="42a34-165">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="42a34-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="42a34-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="42a34-166">0x80041033</span></span> | <span data-ttu-id="42a34-167">WMI wurde wahrscheinlich beendet und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="42a34-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="42a34-168">Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus.</span><span class="sxs-lookup"><span data-stu-id="42a34-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="42a34-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="42a34-169">0x80041015</span></span> | <span data-ttu-id="42a34-170">Der Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-ausgefallen ist.</span><span class="sxs-lookup"><span data-stu-id="42a34-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="42a34-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="42a34-171">0x80041058</span></span> | <span data-ttu-id="42a34-172">Die Abfrage kann nicht analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="42a34-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="42a34-173">0</span><span class="sxs-lookup"><span data-stu-id="42a34-173">0</span></span> | <span data-ttu-id="42a34-174">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="42a34-174">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="42a34-175">Hinweise</span><span class="sxs-lookup"><span data-stu-id="42a34-175">Remarks</span></span>

<span data-ttu-id="42a34-176">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemServices::ExecNotificationQuery](https://msdn.microsoft.com/library/aa392105(v=vs.85).aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="42a34-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](https://msdn.microsoft.com/library/aa392105(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="42a34-177">Nachdem die Funktion zurückgibt, der Aufrufer in regelmäßigen Abständen übergibt das zurückgegebene `ppEnum` -Objekt an die [Weiter](next.md) Funktion, um festzustellen, ob alle Ereignisse verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="42a34-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="42a34-178">Begrenzt die Anzahl der `AND` und `OR` Schlüsselwörter, die in der WQL-Abfragen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="42a34-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="42a34-179">Große Anzahl von WQL Schlüsselwörter in eine komplexe Abfrage kann dazu führen, dass WMI zurückzugebenden der `WBEM_E_QUOTA_VIOLATION` (oder 0x8004106c) Fehlercode als ein `HRESULT` Wert.</span><span class="sxs-lookup"><span data-stu-id="42a34-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="42a34-180">Das Limit von WQL-Schlüsselwörter, hängt davon ab, wie komplex die Abfrage ist.</span><span class="sxs-lookup"><span data-stu-id="42a34-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="42a34-181">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch Aufrufen der [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="42a34-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="42a34-182">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="42a34-182">Requirements</span></span>  
 <span data-ttu-id="42a34-183">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42a34-183">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42a34-184">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="42a34-184">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="42a34-185">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="42a34-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a34-186">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42a34-186">See also</span></span>  
[<span data-ttu-id="42a34-187">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="42a34-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
