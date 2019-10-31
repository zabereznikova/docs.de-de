---
title: Execquerywmi-Funktion (Referenz zur nicht verwalteten API)
description: Die execquerywmi-Funktion führt eine Abfrage zum Abrufen von-Objekten aus.
ms.date: 11/06/2017
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
ms.openlocfilehash: 3c6ea58eca5ac635893a24b57ade261e04a69721
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130434"
---
# <a name="execquerywmi-function"></a><span data-ttu-id="48ba9-103">ExecQueryWmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="48ba9-103">ExecQueryWmi function</span></span>

<span data-ttu-id="48ba9-104">Führt eine Abfrage zum Abrufen von Objekten aus.</span><span class="sxs-lookup"><span data-stu-id="48ba9-104">Executes a query to retrieve objects.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="48ba9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="48ba9-105">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="48ba9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="48ba9-106">Parameters</span></span>

`strQueryLanguage`\
<span data-ttu-id="48ba9-107">in Eine Zeichenfolge mit der gültigen von der Windows-Verwaltung unterstützten Abfragesprache.</span><span class="sxs-lookup"><span data-stu-id="48ba9-107">[in] A string with the valid query language supported by Windows Management.</span></span> <span data-ttu-id="48ba9-108">Der Wert muss "WQL" und das Akronym für WMI-Abfragesprache sein.</span><span class="sxs-lookup"><span data-stu-id="48ba9-108">It must be "WQL", the acronym for WMI Query Language.</span></span>

`strQuery`\
<span data-ttu-id="48ba9-109">in Der Text der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="48ba9-109">[in] The text of the query.</span></span> <span data-ttu-id="48ba9-110">Dieser Parameter kann nicht `null`werden.</span><span class="sxs-lookup"><span data-stu-id="48ba9-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="48ba9-111">in Eine Kombination von Flags, die sich auf das Verhalten dieser Funktion auswirken.</span><span class="sxs-lookup"><span data-stu-id="48ba9-111">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="48ba9-112">Die folgenden Werte sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="48ba9-112">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

| <span data-ttu-id="48ba9-113">Konstante</span><span class="sxs-lookup"><span data-stu-id="48ba9-113">Constant</span></span> | <span data-ttu-id="48ba9-114">Wert</span><span class="sxs-lookup"><span data-stu-id="48ba9-114">Value</span></span>  | <span data-ttu-id="48ba9-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48ba9-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="48ba9-116">0x20000</span><span class="sxs-lookup"><span data-stu-id="48ba9-116">0x20000</span></span> | <span data-ttu-id="48ba9-117">Wenn festgelegt, ruft die Funktion die im lokalisierten Namespace des Gebiets Schemas der aktuellen Verbindung gespeicherten geänderten Qualifizierer ab.</span><span class="sxs-lookup"><span data-stu-id="48ba9-117">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="48ba9-118">Wenn nicht festgelegt, ruft die Funktion nur die Qualifizierer ab, die im unmittelbaren Namespace gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="48ba9-118">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="48ba9-119">0x10</span><span class="sxs-lookup"><span data-stu-id="48ba9-119">0x10</span></span> | <span data-ttu-id="48ba9-120">Das-Flag verursacht einen semisynchronen-Rückruf.</span><span class="sxs-lookup"><span data-stu-id="48ba9-120">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="48ba9-121">0x20</span><span class="sxs-lookup"><span data-stu-id="48ba9-121">0x20</span></span> | <span data-ttu-id="48ba9-122">Die-Funktion gibt einen vorwärts-Enumerator zurück.</span><span class="sxs-lookup"><span data-stu-id="48ba9-122">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="48ba9-123">In der Regel sind vorwärts-Enumeratoren schneller und verbrauchen weniger Arbeitsspeicher als herkömmliche Enumeratoren, aber Sie erlauben keine Aufrufe von [Klonen](clone.md).</span><span class="sxs-lookup"><span data-stu-id="48ba9-123">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="48ba9-124">0</span><span class="sxs-lookup"><span data-stu-id="48ba9-124">0</span></span> | <span data-ttu-id="48ba9-125">WMI behält Zeiger auf Objekte in der-Enumeration bei, bis Sie freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="48ba9-125">WMI retains pointers to objects in the enumeration until they are released.</span></span> |
| `WBEM_FLAG_ENSURE_LOCATABLE` | <span data-ttu-id="48ba9-126">0x100</span><span class="sxs-lookup"><span data-stu-id="48ba9-126">0x100</span></span> | <span data-ttu-id="48ba9-127">Stellt sicher, dass alle zurückgegebenen Objekte über genügend Informationen verfügen, damit Systemeigenschaften, z. b. **__PATH**, **__RELPATH**und **__SERVER**, nicht `null`werden.</span><span class="sxs-lookup"><span data-stu-id="48ba9-127">Ensures that any returned objects have enough information in them so that system properties, such as **__PATH**, **__RELPATH**, and **__SERVER**, are not `null`.</span></span> |
| `WBEM_FLAG_PROTOTYPE` | <span data-ttu-id="48ba9-128">2</span><span class="sxs-lookup"><span data-stu-id="48ba9-128">2</span></span> | <span data-ttu-id="48ba9-129">Dieses Flag wird für die Prototyperstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="48ba9-129">This flag is used for prototyping.</span></span> <span data-ttu-id="48ba9-130">Die Abfrage wird nicht ausgeführt, sondern es wird ein Objekt zurückgegeben, das wie ein typisches Ergebnis Objekt aussieht.</span><span class="sxs-lookup"><span data-stu-id="48ba9-130">It does not execute the query and instead returns an object that looks like a typical result object.</span></span> |
| `WBEM_FLAG_DIRECT_READ` | <span data-ttu-id="48ba9-131">0x200</span><span class="sxs-lookup"><span data-stu-id="48ba9-131">0x200</span></span> | <span data-ttu-id="48ba9-132">Bewirkt, dass der direkte Zugriff auf den Anbieter für die angegebene Klasse ohne Berücksichtigung der zugehörigen übergeordneten Klasse oder Unterklassen verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="48ba9-132">Causes direct access to the provider for the class specified without regard to its parent class or any subclasses.</span></span> |

<span data-ttu-id="48ba9-133">Die empfohlenen Flags sind `WBEM_FLAG_RETURN_IMMEDIATELY` und `WBEM_FLAG_FORWARD_ONLY`, um eine optimale Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="48ba9-133">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="48ba9-134">in In der Regel ist dieser Wert `null`.</span><span class="sxs-lookup"><span data-stu-id="48ba9-134">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="48ba9-135">Andernfalls handelt es sich um einen Zeiger auf eine [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, der die angeforderten Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="48ba9-135">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="48ba9-136">vorgenommen Wenn kein Fehler auftritt, empfängt den Zeiger auf den Enumerator, der dem Aufrufer das Abrufen der Instanzen im Resultset der Abfrage ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="48ba9-136">[out] If no error occurs, receives the pointer to the enumerator that allows the caller to retrieve the instances in the query's result set.</span></span> <span data-ttu-id="48ba9-137">Die Abfrage kann ein Resultset mit 0 (null) Instanzen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="48ba9-137">The query can have a result set with zero instances.</span></span> <span data-ttu-id="48ba9-138">Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="48ba9-138">See the [Remarks](#remarks) section for more information.</span></span>

`authLevel`\
<span data-ttu-id="48ba9-139">in Die Autorisierungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="48ba9-139">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="48ba9-140">in Die Ebene des Identitäts Wechsels.</span><span class="sxs-lookup"><span data-stu-id="48ba9-140">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="48ba9-141">in Ein Zeiger auf ein [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) -Objekt, das den aktuellen Namespace darstellt.</span><span class="sxs-lookup"><span data-stu-id="48ba9-141">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="48ba9-142">in Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="48ba9-142">[in] The user name.</span></span> <span data-ttu-id="48ba9-143">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="48ba9-143">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="48ba9-144">in Das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="48ba9-144">[in] The password.</span></span> <span data-ttu-id="48ba9-145">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="48ba9-145">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="48ba9-146">in Der Domänen Name des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="48ba9-146">[in] The domain name of the user.</span></span> <span data-ttu-id="48ba9-147">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="48ba9-147">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="48ba9-148">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="48ba9-148">Return value</span></span>

<span data-ttu-id="48ba9-149">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="48ba9-149">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="48ba9-150">Konstante</span><span class="sxs-lookup"><span data-stu-id="48ba9-150">Constant</span></span>  |<span data-ttu-id="48ba9-151">Wert</span><span class="sxs-lookup"><span data-stu-id="48ba9-151">Value</span></span>  |<span data-ttu-id="48ba9-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48ba9-152">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="48ba9-153">0x80041003</span><span class="sxs-lookup"><span data-stu-id="48ba9-153">0x80041003</span></span> | <span data-ttu-id="48ba9-154">Der Benutzer verfügt nicht über die Berechtigung zum Anzeigen einer oder mehrerer Klassen, die von der Funktion zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="48ba9-154">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="48ba9-155">0x80041001</span><span class="sxs-lookup"><span data-stu-id="48ba9-155">0x80041001</span></span> | <span data-ttu-id="48ba9-156">Ein nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="48ba9-156">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="48ba9-157">0x80041008</span><span class="sxs-lookup"><span data-stu-id="48ba9-157">0x80041008</span></span> | <span data-ttu-id="48ba9-158">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="48ba9-158">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUERY` | <span data-ttu-id="48ba9-159">0x80041017</span><span class="sxs-lookup"><span data-stu-id="48ba9-159">0x80041017</span></span> | <span data-ttu-id="48ba9-160">Die Abfrage enthielt einen Syntax Fehler.</span><span class="sxs-lookup"><span data-stu-id="48ba9-160">The query had a syntax error.</span></span> |
| `WBEM_E_INVALID_QUERY_TYPE` | <span data-ttu-id="48ba9-161">0x80041018</span><span class="sxs-lookup"><span data-stu-id="48ba9-161">0x80041018</span></span> | <span data-ttu-id="48ba9-162">Die angeforderte Abfragesprache wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="48ba9-162">The requested query language is not supported.</span></span> |
| `WBEM_E_QUOTA_VIOLATION` | <span data-ttu-id="48ba9-163">0x8004106c</span><span class="sxs-lookup"><span data-stu-id="48ba9-163">0x8004106c</span></span> | <span data-ttu-id="48ba9-164">Die Abfrage ist zu komplex.</span><span class="sxs-lookup"><span data-stu-id="48ba9-164">The query is too complex.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="48ba9-165">0x80041006</span><span class="sxs-lookup"><span data-stu-id="48ba9-165">0x80041006</span></span> | <span data-ttu-id="48ba9-166">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="48ba9-166">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="48ba9-167">0x80041033</span><span class="sxs-lookup"><span data-stu-id="48ba9-167">0x80041033</span></span> | <span data-ttu-id="48ba9-168">WMI wurde wahrscheinlich angehalten und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="48ba9-168">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="48ba9-169">Ruft [connectserverwmi](connectserverwmi.md) erneut auf.</span><span class="sxs-lookup"><span data-stu-id="48ba9-169">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="48ba9-170">0x80041015</span><span class="sxs-lookup"><span data-stu-id="48ba9-170">0x80041015</span></span> | <span data-ttu-id="48ba9-171">Fehler beim Remote Prozedur Aufruf (RPC)-Link zwischen dem aktuellen Prozess und WMI.</span><span class="sxs-lookup"><span data-stu-id="48ba9-171">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="48ba9-172">0x80041002 angezeigt</span><span class="sxs-lookup"><span data-stu-id="48ba9-172">0x80041002</span></span> | <span data-ttu-id="48ba9-173">Die Abfrage gibt eine Klasse an, die nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="48ba9-173">The query specifies a class that does not exist.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="48ba9-174">0</span><span class="sxs-lookup"><span data-stu-id="48ba9-174">0</span></span> | <span data-ttu-id="48ba9-175">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="48ba9-175">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="48ba9-176">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48ba9-176">Remarks</span></span>

<span data-ttu-id="48ba9-177">Diese Funktion umschließt einen aufzurufenden Befehl der [IWbemServices:: ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) -Methode.</span><span class="sxs-lookup"><span data-stu-id="48ba9-177">This function wraps a call to the [IWbemServices::ExecQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execquery) method.</span></span>

<span data-ttu-id="48ba9-178">Diese Funktion verarbeitet die im `strQuery`-Parameter angegebene Abfrage und erstellt einen Enumerator, über den der Aufrufer auf die Abfrageergebnisse zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="48ba9-178">This function processes the query specified in the `strQuery` parameter and creates an enumerator through which the caller can access the query results.</span></span> <span data-ttu-id="48ba9-179">Der Enumerator ist ein Zeiger auf eine [ienumwbemclassobject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) -Schnittstelle. die Abfrageergebnisse sind Instanzen von Klassen Objekten, die über die [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) -Schnittstelle verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="48ba9-179">The enumerator is a pointer to an [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) interface; the query results are instances of class objects made available through the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) interface.</span></span>

<span data-ttu-id="48ba9-180">Es gibt Grenzwerte für die Anzahl der `AND`-und `OR` Schlüsselwörter, die in WQL-Abfragen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="48ba9-180">There are limits to the number of `AND` and `OR` keywords that can be used in WQL queries.</span></span> <span data-ttu-id="48ba9-181">Eine große Anzahl von WQL-Schlüsselwörtern, die in einer komplexen Abfrage verwendet werden, kann dazu führen, dass WMI den `WBEM_E_QUOTA_VIOLATION` Fehlercode (oder 0x8004106c) als `HRESULT` Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="48ba9-181">Large numbers of WQL keywords used in a complex query can cause WMI to return the `WBEM_E_QUOTA_VIOLATION` (or 0x8004106c) error code as an `HRESULT` value.</span></span> <span data-ttu-id="48ba9-182">Das Limit von WQL-Schlüsselwörtern hängt von der Komplexität der Abfrage ab.</span><span class="sxs-lookup"><span data-stu-id="48ba9-182">The limit of WQL keywords depends on how complex the query is.</span></span>

<span data-ttu-id="48ba9-183">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, indem Sie die [GetErrorInfo](geterrorinfo.md) -Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="48ba9-183">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="48ba9-184">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="48ba9-184">Requirements</span></span>

<span data-ttu-id="48ba9-185">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48ba9-185">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="48ba9-186">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="48ba9-186">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="48ba9-187">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="48ba9-187">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="48ba9-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48ba9-188">See also</span></span>

- [<span data-ttu-id="48ba9-189">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="48ba9-189">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
