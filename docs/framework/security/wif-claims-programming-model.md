---
title: WIF-Claims-Programmiermodell
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 149cb875-9b1c-4695-b88a-fbf1725a02f9
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 6d7059c5209dc95ce68f28e0f32db929e7c97271
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="wif-claims-programming-model"></a>WIF-Claims-Programmiermodell
Entwickler von ASP.NET und Windows Communication Foundation (WCF) verwenden normalerweise die IIdentity- und IPrincipal-Schnittstellen zum Arbeiten mit Identitätsinformationen des Benutzers. Windows Identity Foundation (WIF) wurde in .NET 4.5 integriert, sodass Ansprüche jetzt immer für jeden Prinzipal vorhanden sind, wie in der folgenden Abbildung dargestellt:  
  
 ![WIF-Claims-Programmiermodell](../../../docs/framework/security/media/wifclaimsprogrammingmodel.png "WIFClaimsProgrammingModel")  
  
 In .NET 4.5 enthält System.Security.Claims die neuen Klassen ClaimsPrincipal und ClaimsIdentity (siehe Abbildung oben). Alle Prinzipale in .NET werden nun von ClaimsPrincipal abgeleitet. Alle integrierten Identitätsklassen, z.B. FormsIdentity für ASP.NET und WindowsIdentity werden jetzt aus ClaimsIdentity abgeleitet. Auf ähnliche Weise werden alle integrierten Prinzipalklassen wie GenericPrincipal und WindowsPrincipal aus ClaimsPrincipal abgeleitet.  
  
 Ein Anspruch wird von der <xref:System.Security.Claims.Claim>-Klasse dargestellt. Diese Klasse hat die folgenden Eigenschaften:  
  
-   <xref:System.Security.Claims.Claim.Type%2A> stellt den Typ des Anspruchs dar und ist in der Regel ein URI. Der Anspruch der E-Mailadresse wird z.B. als `http://schemas.microsoft.com/ws/2008/06/identity/claims/email` dargestellt.  
  
-   <xref:System.Security.Claims.Claim.Value%2A> enthält den Wert des Anspruchs und wird als Zeichenfolge dargestellt. Der Anspruch der E-Mailadresse kann z.B. als „someone@contoso.com“ dargestellt werden.  
  
-   <xref:System.Security.Claims.Claim.ValueType%2A> stellt den Typ des Anspruchswerts dar und ist in der Regel ein URI. Der Zeichenfolgentyp wird z.B. durch `http://www.w3.org/2001/XMLSchema#string` dargestellt. Gemäß dem XML-Schema muss der Werttyp ein QName sein. Der Wert muss im Format `namespace#format` vorhanden sein, um WIF zur Ausgabe eines gültigen QName-Werts zu aktivieren. Ist der Namespace kein klar definierter Namespace, kann die generierte XML-Datei möglicherweise nicht vom Schema überprüft werden, da keine veröffentlichte XSD-Datei für diesen Namespace vorhanden sein wird. Der Standardwert ist `http://www.w3.org/2001/XMLSchema#string`. Weitere Informationen zu bekannten Werttypen, die Sie sicher verwenden können, finden Sie unter [http://www.w3.org/2001/XMLSchema](http://go.microsoft.com/fwlink/?LinkId=209155).  
  
-   <xref:System.Security.Claims.Claim.Issuer%2A> ist der Bezeichner für den Sicherheitstokendienst (STS), der den Anspruch ausgestellt hat. Dies kann als URL des STS dargestellt werden, oder als Name, der den STS darstellt, beispielsweise `https://sts1.contoso.com/sts`.  
  
-   <xref:System.Security.Claims.Claim.OriginalIssuer%2A> ist der Bezeichner des STS, der den Anspruch ursprünglich erhoben hat, unabhängig davon, wie viele STS in der Kette sind. Dies wird einfach als <xref:System.Security.Claims.Claim.Issuer%2A> dargestellt.  
  
-   <xref:System.Security.Claims.Claim.Subject%2A> ist der Antragsteller, dessen Identität überprüft wird. Sie enthält eine <xref:System.Security.Claims.ClaimsIdentity>.  
  
-   <xref:System.Security.Claims.Claim.Properties%2A> ist ein Wörterbuch, mit dem der Entwickler anwendungsspezifische Daten bereitstellen kann, die zusammen mit den anderen Eigenschaften übertragen werden, und für die benutzerdefinierte Überprüfung verwendet werden kann.  
  
## <a name="identity-delegation"></a>Identitätsdelegierung  
 Eine wichtige Eigenschaft von <xref:System.Security.Claims.ClaimsIdentity> ist <xref:System.Security.Claims.ClaimsIdentity.Actor%2A>. Diese Eigenschaft aktiviert die Delegierung von Anmeldeinformationen in einem System mit mehreren Ebenen, in dem eine mittlere Ebene als Client agiert, der Anforderungen an einen Back-End-Dienst stellt.  
  
### <a name="accessing-claims-through-threadcurrentprincipal"></a>Zugriff auf Ansprüche über Thread.CurrentPrincipal  
 Verwenden Sie `Thread.CurrentPrincipal`, um auf den Satz von Ansprüchen des aktuellen Benutzers in einer Anwendung der vertrauenden Seite zugreifen zu können.  
  
 Das folgende Codebeispiel zeigt die Verwendung dieser Methode zum Abrufen einer System.Security.Claims.ClaimsIdentity:  
  
```  
ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
```  
  
 Weitere Informationen finden Sie unter <xref:System.Security.Claims>.  
  
### <a name="role-claim-type"></a>Rollenanspruchstyp  
 Bei der Konfiguration Ihrer Anwendung der vertrauenden Seite müssen Sie Ihren Rollenanspruchstyp bestimmen. Dieser Anspruchstyp wird von System.Security.Claims.ClaimsPrincipal.IsInRole(System.String) verwendet. Der Standardanspruchstyp ist `http://schemas.microsoft.com/ws/2008/06/identity/claims/role`.  
  
### <a name="claims-extracted-by-windows-identity-foundation-from-different-token-types"></a>Ansprüche, die von Windows Identity Foundation aus anderen Tokentypen extrahiert wurden  
 WIF unterstützt verschiedene Kombinationen von standardmäßigen Authentifizierungsmechanismen. Die folgende Tabelle enthält die Ansprüche, die WIF aus anderen Tokentypen extrahiert.  
  
|Tokentyp|Erstellter Anspruch|Zuordnung zu Windows-Zugriffstoken|  
|-|-|-|  
|SAML 1.1|1.  Alle Ansprüche aus System.IdentityModel.SecurityTokenService.GetOutputClaimsIdentity(System.Security.Claims.ClaimsPrincipal,System.IdentityModel.Protocols.WSTrust.RequestSecurityToken,System.IdentityModel.Scope).<br />2.  Der `http://schemas.microsoft.com/ws/2008/06/identity/claims/confirmationkey`-Anspruch, der die XML-Serialisierung des Bestätigungsschlüssels enthält, wenn das Token ein Prüftoken enthält.<br />3.  Der `http://schemas.microsoft.com/ws/2008/06/identity/claims/samlissuername`-Anspruch des Ausstellerelements.<br />4.  AuthenticationMethod- und AuthenticationInstant-Ansprüche, wenn das Token eine Authentifizierungsanweisung enthält.|Zusätzlich zu den in „SAML 1.1“ aufgeführten Ansprüchen, mit Ausnahme der Ansprüche des Typs `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name`, werden Ansprüche mit Beziehung zur Windows-Authentifizierung hinzugefügt, und die Identität wird von WindowsClaimsIdentity dargestellt.|  
|SAML 2.0|Identisch mit „SAML 1.1“.|Identisch mit „SAML 1.1 Windowskonto zugeordnet“.|  
|X509|1.  Ansprüche mit den Eigenschaften X500 distinguished Name, EmailName, DnsName, SimpleName, UpnName, UrlName, Fingerabdruck, RsaKey (dies kann mithilfe der RSACryptoServiceProvider.ExportParameters-Methode aus der X509Certificate2.PublicKey.Key-Eigenschaft extrahiert werden), DsaKey (dies kann mithilfe der DSACryptoServiceProvider.ExportParameters-Methode aus der X509Certificate2.PublicKey.Key-Eigenschaft extrahiert werden), SerialNumber aus dem X509-Zertifikat.<br />2.  AuthenticationMethod-Anspruch mit einem `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/x509`-Wert. AuthenticationInstant-Anspruch mit dem Zeitwert, zu dem das Zertifikat im XmlSchema-DateTime-Format überprüft wurde.|1.  Er verwendet den vollqualifizierten Domänennamen des Windows-Kontos als `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name`-Anspruchswert. sein.<br />2.  Ansprüche aus dem X509-Zertifikat, die Windows nicht zugeordnet sind, und Ansprüche aus dem Windows-Konto, die durch die Zuordnung des Zertifikats zu Windows abgerufen werden.|  
|UPN|1.  Ansprüche sind den Ansprüchen im Abschnitt Windows-Authentifizierung ähnlich.<br />2.  AuthenticationMethod-Anspruch mit einem `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/password`-Wert. Der AuthenticationInstant-Anspruch mit dem Zeitwert, zu dem das Kennwort im XmlSchema-DateTime-Format überprüft wurde.||  
|Windows (Kerberos oder NTLM)|1.  Aus dem Zugriffstoken generierte Ansprüche, beispielsweise: PrimarySID, DenyOnlyPrimarySID PrimaryGroupSID, DenyOnlyPrimaryGroupSID, GroupSID, DenyOnlySID und Name<br />2.  AuthenticationMethod mit einem `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/windows`-Wert. Der AuthenticationInstant-Anspruch mit dem Zeitwert, zu dem das Windows-Zugangstoken im XmlSchema-DateTime-Format erstellt wurde.||  
|RSA-Schlüsselpaar|1.  Der `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/rsa`-Anspruch mit dem Wert des RSAKeyValue.<br />2.  AuthenticationMethod-Anspruch mit einem `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/signature`-Wert. Der AuthenticationInstant-Anspruch mit dem Zeitwert, zu dem der RSA-Schlüssel (d.h. die Signatur wurde überprüft) im XMLSchema-DateTime-Format authentifiziert wurde.||  
  
|Authentifizierungstyp|URI, der im AuthenticationMethod-Anspruch ausgegeben wurde|  
|-|-|  
|Kennwort|`urn:oasis:names:tc:SAML:1.0:am:password`|  
|Kerberos|`urn:ietf:rfc:1510`|  
|SecureRemotePassword|`urn:ietf:rfc:2945`|  
|TLSClient|`urn:ietf:rfc:2246`|  
|X509|`urn:oasis:names:tc:SAML:1.0:am:X509-PKI`|  
|PGP|`urn:oasis:names:tc:SAML:1.0:am:PGP`|  
|Spki|`urn:oasis:names:tc:SAML:1.0:am:SPKI`|  
|XmlDSig|`urn:ietf:rfc:3075`|  
|Nicht angegeben.|`urn:oasis:names:tc:SAML:1.0:am:unspecified`|
