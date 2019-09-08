---
title: Connectserverwmi-Funktion (Referenz zur nicht verwalteten API)
description: Die connectserverwmi-Funktion verwendet DCOM, um eine Verbindung mit einem WMI-Namespace herzustellen.
ms.date: 11/06/2017
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ebb268dcee877f4e9aea0c88852333897030dd1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798756"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="21546-103">Connectserverwmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="21546-103">ConnectServerWmi function</span></span>

<span data-ttu-id="21546-104">Erstellt über DCOM eine Verbindung mit einem WMI-Namespace auf einem angegebenen Computer.</span><span class="sxs-lookup"><span data-stu-id="21546-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="21546-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="21546-105">Syntax</span></span>

```cpp
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel,
   [in] DWORD              authLevel
);
```

## <a name="parameters"></a><span data-ttu-id="21546-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="21546-106">Parameters</span></span>

`strNetworkResource`\
<span data-ttu-id="21546-107">in Zeiger auf ein gültiges `BSTR` -Objekt, das den Objekt Pfad des korrekten WMI-Namespace enthält.</span><span class="sxs-lookup"><span data-stu-id="21546-107">[in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="21546-108">Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="21546-108">See the [Remarks](#remarks) section for more information.</span></span>

`strUser`\
<span data-ttu-id="21546-109">in Ein Zeiger auf einen gültigen `BSTR` , der den Benutzernamen enthält.</span><span class="sxs-lookup"><span data-stu-id="21546-109">[in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="21546-110">Ein `null` -Wert gibt den aktuellen Sicherheitskontext an.</span><span class="sxs-lookup"><span data-stu-id="21546-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="21546-111">Wenn der Benutzer aus einer anderen Domäne als die aktuelle Domäne gehört, `strUser` kann auch die Domäne und den Benutzernamen durch einen umgekehrten Schrägstrich getrennt enthalten.</span><span class="sxs-lookup"><span data-stu-id="21546-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="21546-112">`strUser`kann auch im UPN-Format (User Principal Name) vorliegen, z `userName@domainName`. b.</span><span class="sxs-lookup"><span data-stu-id="21546-112">`strUser` can also be in user principal name (UPN) format, such as `userName@domainName`.</span></span> <span data-ttu-id="21546-113">Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ".</span><span class="sxs-lookup"><span data-stu-id="21546-113">See the [Remarks](#remarks) section for more information.</span></span>

`strPassword`\
<span data-ttu-id="21546-114">in Ein Zeiger auf einen gültigen `BSTR` , der das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="21546-114">[in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="21546-115">`null` Gibt den aktuellen Sicherheitskontext an.</span><span class="sxs-lookup"><span data-stu-id="21546-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="21546-116">Eine leere Zeichenfolge ("") gibt ein gültiges Kennwort der Länge 0 (null) an.</span><span class="sxs-lookup"><span data-stu-id="21546-116">An empty string ("") indicates a valid zero-length password.</span></span>

`strLocale`\
<span data-ttu-id="21546-117">in Ein Zeiger auf einen gültigen `BSTR` , der das richtige Gebiets Schema für den Informations Abruf angibt.</span><span class="sxs-lookup"><span data-stu-id="21546-117">[in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="21546-118">Bei Microsoft-Gebiets Schema Bezeichnern ist das Format der Zeichenfolge "\_MS*xxx*", wobei *xxx* eine Zeichenfolge in Hexadezimal Form ist, die den Gebiets Schema Bezeichner (LCID) angibt.</span><span class="sxs-lookup"><span data-stu-id="21546-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="21546-119">Wenn ein ungültiges Gebiets Schema angegeben wird, gibt `WBEM_E_INVALID_PARAMETER` die Methode zurück, mit Ausnahme von Windows 7, wobei stattdessen das Standard Gebiets Schema des Servers verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="21546-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="21546-120">Wenn "NULL1", wird das aktuelle Gebiets Schema verwendet.</span><span class="sxs-lookup"><span data-stu-id="21546-120">If \`null1, the current locale is used.</span></span>

`lSecurityFlags`\
<span data-ttu-id="21546-121">in Flags, die an die `ConnectServerWmi` Methode übergeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="21546-121">[in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="21546-122">Der Wert 0 (null) für diesen Parameter führt dazu, dass nur dann `ConnectServerWmi` zurückgegeben wird, nachdem eine Verbindung mit dem Server hergestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="21546-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="21546-123">Dies könnte dazu führen, dass eine Anwendung nicht unbegrenzt reagiert, wenn der Server beschädigt ist.</span><span class="sxs-lookup"><span data-stu-id="21546-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="21546-124">Die anderen gültigen Werte lauten:</span><span class="sxs-lookup"><span data-stu-id="21546-124">The other valid values are:</span></span>

| <span data-ttu-id="21546-125">Konstante</span><span class="sxs-lookup"><span data-stu-id="21546-125">Constant</span></span>  | <span data-ttu-id="21546-126">Wert</span><span class="sxs-lookup"><span data-stu-id="21546-126">Value</span></span>  | <span data-ttu-id="21546-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21546-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="21546-128">0x40</span><span class="sxs-lookup"><span data-stu-id="21546-128">0x40</span></span> | <span data-ttu-id="21546-129">Für die interne Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="21546-129">Reserved for internal use.</span></span> <span data-ttu-id="21546-130">Nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="21546-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="21546-131">0x80</span><span class="sxs-lookup"><span data-stu-id="21546-131">0x80</span></span> | <span data-ttu-id="21546-132">`ConnectServerWmi`gibt zwei Minuten oder weniger zurück.</span><span class="sxs-lookup"><span data-stu-id="21546-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

`strAuthority`\
<span data-ttu-id="21546-133">in Der Domänen Name des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="21546-133">[in] The domain name of the user.</span></span> <span data-ttu-id="21546-134">Die folgenden Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="21546-134">It can have the following values:</span></span>

| <span data-ttu-id="21546-135">Wert</span><span class="sxs-lookup"><span data-stu-id="21546-135">Value</span></span> | <span data-ttu-id="21546-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21546-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="21546-137">leer</span><span class="sxs-lookup"><span data-stu-id="21546-137">blank</span></span> | <span data-ttu-id="21546-138">Die NTLM-Authentifizierung wird verwendet, und die NTLM-Domäne des aktuellen Benutzers wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="21546-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="21546-139">Wenn `strUser` die Domäne angibt (der empfohlene Speicherort), darf Sie hier nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="21546-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="21546-140">Die Funktion gibt `WBEM_E_INVALID_PARAMETER` zurück, wenn Sie die Domäne in beiden Parametern angeben.</span><span class="sxs-lookup"><span data-stu-id="21546-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="21546-141">Kerberos:*Prinzipal Name*</span><span class="sxs-lookup"><span data-stu-id="21546-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="21546-142">Die Kerberos-Authentifizierung wird verwendet, und dieser Parameter enthält einen Kerberos-Prinzipal Namen.</span><span class="sxs-lookup"><span data-stu-id="21546-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="21546-143">Ntlmdomain:*Domänen Name*</span><span class="sxs-lookup"><span data-stu-id="21546-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="21546-144">Die NT-LAN-Manager-Authentifizierung wird verwendet, und dieser Parameter enthält einen NTLM-Domänen Namen.</span><span class="sxs-lookup"><span data-stu-id="21546-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`\
<span data-ttu-id="21546-145">in Normalerweise ist `null`dieser Parameter.</span><span class="sxs-lookup"><span data-stu-id="21546-145">[in] Typically, this parameter is `null`.</span></span> <span data-ttu-id="21546-146">Andernfalls handelt es sich um einen Zeiger auf ein [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) -Objekt, das von einem oder mehreren dynamischen Klassen Anbietern benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="21546-146">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) object required by one or more dynamic class providers.</span></span>

`ppNamespace`\
<span data-ttu-id="21546-147">vorgenommen Wenn die Funktion zurückgibt, empfängt einen Zeiger auf ein [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) -Objekt, das an den angegebenen Namespace gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="21546-147">[out] When the function returns, receives a pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object bound to the specified namespace.</span></span> <span data-ttu-id="21546-148">`null` Wenn ein Fehler vorliegt, wird festgelegt, dass auf den Wert verweist.</span><span class="sxs-lookup"><span data-stu-id="21546-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`\
<span data-ttu-id="21546-149">in Die Ebene des Identitäts Wechsels.</span><span class="sxs-lookup"><span data-stu-id="21546-149">[in] The impersonation level.</span></span>

`authLevel`\
<span data-ttu-id="21546-150">in Die Autorisierungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="21546-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="21546-151">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="21546-151">Return value</span></span>

<span data-ttu-id="21546-152">Die folgenden Werte, die von dieser Funktion zurückgegeben werden, sind in der *wbemcli. h* -Header Datei definiert, oder Sie können Sie als Konstanten im Code definieren:</span><span class="sxs-lookup"><span data-stu-id="21546-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="21546-153">Konstante</span><span class="sxs-lookup"><span data-stu-id="21546-153">Constant</span></span>  |<span data-ttu-id="21546-154">Wert</span><span class="sxs-lookup"><span data-stu-id="21546-154">Value</span></span>  |<span data-ttu-id="21546-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21546-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="21546-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="21546-156">0x80041001</span></span> | <span data-ttu-id="21546-157">Es ist ein allgemeiner Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="21546-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="21546-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="21546-158">0x80041008</span></span> | <span data-ttu-id="21546-159">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="21546-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="21546-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="21546-160">0x80041006</span></span> | <span data-ttu-id="21546-161">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="21546-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="21546-162">0</span><span class="sxs-lookup"><span data-stu-id="21546-162">0</span></span> | <span data-ttu-id="21546-163">Der Funktions Aufrufvorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="21546-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="21546-164">Hinweise</span><span class="sxs-lookup"><span data-stu-id="21546-164">Remarks</span></span>

<span data-ttu-id="21546-165">Diese Funktion umschließt einen Rückruf für die [IWBEMLocator:: ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) -Methode.</span><span class="sxs-lookup"><span data-stu-id="21546-165">This function wraps a call to the [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) method.</span></span>

<span data-ttu-id="21546-166">Für den lokalen Zugriff auf den Standard Namespace `strNetworkResource` kann ein einfacher Objekt Pfad sein: "root\default" oder "\\.\root\default".</span><span class="sxs-lookup"><span data-stu-id="21546-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="21546-167">Für den Zugriff auf den Standard Namespace auf einem Remote Computer mit com oder Microsoft-kompatiblem Netzwerk verwenden Sie den Computer\\Namen: "myserver\root\default".</span><span class="sxs-lookup"><span data-stu-id="21546-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="21546-168">Der Computername kann auch ein DNS-Name oder eine IP-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="21546-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="21546-169">Die `ConnectServerWmi` Funktion kann auch mit IPv6-Adressen eine Verbindung mit Computern herstellen, auf denen IPv6 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="21546-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="21546-170">`strUser`darf keine leere Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="21546-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="21546-171">Wenn die Domäne in `strAuthority`angegeben ist, darf Sie nicht auch in `strUser`enthalten sein, oder die Funktion gibt `WBEM_E_INVALID_PARAMETER`zurück.</span><span class="sxs-lookup"><span data-stu-id="21546-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>

## <a name="requirements"></a><span data-ttu-id="21546-172">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="21546-172">Requirements</span></span>

 <span data-ttu-id="21546-173">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21546-173">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="21546-174">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="21546-174">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="21546-175">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="21546-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="21546-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21546-176">See also</span></span>

- [<span data-ttu-id="21546-177">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="21546-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
