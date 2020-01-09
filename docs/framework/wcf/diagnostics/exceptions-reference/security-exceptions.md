---
title: Sicherheitsausnahmen
ms.date: 03/30/2017
ms.assetid: 76d5e5cd-e4f4-404f-9a5a-ec3522494ad8
ms.openlocfilehash: e96c317862867b9e461eb2d13dce6ede5b30cf13
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348244"
---
# <a name="security-exceptions"></a>Sicherheitsausnahmen

Dieses Thema enthält alle Sicherheitsausnahmen.

## <a name="exception-list"></a>Ausnahmeliste

|Ressourcencode|Ressourcenzeichenfolge|
|-------------------|---------------------|
|AnonymousLogonsAreNotAllowed|Der Dienst lässt keine anonymen Anmeldungen zu.|
|AtLeastOneContractOperationRequestRequiresProtectionLevelNotSupportedByBinding|Die Anforderungsnachricht muss geschützt werden. Dies ist für einen Vorgang des angegebenen Vertrags erforderlich. Der Schutz muss von der angegebenen Bindung bereitgestellt werden.|
|AtLeastOneContractOperationResponseRequiresProtectionLevelNotSupportedByBinding|Die Antwortnachricht muss geschützt werden. Dies ist für einen Vorgang des angegebenen Vertrags erforderlich. Der Schutz muss von der angegebenen Bindung bereitgestellt werden.|
|AtMostOnePrimarySignatureInReceiveSecurityHeader|In einem Sicherheitsheader ist nur eine primäre Signatur zulässig.|
|BadContextTokenFaultReason|Der Sicherheitskontext ist abgelaufen oder ungültig. Die Nachricht wurde nicht verarbeitet.|
|BadEncryptionState|EncryptedData oder EncryptedKey befinden sich in einem für diesen Vorgang ungültigen Status.|
|BasicHttpMessageSecurityRequiresCertificate|Die BasicHttp-Bindung erfordert, dass BasicHttpBinding.Security.Message.ClientCredentialType dem Anmeldeinformationstyp BasicHttpMessageCredentialType.Certificate für sichere Nachrichten entspricht. Wählen Sie die Transport- oder TransportWithMessageCredential-Sicherheit für UserName-Anmeldeinformationen.|
|BasicTokenCannotBeWrittenWithoutEncryption|Das Basistoken kann nicht ohne Verschlüsselung geschrieben werden.|
|BindingDoesNotSupportProtectionForRst|Die angegebene Bindung für den angegebenen Vertrag ist mit SecureConversation konfiguriert, der Authentifizierungsmodus kann jedoch keine für die Aushandlung erforderliche und auf Anforderung/Antwort basierende Integrität und Vertraulichkeit bereitstellen.|
|BindingDoesNotSupportWindowsIdenityForImpersonation|Der angegebene Vertragsvorgang erfordert Windows-Identität für den automatischen Identitätswechsel. Die angegebene Bindung für den angegebenen Vertrag stellt jedoch keine Windows-Identität bereit, die den Aufrufer darstellt.|
|CachedNegotiationStateQuotaReached|Der Dienst kann den Aushandlungsstatus nicht zwischenspeichern, weil die angegebene Kapazität ausgeschöpft wurde. Wiederholen Sie die Anforderung.|
|CacheQuotaReached|Das Element kann nicht hinzugefügt werden. Die maximale Cachegröße wurde erreicht.|
|CannotDetermineSPNBasedOnAddress|Der Client kann den Dienstprinzipalnamen auf der Basis der Identität in der angegebenen Zieladresse für die Verwendung durch SspiNegotiation/Kerberos nicht bestimmen. Bei der Zieladressen Identität muss es sich um eine UPN-Identität (z. b. acmedomain\\\alice) oder SPN-Identität (wie Host/Bob-Machine) handeln.|
|CannotFindCert|Das X.509-Zertifikat kann mit den angegebenen Suchkriterien nicht gefunden werden: StoreName, StoreLocation, FindType, FindValue.|
|CannotFindCertForTarget|Das X.509-Zertifikat kann mit den angegebenen Suchkriterien nicht gefunden werden: StoreName, StoreLocation, FindType, FindValue für das angegebene Ziel.|
|CannotFindCorrelationStateForApplyingSecurity|Es kann kein Korrelierungsstatus für das Anwenden von Sicherheit zum Antworten gefunden werden.|
|CannotFindNegotiationState|Der Aushandlungsstatus für den angegebenen Kontext kann nicht gefunden werden.|
|CannotFindSecuritySession|Die Sicherheitssitzung mit der angegebenen ID kann nicht gefunden werden.|
|CannotImportProtectionLevelForContract|Die Richtlinie zum Importieren eines Prozesses kann keine Bindung für den angegebenen Vertrag importieren. Die Schutzanforderungen für die Bindung sind nicht mit einer Bindung kompatibel, die bereits für den Vertrag importiert wurde. Sie müssen die Bindung neu konfigurieren.|
|CannotImportSupportingTokensForOperationWithoutRequestAction|Fehler beim Sicherheitsrichtlinienimport. Die Sicherheitsrichtlinie enthält Anforderungen für unterstützende Token beim Vorgangsbereich. Die Vertragsbeschreibung gibt jedoch nicht die Aktion für die diesem Vorgang zugeordnete Anforderungsnachricht an.|
|CannotIssueRstTokenType|Das Token oder der angegebene Typ kann nicht ausgeben werden.|
|CannotObtainIssuedTokenKeySize|Die Schlüsselgröße des ausgegebenen Tokens kann nicht bestimmt werden.|
|CannotPerformImpersonationOnUsernameToken|Der Identitätswechsel kann nicht mithilfe des Clienttokens durchgeführt werden. Die angegebene Bindung für den angegebenen Vertrag verwendet das Benutzernamen-Sicherheitstoken zur Clientauthentifizierung mit einem registrierten Mitgliedschaftsanbieter. Verwenden Sie einen anderen Sicherheitstokentyp für den Client.|
|CannotPerformS4UImpersonationOnPlatform|Die angegebene Bindung für den angegebenen Vertrag unterstützt den Identitätswechsel nur unter Windows Server 2003 und neueren Versionen von Windows. Verwenden Sie die SspiNegotiated-Authentifizierung und eine Bindung mit Secure Conversation mit aktiviertem Abbruch.|
|CannotReadKeyIdentifier|Der KeyIdentifier kann nicht aus dem angegebenen Element mit dem angegebenen Namespace gelesen werden.|
|CannotReadToken|Das Token aus dem angegebenen Element mit dem angegebenen Namespace für BinarySecurityToken mit dem angegebenen ValueType kann nicht gelesen werden. Wenn Sie dieses Element für gültig halten, stellen Sie sicher, dass die Sicherheit für das Verbrauchen von Token mit dem angegebenen Namen, Namespace und Werttyp konfiguriert ist.|
|CertificateUnsupportedForHttpTransportCredentialOnly|Die zertifikatbasierte Clientauthentifizierung wird im TransportCredentialOnly-Sicherheitsmodus nicht unterstützt. Wählen Sie den Transportsicherheitsmodus aus.|
|ClaimTypeCannotBeEmpty|Der claimType kann keine leere Zeichenfolge sein.|
|ClientCertificateNotProvided|Das Clientzertifikat wurde nicht bereitgestellt. Das Zertifikat kann für ClientCredentials oder ServiceCredentials festgelegt werden.|
|ClientCredentialTypeMustBeSpecifiedForMixedMode|ClientCredentialType.None ist für den TransportWithMessageCredential-Sicherheitsmodus ungültig. Geben Sie einen Anmeldeinformationstyp für Nachrichten an, oder verwenden Sie einen anderen Sicherheitsmodus.|
|ConfigurationSchemaInsuffientForSecurityBindingElementInstance|Das Konfigurationsschema ist nicht ausreichend, um die nicht standardmäßige Konfiguration des folgenden Sicherheitsbindungselements zu beschreiben:|
|DerivedKeyTokenGenerationAndLengthTooHigh|Die angegebene Generierung und die angegebene Länge des abgeleiteten Schlüssels führen zu einem Schlüsselableitungsoffset, der größer als der maximal zulässige Offset ist.|
|DnsIdentityCheckFailedForIncomingMessage|Fehler bei der Identitätsprüfung für die eingehende Nachricht. Die erwartete DNS (Domain Name System)-Identität des Remoteendpunkts wurde angegeben. Der Remoteendpunkt hat jedoch den angegebenen DNS-Anspruch bereitgestellt. Wenn es sich hierbei um einen rechtmäßigen Remoteendpunkt handelt, können Sie das Problem beheben, indem Sie beim Erstellen eines Kanalproxys die DNS-Identität als Identity-Eigenschaft von EndpointAddress angeben.|
|DnsIdentityCheckFailedForOutgoingMessage|Die Identitätsprüfung für die ausgehende Nachricht ist fehlgeschlagen. Der Remote Endpunkt muss über die angegebene Domänen Namen-System Identität verfügen. Der Remoteendpunkt hat den DNS-Anspruch bereitgestellt. Wenn es sich hierbei um einen rechtmäßigen Remoteendpunkt handelt, können Sie das Problem beheben, indem Sie beim Erstellen eines Kanalproxys ausdrücklich die DNS-Identität als Identity-Eigenschaft von EndpointAddress angeben.|
|DuplicateIdInMessageToBeVerified|Die angegebene ID ist in der Meldung, die zur Überprüfung bereitgestellt wird, zweimal aufgetreten.|
|EmptyBase64Attribute|Für den erforderlichen base64-Attributnamen und den erforderlichen Namespace wurde ein leerer Wert gefunden.|
|ExportOfBindingWithAsymmetricAndTransportSecurityNotSupported|Fehler beim Sicherheitsrichtlinienexport. Die Bindung enthält sowohl ein AsymmetricSecurityBindingElement als auch ein sicheres Transportbindungselement. Der Richtlinienexport für diese Bindung wird nicht unterstützt.|
|ExportOfBindingWithSymmetricAndTransportSecurityNotSupported|Fehler beim Sicherheitsrichtlinienexport. Die Bindung enthält sowohl ein SymmetricSecurityBindingElement als auch ein sicheres Transportbindungselement. Der Richtlinienexport für diese Bindung wird nicht unterstützt.|
|ExportOfBindingWithTransportSecurityBindingElementAndNoTransportSecurityNotSupported|Fehler beim Sicherheitsrichtlinienexport. Die Bindung enthält ein TransportSecurityBindingElement, jedoch kein Transportbindungselement, das ITransportTokenAssertionProvider implementiert. Der Richtlinienexport für diese Bindung wird nicht unterstützt. Das Transportbindungselement in der Bindung muss die ITransportTokenAssertionProvider-Schnittstelle implementieren.|
|FoundMultipleCerts|Mehrere X.509-Zertifikate gefunden, die das angegebene Suchkriterium verwenden: StoreName, StoreLocation, FindType, FindValue. Stellen Sie einen spezifischeren Fundwert bereit.|
|FoundMultipleCertsForTarget|Es wurden mehrere X.509-Zertifikate mit den folgenden Suchkriterien gefunden: StoreName, StoreLocation, FindType, FindValue für das angegebene Ziel. Stellen Sie einen spezifischeren Fundwert bereit.|
|HeaderDecryptionNotSupportedInWsSecurityJan2004|SecurityVersion.WSSecurityJan2004 unterstützt keine Entschlüsselung von Headern. Verwenden Sie SecurityVersion.WsSecurityXXX2005 oder höher, oder verwenden Sie die Transportsicherheit, um die vollständige Nachricht zu verschlüsseln.|
|IdentityCheckFailedForIncomingMessage|Fehler bei der Identitätsprüfung für die eingehende Nachricht. Die erwartete Identität wird für den Zielendpunkt angegeben.|
|IdentityCheckFailedForOutgoingMessage|Fehler bei der Identitätsprüfung für die ausgehende Nachricht. Die erwartete Identität wird für den Zielendpunkt angegeben.|
|IncorrectSpnOrUpnSpecified|Fehler bei der SSPI (Security Support Provider Interface)-Authentifizierung. Der Server darf nicht mit einem Konto mit der angegebenen Identität ausgeführt werden. Wenn der Server mit einem Dienstkonto ausgeführt wird (z. B. mit dem Netzwerkdienst), geben Sie den ServicePrincipalName des Kontos als Identität in der EndpointAddress für den Server an. Wenn der Server mit einem Benutzerkonto ausgeführt wird, geben Sie den UserPrincipalName des Kontos als Identität in der EndpointAddress für den Server an.|
|InvalidAttributeInSignedHeader|Der angegebene signierte Header enthält das angegebene Attribut. Das erwartete Attribut wird angegeben.|
|InvalidCloseResponseAction|Schließen-Antwort von Sicherheitssitzung mit der angegebenen ungültigen Aktion empfangen.|
|InvalidQName|Der QName ist ungültig.|
|InvalidRenewResponseAction|Erneuern-Antwort von Sicherheitssitzung mit der angegebenen ungültigen Aktion empfangen.|
|InvalidSspiNegotiation|Fehler bei der SSPI (Security Support Provider Interface)-Aushandlung.|
|IssuerBindingNotPresentInTokenRequirement|Der Sicherheitstoken-Manager erfordert das verteilbare Sicherheitsbindungselement in der Tokenanforderung mit der Beschreibung der sicheren Konversation. Die Tokenanforderung wird wie folgt angegeben:|
|KeyLengthMustBeMultipleOfEight|Die angegebene Schlüssellänge für symmetrische Schlüssel ist kein Vielfaches von 8.|
|LsaAuthorityNotContacted|Interner SSL-Fehler. (Weitere Informationen finden Sie im Win32-Statuscode.) Überprüfen Sie das Serverzertifikat, um herauszufinden, ob ein Schlüsselaustausch möglich ist.|
|MaximumPolicyRedirectionsExceeded|Die Grenze für den rekursiven Richtlinienabruf wurde erreicht. Überprüfen Sie, ob sich eine Schleife in der Verbunddienstkette befindet.|
|MessagePartSpecificationMustBeImmutable|Eine Nachrichtenteilspezifikation muss vor dem Festlegen beständig gemacht werden.|
|MissingCustomCertificateValidator|X509CertificateValidationMode.Custom erfordert CustomCertificateValidator. Geben Sie die CustomCertificateValidator-Eigenschaft an.|
|MissingCustomUserNamePasswordValidator|UserNamePasswordValidationMode.Custom erfordert CustomUserNamePasswordValidator. Geben Sie die CustomUserNamePasswordValidator-Eigenschaft an.|
|MissingMembershipProvider|UserNamePasswordValidationMode.MembershipProvider erfordert MembershipProvider. Geben Sie die MembershipProvider-Eigenschaft an.|
|NoBinaryNegoToSend|Es wurde keine binäre Aushandlung an die andere Partei gesendet.|
|NoEncryptionPartsSpecified|Es wurden keine Verschlüsselungsnachrichtenteile für Nachrichten mit der angegebenen Aktion angegeben.|
|NoKeyInfoInEncryptedItemToFindDecryptingToken|Im verschlüsselten Element wurde kein KeyInfo-Wert gefunden, um nach dem Entschlüsselungstoken zu suchen.|
|NonceLengthTooShort|Die angegebene Nonce ist zu kurz. Die erforderliche minimale Noncelänge beträgt 4 Byte.|
|NoOutgoingEndpointAddressAvailableForDoingIdentityCheck|Es ist keine ausgehende EndpointAddress verfügbar, um die Identität einer zu sendenden Nachricht zu prüfen.|
|NoOutgoingEndpointAddressAvailableForDoingIdentityCheckOnReply|Es ist keine ausgehende EndpointAddress verfügbar, um die Identität einer erhaltenen Antwort zu prüfen.|
|NoPartsOfMessageMatchedPartsToSign|Es wurde keine Signatur erstellt, da kein Teil der Nachricht mit der angegebenen Nachrichtenteilspezifikation übereinstimmt.|
|NoPrincipalSpecifiedInAuthorizationContext|Im Autorisierungskontext ist kein benutzerdefinierter Prinzipal angegeben.|
|NoSignatureAvailableInSecurityHeaderToDoReplayDetection|Im Sicherheitsheader ist keine Signatur zum Bereitstellen der Nonce für die Wiedergabeerkennung verfügbar.|
|NoSignaturePartsSpecified|Für Nachrichten mit der angegebenen Aktion wurden keine Signaturnachrichtenteile angegeben.|
|NoSigningTokenAvailableToDoIncomingIdentityCheck|Zum Ausführen der eingehenden Identitätsprüfung ist kein Signaturtoken verfügbar.|
|NoTimestampAvailableInSecurityHeaderToDoReplayDetection|Im Sicherheitsheader ist kein Zeitstempel für die Wiedergabeerkennung verfügbar.|
|NoTransportTokenAssertionProvided|Fehler beim Exportieren der Sicherheitsrichtlinie. Die bereitgestellte Transporttokenassertion vom angegebenen Typ hat keine Transporttokenassertion zur Aufnahme in die sp:TransportBinding-Sicherheitsrichtlinienassertion erstellt.|
|OnlyOneOfEncryptedKeyOrSymmetricBindingCanBeSelected|Das symmetrische Sicherheitsprotokoll kann entweder mit einem symmetrischen Tokenanbieter und einem symmetrischen Tokenauthentifizierer oder einem asymmetrischen Tokenanbieter konfiguriert werden. Es kann jedoch nicht mit beiden konfiguriert werden.|
|OperationCannotBeDoneOnReceiverSideSecurityHeaders|Dieser Vorgang kann für Empfängersicherheitsheader nicht ausgeführt werden.|
|OperationDoesNotAllowImpersonation|Der angegebene Dienstvorgang, der dem Vertrag mit dem angegebenen Namen und dem angegebenen Namespace angehört, lässt keine Identitätswechsel zu.|
|PolicyRequiresConfidentialityWithoutIntegrity|Die Nachrichtensicherheitsrichtlinie für die angegebene Aktion erfordert Vertraulichkeit ohne Integrität. Vertraulichkeit ohne Integrität wird nicht unterstützt.|
|PrimarySignatureIsRequiredToBeEncrypted|Die primäre Signatur muss verschlüsselt werden.|
|PropertySettingErrorOnProtocolFactory|Die erforderliche Eigenschaft für die angegebene Sicherheitsprotokollfactory ist nicht festgelegt oder weist einen ungültigen Wert auf.|
|ProtocolFactoryCouldNotCreateProtocol|Die Protokollfactory kann kein Protokoll erstellen.|
|PublicKeyNotRSA|Der öffentliche Schlüssel ist kein RSA-Schlüssel.|
|RequiredMessagePartNotEncrypted|Der angegebene erforderliche Nachrichtenteil wurde nicht verschlüsselt.|
|RequiredMessagePartNotEncryptedNs|Der angegebene erforderliche Nachrichtenteil wurde nicht verschlüsselt.|
|RequiredMessagePartNotSigned|Der angegebene erforderliche Nachrichtenteil wurde nicht signiert.|
|RequiredMessagePartNotSignedNs|Der angegebene erforderliche Nachrichtenteil wurde nicht signiert.|
|RequiredSecurityHeaderElementNotSigned|Das angegebene Sicherheits Header Element mit der angegebenen ID muss signiert sein.|
|RequiredSecurityTokenNotEncrypted|Das angegebene Sicherheitstoken mit dem angegebenen Anfügemodus muss verschlüsselt werden.|
|RequiredSecurityTokenNotSigned|Das angegebene Sicherheitstoken mit dem angegebenen Anfügemodus muss signiert werden.|
|RequiredSignatureMissing|Die Signatur muss im Sicherheitsheader enthalten sein.|
|RequireNonCookieMode|Die angegebene Bindung mit dem angegebenen Namespace ist zum Ausstellen von Cookie-Sicherheitskontexttoken konfiguriert. Die COM+-Integrationsdienste unterstützen keine Cookie-Sicherheitskontexttoken.|
|RevertingPrivilegeFailed|Fehler beim Zurücksetzungsvorgang mit der angegebenen Ausnahme.|
|RSTRAuthenticatorIncorrect|Der RequestSecurityTokenResponse CombinedHash ist fehlerhaft.|
|SecureConversationCancelNotAllowedFaultReason|Das Abbrechen sicherer Konversation wird durch die Bindung nicht zugelassen.|
|SecureConversationDriverVersionDoesNotSupportSession|Die konfigurierte SecureConversation-Version unterstützt keine Sitzungen. Verwenden Sie WSSecureConversationFeb2005 oder höher.|
|SecureConversationRequiredByReliableSession|Es kann keine zuverlässige Sitzung ohne sichere Konversation eingerichtet werden. Aktivieren Sie die sichere Konversation.|
|SecurityAuditFailToLoadDll|Die angegebene Dynamic Link Library (DLL) wurde nicht geladen.|
|SecurityAuditNotSupportedOnChannelFactory|SecurityAuditBehavior wird für die Kanalfactory nicht unterstützt.|
|SecurityAuditPlatformNotSupported|Das Schreiben von Überwachungsmeldungen in das Sicherheitsprotokoll wird von der aktuellen Plattform nicht unterstützt. Sie müssen die Überwachungsmeldungen in das Anwendungsprotokoll schreiben.|
|SecurityBindingElementCannotBeExpressedInConfig|Für den Endpunkt wurde eine Sicherheitsrichtlinie importiert. Die Sicherheitsrichtlinie enthält Anforderungen, die nicht in einer WCF (Windows Communication Foundation)-Konfiguration dargestellt werden können. Suchen Sie nach einem Kommentar zu den SecurityBindingElement-Parametern, die in der generierten Konfigurationsdatei erforderlich sind. Erstellen Sie mithilfe von Code das richtige Bindungselement. Die Bindungskonfiguration in der Konfigurationsdatei ist nicht sicher.|
|SecurityBindingSupportsOneWayOnly|Die SecurityBinding für die angegebene Bindung des angegebenen Vertrags unterstützt nur OneWay-Vorgänge.|
|SecurityContextDoesNotAllowImpersonation|Der Identitätswechsel kann nicht gestartet werden, weil der SecurityContext für die UltimateReceiver-Rolle aus der Anforderungsnachricht mit der angegebenen Aktion keiner Windows-Identität zugeordnet ist.|
|SecurityListenerClosing|Der Listener nimmt keine neuen sicheren Konversationen an, da er gerade geschlossen wird.|
|SecurityListenerClosingFaultReason|Der Server nimmt keine neuen sicheren Konversationen an, da er gerade geschlossen wird. Wiederholen Sie den Vorgang zu einem späteren Zeitpunkt.|
|SecurityProtocolFactoryShouldBeSetBeforeThisOperation|Die Sicherheitsprotokollfactory muss festgelegt werden, bevor dieser Vorgang ausgeführt wird.|
|SecuritySessionAbortedFaultReason|Die Sicherheitssitzung wurde beendet. Möglicherweise wurden zu lange keine Meldungen dieser Sitzung empfangen.|
|SecuritySessionKeyIsStale|Der Sitzungsschlüssel muss erneuert werden, bevor Anwendungsnachrichten gesichert werden können.|
|SecuritySessionLimitReached|Es kann keine Sicherheitssitzung erstellt werden. Wiederholen Sie den Vorgang zu einem späteren Zeitpunkt.|
|SecuritySessionNotPending|Es steht keine Sicherheits Sitzung mit der angegebenen ID aus.|
|SecurityTokenParametersHasIncompatibleInclusionMode|Die angegebene Bindung ist mit einem Sicherheitstokenparameter konfiguriert, der über einen inkompatiblen Sicherheitstoken-Einfügemodus verfügt. Geben Sie einen anderen Sicherheitstoken-Einfügemodus an.|
|SecurityVersionDoesNotSupportEncryptedKeyBinding|Die angegebene Bindung für den angegebenen Vertrag wurde mit einer inkompatiblen Sicherheitsversion konfiguriert, die keine nicht zugewiesenen Verweise für EncryptedKeys unterstützt. Verwenden Sie mindestens den angegebenen Wert als Sicherheitsversion für die Bindung.|
|SecurityVersionDoesNotSupportSignatureConfirmation|Die angegebene SecurityVersion unterstützt keine Signaturbestätigung. Verwenden Sie eine neuere SecurityVersion.|
|SecurityVersionDoesNotSupportThumbprintX509KeyIdentifierClause|Die angegebene Bindung für den angegebenen Vertrag ist mit einer Sicherheitsversion konfiguriert, die keine externen Verweise auf X.509-Token mithilfe des Fingerabdruckwerts des Zertifikats unterstützt. Verwenden Sie mindestens den angegebenen Wert als Sicherheitsversion für die Bindung.|
|SenderSideSupportingTokensMustSpecifySecurityTokenParameters|Sicherheitstokenparameter müssen für jede Nachricht mit unterstützenden Token angegeben werden.|
|ServerCertificateNotProvided|Der Empfänger hat kein Zertifikat bereitgestellt. Dieses Zertifikat ist für das TLS-Protokoll erforderlich. Beide Parteien müssen Zugriff auf die Zertifikate haben.|
|SignatureConfirmationNotSupported|Die konfigurierte SecurityVersion unterstützt keine Signaturbestätigungen. Verwenden Sie WSSecurityXXX2005 oder höher.|
|SignatureConfirmationRequiresRequestReply|Die Protokollfactory muss Anforderung/Antwort-Sicherheit unterstützen, um Signaturbestätigung zu bieten.|
|SignatureNotExpected|Für diese Nachricht wird keine Signatur erwartet.|
|SigningTokenHasNoKeys|Das angegebene Signaturtoken verfügt über keine Schlüssel. Das Sicherheitstoken wird in einem Kontext verwendet, der kryptografische Vorgänge erfordert. Entweder unterstützt der Tokentyp keine kryptografischen Vorgänge oder die bestimmte Tokeninstanz enthält keine kryptografischen Schlüssel. Überprüfen Sie Ihre Konfiguration, um sicherzustellen, dass keine nicht kryptografiefähigen Tokentypen (beispielsweise UserNameSecurityToken) in einem Kontext angegeben werden, der Kryptografievorgänge erfordert (beispielsweise ein unterzeichnendes Token).|
|SpnegoImpersonationLevelCannotBeSetToNone|Die Security Support Provider Interface (SSPI) unterstützt die Identitätswechselebene "None" nicht. Geben Sie eine gültige Identifikationsebene, eine gültige Identitätswechselebene oder eine gültige Delegationsebene an.|
|SslClientCertMustHavePrivateKey|Das angegebene Zertifikat muss einen privaten Schlüssel aufweisen. Der Prozess muss über Zugriffsrechte für den privaten Schlüssel verfügen.|
|SslServerCertMustDoKeyExchange|Das angegebene Zertifikat muss einen privaten Schlüssel aufweisen, der den Schlüsselaustausch ermöglicht. Der Prozess muss über Zugriffsrechte für den privaten Schlüssel verfügen.|
|StandardsManagerCannotWriteObject|Das angegebene Objekt kann vom Tokenserialisierungsprogramm nicht serialisiert werden.  Wenn es sich hierbei um einen benutzerdefinierten Typ handelt, müssen Sie ein benutzerdefiniertes Serialisierungsprogramm bereitstellen.|
|TimeStampHasCreationAheadOfExpiry|Der Sicherheitszeitstempel ist ungültig, weil der Wert für den Erstellungszeitpunkt größer als oder gleich dem Wert für den Ablaufzeitpunkt ist.|
|TimeStampHasCreationTimeInFuture|Der Sicherheitszeitstempel ist ungültig, weil der Erstellungszeitpunkt in der Zukunft liegt. Die aktuelle Uhrzeit ist angegeben, und die erlaubte Taktverschiebung ist angegeben.|
|TimeStampHasExpiryTimeInPast|Der Sicherheitszeitstempel ist veraltet, weil der Ablaufzeitpunkt in der Vergangenheit liegt. Die aktuelle Uhrzeit ist angegeben, und die erlaubte Taktverschiebung ist angegeben.|
|TimeStampWasCreatedTooLongAgo|Der Sicherheitszeitstempel ist veraltet, weil der Erstellungszeitpunkt zu weit in der Vergangenheit liegt. Die aktuelle Uhrzeit, die maximale Lebensdauer des Zeitstempels und die erlaubte Taktverschiebung werden angegeben.|
|TokenProviderCannotGetTokensForTarget|Der Tokenanbieter kann keine Token für das angegebene Ziel abrufen.|
|TooManyIssuedSecurityTokenParameters|Ein Abschnitt der verbundenen Sicherheitskette enthält mehrere IssuedSecurityTokenParameters. Das InfoCard-System unterstützt nur einen IssuedSecurityTokenParameter für jeden Abschnitt.|
|TransportDoesNotProtectMessage|Die angegebene Bindung für den angegebenen Vertrag ist mit einem Authentifizierungsmodus konfiguriert, der Integrität und Vertraulichkeit auf der Transportebene erfordert. Der Transport kann jedoch keine Integrität und Vertraulichkeit bereitstellen.|
|TrustApr2004DoesNotSupportCertainIssuedTokens|WSTrustApr2004 unterstützt herausgebende X.509-Zertifikate oder EncryptedKeys nicht. Verwenden Sie WSTrustFeb2005 oder höher.|
|TrustDriverVersionDoesNotSupportSession|Die konfigurierte Trust-Version unterstützt keine Sitzungen. Verwenden Sie WSTrustFeb2005 oder höher.|
|UnableToCreateICryptoFromTokenForSignatureVerification|Aus dem angegebenen Token zur Signaturüberprüfung kann keine ICrypto-Schnittstelle erstellt werden.|
|UnableToCreateSymmetricAlgorithmFromToken|Der angegebene symmetrische Algorithmus kann nicht aus dem Token erstellt werden.|
|UnableToDeriveKeyFromKeyInfoClause|Die angegebene KeyInfo-Klausel wurde in das angegebene Token aufgelöst. Dieses enthält keinen symmetrischen Schlüssel, der zur Ableitung verwendet werden kann.|
|UnableToFindTokenAuthenticator|Es wurde kein Tokenauthentifizierer für den angegebenen Tokentyp gefunden. Token dieses Typs können gemäß den aktuellen Sicherheitseinstellungen nicht akzeptiert werden.|
|UnableToLoadCertificateIdentity|Die in der Konfiguration angegebene X.509-Zertifikatsidentität kann nicht geladen werden.|
|UnexpectedEmptyElementExpectingClaim|Das angegebene Element aus dem angegebenen Namespace ist leer und gibt keinen gültigen Identitätsanspruch an.|
|UnknownEncodingInBinarySecurityToken|Unbekannte Codierung beim Lesen des binären Sicherheitstokens.|
|UnsecuredMessageFaultReceived|Ein nicht gesicherter oder fehlerhaft gesicherter Fehler wurde vom anderen Teilnehmer empfangen. Den Fehlercode und Details finden Sie in der inneren FaultException.|
|UnsupportedPasswordType|Das angegebene Benutzernamentoken weist einen nicht unterstützten Kennworttyp auf.|
|UnsupportedSecureConversationBootstrapProtectionRequirements|Die Sicherheitsrichtlinie kann nicht importiert werden. Die Schutzanforderungen für die sichere Konversations-Bootstrapbindung werden nicht unterstützt. Die Schutzanforderungen für die sichere Konversations-Bootstrapbindung sehen vor, dass sowohl die Anforderung als auch die Antwort signiert und verschlüsselt sein müssen.|
|UnsupportedSecurityPolicyAssertion|Es wurde eine nicht unterstützte Sicherheitsrichtlinienassertion beim Sicherheitsrichtlinienimport erkannt.|
