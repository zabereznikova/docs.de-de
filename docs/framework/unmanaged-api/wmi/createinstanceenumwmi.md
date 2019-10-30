---
title: Funktion "-Funktion" (nicht verwaltete API-Referenz)
description: Die Funktion "kreateinstanceenumwmi" gibt einen Enumerator zurück, der Instanzen einer bestimmten Klasse enthält, die die Auswahlkriterien erfüllen.
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
ms.openlocfilehash: 9ffa718be0e8b67471fdf8cb277df201388d2840
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130405"
---
# <a name="createinstanceenumwmi-function"></a><span data-ttu-id="0b943-103">Funktion "-Funktion"</span><span class="sxs-lookup"><span data-stu-id="0b943-103">CreateInstanceEnumWmi function</span></span>

<span data-ttu-id="0b943-104">Gibt einen Enumerator zurück, der die Instanzen einer bestimmten Klasse zurückgibt, die angegebene Auswahlkriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="0b943-104">Returns an enumerator that returns the instances of a specified class that meet specified selection criteria.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="0b943-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b943-105">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="0b943-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0b943-106">Parameters</span></span>

`strFilter`\
<span data-ttu-id="0b943-107">in Der Name der Klasse, für die-Instanzen gewünscht werden.</span><span class="sxs-lookup"><span data-stu-id="0b943-107">[in] The name of the class for which instances are desired.</span></span> <span data-ttu-id="0b943-108">Dieser Parameter kann nicht `null`werden.</span><span class="sxs-lookup"><span data-stu-id="0b943-108">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="0b943-109">in Eine Kombination von Flags, die sich auf das Verhalten dieser Funktion auswirken.</span><span class="sxs-lookup"><span data-stu-id="0b943-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="0b943-110">Die folgenden Werte sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="0b943-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0b943-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="0b943-111">Constant</span></span>  |<span data-ttu-id="0b943-112">Wert</span><span class="sxs-lookup"><span data-stu-id="0b943-112">Value</span></span>  |<span data-ttu-id="0b943-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b943-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="0b943-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="0b943-114">0x20000</span></span> | <span data-ttu-id="0b943-115">Wenn festgelegt, ruft die Funktion die im lokalisierten Namespace des Gebiets Schemas der aktuellen Verbindung gespeicherten geänderten Qualifizierer ab.</span><span class="sxs-lookup"><span data-stu-id="0b943-115">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="0b943-116">Wenn nicht festgelegt, ruft die Funktion nur die Qualifizierer ab, die im unmittelbaren Namespace gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="0b943-116">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="0b943-117">0</span><span class="sxs-lookup"><span data-stu-id="0b943-117">0</span></span> | <span data-ttu-id="0b943-118">Die-Enumeration enthält diese und alle Unterklassen in der Hierarchie.</span><span class="sxs-lookup"><span data-stu-id="0b943-118">The enumeration includes this and all subclasses in the hierarchy.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="0b943-119">1</span><span class="sxs-lookup"><span data-stu-id="0b943-119">1</span></span> | <span data-ttu-id="0b943-120">Die-Enumeration enthält nur reine Instanzen dieser Klasse und schließt alle Instanzen von Unterklassen aus, die Eigenschaften bereitstellen, die in dieser Klasse nicht gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="0b943-120">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="0b943-121">0x10</span><span class="sxs-lookup"><span data-stu-id="0b943-121">0x10</span></span> | <span data-ttu-id="0b943-122">Das-Flag verursacht einen semisynchronen-Rückruf.</span><span class="sxs-lookup"><span data-stu-id="0b943-122">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="0b943-123">0x20</span><span class="sxs-lookup"><span data-stu-id="0b943-123">0x20</span></span> | <span data-ttu-id="0b943-124">Die-Funktion gibt einen vorwärts-Enumerator zurück.</span><span class="sxs-lookup"><span data-stu-id="0b943-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="0b943-125">In der Regel sind vorwärts-Enumeratoren schneller und verbrauchen weniger Arbeitsspeicher als herkömmliche Enumeratoren, aber Sie erlauben keine Aufrufe von [Klonen](clone.md).</span><span class="sxs-lookup"><span data-stu-id="0b943-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="0b943-126">0</span><span class="sxs-lookup"><span data-stu-id="0b943-126">0</span></span> | <span data-ttu-id="0b943-127">WMI behält Zeiger auf Objekte in der-Enumeration bei, bis Sie freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0b943-127">WMI retains pointers to objects in the enumeration until they are released.</span></span> |

<span data-ttu-id="0b943-128">Die empfohlenen Flags sind `WBEM_FLAG_RETURN_IMMEDIATELY` und `WBEM_FLAG_FORWARD_ONLY`, um eine optimale Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="0b943-128">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="0b943-129">in In der Regel ist dieser Wert `null`.</span><span class="sxs-lookup"><span data-stu-id="0b943-129">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="0b943-130">Andernfalls handelt es sich um einen Zeiger auf eine [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, der die angeforderten Instanzen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0b943-130">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that may be used by the provider that is providing the requested instances.</span></span>

`ppEnum`\
<span data-ttu-id="0b943-131">vorgenommen Empfängt den Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="0b943-131">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`\
<span data-ttu-id="0b943-132">in Die Autorisierungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="0b943-132">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="0b943-133">in Die Ebene des Identitäts Wechsels.</span><span class="sxs-lookup"><span data-stu-id="0b943-133">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="0b943-134">in Ein Zeiger auf ein [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) -Objekt, das den aktuellen Namespace darstellt.</span><span class="sxs-lookup"><span data-stu-id="0b943-134">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="0b943-135">in Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="0b943-135">[in] The user name.</span></span> <span data-ttu-id="0b943-136">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="0b943-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="0b943-137">in Das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="0b943-137">[in] The password.</span></span> <span data-ttu-id="0b943-138">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="0b943-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="0b943-139">in Der Domänen Name des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="0b943-139">[in] The domain name of the user.</span></span> <span data-ttu-id="0b943-140">Weitere Informationen finden Sie in der [connectserverwmi](connectserverwmi.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="0b943-140">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="0b943-141">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0b943-141">Return value</span></span>

<span data-ttu-id="0b943-142">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="0b943-142">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0b943-143">Konstante</span><span class="sxs-lookup"><span data-stu-id="0b943-143">Constant</span></span>  |<span data-ttu-id="0b943-144">Wert</span><span class="sxs-lookup"><span data-stu-id="0b943-144">Value</span></span>  |<span data-ttu-id="0b943-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b943-145">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="0b943-146">0x80041003</span><span class="sxs-lookup"><span data-stu-id="0b943-146">0x80041003</span></span> | <span data-ttu-id="0b943-147">Der Benutzer verfügt nicht über die Berechtigung zum Anzeigen von Instanzen der angegebenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="0b943-147">The user does not have permission to view instances of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="0b943-148">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0b943-148">0x80041001</span></span> | <span data-ttu-id="0b943-149">Ein nicht angegebener Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0b943-149">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="0b943-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="0b943-150">0x80041010</span></span> | <span data-ttu-id="0b943-151">`strFilter` existiert nicht.</span><span class="sxs-lookup"><span data-stu-id="0b943-151">`strFilter` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0b943-152">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0b943-152">0x80041008</span></span> | <span data-ttu-id="0b943-153">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="0b943-153">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0b943-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0b943-154">0x80041006</span></span> | <span data-ttu-id="0b943-155">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0b943-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="0b943-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="0b943-156">0x80041033</span></span> | <span data-ttu-id="0b943-157">WMI wurde wahrscheinlich angehalten und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="0b943-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="0b943-158">Ruft [connectserverwmi](connectserverwmi.md) erneut auf.</span><span class="sxs-lookup"><span data-stu-id="0b943-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="0b943-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="0b943-159">0x80041015</span></span> | <span data-ttu-id="0b943-160">Fehler beim Remote Prozedur Aufruf (RPC)-Link zwischen dem aktuellen Prozess und WMI.</span><span class="sxs-lookup"><span data-stu-id="0b943-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="0b943-161">0</span><span class="sxs-lookup"><span data-stu-id="0b943-161">0</span></span> | <span data-ttu-id="0b943-162">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="0b943-162">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="0b943-163">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b943-163">Remarks</span></span>

<span data-ttu-id="0b943-164">Diese Funktion umschließt einen aufzurufenden Befehl der Methode [IWbemServices:: | ateclassenum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) .</span><span class="sxs-lookup"><span data-stu-id="0b943-164">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) method.</span></span>

<span data-ttu-id="0b943-165">Beachten Sie, dass der zurückgegebene Enumerator NULL Elemente aufweisen kann.</span><span class="sxs-lookup"><span data-stu-id="0b943-165">Note that the returned enumerator can have zero elements.</span></span>

<span data-ttu-id="0b943-166">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, indem Sie die [GetErrorInfo](geterrorinfo.md) -Funktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0b943-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="0b943-167">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0b943-167">Requirements</span></span>

<span data-ttu-id="0b943-168">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b943-168">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="0b943-169">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="0b943-169">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="0b943-170">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0b943-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0b943-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b943-171">See also</span></span>

- [<span data-ttu-id="0b943-172">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="0b943-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
