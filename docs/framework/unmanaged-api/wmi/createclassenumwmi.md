---
title: Funktion "-API-Funktion" (nicht verwaltete API-Referenz)
description: Die Funktion "kreateclassenumwmi" gibt einen Enumerator für alle Klassen zurück, die die angegebenen Kriterien erfüllen.
ms.date: 11/06/2017
api_name:
- CreateClassEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateClassEnumWmi
helpviewer_keywords:
- CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 5b80954e288f6720c75d0af0b8af083fa4856754
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719735"
---
# <a name="createclassenumwmi-function"></a><span data-ttu-id="cb438-103">CreateClassEnumWmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="cb438-103">CreateClassEnumWmi function</span></span>

<span data-ttu-id="cb438-104">Gibt einen Enumerator für alle Klassen zurück, die die angegebenen Auswahlkriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="cb438-104">Returns an enumerator for all classes that satisfy the specified selection criteria.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="cb438-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb438-105">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="cb438-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="cb438-106">Parameters</span></span>

`strSuperclass`\
<span data-ttu-id="cb438-107">in Wenn nicht `null` oder leer, wird der Name einer übergeordneten Klasse angegeben. der Enumerator gibt nur Unterklassen dieser Klasse zurück.</span><span class="sxs-lookup"><span data-stu-id="cb438-107">[in] If not `null` or blank, specifies the name of a parent class; the enumerator returns only subclasses of this class.</span></span> <span data-ttu-id="cb438-108">Wenn Sie `null` oder leer ist und `lFlags` WBEM_FLAG_SHALLOW ist, gibt nur Klassen der obersten Ebene zurück (Klassen ohne übergeordnete Klasse).</span><span class="sxs-lookup"><span data-stu-id="cb438-108">If it is `null` or blank and `lFlags` is WBEM_FLAG_SHALLOW, returns only top-level classes (classes with no parent class).</span></span> <span data-ttu-id="cb438-109">Wenn Sie `null` oder leer ist und `lFlags` ist `WBEM_FLAG_DEEP` , werden alle Klassen im-Namespace zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cb438-109">If it is `null` or blank and `lFlags` is `WBEM_FLAG_DEEP`, returns all classes in the namespace.</span></span>

`lFlags`\
<span data-ttu-id="cb438-110">in Eine Kombination von Flags, die sich auf das Verhalten dieser Funktion auswirken.</span><span class="sxs-lookup"><span data-stu-id="cb438-110">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="cb438-111">Die folgenden Werte sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="cb438-111">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="cb438-112">Konstante</span><span class="sxs-lookup"><span data-stu-id="cb438-112">Constant</span></span>  |<span data-ttu-id="cb438-113">Wert</span><span class="sxs-lookup"><span data-stu-id="cb438-113">Value</span></span>  |<span data-ttu-id="cb438-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cb438-114">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="cb438-115">0x20000</span><span class="sxs-lookup"><span data-stu-id="cb438-115">0x20000</span></span> | <span data-ttu-id="cb438-116">Wenn festgelegt, ruft die Funktion die im lokalisierten Namespace des Gebiets Schemas der aktuellen Verbindung gespeicherten geänderten Qualifizierer ab.</span><span class="sxs-lookup"><span data-stu-id="cb438-116">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="cb438-117">Wenn nicht festgelegt, ruft die Funktion nur die Qualifizierer ab, die im unmittelbaren Namespace gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="cb438-117">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="cb438-118">0</span><span class="sxs-lookup"><span data-stu-id="cb438-118">0</span></span> | <span data-ttu-id="cb438-119">Die-Enumeration enthält alle Unterklassen in der Hierarchie, aber nicht diese Klasse.</span><span class="sxs-lookup"><span data-stu-id="cb438-119">The enumeration includes all subclasses in the hierarchy, but not this class.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="cb438-120">1</span><span class="sxs-lookup"><span data-stu-id="cb438-120">1</span></span> | <span data-ttu-id="cb438-121">Die-Enumeration enthält nur reine Instanzen dieser Klasse und schließt alle Instanzen von Unterklassen aus, die Eigenschaften bereitstellen, die in dieser Klasse nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="cb438-121">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="cb438-122">0x10</span><span class="sxs-lookup"><span data-stu-id="cb438-122">0x10</span></span> | <span data-ttu-id="cb438-123">Das-Flag verursacht einen semisynchronen-Rückruf.</span><span class="sxs-lookup"><span data-stu-id="cb438-123">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="cb438-124">0x20</span><span class="sxs-lookup"><span data-stu-id="cb438-124">0x20</span></span> | <span data-ttu-id="cb438-125">Die-Funktion gibt einen vorwärts-Enumerator zurück.</span><span class="sxs-lookup"><span data-stu-id="cb438-125">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="cb438-126">In der Regel sind vorwärts-Enumeratoren schneller und verbrauchen weniger Arbeitsspeicher als herkömmliche Enumeratoren, aber Sie erlauben keine Aufrufe von [Klonen](clone.md).</span><span class="sxs-lookup"><span data-stu-id="cb438-126">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="cb438-127">0</span><span class="sxs-lookup"><span data-stu-id="cb438-127">0</span></span> | <span data-ttu-id="cb438-128">WMI behält Zeiger auf Objekte in der-Enumeration bei, bis Sie freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cb438-128">WMI retains pointers to objects in the enumeration until they are released.</span></span> |

<span data-ttu-id="cb438-129">Die empfohlenen Flags sind `WBEM_FLAG_RETURN_IMMEDIATELY` und, `WBEM_FLAG_FORWARD_ONLY` um eine optimale Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="cb438-129">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="cb438-130">in Normalerweise ist dieser Wert `null` .</span><span class="sxs-lookup"><span data-stu-id="cb438-130">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="cb438-131">Andernfalls handelt es sich um einen Zeiger auf eine [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, der die angeforderten Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="cb438-131">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="cb438-132">vorgenommen Empfängt den Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="cb438-132">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`\
<span data-ttu-id="cb438-133">in Die Autorisierungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="cb438-133">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="cb438-134">in Die Ebene des Identitäts Wechsels.</span><span class="sxs-lookup"><span data-stu-id="cb438-134">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="cb438-135">in Ein Zeiger auf ein [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) -Objekt, das den aktuellen Namespace darstellt.</span><span class="sxs-lookup"><span data-stu-id="cb438-135">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="cb438-136">in Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="cb438-136">[in] The user name.</span></span> <span data-ttu-id="cb438-137">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="cb438-137">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="cb438-138">in Das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="cb438-138">[in] The password.</span></span> <span data-ttu-id="cb438-139">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="cb438-139">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="cb438-140">in Der Domänen Name des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="cb438-140">[in] The domain name of the user.</span></span> <span data-ttu-id="cb438-141">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="cb438-141">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="cb438-142">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cb438-142">Return value</span></span>

<span data-ttu-id="cb438-143">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="cb438-143">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="cb438-144">Konstante</span><span class="sxs-lookup"><span data-stu-id="cb438-144">Constant</span></span>  |<span data-ttu-id="cb438-145">Wert</span><span class="sxs-lookup"><span data-stu-id="cb438-145">Value</span></span>  |<span data-ttu-id="cb438-146">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cb438-146">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="cb438-147">0x80041003</span><span class="sxs-lookup"><span data-stu-id="cb438-147">0x80041003</span></span> | <span data-ttu-id="cb438-148">Der Benutzer verfügt nicht über die Berechtigung zum Anzeigen einer oder mehrerer Klassen, die von der Funktion zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="cb438-148">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="cb438-149">0x80041001</span><span class="sxs-lookup"><span data-stu-id="cb438-149">0x80041001</span></span> | <span data-ttu-id="cb438-150">Ein unbekannter Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="cb438-150">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="cb438-151">0x80041010</span><span class="sxs-lookup"><span data-stu-id="cb438-151">0x80041010</span></span> | <span data-ttu-id="cb438-152">`strSuperClass` existiert nicht.</span><span class="sxs-lookup"><span data-stu-id="cb438-152">`strSuperClass` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="cb438-153">0x80041008</span><span class="sxs-lookup"><span data-stu-id="cb438-153">0x80041008</span></span> | <span data-ttu-id="cb438-154">Ein Parameter ist nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="cb438-154">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="cb438-155">0x80041006</span><span class="sxs-lookup"><span data-stu-id="cb438-155">0x80041006</span></span> | <span data-ttu-id="cb438-156">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="cb438-156">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="cb438-157">0x80041033</span><span class="sxs-lookup"><span data-stu-id="cb438-157">0x80041033</span></span> | <span data-ttu-id="cb438-158">WMI wurde wahrscheinlich angehalten und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="cb438-158">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="cb438-159">Ruft [connectserverwmi](connectserverwmi.md) erneut auf.</span><span class="sxs-lookup"><span data-stu-id="cb438-159">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="cb438-160">0x80041015</span><span class="sxs-lookup"><span data-stu-id="cb438-160">0x80041015</span></span> | <span data-ttu-id="cb438-161">Fehler beim Remote Prozedur Aufruf (RPC)-Link zwischen dem aktuellen Prozess und WMI.</span><span class="sxs-lookup"><span data-stu-id="cb438-161">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="cb438-162">0</span><span class="sxs-lookup"><span data-stu-id="cb438-162">0</span></span> | <span data-ttu-id="cb438-163">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="cb438-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="cb438-164">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cb438-164">Remarks</span></span>

<span data-ttu-id="cb438-165">Diese Funktion umschließt einen aufzurufenden Befehl der Methode [IWbemServices:: | ateclassenum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) .</span><span class="sxs-lookup"><span data-stu-id="cb438-165">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) method.</span></span>

<span data-ttu-id="cb438-166">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, indem Sie die [GetErrorInfo](geterrorinfo.md) -Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="cb438-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="cb438-167">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cb438-167">Requirements</span></span>

<span data-ttu-id="cb438-168">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb438-168">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="cb438-169">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="cb438-169">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="cb438-170">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cb438-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cb438-171">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb438-171">See also</span></span>

- [<span data-ttu-id="cb438-172">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="cb438-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
