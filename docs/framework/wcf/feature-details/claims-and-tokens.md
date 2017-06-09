---
title: "Anspr&#252;che und Token | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Ansprüche [WCF], Und Token"
ms.assetid: eff167f3-33f8-483d-a950-aa3e9f97a189
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Anspr&#252;che und Token
In diesem Thema werden die verschiedenen Anspruchstypen beschrieben, die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] aus den Standardtoken erstellt, die es unterstützt.  
  
 Sie können die Ansprüche von Clientanmeldeinformationen prüfen, indem Sie die <xref:System.IdentityModel.Claims.ClaimSet>\-Klasse und die <xref:System.IdentityModel.Claims.Claim>\-Klasse verwenden.  `ClaimSet` enthält eine Auflistung von `Claim`\-Objekten.  Jeder `Claim` verfügt über die folgenden wichtigen Member:  
  
-   Die <xref:System.IdentityModel.Claims.Claim.ClaimType%2A>\-Eigenschaft gibt einen Uniform Resource Identifier \(URI\) zurück, der den Typ des erhobenen Anspruches angibt.  Beispielsweise kann es sich bei einem Anspruchstypen um einen Fingerabdruck eines Zertifikats handeln. In diesem Fall ist der URI http:schemas.microsoft.com\/ws\/20005\/05\/identity\/claims\/thumprint.  
  
-   Die <xref:System.IdentityModel.Claims.Claim.Right%2A>\-Eigenschaft gibt einen URI zurück, der das Recht des Anspruchs angibt.  Vordefinierte Rechte befinden sich in der <xref:System.IdentityModel.Claims.Rights>\-Klasse \(<xref:System.IdentityModel.Claims.Rights.Identity%2A>, <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>\).  
  
-   Die <xref:System.IdentityModel.Claims.Claim.Resource%2A>\-Eigenschaft gibt die dem Anspruch zugeordnete Ressource zurück.  
  
 Jeder <xref:System.IdentityModel.Claims.ClaimSet> verfügt auch über eine <xref:System.IdentityModel.Claims.ClaimSet.Issuer%2A>\-Eigenschaft, die den <xref:System.IdentityModel.Claims.ClaimSet> des `Issuer` darstellt.  
  
## Windows\-Konten  
 Wo einem Windows\-Benutzerkonto Clientanmeldeinformationen zugeordnet werden, weist der resultierende <xref:System.IdentityModel.Claims.ClaimSet> die folgenden Werte auf:  
  
-   Der `Issuer` ist der von der statischen Windows\-Eigenschaft der <xref:System.IdentityModel.Claims.ClaimSet>\-Klasse zurückgegebene Wert.  
  
-   In der Auflistung sind folgende Ansprüche enthalten:  
  
    -   Ein <xref:System.IdentityModel.Claims.Claim> mit einem <xref:System.IdentityModel.Claims.Claim.ClaimType%2A>\-Wert der Sicherheits\-ID \(SID\), einem <xref:System.IdentityModel.Claims.Claim.Right%2A>\-Eigenschaftswert von `Identity` und einer <xref:System.IdentityModel.Claims.Claim.Resource%2A>, die den tatsächlichen SID\-Wert zurückgibt.  Eine SID ist ein eindeutiger Wert, den der Domänencontroller jedem Benutzer angibt.  Die SID wird verwendet, um den Benutzer in Interaktionen mit Windows\-Sicherheit zu identifizieren.  
  
    -   Ein <xref:System.IdentityModel.Claims.Claim> mit einem <xref:System.IdentityModel.Claims.Claim.ClaimType%2A>\-Wert der SID, einem <xref:System.IdentityModel.Claims.Claim.Right%2A> von `PossessProperty` und einer <xref:System.IdentityModel.Claims.Claim.Resource%2A> des SID\-Werts.  
  
    -   Ein <xref:System.IdentityModel.Claims.Claim> mit einem <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> von <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, einem <xref:System.IdentityModel.Claims.Claim.Right%2A> von `PossessProperty` und einer <xref:System.IdentityModel.Claims.Claim.Resource%2A> der den Benutzernamen enthaltenden Zeichenfolge \(beispielsweise "MYMACHINE\\Bob"\).  
  
    -   Zusätzliche SID\-Ansprüche bei <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> für die verschiedenen Gruppen, zu denen der Benutzer gehört.  
  
## Zertifikate  
 Wenn es sich bei den Clientanmeldeinformationen um ein Zertifikat handelt, verfügt der resultierende <xref:System.IdentityModel.Claims.ClaimSet> über die folgenden Werte:  
  
-   Bei selbst herausgegebenen Zertifikaten ist `Issuer` der <xref:System.IdentityModel.Claims.ClaimSet> selbst.  <xref:System.IdentityModel.Claims.ClaimSet> gibt einen <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> von <xref:System.IdentityModel.Claims.ClaimTypes.Thumbprint%2A>, ein <xref:System.IdentityModel.Claims.Claim.Right%2A> von `Identity` und einen <xref:System.IdentityModel.Claims.Claim.Resource%2A>\-Wert zurück, bei dem es sich um einen <xref:System.Byte>\-Array handelt, der den Fingerabdruck des Zertifikats beinhaltet.  
  
-   Für ein von einer Zertifizierungsstelle ausgestelltes Zertifikat ist der Aussteller der `ClaimSet`, der das Zertifikat der Zertifizierungsstelle darstellt.  
  
-   Die `Claims` in der Auflistung beinhalten folgende Elemente:  
  
    -   Ein `Claim` mit dem `ClaimType` Fingerabdruck, einem `Right` von PossessProperty und einer `Resource`, bei der es sich um ein Bytearray handelt, das den Fingerabdruck des Zertifikats beinhaltet.  
  
    -   Zusätzliche PossessProperty\-Ansprüche verschiedener Typen, einschließlich X500DistinguishedName, DNS, Name, UPN und RSA sind verschiedene Eigenschaften des Zertifikats.  Die Ressource für den RSA\-Anspruch ist der dem Zertifikat zugewiesene öffentliche Schlüssel.**Hinweis**: Wenn der Clientanmeldeinformationstyp ein Zertifikat ist, das der Dienst einem Windows\-Konto zuordnet, werden zwei `ClaimSet`\-Objekte generiert.  Die erste Ressource beinhaltet alle Ansprüche in Zusammenhang mit dem Windows\-Konto, und die zweite Ressource beinhaltet alle Ansprüche, die mit dem Zertifikat in Zusammenhang stehen.  
  
## Benutzername\/Kennwort  
 Handelt es sich bei den Clientanmeldeinformationen um einen Benutzernamen bzw. ein Kennwort \(oder Äquivalent\), der bzw. das keinem Windows\-Konto zugeordnet ist, wird der daraus resultierende `ClaimSet` von der statischen <xref:System.IdentityModel.Claims.ClaimSet.System%2A>\-Eigenschaft der `ClaimSet`\-Klasse ausgestellt.  `ClaimSet` beinhaltet einen `Identity`\-Anspruch vom Typ  `` <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, dessen Ressource der vom Client angegebene Benutzername ist.  Ein entsprechender Anspruch besitzt ein`Right` von `PossessProperty`.  
  
## RSA\-Schlüssel  
 Wird ein RSA\-Schlüssel verwendet, der keinem Zertifikat zugewiesen ist, ist der resultierende `ClaimSet` selbst ausgestellt und beinhaltet einen `Identity`\-Anspruch vom  `` Typ `` <xref:System.IdentityModel.Claims.ClaimTypes.Rsa%2A>, dessen Ressource der RSA\-Schlüssel ist.  Ein entsprechender Anspruch besitzt ein `Right` von `PossessProperty`.  
  
## SAML  
 Wird der Client mit einem Security Assertions Markup Language \(SAML\)\-Token authentifiziert, wird der resultierende `ClaimSet` von der Entität ausgestellt, von der das SAML\-Token signiert wurde. Oftmals handelt es sich dabei um das Zertifikat des Sicherheitstokendiensts \(STS\), von dem das SAML\-Token ausgestellt wurde.  `ClaimSet` enthält verschiedene Ansprüche, die sich im SAML\-Token befinden.  Beinhaltet das SAML\-Token einen `SamlSubject` mit einem Nicht\-`null`\-Namen, werden ein `Identity`\-Anspruch mit dem Typ <xref:System.IdentityModel.Claims.ClaimTypes.NameIdentifier%2A> und ein Ressourcentyp von <xref:System.IdentityModel.Tokens.SamlNameIdentifierClaimResource> erstellt.  
  
## Identitätsansprüche und ServiceSecurityContext.IsAnonymous  
 Beinhaltet keines der `ClaimSet`\-Objekte, die aus den Clientanmeldeinformationen resultieren, einen Anspruch mit einem `Right` von  `Identity,`, gibt die <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A>\-Eigenschaft `true` zurück.  Ist mindestens ein derartiger Anspruch vorhanden, gibt die `IsAnonymous`\-Eigenschaft `false` zurück.  
  
## Siehe auch  
 <xref:System.IdentityModel.Claims.ClaimSet>   
 <xref:System.IdentityModel.Claims.Claim>   
 <xref:System.IdentityModel.Claims.Rights>   
 <xref:System.IdentityModel.Claims.ClaimTypes>   
 [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)