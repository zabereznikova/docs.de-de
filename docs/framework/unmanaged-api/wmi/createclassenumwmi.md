---
title: CreateClassEnumWmi-Funktion (Referenz zur nicht verwalteten API)
description: Die CreateClassEnumWmi-Funktion gibt einen Enumerator für alle Klassen, die bestimmte Kriterien erfüllen.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a4d2c2bd28640d0ac7124f8e0864e9e72fb1eb9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935628"
---
# <a name="createclassenumwmi-function"></a><span data-ttu-id="59617-103">CreateClassEnumWmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="59617-103">CreateClassEnumWmi function</span></span>
<span data-ttu-id="59617-104">Gibt einen Enumerator für alle Klassen zurück, die die angegebenen Auswahlkriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="59617-104">Returns an enumerator for all classes that satisfy the specified selection criteria.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="59617-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="59617-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="59617-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="59617-106">Parameters</span></span>

`strSuperclass`\
<span data-ttu-id="59617-107">[in] Wenn dies nicht der `null` oder leer ist, gibt den Namen einer übergeordneten Klasse; nur Unterklassen dieser Klasse Sie vom Enumerator zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="59617-107">[in] If not `null` or blank, specifies the name of a parent class; the enumerator returns only subclasses of this class.</span></span> <span data-ttu-id="59617-108">Ist dies `null` oder ein Leerzeichen und `lFlags` WBEM_FLAG_SHALLOW ist, wird nur auf oberster Ebene Klassen (keine übergeordnete Klasse).</span><span class="sxs-lookup"><span data-stu-id="59617-108">If it is `null` or blank and `lFlags` is WBEM_FLAG_SHALLOW, returns only top-level classes (classes with no parent class).</span></span> <span data-ttu-id="59617-109">Ist dies `null` oder ein Leerzeichen und `lFlags` ist `WBEM_FLAG_DEEP`, alle Klassen im Namespace zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="59617-109">If it is `null` or blank and `lFlags` is `WBEM_FLAG_DEEP`, returns all classes in the namespace.</span></span>

`lFlags`\
<span data-ttu-id="59617-110">[in] Eine Kombination von Flags, die das Verhalten dieser Funktion zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="59617-110">[in] A combination of flags that affect the behavior of this function.</span></span> <span data-ttu-id="59617-111">Die folgenden Werte werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="59617-111">The following values are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="59617-112">Konstante</span><span class="sxs-lookup"><span data-stu-id="59617-112">Constant</span></span>  |<span data-ttu-id="59617-113">Wert</span><span class="sxs-lookup"><span data-stu-id="59617-113">Value</span></span>  |<span data-ttu-id="59617-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59617-114">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | <span data-ttu-id="59617-115">0x20000</span><span class="sxs-lookup"><span data-stu-id="59617-115">0x20000</span></span> | <span data-ttu-id="59617-116">Wenn festgelegt ist, die Funktion ruft ab, die ergänzende Qualifizierer, die in der lokalisierten Namespace des Gebietsschemas für die aktuelle Verbindung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="59617-116">If set, the function retrieves the amended qualifiers stored in the localized namespace of the current connection's locale.</span></span> <br/> <span data-ttu-id="59617-117">Wenn dies nicht festgelegt ist, die Funktion ruft nur die Qualifizierer, die in der unmittelbaren Namespace gespeichert.</span><span class="sxs-lookup"><span data-stu-id="59617-117">If not set, the function retrieves only the qualifiers stored in the immediate namespace.</span></span> |
| `WBEM_FLAG_DEEP` | <span data-ttu-id="59617-118">0</span><span class="sxs-lookup"><span data-stu-id="59617-118">0</span></span> | <span data-ttu-id="59617-119">Die Enumeration enthält alle Unterklassen in der Hierarchie, aber nicht von dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="59617-119">The enumeration includes all subclasses in the hierarchy, but not this class.</span></span> |
| `WBEM_FLAG_SHALLOW` | <span data-ttu-id="59617-120">1</span><span class="sxs-lookup"><span data-stu-id="59617-120">1</span></span> | <span data-ttu-id="59617-121">Die Enumeration enthält nur reine Instanzen dieser Klasse und schließt alle Instanzen von Unterklassen, die angeben von Eigenschaften, die in dieser Klasse nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="59617-121">The enumeration includes only pure instances of this class and excludes all instances of subclasses that supply properties not found in this class.</span></span> |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | <span data-ttu-id="59617-122">0x10</span><span class="sxs-lookup"><span data-stu-id="59617-122">0x10</span></span> | <span data-ttu-id="59617-123">Das Flag wird halbsynchron aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="59617-123">The flag causes a semisynchronous call.</span></span> |
| `WBEM_FLAG_FORWARD_ONLY` | <span data-ttu-id="59617-124">0x20</span><span class="sxs-lookup"><span data-stu-id="59617-124">0x20</span></span> | <span data-ttu-id="59617-125">Die Funktion gibt einen Enumerator vorwärts gerichtete.</span><span class="sxs-lookup"><span data-stu-id="59617-125">The function returns a forward-only enumerator.</span></span> <span data-ttu-id="59617-126">In der Regel vorwärts-Enumeratoren sind schneller, und verwenden Sie weniger Arbeitsspeicher als konventionelle Enumeratoren, aber sie ermöglichen keine Aufrufe von [Klon](clone.md).</span><span class="sxs-lookup"><span data-stu-id="59617-126">Typically, forward-only enumerators are faster and use less memory than conventional enumerators, but they do not allow calls to [Clone](clone.md).</span></span> |
| `WBEM_FLAG_BIDIRECTIONAL` | <span data-ttu-id="59617-127">0</span><span class="sxs-lookup"><span data-stu-id="59617-127">0</span></span> | <span data-ttu-id="59617-128">WMI behält Zeiger auf Objekte in der Enumeration, bis sie freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="59617-128">WMI retains pointers to objects in the enumeration until they are released.</span></span> |

<span data-ttu-id="59617-129">Die empfohlene Flags sind `WBEM_FLAG_RETURN_IMMEDIATELY` und `WBEM_FLAG_FORWARD_ONLY` für eine optimale Leistung.</span><span class="sxs-lookup"><span data-stu-id="59617-129">The recommended flags are `WBEM_FLAG_RETURN_IMMEDIATELY` and `WBEM_FLAG_FORWARD_ONLY` for best performance.</span></span>

`pCtx`\
<span data-ttu-id="59617-130">[in] Dieser Wert in der Regel ist `null`.</span><span class="sxs-lookup"><span data-stu-id="59617-130">[in] Typically, this value is `null`.</span></span> <span data-ttu-id="59617-131">Andernfalls wird ein Zeiger auf ein [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Instanz, die vom Anbieter verwendet werden kann, die die angeforderten Klassen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="59617-131">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) instance that can be used by the provider that is providing the requested classes.</span></span>

`ppEnum`\
<span data-ttu-id="59617-132">[out] Erhält der Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="59617-132">[out] Receives the pointer to the enumerator.</span></span>

`authLevel`\
<span data-ttu-id="59617-133">[in] Die Autorisierungsebene.</span><span class="sxs-lookup"><span data-stu-id="59617-133">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="59617-134">[in] Die Ebene des Identitätswechsels.</span><span class="sxs-lookup"><span data-stu-id="59617-134">[in] The impersonation level.</span></span>

`pCurrentNamespace`\
<span data-ttu-id="59617-135">[in] Ein Zeiger auf ein [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) -Objekt, das den aktuellen Namespace darstellt.</span><span class="sxs-lookup"><span data-stu-id="59617-135">[in] A pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object that represents the current namespace.</span></span>

`strUser`\
<span data-ttu-id="59617-136">[in] Der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="59617-136">[in] The user name.</span></span> <span data-ttu-id="59617-137">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="59617-137">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="59617-138">[in] Das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="59617-138">[in] The password.</span></span> <span data-ttu-id="59617-139">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="59617-139">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="59617-140">[in] Der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="59617-140">[in] The domain name of the user.</span></span> <span data-ttu-id="59617-141">Finden Sie unter den [ConnectServerWmi](connectserverwmi.md) -Funktion für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="59617-141">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="59617-142">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="59617-142">Return value</span></span>

<span data-ttu-id="59617-143">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="59617-143">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="59617-144">Konstante</span><span class="sxs-lookup"><span data-stu-id="59617-144">Constant</span></span>  |<span data-ttu-id="59617-145">Wert</span><span class="sxs-lookup"><span data-stu-id="59617-145">Value</span></span>  |<span data-ttu-id="59617-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59617-146">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | <span data-ttu-id="59617-147">0x80041003</span><span class="sxs-lookup"><span data-stu-id="59617-147">0x80041003</span></span> | <span data-ttu-id="59617-148">Der Benutzer keine Berechtigung zum Anzeigen, eine oder mehrere Klassen, die die Funktion zurückgeben kann.</span><span class="sxs-lookup"><span data-stu-id="59617-148">The user does not have permission to view one or more of the classes that the function can return.</span></span> |
| `WBEM_E_FAILED` | <span data-ttu-id="59617-149">0x80041001</span><span class="sxs-lookup"><span data-stu-id="59617-149">0x80041001</span></span> | <span data-ttu-id="59617-150">Ein Unbekannter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="59617-150">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_CLASS` | <span data-ttu-id="59617-151">0x80041010</span><span class="sxs-lookup"><span data-stu-id="59617-151">0x80041010</span></span> | <span data-ttu-id="59617-152">`strSuperClass` existiert nicht.</span><span class="sxs-lookup"><span data-stu-id="59617-152">`strSuperClass` does not exist.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="59617-153">0x80041008</span><span class="sxs-lookup"><span data-stu-id="59617-153">0x80041008</span></span> | <span data-ttu-id="59617-154">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="59617-154">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="59617-155">0x80041006</span><span class="sxs-lookup"><span data-stu-id="59617-155">0x80041006</span></span> | <span data-ttu-id="59617-156">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="59617-156">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_SHUTTING_DOWN` | <span data-ttu-id="59617-157">0x80041033</span><span class="sxs-lookup"><span data-stu-id="59617-157">0x80041033</span></span> | <span data-ttu-id="59617-158">WMI wurde wahrscheinlich beendet und neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="59617-158">WMI was probably stopped and restarting.</span></span> <span data-ttu-id="59617-159">Rufen Sie [ConnectServerWmi](connectserverwmi.md) erneut aus.</span><span class="sxs-lookup"><span data-stu-id="59617-159">Call [ConnectServerWmi](connectserverwmi.md) again.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="59617-160">0x80041015</span><span class="sxs-lookup"><span data-stu-id="59617-160">0x80041015</span></span> | <span data-ttu-id="59617-161">Der Remoteprozeduraufruf-Remoteprozeduraufruf (RPC)-Link zwischen dem aktuellen Prozess und die WMI-hat Fehler.</span><span class="sxs-lookup"><span data-stu-id="59617-161">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="59617-162">0</span><span class="sxs-lookup"><span data-stu-id="59617-162">0</span></span> | <span data-ttu-id="59617-163">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="59617-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="59617-164">Hinweise</span><span class="sxs-lookup"><span data-stu-id="59617-164">Remarks</span></span>

<span data-ttu-id="59617-165">Diese Funktion umschließt einen Aufruf der [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) Methode.</span><span class="sxs-lookup"><span data-stu-id="59617-165">This function wraps a call to the [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) method.</span></span>

<span data-ttu-id="59617-166">Wenn der Funktionsaufruf fehlschlägt, können Sie zusätzliche Fehlerinformationen abrufen, durch den Aufruf der [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="59617-166">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="59617-167">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="59617-167">Requirements</span></span>

<span data-ttu-id="59617-168">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59617-168">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="59617-169">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="59617-169">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="59617-170">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="59617-170">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="59617-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59617-171">See also</span></span>

- [<span data-ttu-id="59617-172">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="59617-172">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)