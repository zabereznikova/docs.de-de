---
title: CreateInstanceEnumWmi-Funktion (Referenz zur nicht verwalteten API)
description: Die CreateInstanceEnumWmi-Funktion gibt einen Enumerator, mit der Instanzen einer bestimmten Klasse, die Volltextauswahlkriterien erfüllen zurück.
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
ms.openlocfilehash: 8a1d082cae19bd83c90e063d841a0c9e4602bc40
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373048"
---
# <a name="createinstanceenumwmi-function"></a><span data-ttu-id="d22e1-103">CreateInstanceEnumWmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="d22e1-103">CreateInstanceEnumWmi function</span></span>

<span data-ttu-id="d22e1-104">Gibt einen Enumerator, der die Instanzen einer bestimmten Klasse zurückgibt, die angegebenen Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="d22e1-104">Returns an enumerator that returns the instances of a specified class that meet specified selection criteria.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="d22e1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d22e1-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="d22e1-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d22e1-106">Parameters</span></span>

`strFilter`\
<span data-ttu-id="d22e1-107">[in] Der Name der Klasse, für die Instanzen gewünscht werden.</span><span class="sxs-lookup"><span data-stu-id="d22e1-107">[in] The name of the class for which instances are desired.</span></span> <span data-ttu-id="d22e1-108">Dieser Parameter darf nicht sein `null`.</span><span class="sxs-lookup"><span data-stu-id="d22e1-108">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="d22e1-109">[in] Eine Kombination von Flags, die das Verhalten dieser Funktion zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="d22e1-109">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="d22e1-110">Die folgenden Werte werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="d22e1-110">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d22e1-111">Konstante</span><span class="sxs-lookup"><span data-stu-id="d22e1-111">Constant</span></span>  |<span data-ttu-id="d22e1-112">Wert</span><span class="sxs-lookup"><span data-stu-id="d22e1-112">Value</span></span>  |<span data-ttu-id="d22e1-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d22e1-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="d22e1-114">0x20000</span><span class="sxs-lookup"><span data-stu-id="d22e1-114">0x20000</span></span> | <span data-ttu-id="d22e1-115">Wenn festgelegt ist, die Funktion ruft ab, die ergänzende Qualifizierer, die in der lokalisierten Namespace des Gebietsschemas für die aktuelle Verbindung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d22e1-115">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="d22e1-116">Wenn dies nicht festgelegt ist, die Funktion ruft nur die Qualifizierer, die in der unmittelbaren Namespace gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d22e1-116">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="d22e1-117">0</span><span class="sxs-lookup"><span data-stu-id="d22e1-117">0</span></span> | <span data-ttu-id="d22e1-118">Die Enumeration enthält auch alle Unterklassen in der Hierarchie an.</span><span class="sxs-lookup"><span data-stu-id="d22e1-118">The enumeration includes this and all subclasses in the hierarchy.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="d22e1-119">1</span><span class="sxs-lookup"><span data-stu-id="d22e1-119">1</span></span> | <span data-ttu-id="d22e1-120">Die Enumeration enthält nur reine Instanzen dieser Klasse und schließt alle Instanzen von Unterklassen, die angeben von Eigenschaften, die in dieser Klasse nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="d22e1-120">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="d22e1-121">0x10</span><span class="sxs-lookup"><span data-stu-id="d22e1-121">0x10</span></span> | <span data-ttu-id="d22e1-122">Das Flag wird halbsynchron aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d22e1-122">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="d22e1-123">0x20</span><span class="sxs-lookup"><span data-stu-id="d22e1-123">0x20</span></span> | <span data-ttu-id="d22e1-124">Die Funktion gibt einen Enumerator vorwärts gerichtete.</span><span class="sxs-lookup"><span data-stu-id="d22e1-124">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="d22e1-125">In der Regel vorwärts-Enumeratoren sind schneller, und verwenden Sie weniger Arbeitsspeicher als konventionelle Enumeratoren, aber sie ermöglichen keine Aufrufe von [Klon](clone.md).</span><span class="sxs-lookup"><span data-stu-id="d22e1-125">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="d22e1-126">0</span><span class="sxs-lookup"><span data-stu-id="d22e1-126">0</span></span> | <span data-ttu-id="d22e1-127">WMI behält Zeiger auf Objekte in der Enumeration, bis sie freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d22e1-127">WMI retains pointers to objects in the enumeration until they are released.</span></span> |

<span data-ttu-id="d22e1-128">Die empfohlene Flags sind `WBEM_FLAG_RETURN_IMMEDIATELY` und `WBEM_FLAG_FORWARD_ONLY` für eine optimale Leistung.</span><span class="sxs-lookup"><span data-stu-id="d22e1-128">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="d22e1-129">[in] Dieser Wert in der Regel ist `null`.</span><span class="sxs-lookup"><span data-stu-id="d22e1-129">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="d22e1-130">Andernfalls wird ein Zeiger auf ein [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, die die angeforderten Instanzen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d22e1-130">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that may be used by the provider that is providing the requested instances.</span></span>

`ppEnum`\
<span data-ttu-id="d22e1-131">[out] Erhält der Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="d22e1-131">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`\
<span data-ttu-id="d22e1-132">[in] Die Autorisierungsebene.</span><span class="sxs-lookup"><span data-stu-id="d22e1-132">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="d22e1-133">[in] Die Ebene des Identitätswechsels.</span><span class="sxs-lookup"><span data-stu-id="d22e1-133">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="d22e1-134">[in] Ein Zeiger auf ein [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) -Objekt, das den aktuellen Namespace darstellt.</span><span class="sxs-lookup"><span data-stu-id="d22e1-134">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="d22e1-135">[in] Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="d22e1-135">[in] The user name.</span></span> <span data-ttu-id="d22e1-136">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="d22e1-136">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="d22e1-137">[in] Das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="d22e1-137">[in] The password.</span></span> <span data-ttu-id="d22e1-138">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="d22e1-138">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="d22e1-139">[in] Der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="d22e1-139">[in] The domain name of the user.</span></span> <span data-ttu-id="d22e1-140">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="d22e1-140">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="d22e1-141">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d22e1-141">Return value</span></span>

<span data-ttu-id="d22e1-142">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="d22e1-142">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d22e1-143">Konstante</span><span class="sxs-lookup"><span data-stu-id="d22e1-143">Constant</span></span>  |<span data-ttu-id="d22e1-144">Wert</span><span class="sxs-lookup"><span data-stu-id="d22e1-144">Value</span></span>  |<span data-ttu-id="d22e1-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d22e1-145">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="d22e1-146">0x80041003</span><span class="sxs-lookup"><span data-stu-id="d22e1-146">0x80041003</span></span> | <span data-ttu-id="d22e1-147">Der Benutzer keine Berechtigung zum Anzeigen von Instanzen der angegebenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="d22e1-147">The user does not have permission to view instances of the specified class.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="d22e1-148">0x80041001</span><span class="sxs-lookup"><span data-stu-id="d22e1-148">0x80041001</span></span> | <span data-ttu-id="d22e1-149">Ein Unbekannter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d22e1-149">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="d22e1-150">0x80041010</span><span class="sxs-lookup"><span data-stu-id="d22e1-150">0x80041010</span></span> | <span data-ttu-id="d22e1-151">`strFilter` existiert nicht.</span><span class="sxs-lookup"><span data-stu-id="d22e1-151">`strFilter` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d22e1-152">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d22e1-152">0x80041008</span></span> | <span data-ttu-id="d22e1-153">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="d22e1-153">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="d22e1-154">0x80041006</span><span class="sxs-lookup"><span data-stu-id="d22e1-154">0x80041006</span></span> | <span data-ttu-id="d22e1-155">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d22e1-155">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="d22e1-156">0x80041033</span><span class="sxs-lookup"><span data-stu-id="d22e1-156">0x80041033</span></span> | <span data-ttu-id="d22e1-157">WMI wurde wahrscheinlich beendet und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="d22e1-157">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="d22e1-158">Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus.</span><span class="sxs-lookup"><span data-stu-id="d22e1-158">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="d22e1-159">0x80041015</span><span class="sxs-lookup"><span data-stu-id="d22e1-159">0x80041015</span></span> | <span data-ttu-id="d22e1-160">Der Remoteprozeduraufruf-Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-hat Fehler.</span><span class="sxs-lookup"><span data-stu-id="d22e1-160">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d22e1-161">0</span><span class="sxs-lookup"><span data-stu-id="d22e1-161">0</span></span> | <span data-ttu-id="d22e1-162">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d22e1-162">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="d22e1-163">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d22e1-163">Remarks</span></span>

<span data-ttu-id="d22e1-164">Diese Funktion umschließt einen Aufruf der [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) Methode.</span><span class="sxs-lookup"><span data-stu-id="d22e1-164">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createinstanceenum) method.</span></span>

<span data-ttu-id="d22e1-165">Beachten Sie, dass der zurückgegebene Enumerator 0 (null) Elemente verfügen kann.</span><span class="sxs-lookup"><span data-stu-id="d22e1-165">Note that the returned enumerator can have zero elements.</span></span>

<span data-ttu-id="d22e1-166">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch den Aufruf der [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="d22e1-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="d22e1-167">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d22e1-167">Requirements</span></span>

<span data-ttu-id="d22e1-168">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d22e1-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d22e1-169">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d22e1-169">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="d22e1-170">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d22e1-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d22e1-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d22e1-171">See also</span></span>

- [<span data-ttu-id="d22e1-172">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="d22e1-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)