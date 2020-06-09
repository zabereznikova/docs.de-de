---
title: Veröffentlichung von Informationen
ms.date: 03/30/2017
ms.assetid: 4064c89f-afa6-444a-aa7e-807ef072131c
ms.openlocfilehash: a58ac4dd3715052031c7fb5c1da480c0d01396ea
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596863"
---
# <a name="information-disclosure"></a>Veröffentlichung von Informationen

Die Veröffentlichung von Informationen ermöglicht Angreifern, an wertvolle Informationen über ein System zu gelangen. Daher sollten Sie immer genau überlegen, welche Informationen offengelegt werden und ob sie von anderen Personen böswillig missbraucht werden könnten. Im Folgenden finden Sie eine Übersicht über mögliche Angriffe auf veröffentlichte Informationen mit den entsprechenden Entschärfungen.

## <a name="message-security-and-http"></a>Nachrichtensicherheit und HTTP

Falls Sie die Sicherheit auf Nachrichtenebene mit einer HTTP-Transportschicht verwenden, dürfen Sie nicht vergessen, dass bei dieser Sicherheitsstufe HTTP-Header nicht geschützt sind. HTTP-Header lassen sich nur durch einen HTTPS-Transport, nicht jedoch durch HTTP schützen. Beim HTTPS-Transport wird die gesamte Nachricht einschließlich der HTTP-Header mit dem SSL-Protokoll (Secure Sockets Layer) verschlüsselt.

## <a name="policy-information"></a>Richtlinieninformationen

Der Schutz von Richtlinien ist sehr wichtig, vor allem in Verbundszenarien, bei denen die Richtlinien auch vertrauliche Informationen zu den Anforderungen für ausgegebene Token und zu den Tokenausstellern enthalten. In diesen Fällen sollte möglichst der Richtlinienendpunkt des Verbunddiensts gesichert werden, damit Angreifer keine Informationen zum Dienst, wie zum Beispiel Informationen zur Art der Ansprüche, die in das ausgegebene Token aufgenommen werden müssen, einholen oder keine Clients an bösartige Tokenaussteller umleiten können. So können Angreifer beispielsweise Benutzernamen-/Kennwortkombinationen ermitteln, indem sie die Vertrauenskette des Verbunds so umkonfigurieren, dass sie bei einem Aussteller endet, der einen Man-In-The-Middle-Angriff (MITM-Angriff, Janusangriff) durchgeführt hat. Auch sollte von Verbundclients, die ihre Bindungen über den Abruf einer Richtlinie erhalten, überprüft werden, ob die Aussteller in der bezogenen Vertrauenskette des Verbunds tatsächlich vertrauenswürdig sind. Weitere Informationen zu Verbund Szenarien finden Sie unter [Federation](federation.md).

## <a name="memory-dumps-can-reveal-claim-information"></a>Anspruchsinformationen in Speicherabbildern

Falls in einer Anwendung ein Fehler auftritt, können Protokolldateien (wie zum Beispiel die von Dr. Watson erzeugten Protokolldateien) Anspruchsinformationen enthalten. Diese Informationen sollten nicht für andere Einheiten in der Organisation wie Supportteams exportiert werden, da sonst auch die Anspruchsinformationen mit persönlichen Daten exportiert werden. Sie können diese Gefahr umgehen, indem Sie keine Protokolldateien an Unbekannte senden.

## <a name="endpoint-addresses"></a>Endpunktadressen

Eine Endpunktadresse enthält die für die Kommunikation mit einem Endpunkt erforderlichen Informationen. Bei der SOAP-Sicherheit muss die vollständige Adresse in den gesendeten Sicherheitsaushandlungsnachrichten enthalten sein, damit zwischen Client und Server ein symmetrischer Schlüssel ausgehandelt werden kann. Da es sich bei der Sicherheitsaushandlung um einen Bootstrapprozess handelt, können die Adressheader während des Prozesses nicht verschlüsselt werden. Daher sollte die Adresse keine vertraulichen Daten enthalten, da dies zu Angriffen auf veröffentlichte Informationen führen kann.

## <a name="certificates-transferred-unencrypted"></a>Unverschlüsselt übertragene Zertifikate

Wenn Sie für die Authentifizierung eines Clients ein X.509-Zertifikat verwenden, wird das Zertifikat unverschlüsselt im SOAP-Header übertragen. Beachten Sie, dass es sich hierbei um eine mögliche Veröffentlichung personenbezogener Informationen (PII, Personally Identifiable Information) handelt. Dies ist kein Problem beim `TransportWithMessageCredential`-Modus, bei dem die gesamte Nachricht mithilfe von Sicherheit auf Transportebene verschlüsselt wird.

## <a name="service-references"></a>Dienstverweise

Bei einem Dienstverweis handelt es sich um einen Verweis auf einen anderen Dienst. So kann zum Beispiel ein Dienst im Laufe eines Vorgangs einen Dienstverweis an einen Client übergeben. Der Dienst Verweis wird auch mit einer *Vertrauensstellungs Identität*verwendet. Dies ist eine interne Komponente, die die Identität des Ziel Prinzipals sicherstellt, bevor Informationen wie Anwendungsdaten oder Anmelde Informationen für das Ziel offenlegen werden. Falls die Remotevertrauensidentität nicht überprüft werden kann oder falsch ist, sollte sich der Sender vergewissern, dass keine Daten veröffentlicht wurden, die den Sender, die Anwendung oder den Benutzer gefährden könnten.

Folgende Maßnahmen mindern das Risiko:

- Dienstverweise werden als vertrauenswürdig angesehen. Falls Sie Dienstverweisinstanzen übertragen, sollten Sie daher sicherstellen, dass diese nicht manipuliert wurden.

- Bei einigen Anwendungen haben Benutzer die Möglichkeit, die Vertrauenswürdigkeit interaktiv basierend auf Daten im Dienstverweis und anhand von vertrauenswürdigen Daten, die durch den Remotehost belegt wurden, herzustellen. WCF bietet Erweiterbarkeits Punkte für eine solche Funktion, der Benutzer muss Sie jedoch implementieren.

## <a name="ntlm"></a>NTLM

In der Windows-Domänenumgebung wird zur Authentifizierung und Autorisierung von Benutzern über die Windows-Authentifizierung standardmäßig das Kerberos-Protokoll verwendet. Falls das Kerberos-Protokoll nicht verwendet werden kann, wird für diesen Zweck NT LAN Manager (NTLM) herangezogen. Sie können dieses Verhalten deaktivieren, indem Sie die <xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A>-Eigenschaft auf `false` festlegen. Beachten Sie unter anderem folgende Punkte, wenn Sie NTLM zulassen:

- NTLM gibt den Clientbenutzernamen bekannt. Falls der Benutzername vertraulich behandelt werden muss, legen Sie die `AllowNTLM`-Eigenschaft für die Bindung auf `false` fest.

- NTLM stellt keine Serverauthentifizierung bereit. Daher hat der Client bei Verwendung von NTLM als Authentifizierungsprotokoll keine Möglichkeit sicherzustellen, dass die Kommunikation mit dem richtigen Dienst erfolgt.

### <a name="specifying-client-credentials-or-invalid-identity-forces-ntlm-usage"></a>Die Angabe von Clientanmeldeinformationen oder eine ungültige Identität erzwingt die Verwendung von NTLM

Werden beim Erstellen eines Clients Clientanmeldeinformationen ohne Domänennamen oder eine ungültige Serveridentität angegeben, wird NTLM anstelle des Kerberos-Protokolls verwendet (sofern die `AllowNtlm`-Eigenschaft auf `true` festgelegt wurde). Da NTLM keine Serverauthentifizierung durchführt, können Informationen potenziell offengelegt werden.

Beispielsweise ist es möglich, Windows-Client Anmelde Informationen ohne Domänen Namen anzugeben, wie im folgenden Visual c#-Code dargestellt.

```csharp
MyChannelFactory.Credentials.Windows.ClientCredential = new System.Net.NetworkCredential("username", "password");
```

Da im Code kein Domänenname angegeben wird, wird NTLM verwendet.

Falls bei Verwendung der Funktion für die Endpunktidentität zwar eine Domäne, jedoch ein ungültiger Dienstprinzipalname angegeben wird, wird NTLM verwendet. Weitere Informationen zur Angabe der Endpunkt Identität finden Sie unter [Dienst Identität und-Authentifizierung](service-identity-and-authentication.md).

## <a name="see-also"></a>Weitere Informationen

- [Sicherheitshinweise](security-considerations-in-wcf.md)
- [Rechte Erweiterungen](elevation-of-privilege.md)
- [Denial of Service](denial-of-service.md)
- [Manipulation](tampering.md)
- [Nicht unterstützte Szenarien](unsupported-scenarios.md)
- [Wiederholungsangriffe](replay-attacks.md)
