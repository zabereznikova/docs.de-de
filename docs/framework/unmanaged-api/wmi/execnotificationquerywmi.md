---
title: ExecNotificationQueryWmi-Funktion (Referenz zur nicht verwalteten API)
description: ExecNotificationQueryWmi-Funktion führt eine Abfrage, um Ereignisse zu empfangen.
ms.date: 11/06/2017
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
ms.openlocfilehash: 9cac00ff96d0c7007bdd6135282c3f767217385e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935615"
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="7eec1-103">ExecNotificationQueryWmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="7eec1-103">ExecNotificationQueryWmi function</span></span>

<span data-ttu-id="7eec1-104">Führt eine Abfrage zum Empfangen von Ereignissen aus.</span><span class="sxs-lookup"><span data-stu-id="7eec1-104">Executes a query to receive events.</span></span> <span data-ttu-id="7eec1-105">Der Aufruf sofort zurückgegeben, und der Aufrufer Abfragen kann des zurückgegebenen Enumerators für Ereignisse, deren eintreffen.</span><span class="sxs-lookup"><span data-stu-id="7eec1-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="7eec1-106">Den zurückgegebenen Enumerator freigegeben wird, bricht die Abfrage ab.</span><span class="sxs-lookup"><span data-stu-id="7eec1-106">Releasing the returned enumerator cancels the query.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="7eec1-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7eec1-107">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="7eec1-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="7eec1-108">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="7eec1-109">[in] Eine Zeichenfolge mit der gültigen Abfragesprache, die von der Windows-Verwaltung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7eec1-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="7eec1-110">Es muss "WQL", das Akronym für WMI-Abfragesprache.</span><span class="sxs-lookup"><span data-stu-id="7eec1-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="7eec1-111">[in] Der Text der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="7eec1-111">[in] The text of the query.</span></span> <span data-ttu-id="7eec1-112">Dieser Parameter darf nicht sein `null`.</span><span class="sxs-lookup"><span data-stu-id="7eec1-112">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="7eec1-113">[in] Eine Kombination der folgenden zwei Flags, die das Verhalten dieser Funktion zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="7eec1-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="7eec1-114">Diese Werte werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="7eec1-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

| <span data-ttu-id="7eec1-115">Konstante</span><span class="sxs-lookup"><span data-stu-id="7eec1-115">Constant</span></span> | <span data-ttu-id="7eec1-116">Wert</span><span class="sxs-lookup"><span data-stu-id="7eec1-116">Value</span></span>  | <span data-ttu-id="7eec1-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7eec1-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="7eec1-118">0x10</span><span class="sxs-lookup"><span data-stu-id="7eec1-118">0x10</span></span> | <span data-ttu-id="7eec1-119">Das Flag wird halbsynchron aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="7eec1-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="7eec1-120">Wenn dieses Flag nicht festgelegt ist, schlägt der Aufruf fehl.</span><span class="sxs-lookup"><span data-stu-id="7eec1-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="7eec1-121">Grund hierfür ist Ereignisse kontinuierlich stammen, was bedeutet, dass der Benutzer den zurückgegebenen Enumerator abrufen muss.</span><span class="sxs-lookup"><span data-stu-id="7eec1-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="7eec1-122">Dieser Aufruf auf unbestimmte Zeit blockiert wird, die unmöglich.</span><span class="sxs-lookup"><span data-stu-id="7eec1-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="7eec1-123">0x20</span><span class="sxs-lookup"><span data-stu-id="7eec1-123">0x20</span></span> | <span data-ttu-id="7eec1-124">Die Funktion gibt einen Enumerator vorwärts gerichtete.</span><span class="sxs-lookup"><span data-stu-id="7eec1-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="7eec1-125">In der Regel vorwärts-Enumeratoren sind schneller, und verwenden Sie weniger Arbeitsspeicher als konventionelle Enumeratoren, aber sie ermöglichen keine Aufrufe von [Klon](clone.md).</span><span class="sxs-lookup"><span data-stu-id="7eec1-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`\
<span data-ttu-id="7eec1-126">[in] Dieser Wert in der Regel ist `null`.</span><span class="sxs-lookup"><span data-stu-id="7eec1-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="7eec1-127">Andernfalls wird ein Zeiger auf ein [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, die die angeforderte Ereignisse bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7eec1-127">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested events.</span></span>

`ppEnum`\
<span data-ttu-id="7eec1-128">[out] Wenn kein Fehler auftritt, empfängt den Zeiger auf der Enumerator, der dem Aufrufer zum Abrufen von Instanzen im Resultset der Abfrage ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="7eec1-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="7eec1-129">Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="7eec1-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="7eec1-130">[in] Die Autorisierungsebene.</span><span class="sxs-lookup"><span data-stu-id="7eec1-130">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="7eec1-131">[in] Die Ebene des Identitätswechsels.</span><span class="sxs-lookup"><span data-stu-id="7eec1-131">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="7eec1-132">[in] Ein Zeiger auf ein [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) -Objekt, das den aktuellen Namespace darstellt.</span><span class="sxs-lookup"><span data-stu-id="7eec1-132">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="7eec1-133">[in] Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="7eec1-133">[in] The user name.</span></span> <span data-ttu-id="7eec1-134">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="7eec1-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="7eec1-135">[in] Das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="7eec1-135">[in] The password.</span></span> <span data-ttu-id="7eec1-136">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="7eec1-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="7eec1-137">[in] Der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="7eec1-137">[in] The domain name of the user.</span></span> <span data-ttu-id="7eec1-138">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="7eec1-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="7eec1-139">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7eec1-139">Return value</span></span>

<span data-ttu-id="7eec1-140">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="7eec1-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7eec1-141">Konstante</span><span class="sxs-lookup"><span data-stu-id="7eec1-141">Constant</span></span>  |<span data-ttu-id="7eec1-142">Wert</span><span class="sxs-lookup"><span data-stu-id="7eec1-142">Value</span></span>  |<span data-ttu-id="7eec1-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7eec1-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="7eec1-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="7eec1-144">0x80041003</span></span> | <span data-ttu-id="7eec1-145">Der Benutzer keine Berechtigung zum Anzeigen, eine oder mehrere Klassen, die die Funktion zurückgeben kann.</span><span class="sxs-lookup"><span data-stu-id="7eec1-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="7eec1-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="7eec1-146">0x80041001</span></span> | <span data-ttu-id="7eec1-147">Ein Unbekannter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7eec1-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7eec1-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7eec1-148">0x80041008</span></span> | <span data-ttu-id="7eec1-149">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="7eec1-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="7eec1-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="7eec1-150">0x80041010</span></span> | <span data-ttu-id="7eec1-151">Die Abfrage gibt eine Klasse, die nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7eec1-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="7eec1-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="7eec1-152">0x80042002</span></span> | <span data-ttu-id="7eec1-153">Zu viel Genauigkeit bei der Übermittlung von Ereignissen wurde angefordert.</span><span class="sxs-lookup"><span data-stu-id="7eec1-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="7eec1-154">Eine größere Abruf Toleranz muss angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7eec1-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="7eec1-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="7eec1-155">0x80042001</span></span> | <span data-ttu-id="7eec1-156">Die Abfrage fordert Informationen als Windows-Verwaltung bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="7eec1-156">The query requests more information than Windows Management can provide.</span></span> <span data-ttu-id="7eec1-157">Dies `HRESULT` wird zurückgegeben, wenn ein Event-in einer Anforderung zum Abrufen aller Objekte in einem Namespace Abfrageergebnisse.</span><span class="sxs-lookup"><span data-stu-id="7eec1-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="7eec1-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="7eec1-158">0x80041017</span></span> | <span data-ttu-id="7eec1-159">Die Abfrage musste ein Syntaxfehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7eec1-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="7eec1-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="7eec1-160">0x80041018</span></span> | <span data-ttu-id="7eec1-161">Die angeforderte Abfragesprache wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7eec1-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="7eec1-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="7eec1-162">0x8004106c</span></span> | <span data-ttu-id="7eec1-163">Die Abfrage ist zu komplex.</span><span class="sxs-lookup"><span data-stu-id="7eec1-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7eec1-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7eec1-164">0x80041006</span></span> | <span data-ttu-id="7eec1-165">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="7eec1-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="7eec1-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="7eec1-166">0x80041033</span></span> | <span data-ttu-id="7eec1-167">WMI wurde wahrscheinlich beendet und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="7eec1-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="7eec1-168">Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus.</span><span class="sxs-lookup"><span data-stu-id="7eec1-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="7eec1-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="7eec1-169">0x80041015</span></span> | <span data-ttu-id="7eec1-170">Der Remoteprozeduraufruf-Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-hat Fehler.</span><span class="sxs-lookup"><span data-stu-id="7eec1-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="7eec1-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="7eec1-171">0x80041058</span></span> | <span data-ttu-id="7eec1-172">Die Abfrage kann nicht analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="7eec1-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="7eec1-173">0</span><span class="sxs-lookup"><span data-stu-id="7eec1-173">0</span></span> | <span data-ttu-id="7eec1-174">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="7eec1-174">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="7eec1-175">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7eec1-175">Remarks</span></span>

<span data-ttu-id="7eec1-176">Diese Funktion umschließt einen Aufruf der [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) Methode.</span><span class="sxs-lookup"><span data-stu-id="7eec1-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) method.</span></span>

<span data-ttu-id="7eec1-177">Nachdem die Funktion zurückgibt, der Aufrufer in regelmäßigen Abständen übergibt das zurückgegebene `ppEnum` -Objekt an die [Weiter](next.md) Funktion, um festzustellen, ob alle Ereignisse zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="7eec1-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="7eec1-178">Bestehen Einschränkungen in Bezug auf die Anzahl der `AND` und `OR` Schlüsselwörter, die in WQL-Abfragen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="7eec1-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="7eec1-179">Große Anzahl von WQL-Schlüsselwörter, die verwendet werden, in eine komplexe Abfrage kann dazu führen, dass WMI Zurückgeben der `WBEM_E_QUOTA_VIOLATION` (oder 0x8004106c) Fehlercode als ein `HRESULT` Wert.</span><span class="sxs-lookup"><span data-stu-id="7eec1-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="7eec1-180">Das Limit von WQL-Schlüsselwörter, hängt davon ab, wie komplex die Abfrage ist.</span><span class="sxs-lookup"><span data-stu-id="7eec1-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="7eec1-181">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch den Aufruf der [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="7eec1-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="7eec1-182">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7eec1-182">Requirements</span></span>

<span data-ttu-id="7eec1-183">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eec1-183">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="7eec1-184">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7eec1-184">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="7eec1-185">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7eec1-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7eec1-186">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7eec1-186">See also</span></span>

- [<span data-ttu-id="7eec1-187">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="7eec1-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)