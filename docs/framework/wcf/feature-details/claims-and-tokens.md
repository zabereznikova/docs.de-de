---
title: Ansprüche und Token
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], and tokens
ms.assetid: eff167f3-33f8-483d-a950-aa3e9f97a189
ms.openlocfilehash: cbc97f2224bce640757e1cef88fe325db477cfd7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84587026"
---
# <a name="claims-and-tokens"></a>Ansprüche und Token

In diesem Thema werden die verschiedenen Anspruchs Typen beschrieben, die Windows Communication Foundation (WCF) aus den Standard Token erstellt, die es unterstützt.

Sie können die Ansprüche von Clientanmeldeinformationen prüfen, indem Sie die <xref:System.IdentityModel.Claims.ClaimSet>-Klasse und die <xref:System.IdentityModel.Claims.Claim>-Klasse verwenden. `ClaimSet` enthält eine Auflistung von `Claim`-Objekten. Jeder `Claim` verfügt über die folgenden wichtigen Member:

- Die <xref:System.IdentityModel.Claims.Claim.ClaimType%2A>-Eigenschaft gibt einen Uniform Resource Identifier (URI) zurück, der den Typ des erhobenen Anspruches angibt. Ein Anspruchstyp kann z. b. ein Fingerabdruck eines Zertifikats sein. in diesem Fall ist der URI `http://schemas.microsoft.com/ws/20005/05/identity/claims/thumprint` .

- Die <xref:System.IdentityModel.Claims.Claim.Right%2A>-Eigenschaft gibt einen URI zurück, der das Recht des Anspruchs angibt. Vordefinierte Rechte befinden sich in der <xref:System.IdentityModel.Claims.Rights>-Klasse (<xref:System.IdentityModel.Claims.Rights.Identity%2A>, <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>).

- Die <xref:System.IdentityModel.Claims.Claim.Resource%2A>-Eigenschaft gibt die dem Anspruch zugeordnete Ressource zurück.

Jeder <xref:System.IdentityModel.Claims.ClaimSet> verfügt auch über eine <xref:System.IdentityModel.Claims.ClaimSet.Issuer%2A>-Eigenschaft, die den <xref:System.IdentityModel.Claims.ClaimSet> des `Issuer` darstellt.

## <a name="windows-accounts"></a>Windows-Konten

Wo einem Windows-Benutzerkonto Clientanmeldeinformationen zugeordnet werden, weist der resultierende <xref:System.IdentityModel.Claims.ClaimSet> die folgenden Werte auf:

- Der `Issuer` ist der von der statischen Windows-Eigenschaft der <xref:System.IdentityModel.Claims.ClaimSet>-Klasse zurückgegebene Wert.

- In der Auflistung sind folgende Ansprüche enthalten:

  - Ein <xref:System.IdentityModel.Claims.Claim> mit einem <xref:System.IdentityModel.Claims.Claim.ClaimType%2A>-Wert der Sicherheits-ID (SID), einem <xref:System.IdentityModel.Claims.Claim.Right%2A>-Eigenschaftswert von `Identity` und einer <xref:System.IdentityModel.Claims.Claim.Resource%2A>, die den tatsächlichen SID-Wert zurückgibt. Eine SID ist ein eindeutiger Wert, den der Domänencontroller jedem Benutzer angibt. Die SID wird verwendet, um den Benutzer in Interaktionen mit Windows-Sicherheit zu identifizieren.

  - Ein <xref:System.IdentityModel.Claims.Claim> mit einem <xref:System.IdentityModel.Claims.Claim.ClaimType%2A>-Wert der SID, einem <xref:System.IdentityModel.Claims.Claim.Right%2A> von `PossessProperty` und einer <xref:System.IdentityModel.Claims.Claim.Resource%2A> des SID-Werts.

  - Ein <xref:System.IdentityModel.Claims.Claim> mit einem <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> von <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, einem <xref:System.IdentityModel.Claims.Claim.Right%2A> von `PossessProperty` und einer <xref:System.IdentityModel.Claims.Claim.Resource%2A> der den Benutzernamen enthaltenden Zeichenfolge (beispielsweise "MYMACHINE\Bob").

  - Zusätzliche SID-Ansprüche bei <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> für die verschiedenen Gruppen, zu denen der Benutzer gehört.

## <a name="certificates"></a>Zertifikate

Wenn es sich bei den Clientanmeldeinformationen um ein Zertifikat handelt, verfügt der resultierende <xref:System.IdentityModel.Claims.ClaimSet> über die folgenden Werte:

- Bei selbst herausgegebenen Zertifikaten ist `Issuer` der <xref:System.IdentityModel.Claims.ClaimSet> selbst. <xref:System.IdentityModel.Claims.ClaimSet> gibt einen <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> von <xref:System.IdentityModel.Claims.ClaimTypes.Thumbprint%2A>, ein <xref:System.IdentityModel.Claims.Claim.Right%2A> von `Identity` und einen <xref:System.IdentityModel.Claims.Claim.Resource%2A>-Wert zurück, bei dem es sich um einen <xref:System.Byte>-Array handelt, der den Fingerabdruck des Zertifikats beinhaltet.

- Für ein von einer Zertifizierungsstelle ausgestelltes Zertifikat ist der Aussteller der `ClaimSet`, der das Zertifikat der Zertifizierungsstelle darstellt.

- Die `Claims` in der Auflistung beinhalten folgende Elemente:

  - Ein `Claim` mit dem `ClaimType` Fingerabdruck, einem `Right` von PossessProperty und einer `Resource`, bei der es sich um ein Bytearray handelt, das den Fingerabdruck des Zertifikats beinhaltet.

  - Zusätzliche PossessProperty-Ansprüche verschiedener Typen, einschließlich X500DistinguishedName, DNS, Name, UPN und RSA sind verschiedene Eigenschaften des Zertifikats. Die Ressource für den RSA-Anspruch ist der öffentliche Schlüssel, der dem Zertifikat zugeordnet ist. **Hinweis** Wenn der Client Anmelde Informationstyp ein Zertifikat ist, das dem Dienst einem Windows-Konto zugeordnet ist, `ClaimSet` werden zwei Objekte generiert. Die erste Ressource beinhaltet alle Ansprüche in Zusammenhang mit dem Windows-Konto, und die zweite Ressource beinhaltet alle Ansprüche, die mit dem Zertifikat in Zusammenhang stehen.

## <a name="user-namepassword"></a>Benutzername/Kennwort

Handelt es sich bei den Clientanmeldeinformationen um einen Benutzernamen bzw. ein Kennwort (oder Äquivalent), der bzw. das keinem Windows-Konto zugeordnet ist, wird der daraus resultierende `ClaimSet` von der statischen <xref:System.IdentityModel.Claims.ClaimSet.System%2A>-Eigenschaft der `ClaimSet`-Klasse ausgestellt. Der `ClaimSet` enthält einen `Identity` Anspruch vom Typ, <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A> dessen Ressource der vom Client bereitgestellte Benutzername ist. Ein entsprechender Anspruch besitzt ein`Right` von `PossessProperty`.

## <a name="rsa-keys"></a>RSA-Schlüssel

Wenn ein RSA-Schlüssel verwendet wird, der keinem Zertifikat zugeordnet ist, `ClaimSet` wird das resultierende selbst ausgegeben und enthält einen `Identity` Anspruch vom Typ, <xref:System.IdentityModel.Claims.ClaimTypes.Rsa%2A> dessen Ressource der RSA-Schlüssel ist. Ein entsprechender Anspruch besitzt ein`Right` von `PossessProperty`.

## <a name="saml"></a>SAML

Wird der Client mit einem Security Assertions Markup Language (SAML)-Token authentifiziert, wird der resultierende `ClaimSet` von der Entität ausgestellt, von der das SAML-Token signiert wurde. Oftmals handelt es sich dabei um das Zertifikat des Sicherheitstokendiensts (STS), von dem das SAML-Token ausgestellt wurde. `ClaimSet` enthält verschiedene Ansprüche, die sich im SAML-Token befinden. Beinhaltet das SAML-Token einen `SamlSubject` mit einem Nicht-`null`-Namen, werden ein `Identity`-Anspruch mit dem Typ <xref:System.IdentityModel.Claims.ClaimTypes.NameIdentifier%2A> und ein Ressourcentyp von <xref:System.IdentityModel.Tokens.SamlNameIdentifierClaimResource> erstellt.

## <a name="identity-claims-and-servicesecuritycontextisanonymous"></a>Identitätsansprüche und ServiceSecurityContext.IsAnonymous

Wenn keines der Objekte, die `ClaimSet` aus den Client Anmelde Informationen resultieren, einen Anspruch mit dem Wert enthält, `Right` `Identity,` gibt die- <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A> Eigenschaft zurück `true` . Ist mindestens ein derartiger Anspruch vorhanden, gibt die `IsAnonymous`-Eigenschaft `false` zurück.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Claims.ClaimSet>
- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.Rights>
- <xref:System.IdentityModel.Claims.ClaimTypes>
- [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](managing-claims-and-authorization-with-the-identity-model.md)
