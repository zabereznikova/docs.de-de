---
title: Execnotificationquerywmi-Funktion (Referenz zur nicht verwalteten API)
description: Die execnotificationquerywmi-Funktion führt eine Abfrage aus, um Ereignisse zu empfangen.
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
ms.openlocfilehash: 3d8a7683eef52a5e91bf7aa84d5aa7db7dbdac8d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130442"
---
# <a name="execnotificationquerywmi-function"></a><span data-ttu-id="15921-103">ExecNotificationQueryWmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="15921-103">ExecNotificationQueryWmi function</span></span>

<span data-ttu-id="15921-104">Führt eine Abfrage zum Empfangen von Ereignissen aus.</span><span class="sxs-lookup"><span data-stu-id="15921-104">Executes a query to receive events.</span></span> <span data-ttu-id="15921-105">Der Aufruf wird sofort zurückgegeben, und der Aufrufer kann den zurückgegebenen Enumerator nach Ereignissen abrufen, sobald sie eintreffen.</span><span class="sxs-lookup"><span data-stu-id="15921-105">The call returns immediately, and the caller can poll the returned enumerator for events as they arrive.</span></span> <span data-ttu-id="15921-106">Wenn Sie den zurückgegebenen Enumerator freigeben, wird die Abfrage abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="15921-106">Releasing the returned enumerator cancels the query.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="15921-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="15921-107">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="15921-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="15921-108">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="15921-109">in Eine Zeichenfolge mit der gültigen von der Windows-Verwaltung unterstützten Abfragesprache.</span><span class="sxs-lookup"><span data-stu-id="15921-109">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="15921-110">Der Wert muss "WQL" und das Akronym für WMI-Abfragesprache sein.</span><span class="sxs-lookup"><span data-stu-id="15921-110">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="15921-111">in Der Text der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="15921-111">[in] The text of the query.</span></span> <span data-ttu-id="15921-112">Dieser Parameter kann nicht `null`werden.</span><span class="sxs-lookup"><span data-stu-id="15921-112">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="15921-113">in Eine Kombination der beiden folgenden Flags, die sich auf das Verhalten dieser Funktion auswirken.</span><span class="sxs-lookup"><span data-stu-id="15921-113">[in] A combination of the following two flags that affect the behavior of this function.</span></span> <span data-ttu-id="15921-114">Diese Werte sind in der Header Datei " *wbemcli. h* " definiert, oder Sie können Sie als Konstanten im Code definieren.</span><span class="sxs-lookup"><span data-stu-id="15921-114">These values are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

| <span data-ttu-id="15921-115">Konstante</span><span class="sxs-lookup"><span data-stu-id="15921-115">Constant</span></span> | <span data-ttu-id="15921-116">Wert</span><span class="sxs-lookup"><span data-stu-id="15921-116">Value</span></span>  | <span data-ttu-id="15921-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15921-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="15921-118">0x10</span><span class="sxs-lookup"><span data-stu-id="15921-118">0x10</span></span> | <span data-ttu-id="15921-119">Das-Flag verursacht einen semisynchronen-Rückruf.</span><span class="sxs-lookup"><span data-stu-id="15921-119">The flag causes a semisynchronous call.</span></span> <span data-ttu-id="15921-120">Wenn dieses Flag nicht festgelegt ist, schlägt der-Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="15921-120">If this flag is not set, the call fails.</span></span> <span data-ttu-id="15921-121">Dies liegt daran, dass Ereignisse kontinuierlich empfangen werden, was bedeutet, dass der Benutzer den zurückgegebenen Enumerator Abfragen muss.</span><span class="sxs-lookup"><span data-stu-id="15921-121">This is because events are received continuously, which means the user must poll the returned enumerator.</span></span> <span data-ttu-id="15921-122">Durch eine unbegrenzte Sperre dieses Aufrufes ist dies unmöglich.</span><span class="sxs-lookup"><span data-stu-id="15921-122">Blocking this call indefinitely makes that impossible.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="15921-123">0x20</span><span class="sxs-lookup"><span data-stu-id="15921-123">0x20</span></span> | <span data-ttu-id="15921-124">Die-Funktion gibt einen vorwärts-Enumerator zurück.</span><span class="sxs-lookup"><span data-stu-id="15921-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="15921-125">In der Regel sind vorwärts-Enumeratoren schneller und verbrauchen weniger Arbeitsspeicher als herkömmliche Enumeratoren, aber Sie erlauben keine Aufrufe von [Klonen](clone.md).</span><span class="sxs-lookup"><span data-stu-id="15921-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |

`pCtx`\
<span data-ttu-id="15921-126">in In der Regel ist dieser Wert `null`.</span><span class="sxs-lookup"><span data-stu-id="15921-126">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="15921-127">Andernfalls handelt es sich um einen Zeiger auf eine [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, der die angeforderten Ereignisse bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="15921-127">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested events.</span></span>

`ppEnum`\
<span data-ttu-id="15921-128">vorgenommen Wenn kein Fehler auftritt, empfängt den Zeiger auf den Enumerator, der dem Aufrufer das Abrufen der Instanzen im Resultset der Abfrage ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="15921-128">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="15921-129">Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="15921-129">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="15921-130">in Die Autorisierungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="15921-130">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="15921-131">in Die Ebene des Identitäts Wechsels.</span><span class="sxs-lookup"><span data-stu-id="15921-131">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="15921-132">in Ein Zeiger auf ein [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) -Objekt, das den aktuellen Namespace darstellt.</span><span class="sxs-lookup"><span data-stu-id="15921-132">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="15921-133">in Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="15921-133">[in] The user name.</span></span> <span data-ttu-id="15921-134">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="15921-134">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="15921-135">in Das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="15921-135">[in] The password.</span></span> <span data-ttu-id="15921-136">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="15921-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="15921-137">in Der Domänen Name des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="15921-137">[in] The domain name of the user.</span></span> <span data-ttu-id="15921-138">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="15921-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="15921-139">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="15921-139">Return value</span></span>

<span data-ttu-id="15921-140">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="15921-140">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="15921-141">Konstante</span><span class="sxs-lookup"><span data-stu-id="15921-141">Constant</span></span>  |<span data-ttu-id="15921-142">Wert</span><span class="sxs-lookup"><span data-stu-id="15921-142">Value</span></span>  |<span data-ttu-id="15921-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15921-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="15921-144">0x80041003</span><span class="sxs-lookup"><span data-stu-id="15921-144">0x80041003</span></span> | <span data-ttu-id="15921-145">Der Benutzer verfügt nicht über die Berechtigung zum Anzeigen einer oder mehrerer Klassen, die von der Funktion zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="15921-145">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="15921-146">0x80041001</span><span class="sxs-lookup"><span data-stu-id="15921-146">0x80041001</span></span> | <span data-ttu-id="15921-147">Ein nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="15921-147">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="15921-148">0x80041008</span><span class="sxs-lookup"><span data-stu-id="15921-148">0x80041008</span></span> | <span data-ttu-id="15921-149">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="15921-149">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="15921-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="15921-150">0x80041010</span></span> | <span data-ttu-id="15921-151">Die Abfrage gibt eine Klasse an, die nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="15921-151">The query specifies a class that does not exist.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | <span data-ttu-id="15921-152">0x80042002</span><span class="sxs-lookup"><span data-stu-id="15921-152">0x80042002</span></span> | <span data-ttu-id="15921-153">Es wurde eine zu viel Genauigkeit bei der Übermittlung von Ereignissen angefordert.</span><span class="sxs-lookup"><span data-stu-id="15921-153">Too much precision in delivery of events has been requested.</span></span> <span data-ttu-id="15921-154">Es muss eine größere Abruf Toleranz angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="15921-154">A larger polling tolerance must be specified.</span></span> |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | <span data-ttu-id="15921-155">0x80042001</span><span class="sxs-lookup"><span data-stu-id="15921-155">0x80042001</span></span> | <span data-ttu-id="15921-156">Die Abfrage fordert mehr Informationen an als die Windows-Verwaltung bereitstellen kann.</span><span class="sxs-lookup"><span data-stu-id="15921-156">The query requests more information than Windows Management can provide.</span></span> <span data-ttu-id="15921-157">Diese `HRESULT` wird zurückgegeben, wenn eine Ereignis Abfrage eine Anforderung zum Abfragen aller Objekte in einem Namespace ergibt.</span><span class="sxs-lookup"><span data-stu-id="15921-157">This `HRESULT` is returned when an event query results in a request to poll all objects in a namespace.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="15921-158">0x80041017</span><span class="sxs-lookup"><span data-stu-id="15921-158">0x80041017</span></span> | <span data-ttu-id="15921-159">Die Abfrage enthielt einen Syntax Fehler.</span><span class="sxs-lookup"><span data-stu-id="15921-159">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="15921-160">0x80041018</span><span class="sxs-lookup"><span data-stu-id="15921-160">0x80041018</span></span> | <span data-ttu-id="15921-161">Die angeforderte Abfragesprache wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="15921-161">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="15921-162">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="15921-162">0x8004106c</span></span> | <span data-ttu-id="15921-163">Die Abfrage ist zu komplex.</span><span class="sxs-lookup"><span data-stu-id="15921-163">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="15921-164">0x80041006</span><span class="sxs-lookup"><span data-stu-id="15921-164">0x80041006</span></span> | <span data-ttu-id="15921-165">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="15921-165">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="15921-166">0x80041033</span><span class="sxs-lookup"><span data-stu-id="15921-166">0x80041033</span></span> | <span data-ttu-id="15921-167">WMI wurde wahrscheinlich angehalten und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="15921-167">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="15921-168">Ruft [connectserverwmi](connectserverwmi.md) erneut auf.</span><span class="sxs-lookup"><span data-stu-id="15921-168">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="15921-169">0x80041015</span><span class="sxs-lookup"><span data-stu-id="15921-169">0x80041015</span></span> | <span data-ttu-id="15921-170">Fehler beim Remote Prozedur Aufruf (RPC)-Link zwischen dem aktuellen Prozess und WMI.</span><span class="sxs-lookup"><span data-stu-id="15921-170">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_UNPARSABLE_QUERY` | <span data-ttu-id="15921-171">0x80041058</span><span class="sxs-lookup"><span data-stu-id="15921-171">0x80041058</span></span> | <span data-ttu-id="15921-172">Die Abfrage kann nicht analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="15921-172">The query cannot be parsed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="15921-173">0</span><span class="sxs-lookup"><span data-stu-id="15921-173">0</span></span> | <span data-ttu-id="15921-174">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="15921-174">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="15921-175">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15921-175">Remarks</span></span>

<span data-ttu-id="15921-176">Diese Funktion umschließt einen Aufruf der [IWbemServices:: ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) -Methode.</span><span class="sxs-lookup"><span data-stu-id="15921-176">This function wraps a call to the [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) method.</span></span>

<span data-ttu-id="15921-177">Nachdem die Funktion zurückgegeben wurde, übergibt der Aufrufer regelmäßig das zurückgegebene `ppEnum` Objekt an die [Next](next.md) -Funktion, um festzustellen, ob Ereignisse verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="15921-177">After the function returns, the caller periodically passes the returned `ppEnum` object to the [Next](next.md) function to see if any events are available.</span></span>

<span data-ttu-id="15921-178">Es gibt Grenzwerte für die Anzahl der `AND`-und `OR` Schlüsselwörter, die in WQL-Abfragen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="15921-178">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="15921-179">Eine große Anzahl von WQL-Schlüsselwörtern, die in einer komplexen Abfrage verwendet werden, kann dazu führen, dass WMI den `WBEM_E_QUOTA_VIOLATION` Fehlercode (oder 0x8004106c) als `HRESULT` Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="15921-179">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="15921-180">Das Limit von WQL-Schlüsselwörtern hängt von der Komplexität der Abfrage ab.</span><span class="sxs-lookup"><span data-stu-id="15921-180">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="15921-181">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, indem Sie die [GetErrorInfo](geterrorinfo.md) -Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="15921-181">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="15921-182">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15921-182">Requirements</span></span>

<span data-ttu-id="15921-183">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15921-183">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="15921-184">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="15921-184">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="15921-185">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="15921-185">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="15921-186">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15921-186">See also</span></span>

- [<span data-ttu-id="15921-187">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="15921-187">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
