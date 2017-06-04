---
title: "WIF-Claims-Programmiermodell | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 149cb875-9b1c-4695-b88a-fbf1725a02f9
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# WIF-Claims-Programmiermodell
ASP.NET und Windows Communication Foundation \(WCF\)\-Entwickler verwenden normalerweise die IIdentity und IPrincipal\-Schnittstelle mit Identitätsinformationen des Benutzers.  In.NET 4.5, Windows Identity Foundation \(WIF\) wurde integriert Ansprüche jetzt immer für einen Prinzipal, wie im folgenden Diagramm dargestellt werden:  
  
 ![WIF&#45;Claims&#45;Programmiermodell](../../../docs/framework/security/media/wifclaimsprogrammingmodel.png "WIFClaimsProgrammingModel")  
  
 In.NET 4.5 enthält System.Security.Claims die neuen ClaimsPrincipal und ClaimsIdentity\-Klassen \(siehe Abbildung oben\).  Alle Prinzipale in.NET jetzt aus ClaimsPrincipal ableiten.  Alle integrierten Identitätsklassen wie FormsIdentity für ASP.NET und WindowsIdentity sind nun vom ClaimsIdentity abgeleitet.  Ebenso werden alle integrierte principal Klassen wie GenericPrincipal und WindowsPrincipal von ClaimsPrincipal abgeleitet.  
  
 Ein Anspruch ist vertreten durch <xref:System.Security.Claims.Claim> Klasse.  Diese Klasse verfügt über die folgenden wichtigen Eigenschaften:  
  
-   <xref:System.Security.Claims.Claim.Type%2A>Stellt die Art der Forderung und in der Regel ein URI.  Beispielsweise wird der E\-mail\-Adresse\-Anspruch dargestellt, als `http://schemas.microsoft.com/ws/2008/06/identity/claims/email`.  
  
-   <xref:System.Security.Claims.Claim.Value%2A>enthält den Wert des Anspruchs und als Zeichenfolge dargestellt wird.  Beispielsweise kann die e\-Mail\-Adresse als "jemand@contoso.com" dargestellt werden.  
  
-   <xref:System.Security.Claims.Claim.ValueType%2A>Stellt den Typ der Wert des Anspruchs und in der Regel ein URI.  Beispielsweise wird der String\-Typ dargestellt, als `http://www.w3.org/2001/XMLSchema#string`.  Der Werttyp muss ein QName gemäß dem XML\-Schema sein.  Der Wert sollte im Format `namespace#format` WIF einen gültigen QName Wert Ausgabe aktivieren.  Wenn der Namespace keine klar definierte Namespace ist, darf nicht das generierte XML Schema validiert, wahrscheinlich sein, denn es eine veröffentlichte XSD\-Datei für diesen Namespace nicht wird.  Der Standard\-Werttyp ist `http://www.w3.org/2001/XMLSchema#string`.  Bitte finden Sie unter [http:\/\/www.w3.org\/2001\/XMLSchema](http://go.microsoft.com/fwlink/?LinkId=209155) bekannten Werttypen, die Verwendung von Sie sicher.  
  
-   <xref:System.Security.Claims.Claim.Issuer%2A>ist der Bezeichner der Sicherheitstokendienst \(STS\), der den Anspruch ausgestellt hat.  Dies kann als URL der STS oder eines Namens, z. B. der STS darstellt, dargestellt werden `https://sts1.contoso.com/sts`.  
  
-   <xref:System.Security.Claims.Claim.OriginalIssuer%2A>ist der Bezeichner des STS, die ursprünglich den Anspruch, unabhängig davon, wie viele STSs ausgestellt werden, in der Kette.  Dies wird dargestellt, wie <xref:System.Security.Claims.Claim.Issuer%2A>.  
  
-   <xref:System.Security.Claims.Claim.Subject%2A>ist das Thema, dessen Identität geprüft wird.  Sie enthält eine <xref:System.Security.Claims.ClaimsIdentity>.  
  
-   <xref:System.Security.Claims.Claim.Properties%2A>ist ein Wörterbuch, das den Entwickler kann anwendungsspezifische Daten liefern, um bei der Übertragung zusammen mit anderen Eigenschaften übertragen werden und kann für die benutzerdefinierte Validierung verwendet werden.  
  
## Identitätsdelegierung der  
 Eine wichtige Eigenschaft des <xref:System.Security.Claims.ClaimsIdentity> ist <xref:System.Security.Claims.ClaimsIdentity.Actor%2A>.  Diese Eigenschaft ermöglicht die Delegierung von Anmeldeinformationen in einem Multi\-Tier\-System in die mittlere Ebene als der Client Anforderungen an einen Back\-End\-Dienst fungiert.  
  
### Zugriff auf Ansprüche über Thread.CurrentPrincipal  
 Verwenden des aktuellen Benutzers Ansprüche in RP\-Anwendung zugreifen, `Thread.CurrentPrincipal`.  
  
 Das folgende Codebeispiel zeigt die Verwendung dieser Methode um eine System.Security.Claims.ClaimsIdentity zu erhalten:  
  
```  
ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
```  
  
 Weitere Informationen finden Sie unter <xref:System.Security.Claims>.  
  
### Rollenanspruchstyp  
 Konfigurieren der Anwendung für die RP gehört zu bestimmen, welche Ihre Rolle sollte sein behaupten.  Dieser Anspruchstyp wird von System.Security.Claims.ClaimsPrincipal.IsInRole\(System.String\) verwendet.  Der Standard\-Anspruchstyp ist `http://schemas.microsoft.com/ws/2008/06/identity/claims/role`.  
  
### Ansprüche, die von Windows\-Identität Foundation aus unterschiedlichen Token extrahiert  
 WIF unterstützt mehrere Authentifizierungsmechanismen out of the Box.  Die folgende Tabelle listet die Ansprüche, die von anderen Tokentypen WIF extrahiert.  
  
||||  
|-|-|-|  
|Tokentyp|Forderung generiert|Karte, um Windows\-Zugriffstoken|  
|SAML 1.1|1.  Alle Ansprüche aus System.IdentityModel.SecurityTokenService.GetOutputClaimsIdentity\(System.Security.Claims.ClaimsPrincipal,System.IdentityModel.Protocols.WSTrust.RequestSecurityToken,System.IdentityModel.Scope\).<br />2.  Die `http://schemas.microsoft.com/ws/2008/06/identity/claims/confirmationkey` Anspruch, die die XML\-Serialisierung des Schlüssels Bestätigung enthält, wenn das Token ein Prüftoken enthält.<br />3.  Die `http://schemas.microsoft.com/ws/2008/06/identity/claims/samlissuername` aus dem Emittenten Element behaupten.<br />4.  AuthenticationMethod und AuthenticationInstant Angaben, wenn das Token eine Authentifizierungsanweisung enthält.|Zusätzlich zu den Ansprüchen gemäß "SAML 1.1", mit Ausnahme der Ansprüche vom Typ `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name`, Windows\-Authentifizierung mit Bezug Ansprüche werden hinzugefügt und die Identität wird durch WindowsClaimsIdentity dargestellt werden.|  
|SAML 2.0|Identisch mit "SAML 1.1".|Identisch mit "SAML 1.1 Windowskonto zugeordnet".|  
|X509|1.  Forderungen mit der X 500 distinguished Name, e\-Mail\-Name, DNS\-Name, SimpleName, UpnName, UrlName, Fingerabdruck, RsaKey \(Dies kann extrahiert werden mithilfe der RSACryptoServiceProvider.ExportParameters\-Methode aus der X509Certificate2.PublicKey.Key\-Eigenschaft\), DsaKey \(Dies kann extrahiert werden mithilfe der DSACryptoServiceProvider.ExportParameters\-Methode aus der X509Certificate2.PublicKey.Key\-Eigenschaft\), SerialNumber Eigenschaften von X 509\-Zertifikat.<br />2.  AuthenticationMethod Anspruch mit Wert `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/x509`.  AuthenticationInstant behaupten, mit dem Wert der Zeit, wann das Zertifikat im XmlSchema\-DateTime\-Format überprüft wurde.|1.  Es verwendet den Windows\-Konto vollständig qualifizierten Domänennamen als den `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name` Wert behaupten.  .<br />2.  Ansprüche von X 509\-Zertifikat nicht Windows zugeordnet, und Ansprüche aus dem Windowskonto erhalten von Windows das Zertifikat zuordnen.|  
|UPN|1.  Ansprüche sind ähnlich wie die Ansprüche im Bereich Windows\-Authentifizierung.<br />2.  AuthenticationMethod Anspruch mit Wert `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/password`.  Die Forderung AuthenticationInstant mit dem Wert der Zeit, wann das Kennwort im XmlSchema\-DateTime\-Format überprüft wurde.||  
|Windows \(Kerberos oder NTLM\)|1.  Ansprüche aus dem Zugriffstoken generiert, z. B.: PrimarySID, DenyOnlyPrimarySID, PrimaryGroupSID, DenyOnlyPrimaryGroupSID, Gruppen\-SID, DenyOnlySID, und Name<br />2.  AuthenticationMethod mit dem Wert `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/windows`.  AuthenticationInstant mit dem Wert der Zeit, wenn die Windows Token zuzugreifen, wurde in das XMLSchema\-DateTime\-Format erstellt.||  
|RSA\-Schlüsselpaar|1.  Die `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/rsa` mit dem Wert der RSAKeyValue behaupten.<br />2.  AuthenticationMethod Anspruch mit dem Wert `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/signature`.  AuthenticationInstant Anspruch mit dem Wert der Zeit, wenn der RSA\-Schlüssel authentifiziert wurde \(d. h. die Signatur wurde verifiziert\) in das XMLSchema\-DateTime\-Format.||  
  
|||  
|-|-|  
|Authentifizierungstyp|URI "AuthenticationMethod" Forderung ausgegeben|  
|Kennwort|`urn:oasis:names:tc:SAML:1.0:am:password`|  
|Kerberos|`urn:ietf:rfc:1510`|  
|SecureRemotePassword|`urn:ietf:rfc:2945`|  
|TLSClient|`urn:ietf:rfc:2246`|  
|X509|`urn:oasis:names:tc:SAML:1.0:am:X509-PKI`|  
|PGP|`urn:oasis:names:tc:SAML:1.0:am:PGP`|  
|Spki|`urn:oasis:names:tc:SAML:1.0:am:SPKI`|  
|XmlDSig|`urn:ietf:rfc:3075`|  
|Nicht angegeben|`urn:oasis:names:tc:SAML:1.0:am:unspecified`|