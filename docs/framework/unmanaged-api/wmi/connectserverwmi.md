---
title: ConnectServerWmi-Funktion (Referenz zur nicht verwalteten API)
description: "Die Funktion ConnectServerWmi verwendet DCOM für die um eine Verbindung mit einem WMI-Namespace zu erstellen."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: ConnectServerWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: ConnectServerWmi
helpviewer_keywords: ConnectServerWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dc821bddf1d33ea1144fef0821b81cf027d8f92f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="4e3af-103">ConnectServerWmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="4e3af-103">ConnectServerWmi function</span></span>
<span data-ttu-id="4e3af-104">Erstellt eine Verbindung über DCOM mit einem WMI-Namespace auf einem angegebenen Computer an.</span><span class="sxs-lookup"><span data-stu-id="4e3af-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="4e3af-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e3af-105">Syntax</span></span>  
  
```  
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
## <a name="parameters"></a><span data-ttu-id="4e3af-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e3af-106">Parameters</span></span>

<span data-ttu-id="4e3af-107">`strNetworkResource`[in] Zeiger auf eine gültige `BSTR` , den richtigen Namespace des WMI-Objektpfad enthält.</span><span class="sxs-lookup"><span data-stu-id="4e3af-107">`strNetworkResource` [in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="4e3af-108">Finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="4e3af-108">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="4e3af-109">`strUser`[in] Ein Zeiger auf eine gültige `BSTR` , die den Benutzernamen enthält.</span><span class="sxs-lookup"><span data-stu-id="4e3af-109">`strUser` [in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="4e3af-110">Ein `null` Wert gibt an, den aktuellen Sicherheitskontext.</span><span class="sxs-lookup"><span data-stu-id="4e3af-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="4e3af-111">Wenn der Benutzer aus einer anderen Domäne als der aktuelle `strUser` kann auch die Domänen- und Benutzernamen Namen getrennt durch einen umgekehrten Schrägstrich enthalten.</span><span class="sxs-lookup"><span data-stu-id="4e3af-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> <span data-ttu-id="4e3af-112">`strUser`kann auch werden Benutzer Benutzerprinzipalnamen (UPN) formatieren im Suhc als  *userName@domainName* .</span><span class="sxs-lookup"><span data-stu-id="4e3af-112">`strUser` can also be in user principal name (UPN) format, suhc as *userName@domainName*.</span></span> <span data-ttu-id="4e3af-113">Finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="4e3af-113">See the [Remarks](#remarks) section for more information.</span></span>

<span data-ttu-id="4e3af-114">`strPassword`[in] Ein Zeiger auf eine gültige `BSTR` , der Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="4e3af-114">`strPassword` [in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="4e3af-115">Ein `null` gibt den aktuellen Sicherheitskontext an.</span><span class="sxs-lookup"><span data-stu-id="4e3af-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="4e3af-116">Eine leere Zeichenfolge ("") gibt ein gültiges Kennwort für die Länge 0 (null) an.</span><span class="sxs-lookup"><span data-stu-id="4e3af-116">An empty string ("") indicates a valid zero-length password.</span></span>

<span data-ttu-id="4e3af-117">`strLocale`[in] Ein Zeiger auf eine gültige `BSTR` , der das richtige Gebietsschema für den Abruf von Informationen angibt.</span><span class="sxs-lookup"><span data-stu-id="4e3af-117">`strLocale` [in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="4e3af-118">Für Microsoft-Gebietsschemabezeichner, ist das Format der Zeichenfolge "MS\_*Xxx*", wobei *Xxx* ist eine Zeichenfolge in hexadezimaler Form, der den Gebietsschemabezeichner (LCID) angibt.</span><span class="sxs-lookup"><span data-stu-id="4e3af-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="4e3af-119">Wenn ein ungültiges Gebietsschema angegeben wird, gibt die Methode `WBEM_E_INVALID_PARAMETER` außer auf Windows 7, in dem das Standardgebietsschema des Servers verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e3af-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="4e3af-120">Wenn "null1, das aktuelle Gebietsschema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4e3af-120">If \`null1, the current locale is used.</span></span> 
 
<span data-ttu-id="4e3af-121">`lSecurityFlags`[in] Flags für die Übergabe an die `ConnectServerWmi` Methode.</span><span class="sxs-lookup"><span data-stu-id="4e3af-121">`lSecurityFlags` [in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="4e3af-122">Der Wert 0 (null) für diesen Parameter im Aufruf führt `ConnectServerWmi` zurückgeben, nachdem eine Verbindung mit dem Server hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4e3af-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="4e3af-123">Dies kann führen in einer Anwendung nicht unbegrenzt reagiert, wenn der Server unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="4e3af-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="4e3af-124">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="4e3af-124">The other valid values are:</span></span>

| <span data-ttu-id="4e3af-125">Konstante</span><span class="sxs-lookup"><span data-stu-id="4e3af-125">Constant</span></span>  | <span data-ttu-id="4e3af-126">Wert</span><span class="sxs-lookup"><span data-stu-id="4e3af-126">Value</span></span>  | <span data-ttu-id="4e3af-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e3af-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="4e3af-128">0 x 40</span><span class="sxs-lookup"><span data-stu-id="4e3af-128">0x40</span></span> | <span data-ttu-id="4e3af-129">Für die interne Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="4e3af-129">Reserved for internal use.</span></span> <span data-ttu-id="4e3af-130">Nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e3af-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="4e3af-131">0 x 80</span><span class="sxs-lookup"><span data-stu-id="4e3af-131">0x80</span></span> | <span data-ttu-id="4e3af-132">`ConnectServerWmi`Gibt innerhalb von zwei Minuten oder weniger.</span><span class="sxs-lookup"><span data-stu-id="4e3af-132">`ConnectServerWmi` returns in two minutes or less.</span></span> |

<span data-ttu-id="4e3af-133">`strAuthority`[in] Der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="4e3af-133">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="4e3af-134">Sie können die folgenden Werte aufweisen:</span><span class="sxs-lookup"><span data-stu-id="4e3af-134">It can have the following values:</span></span>

| <span data-ttu-id="4e3af-135">Wert</span><span class="sxs-lookup"><span data-stu-id="4e3af-135">Value</span></span> | <span data-ttu-id="4e3af-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e3af-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="4e3af-137">leer</span><span class="sxs-lookup"><span data-stu-id="4e3af-137">blank</span></span> | <span data-ttu-id="4e3af-138">NTLM-Authentifizierung verwendet wird, und die NTLM-Domäne des aktuellen Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e3af-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="4e3af-139">Wenn `strUser` gibt die Domäne (als empfohlenen Speicherort) darf nicht hier angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4e3af-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="4e3af-140">Die Funktion gibt `WBEM_E_INVALID_PARAMETER` Wenn Sie die Domäne in beide Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="4e3af-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="4e3af-141">Kerberos:*Prinzipalname*</span><span class="sxs-lookup"><span data-stu-id="4e3af-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="4e3af-142">Kerberos-Authentifizierung wird verwendet, und dieser Parameter enthält einen Kerberos-Prinzipalname.</span><span class="sxs-lookup"><span data-stu-id="4e3af-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="4e3af-143">NTLMDOMAIN:*Domänennamen*</span><span class="sxs-lookup"><span data-stu-id="4e3af-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="4e3af-144">NT LAN Manager-Authentifizierung wird verwendet, und dieser Parameter enthält einen NTLM-Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="4e3af-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`   
<span data-ttu-id="4e3af-145">[in] In der Regel ist dieser Parameter ist `null`.</span><span class="sxs-lookup"><span data-stu-id="4e3af-145">[in] Typically, this parameter is is `null`.</span></span> <span data-ttu-id="4e3af-146">Andernfalls ist ein Zeiger auf ein ["IWbemContext"](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx) Objekt, das durch einen oder mehrere dynamische Klasse Anbieter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4e3af-146">Otherwise, it is a pointer to an [IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx) object required by one or more dynamic class providers.</span></span> 

`ppNamespace`  
<span data-ttu-id="4e3af-147">[out] Wenn die Funktion zurückgibt, erhält einen Zeiger auf eine [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) Objekt an den angegebenen Namespace gebunden.</span><span class="sxs-lookup"><span data-stu-id="4e3af-147">[out] When the function returns, receives a pointer to an [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) object bound to the specified namespace.</span></span> <span data-ttu-id="4e3af-148">Es wird festgelegt, auf `null` , wenn ein Fehler vorliegt.</span><span class="sxs-lookup"><span data-stu-id="4e3af-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`  
<span data-ttu-id="4e3af-149">[in] Die Ebene des Identitätswechsels.</span><span class="sxs-lookup"><span data-stu-id="4e3af-149">[in] The impersonation level.</span></span>

`authLevel`  
<span data-ttu-id="4e3af-150">[in] Die Autorisierungsebene.</span><span class="sxs-lookup"><span data-stu-id="4e3af-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="4e3af-151">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4e3af-151">Return value</span></span>

<span data-ttu-id="4e3af-152">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, oder Sie können diese definieren als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="4e3af-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4e3af-153">Konstante</span><span class="sxs-lookup"><span data-stu-id="4e3af-153">Constant</span></span>  |<span data-ttu-id="4e3af-154">Wert</span><span class="sxs-lookup"><span data-stu-id="4e3af-154">Value</span></span>  |<span data-ttu-id="4e3af-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e3af-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="4e3af-156">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="4e3af-156">0x80041001</span></span> | <span data-ttu-id="4e3af-157">Ein allgemeiner Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4e3af-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4e3af-158">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="4e3af-158">0x80041008</span></span> | <span data-ttu-id="4e3af-159">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="4e3af-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4e3af-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4e3af-160">0x80041006</span></span> | <span data-ttu-id="4e3af-161">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4e3af-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="4e3af-162">0</span><span class="sxs-lookup"><span data-stu-id="4e3af-162">0</span></span> | <span data-ttu-id="4e3af-163">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="4e3af-163">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4e3af-164">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e3af-164">Remarks</span></span>

<span data-ttu-id="4e3af-165">Diese Funktion dient als Wrapper für einen Aufruf der [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) Methode.</span><span class="sxs-lookup"><span data-stu-id="4e3af-165">This function wraps a call to the [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) method.</span></span>

 <span data-ttu-id="4e3af-166">Für den lokalen Zugriff auf den Standardnamespace `strNetworkResource` ein einfaches Objekt-Pfad: "Root\default" oder "\\.\root\default".</span><span class="sxs-lookup"><span data-stu-id="4e3af-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="4e3af-167">Für den Zugriff auf die Standard-Namespace auf einem Remotecomputer von COM- oder Microsoft-kompatiblen-Netzwerken, den Computernamen enthalten: "\\Myserver\root\default".</span><span class="sxs-lookup"><span data-stu-id="4e3af-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="4e3af-168">Der Computername kann auch einen DNS-Namen oder die IP-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="4e3af-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="4e3af-169">Die `ConnectServerWmi` Funktion kann auch mit IPv6-Computern eine Verbindung mit einer IPv6-Adresse.</span><span class="sxs-lookup"><span data-stu-id="4e3af-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

<span data-ttu-id="4e3af-170">`strUser`eine leere Zeichenfolge darf nicht sein.</span><span class="sxs-lookup"><span data-stu-id="4e3af-170">`strUser` cannot be an empty string.</span></span> <span data-ttu-id="4e3af-171">Wenn in die Domäne angegeben ist `strAuthority`, er darf nicht auch einbezogen werden `strUser`, oder die Funktion gibt `WBEM_E_INVALID_PARAMETER`.</span><span class="sxs-lookup"><span data-stu-id="4e3af-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>


## <a name="requirements"></a><span data-ttu-id="4e3af-172">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e3af-172">Requirements</span></span>  
 <span data-ttu-id="4e3af-173">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e3af-173">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e3af-174">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4e3af-174">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4e3af-175">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4e3af-175">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e3af-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e3af-176">See also</span></span>  
[<span data-ttu-id="4e3af-177">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="4e3af-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
