---
title: IdentityModel-Ausnahmen
ms.date: 03/30/2017
ms.assetid: 4ef34497-8ff5-4621-b773-7731cc721231
ms.openlocfilehash: 08d81f4eb35d0f4bda3997d6ab4dfd0ec10407e1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275036"
---
# <a name="identitymodel-exceptions"></a>IdentityModel-Ausnahmen

In diesem Thema werden alle Ausnahmen aufgelistet, die vom IdentityModel generiert werden.  
  
## <a name="exception-list"></a>Ausnahmeliste  
  
|Ressourcencode|Aktuelle Zeichenfolge|  
|-------------------|--------------------|  
|ValueMustBeOf2Types|Der Wert dieses Arguments muss einer dieser zwei Typen sein.|  
|SAMLSubjectNameIdentifierRequiresNameValue|Der für einen SamlNameIdentifier angegebene "Name" darf nicht NULL sein kann oder die Länge 0 (null) haben.|  
|TraceCodeIssuanceTokenProviderEndSecurityNegotiation|Der IssuanceTokenProvider hat die Sicherheitsaushandlung abgeschlossen.|  
|TraceCodeSecurityNewServerSessionKeyIssued|Ein neuer Sicherheitssitzungsschlüssel wurde vom Server ausgegeben.|  
|SAMLAttributeMissingNameAttributeOnRead|Der für das SamlAttribute gelesene "Name" fehlt oder hat die Länge 0 (null).|  
|UnknownICryptoType|Die ICrypto-Implementierung wird nicht unterstützt.|  
|TraceCodeSecurityTokenProviderClosed|Der Sicherheitstokenanbieter wurde geschlossen.|  
|SAMLUnableToLoadAdvice|Das Element konnte nicht geladen werden \<saml:advice> .|  
|SAMLAuthenticationStatementMissingAuthenticationMethodOnRead|Das für eine SamlAuthenticationStatement gelesene Attribut "AuthenticationMethod" fehlt oder hat die Länge 0 (null).|  
|UnsupportedTransformAlgorithm|Nicht unterstützter Transformieren- oder Kanonisierungsalgorithmus.|  
|SAMLAudienceRestrictionShouldHaveOneAudience| SamlAudienceRestrictionCondition muss wenigstens eine Zielgruppe (URI) enthalten.|  
|SAMLEvidenceShouldHaveOneAssertion|SamlEvidence muss entweder durch ID oder Verweis auf wenigstens eine SamlAssertion verweisen.|  
|SAMLAudienceRestrictionInvalidAudienceValueOnRead|Der gelesenen SamlAudienceRestrictionCondition fehlt ein Wert im Element "Audience".|  
|X509ChainBuildFail|Die Kettenerstellung dieses bestimmten X.509-Zertifikats ist fehlgeschlagen. Das Zertifikat, das verwendet wurde, besitzt eine Vertrauenswürdigkeitskette, die nicht überprüft werden kann. Ersetzen Sie das Zertifikat, oder ändern Sie certificateValidationMode.|  
|XDCannotFindValueInDictionaryString|Diese bestimmte Wert-ID wurde nicht in der Wörterbuchzeichenfolge gefunden.|  
|TraceCodeImportSecurityChannelBindingEntry|Sicherheits-ImportChannelBinding wird gestartet.|  
|PrivateKeyExchangeNotSupported|Der private Schlüssel unterstützt die Austausch-KeySpec nicht.|  
|TokenProviderUnableToGetToken|Dieser bestimmte Tokenanbieter konnte kein Sicherheitstoken bereitstellen.|  
|SAMLEntityCannotBeNullOrEmpty|Diese bestimmte SamlAssertion-Entität kann nicht NULL oder leer sein.|  
|SAMLAssertionRequireOneStatement|SamlAssertion erfordert wenigstens eine Anweisung. Stellen Sie sicher, dass Sie der SamlAssertion, die Sie erstellen, mindestens ein SamlStatement hinzugefügt haben.|  
|AESInvalidInputBlockSize|Die Eingabegröße muss ein Vielfaches von bestimmten Bytes sein.|  
|AESCryptAcquireContextFailed|Konnte den CSP-Kontext nicht abrufen.|  
|SAMLAssertionRequireOneStatementOnRead|Die SamlAssertion, die gelesen wurde, enthielt kein SamlStatement. Eine SamlAssertion muss mindestens ein SamlStatement enthalten.|  
|TraceCodeSecuritySessionClosedFaultReceived|Die Clientsicherheitssitzung hat einen "Sitzung wurde geschlossen"-Fehler vom Server empfangen.|  
|TraceCodeIssuanceTokenProviderRedirectApplied|IssuanceTokenProvider hat einen Umleitungsheader angewendet.|  
|TraceCodeSecuritySessionClosedFaultSendFailure|Beim Senden eines "Sicherheitssitzung wurde geschlossen"-Fehlers an den Client ist ein Fehler aufgetreten.|  
|ValueMustBeZero|Der Wert dieses Arguments muss 0 sein.|  
|SAMLUnableToResolveSignatureKey|Kann den in der SamlAssertion-Signatur gefundenen SecurityKeyIdentifier nicht auflösen. Die SamlAssertion-Signatur kann für diesen bestimmten Aussteller nicht überprüft werden.|  
|X509IsNotInTrustedStore|Dieses bestimmte X.509-Zertifikat befindet sich nicht im Speicher für vertrauenswürdige Personen.|  
|SAMLElementNotRecognized|Dieses bestimmte Element wird nicht unterstützt.|  
|SAMLAuthorizationDecisionStatementMissingResourceAttributeOnRead|Das für ein SamlAuthorizationDecisionStatement gelesene Attribut "Resource" fehlt oder hat die Länge 0 (null).|  
|SamlTokenMissingSignature|SamlAssertion ist nicht signiert. SamlAssertions können signiert werden, indem man die SigningCredentials festlegt.|  
|ExpectedElementMissing|Das erwartete Element mit diesem bestimmten Namespace fehlt.|  
|NoKeyIdentifierClauseFound|Keine Klausel dieses bestimmten Typs wurde im SecurityKeyIdentifier gefunden.|  
|MissingPrivateKey|Der private Schlüssel liegt nicht im X.509-Zertifikat vor.|  
|UnexpectedEOFFromReader|Unerwarteter EOF von XML-Reader.|  
|UnsupportedKeyDerivationAlgorithm|Dieser bestimmte Schlüsselableitungsalgorithmus wird nicht unterstützt.|  
|TokenDoesNotSupportKeyIdentifierClauseCreation|Dieses bestimmte Token unterstützt die bestimmte Schlüsselbezeichner-Klauselerstellung nicht.|  
|LastMessageNumberExceeded|Ein Verstoß des Sequenznummernprotokolls wurde erkannt.|  
|SymmetricKeyLengthTooShort|Die Länge des angegebenen symmetrischen Schlüssels ist zu niedrig.|  
|SAMLAuthorityBindingMissingAuthorityKindOnRead|In der gelesenen SamlAuthorityBinding wurde ein "AuthorityKind" gefunden, das gefehlt hatte oder die Länge 0 (null) besaß.  Dies ist nicht zulässig.|  
|XmlTokenBufferIsEmpty|XmlTokenBuffer ist leer.|  
|InvalidXmlQualifiedName|Es wurde ein für XML qualifizierter Name erwartet, aber ein ungültiger Name gefunden.|  
|SAMLAuthorityKindMissingName|Der XmlQualifiedName, der "AuthorityKind" in SamlAuthorityBinding darstellt, kann nicht NULL sein oder die Länge 0 (null) besitzen.|  
|AESCryptEncryptFailed|Konnte diese bestimmten Daten nicht verschlüsseln.|  
|AuthorizationContextCreated|Autorisierungskontext über diese bestimmte ID wird erstellt.|  
|SamlSerializerUnableToReadSecurityKeyIdentifier|Der SamlSerializer enthält keinen SecurityTokenSerializer, der dazu fähig ist, den SecurityKeyIdentifier zu lesen. Wenn Sie einen benutzerdefinierten SecurityKeyIdentifier verwenden, müssen Sie einen benutzerdefinierten SecurityTokenSerializer zur Verfügung stellen.|  
|TraceCodeIssuanceTokenProviderServiceTokenCacheFull|Der IssuanceTokenProvider hat den Diensttokencache eingeschränkt.|  
|TraceCodeSecurityTokenProviderOpened|Sicherheitstokenanbieter wurde geöffnet.|  
|PublicKeyNotRSA|Der öffentliche Schlüssel ist kein RSA-Schlüssel.|  
|InvalidReaderState|Dieser bestimmte Zustand ist für den angegebenen Eingabeleser ungültig.|  
|UnableToResolveReferenceUriForSignature|Unfähig, den bestimmten URI in der Signatur aufzulösen, um den Digest zu berechnen.|  
|EmptyBase64Attribute|Für den erforderlichen base64-Attributnamen und den Namespace wurde ein leerer Wert gefunden.|  
|SAMLSubjectRequiresConfirmationMethodWhenConfirmationDataOrKeyInfoIsSpecified|Die SAML SubjectConfirmation erfordert eine Bestätigungsmethode, wenn die Bestätigungsdaten oder KeyInfo angegeben werden.|  
|SAMLAudienceRestrictionShouldHaveOneAudienceOnRead|Die gelesene SamlAudienceRestrictionCondition muss wenigstens einen "Audience"-Wert enthalten. Es wurde keiner gefunden.|  
|TokenProviderUnableToRenewToken|Dieser bestimmte Tokenanbieter kann das Sicherheitstoken nicht erneuern.|  
|AESIVLengthNotSupported|Dieses bestimmte Bits-IV wird nicht unterstützt. Nur 128 Bits-IV wird unterstützt.|  
|SAMLAuthorityBindingMissingAuthorityKind|Eine SamlAuthorityBinding muss einen "AuthorityKind" enthalten, der nicht NULL ist.|  
|TraceCodeSecuritySessionDemuxFailure|Die eingehende Nachricht ist kein Teil einer vorhandenen Sicherheitssitzung.|  
|TokenRenewalNotSupported|Dieser bestimmte Tokenanbieter unterstützt keine Tokenerneuerung.|  
|AtLeastOneReferenceRequired|In einer Signatur ist mindestens ein Verweis erforderlich.|  
|SAMLSignatureAlreadyRead|Die Signatur wird bereits in der SAML-Assertion gelesen.|  
|AlgorithmAndPrivateKeyMisMatch|Der angegebene Algorithmus und der private Schlüssel passen nicht zusammen.|  
|EmptyTransformChainNotSupported|Die leere Transformationskette wird nicht unterstützt.|  
|SspiWrapperEncryptDecryptAssert1|Sspiwrapper:: verschlüsseltdecrypthelper&#124; ' Offset ' liegt außerhalb des zulässigen Bereichs.|  
|SspiWrapperEncryptDecryptAssert2|Sspiwrapper:: verschlüsseltdecrypthelper&#124; ' size ' liegt außerhalb des zulässigen Bereichs. SecurityTokenManagerCannotCreateAuthenticatorForRequirement=Der Sicherheitstoken-Manager kann keinen Tokenauthentifizierer für diese bestimmte Anforderung erstellen.|  
|UnableToCreateKeyedHashAlgorithm|Unfähig, einen KeyedHashAlgorithm aus dem bestimmten Wert für den bestimmten Signaturalgorithmus zu erstellen.|  
|SAMLUnableToLoadAssertion|Das \<saml:assertion> Element konnte nicht geladen werden.|  
|X509FindValueMismatchMulti|Dieser bestimmte X509FindType erfordert, dass der Typ des Arguments findValue einen von 2 Werten annimmt. Das Argument „findValue“ ist ein anderer Typ.|  
|TraceCodeSecurityIdentityDeterminationSuccess|Identität wurde für eine EndpointAddress bestimmt.|  
|UndefinedUseOfPrefixAtElement|Dieses bestimmte Präfix, das beim Element verwendet wird, verfügt über keinen definierten Namespace.|  
|TraceCodeSecuritySessionResponderOperationFailure|Der Sicherheitssitzungsvorgang am Server ist fehlgeschlagen.|  
|CannotFindCert|Konnte das X.509-Zertifikat mit diesen bestimmten Suchkriterien nicht finden: StoreName, StoreLocation, FindType, FindValue.|  
|X509InvalidUsageTime|Diese bestimmte X.509-Zertifikatsbenutzungsdauer ist ungültig. Die Benutzungsdauer fällt nicht zwischen die erforderliche NotBefore-Zeit und NotAfter-Zeit.|  
|TraceCodeSecurityIdentityDeterminationFailure|Für eine EndpointAdress kann die Identität nicht bestimmt werden.|  
|AsyncObjectAlreadyEnded|Die End-Methode wurde für dieses asynchrone Ergebnisobjekt bereits aufgerufen.|  
|ExternalDictionaryDoesNotContainAllRequiredStrings|Das externe Wörterbuch enthält nicht alle Definitionen für die erforderlichen Zeichenfolgen. Diese bestimmte Zeichenfolge ist im Remotewörterbuch nicht verfügbar.|  
|TraceCodeSecuritySessionKeyRenewalFaultReceived|Die Clientsicherheitssitzung hat einen "Schlüsselerneuerungs"-Fehler vom Server empfangen.|  
|SAMLActionNameRequired|Die Zeichenfolge, die SamlAction darstellt, kann nicht NULL sein oder die Länge 0 (null) besitzen.|  
|SignatureVerificationFailed|Die Signaturüberprüfung ist fehlgeschlagen.|  
|TraceCodeSecurityContextTokenCacheFull|Der SecurityContextSecurityToken-Cache ist voll.|  
|SAMLAssertionMissingMajorVersionAttributeOnRead|Die für das SamlAssertion gelesene "MajorVersion" fehlt oder hat die Länge 0 (null).|  
|SamlAttributeClaimRightShouldBePossessProperty|Für diesen SamlAttribute-Konstruktor ist es erforderlich, dass "Right of the Claim" über den Wert System.IdentityModel.Claims.Rights.PossessProperty verfügt.|  
|AuthorizationPolicyEvaluated|Die Richtlinie mit dieser bestimmten ID wurde ausgewertet.|  
|SAMLUnableToLoadConditions<!-- the misspelling here is deliberate. -->|Das \<saml:conditions> Element konnte nicht geladen werden.|  
|AESKeyLengthNotSupported|Dieser bestimmte Bitschlüssel wird nicht unterstützt. Nur 128, 192 und 256 Bitschlüssel werden unterstützt.|  
|UserNameCannotBeEmpty|Der Benutzername darf nicht leer sein.|  
|AlgorithmAndPublicKeyMisMatch|Der angegebene Algorithmus und der öffentliche Schlüssel passen nicht zusammen.|  
|SAMLUnableToLoadCondition<!-- the misspelling here is deliberate. -->|Das \<saml:conditions> Element konnte nicht geladen werden.|  
|SamlAssertionMissingSigningCredentials|SigningCredentials wurde nicht auf SamlAssertion festgelegt. SamlAssertions müssen signiert werden; legen Sie gültige SigningCredentials auf SamlAssertion fest, um fortzufahren.|  
|SspiPayloadNotEncrypted|Die Binärdaten wurden nicht mit dem SSPI-Sicherheitskontext verschlüsselt.|  
|SAMLAuthorizationDecisionShouldHaveOneActionOnRead|Das SamlAuthorizationDecisionStatement, das gelesen wird, enthält keine SamlAction.|  
|TraceCodeSecurityBindingSecureOutgoingMessageFailure|Das Sicherheitsprotokoll kann die ausgehende Nachricht nicht sichern.|  
|UndefinedUseOfPrefixAtAttribute|Dieses bestimmte Präfix, das am bestimmten Attribut verwendet wird, verfügt über keinen definierten Namespace.|  
|NoInputIsSetForCanonicalization|Für das Schreiben von kanonisierter Ausgabe wurde keine Eingabe festgelegt.|  
|TraceCodeSecurityPendingServerSessionAdded|Dem Server wird eine ausstehende Sicherheitssitzung hinzugefügt.|  
|AsyncCallbackException|Ein AsyncCallback hat eine Ausnahme ausgelöst.|  
|PrivateKeyNotRSA|Der private Schlüssel ist kein RSA-Schlüssel.|  
|TraceCodeSecurityClientSessionKeyRenewed|Die Clientsicherheitssitzung hat den Sitzungsschlüssel erneuert.|  
|SAMLAuthorizationDecisionStatementMissingDecisionAttributeOnRead|Das für SamlAuthorizationDecisionStatement gelesene Attribut "Decision" fehlt oder hat die Länge 0 (null).|  
|SAMLAttributeNameAttributeRequired|Der für ein SamlAttribute angegebene "Name" darf nicht NULL sein oder die Länge 0 (null) haben.|  
|SamlSerializerRequiresExternalSerializers|Der SamlSerializer erfordert einen SecurityTokenSerializer, um den im Token vorhandenen SecurityKeyIdentifier zu serialisieren.|  
|UnableToResolveKeyReference|Die Tokenauflösung kann den bestimmten Sicherheitshauptverweis nicht auflösen.|  
|UnsupportedKeyWrapAlgorithm|Dieser bestimmte Schlüssel-Wrap-Algorithmus wird nicht unterstützt.|  
|SAMLAssertionMissingIssuerAttributeOnRead|Der für das SamlAttribute gelesene "Aussteller" fehlt oder hat die Länge 0 (null).|  
|TraceCodeIssuanceTokenProviderServiceTokenCacheFull|Der IssuanceTokenProvider hat das zwischengespeicherte Diensttoken verwendet.|  
|AESCryptGetKeyParamFailed|Konnte den bestimmten Schlüsselparameter nicht abrufen.|  
|InvalidNamespaceForEmptyPrefix|Der Namespace für das leere Präfix ist ungültig.|  
|AESCipherModeNotSupported|Dieser bestimmte Chiffremodus wird nicht unterstützt. Nur CBC wird unterstützt.|  
|ArgumentCannotBeEmptyString|Das Argument muss eine nicht leere Zeichenfolge sein.|  
|SAMLAssertionMissingMinorVersionAttributeOnRead|Die für das SamlAssertion gelesene "MinorVersion" fehlt oder hat die Länge 0 (null).|  
|SpecifiedStringNotAvailableInDictionary|Die angegebene Zeichenfolge ist kein Eintrag des aktuellen Wörterbuchs.|  
|KerberosApReqInvalidOrOutOfMemory|Der AP-REQ ist ungültig, oder das System verfügt nicht über genug Arbeitsspeicher.|  
|FailLogonUser|Der LogonUser ist für den angegebenen Benutzer fehlgeschlagen. Stellen Sie sicher, dass der Benutzer ein gültiges Windows-Konto besitzt.|  
|ValueMustBeNonNegative|Der Wert dieses Arguments muss nicht negativ sein.|  
|X509ValidationFail|Die angegebene X.509-Zertifikatsvalidierung ist fehlgeschlagen.|  
|TraceCodeSecuritySessionRequestorOperationSuccess|Der Sicherheitssitzungsvorgang wurde beim Client erfolgreich abgeschlossen.|  
|SAMLActionNameRequiredOnRead|Die für das SamlAttribute gelesene Zeichenkette fehlt oder hat die Länge 0.|  
|KerberosMultilegsNotSupported|Identität wird als UPN angegeben. Die Authentifizierung eines Diensts, der unter einem Benutzerkonto ausgeführt wird, erfordert Kerberos-Multi-Legs, das nicht unterstützt wird.|  
|SAMLAssertionIdRequired|Die "assertionId" für SamlAssertion kann nicht NULL oder leer sein.|  
|InvalidOperationForWriterState|Der angegebene Vorgang ist im angegebenen XmlWriter-Zustand ungültig.|  
|CannotValidateSecurityTokenType|Der angegebene Sicherheitstokenauthentifikator kann kein Token des angegebenen Typs überprüfen.|  
|X509FindValueMismatch|Der angegebene X509FindType erfordert, dass der Typ des Arguments „findValue“ der angegebene Wert ist. Das Argument „findValue“ ist ein anderer Typ.|  
|TraceCodeSecurityClientSessionCloseSent|Von der Clientsicherheitssitzung wurde eine 'Schließen'-Nachricht gesendet.|  
|SuiteDoesNotAcceptAlgorithm|Der angegebene Algorithmus wird für den angegebenen Vorgang von der angegebenen Algorithmussuite nicht akzeptiert|  
|TraceCodeSecuritySessionRequestorOperationFailure|Fehler beim Client-Sicherheitssitzungsvorgang.|  
|SAMLUnableToLoadStatement|Konnte kein SamlStatement laden.|  
|InnerReaderMustBeAtElement|Der innere Leser muss beim Element sein.|  
|UnableToCreateTokenReference|Konnte keinen Sicherheitstokenverweis erstellen.|  
|TraceCodeSecurityBindingIncomingMessageVerified|Das Sicherheitsprotokoll hat die eingehende Nachricht bestätigt.|  
|ObjectIsReadOnly|Das Objekt ist schreibgeschützt.|  
|TraceCodeSecurityClientSessionPreviousKeyDiscarded|Die Clientsicherheitssitzung hat den vorherigen Sitzungsschlüssel verworfen.|  
|SAMLTokenTimeInvalid|SamlToken ist nicht zeitgültig. Die aktuelle Zeit liegt außerhalb der wirksamen Zeit und der Ablaufzeitzeit des Tokens.|  
|TraceCodeSecurityIdentityVerificationSuccess|Identitätsüberprüfung war erfolgreich.|  
|SigningTokenHasNoKeys|Das angegebene Signaturtoken verfügt über keine Schlüssel.|  
|TraceCodeSecurityIdentityVerificationFailure|Identitätsüberprüfung ist fehlgeschlagen.|  
|AESCryptImportKeyFailed|Konnte das Schlüsselmaterial nicht importieren.|  
|FailInitializeSecurityContext|InitializeSecurityContent ist fehlgeschlagen. Stellen Sie sicher, dass der Dienstprinzipalname richtig ist.|  
|TraceCodeStreamSecurityUpgradeAccepted|Das Stream Security-Upgrade wurde erfolgreich akzeptiert.|  
|SAMLAuthorityBindingRequiresLocation|Das "Location"-Attribut, das auf der SamlAuthorityBinding angegeben wird, kann nicht NULL sein oder die Länge 0 (null) besitzen.|  
|PublicKeyNotDSA|Der öffentliche Schlüssel ist kein DSA-Schlüssel.|  
|ImpersonationLevelNotSupported|Die Authentifizierungsmodi, die Kerberos verwenden, unterstützen die angegebene Identitätswechselebene nicht. Geben Sie eine gültige Identifikation oder eine Identitätswechselebene an.|  
|RequiredTargetNotSigned|Für das Element mit der angegebenen ID ist es erforderlich, dass es signiert wird; dies ist aber nicht geschehen.|  
|SAMLAuthenticationStatementMissingAuthenticationInstanceOnRead|Das für eine SamlAuthenticationStatement gelesene Attribut "AuthenticationInstant" fehlt oder hat die Länge 0 (null).|  
|SAMLEvidenceShouldHaveOneAssertionOnRead|Der SamlEvidence, der gelesen wurde, enthält weder einen Verweis auf noch eine eingebettete SamlAssertion.|  
|LengthOfArrayToConvertMustGreaterThanZero|Die Länge des Arrays zum Konvertieren einer ganzen Zahl muss größer als 0 (null) sein.|  
|InvalidAsyncResult|Ungültiges AsyncResult.|  
|TraceCodeIssuanceTokenProviderRemovedCachedToken|Der IssuanceTokenProvider hat das abgelaufene Diensttoken entfernt.|  
|IncorrectUserNameFormat|Der Benutzername hat ein ungültiges Format. Das Format des Benutzernamens muss im Format "Benutzername" oder "Domäne \\ \ Benutzername" vorliegen.|  
|TraceCodeImportSecurityChannelBindingEntry|Sicherheits-ExportChannelBinding wird gestartet.|  
|UnsupportedInputTypeForTransform|Der angegebene Eingabetyp wird für die Transformation nicht unterstützt.|  
|CannotFindDocumentRoot|Der Stamm des Dokuments konnte nicht gefunden werden.|  
|XmlBufferQuotaExceeded|Die Größe, die notwendig ist, um den das Pufferkontingent übersteigenden XML-Inhalt zu puffern.|  
|TraceCodeSecuritySessionClosedResponseSendFailure|Beim Senden einer "Sicherheitssitzung wurde geschlossen"-Antwort an den Client ist ein Fehler aufgetreten.|  
|UnableToResolveReferenceInSamlSignature|Konnte den angegebenen Verweis in der SAML-Signatur mit AssertionID nicht auflösen.|  
|SAMLSubjectRequiresNameIdentifierOrConfirmationMethod|Ein SamlSubject erfordert, dass ein "NameIdentifier" oder eine "ConfirmationMethod" angegeben wird. Beide haben gefehlt.|  
|SAMLAttributeMissingNamespaceAttributeOnRead|Der für das SamlAttribute gelesene "Namespace" fehlt oder hat die Länge 0 (null).|  
|SAMLSubjectConfirmationClauseMissingConfirmationMethodOnRead|Auf der SamlSubjectConfirmation, die gelesen wird, kann keine "ConfirmationMethod" gefunden werden.|  
|SecurityTokenRequirementHasInvalidTypeForProperty|Die Tokenanforderung hat einen unerwarteten Typ für die angegebene Eigenschaft. Der erwartete Eigenschaftstyp hat einen anderen Wert.|  
|TraceCodeNegotiationTokenProviderAttached|NegotiationTokenProvider wurde angefügt.|  
|TraceCodeSpnegoClientNegotiationCompleted|Die SSPI-Aushandlung wurde von SpnegoTokenProvider abgeschlossen.|  
|SAMLUnableToLoadUnknownElement|Der ausgewählte SamlSerializer kann dieses Element nicht deserialisieren. Registrieren Sie einen benutzerdefinierten SamlSerializer, um benutzerdefinierte Elemente zu deserialisieren.|  
|CreateSequenceRefused|Die "Sequenz erstellen"-Anforderung wurde vom RM-Ziel abgelehnt.|  
|TraceCodeSecuritySessionRedirectApplied|Die Clientsicherheitssitzung wurde umgeleitet.|  
|SecurityTokenRequirementDoesNotContainProperty|Die Tokenanforderung enthält die angegebene Eigenschaft nicht.|  
|SAMLAttributeValueCannotBeNull|Bei einem der attributeValues, die in SamlAttribute gefunden wurden, stellte sich heraus, dass es einen NULL-Wert besitzt. Stellen Sie sicher, dass Listen nicht NULL sind, wenn sie das SamlAttribute erstellen.|  
|ValueMustBeGreaterThanZero|Der Wert dieses Arguments muss größer als 0 (null) sein.|  
|TraceCodeNegotiationAuthenticatorAttached|Der NegotiationTokenAuthenticator wurde angefügt.|  
|ValueMustBePositive||  
|SAMLAuthorizationDecisionShouldHaveOneAction|Ein SamlAuthorizationDecisionStatement muss wenigstens eine SamlAction enthalten.|  
|TraceCodeSecurityTokenAuthenticatorClosed|Ein Sicherheitstokenauthentifikator wurde geschlossen.|  
|TraceCodeSecurityAuditWrittenSuccess|Das Sicherheitsüberwachungsprotokoll wurde erfolgreich geschrieben.|  
|PrivateKeyNotDSA|Der private Schlüssel ist kein DSA-Schlüssel.|  
|MessageNumberRollover|Die maximale Sequenznummer für diese Sequenz wurde überschritten.|  
|AESPaddingModeNotSupported|Der angegebene Paddingmodus wird nicht unterstützt. Nur PKCS7 und ISO10126 werden unterstützt.|  
|SAMLSubjectRequiresNameIdentifierOrConfirmationMethodOnRead|Der erforderliche "NameIdentifier" und die "ConfirmationMethod"-Elemente können für das gelesene SamlSubject nicht gefunden werden.|  
|TraceCodeSecurityAuditWrittenFailure|Beim Schreiben ins Sicherheitsüberwachungsprotokoll ist ein Fehler aufgetreten.|  
|UnsupportedCryptoAlgorithm|Der angegebene crypto-Algorithmus wird in diesem Kontext nicht unterstützt.|  
|SigningTokenHasNoKeysSupportingTheAlgorithmSuite|Das Signiertoken verfügt über keinen Schlüssel, der die angegebene Algorithmussammlung unterstützt.|  
|SAMLNameIdentifierMissingIdentifierValueOnRead|Die für SamlIdentifier gelesene Zeichenkette "Identifier" fehlt.|  
|SAMLSubjectStatementRequiresSubject|Die SAML-Subjektanweisung erfordert einen angegebenen SAML-Betreff.|  
|TraceCodeSslClientCertMissing|Der SSL-Remoteclient hat ein erforderliches Zertifikat nicht bereitgestellt.|  
|SAMLTokenVersionNotSupported|Die angegebene Haupt- und Nebenversion werden nicht unterstützt.|  
|TraceCodeConfigurationIsReadOnly|Die Konfiguration ist schreibgeschützt.|  
|TraceCodeSecuritySessionRenewFaultSendFailure|Beim Senden eines Erneuerungsfehlers im Sicherheitssitzungsschlüssel an den Client ist ein Fehler aufgetreten.|  
|TraceCodeSecurityInactiveSessionFaulted|Der Server hat eine inaktive Sicherheitssitzung bemängelt.|  
|SAMLUnableToLoadAttribute|Konnte kein SamlAttribute laden.|  
|Psha1KeyLengthInvalid|Die angegebene PSHA1-Schlüssellänge ist ungültig.|  
|KeyIdentifierCannotCreateKey|Dieser SecurityKeyIdentifier verfügt über keine Klausel, die einen Schlüssel erstellen kann.|  
|X509IsNotInTrustedStore|Das angegebene X.509-Zertifikat befindet sich in einem Speicher für nicht vertrauenswürdige Zertifikate.|  
|UnexpectedXmlChildNode|Der angegebene untergeordnete XML-Knoten des angegebenen Typs ist für das angegebene Element unerwartet.|  
|TokenDoesNotMeetKeySizeRequirements|Die Schlüsselgrößenanforderungen der angegebenen Algorithmussammlung werden vom angegebenen Token nicht erfüllt.|  
|TraceCodeSecuritySessionRequestorStartOperation|Am Client wurde ein Sicherheitssitzungsvorgang gestartet.|  
|InvalidHexString|Ungültiges Hexadezimal-Zeichenfolgenformat.|  
|SamlAttributeClaimResourceShouldBeAString|Dieser SamlAttribute-Konstruktor erfordert, dass die Ressource des Anspruchs vom Typ "Zeichenfolge" ist.|  
|SamlSigningTokenNotFound|Die SamlAssertion wird signiert, aber das Token, der SamlAssertion signiert hat, kann nicht gefunden werden. Stellen Sie sicher, dass der SecurityTokenResolver das Token enthält, das SamlAssertion signiert hat.|  
|TraceCodeSecuritySpnToSidMappingFailure|Der ServicePrincipalName konnte keinem SecurityIdentifier zugeordnet werden.|  
|UnableToCreateSignatureFormatterFromAsymmetricCrypto|Konnte kein Signaturformatierungsprogramm für den angegebenen Algorithmus aus der angegebenen asymmetrischen Kryptografie erstellen.|  
|TraceCodeSecurityServerSessionClosedFaultSent|Die Serversicherheitssitzung hat einen "Sitzung wurde geschlossen"-Fehler an den Client gesendet.|  
|UnableToFindPrefix|Unfähig, das Präfix für das angegebene sichtbar genutzte Präfix des angegebenen Elements zu finden.|  
|TraceCodeSecurityTokenAuthenticatorOpened|Ein Sicherheitstokenauthentifikator wurde geöffnet.|  
|RequiredAttributeMissing|Das angegebene Attribut ist auf dem angegebenen Element erforderlich.|  
|LocalIdCannotBeEmpty|Die localId darf nicht leer sein. Geben Sie eine gültige "localId" an.|  
|ValueMustBeInRange|Der Wert dieses Arguments muss in den angegebenen Bereich fallen.|  
|TraceCodeIssuanceTokenProviderBeginSecurityNegotiation|IssuanceTokenProvider hat eine neue Sicherheitsaushandlung gestartet.|  
|InvalidNtMapping|Das angegebene X.509-Zertifikat konnte keinem Windows-Konto zugeordnet werden. Der Name der UPN-Betreffsalternative ist erforderlich.|  
|AESCryptSetKeyParamFailed|Konnte den angegebenen Schlüsselparameter nicht festlegen.|  
|TraceCodeSecuritySessionClosedResponseReceived|Die Clientsicherheitssitzung hat eine "Geschlossen"-Antwort vom Server empfangen.|  
|UnableToCreateSignatureDeformatterFromAsymmetricCrypto|Konnte kein Signaturdeformatierungsprogramm für den angegebenen Algorithmus aus der angegebenen asymmetrischen Kryptografie erstellen.|  
|TraceCodeIdentityModelAsyncCallbackThrewException|Ein asynchroner Rückruf hat eine Ausnahme ausgelöst.|  
|LengthMustBeGreaterThanZero|Die Länge dieses Arguments muss größer als 0 (null) sein.|  
|FoundMultipleCerts|Mehrere X.509-Zertifikate gefunden, die das angegebene Suchkriterium verwenden: StoreName, StoreLocation, FindType, FindValue. Stellen Sie einen spezifischeren Fundwert bereit.|  
|AtLeastOneTransformRequired|Das Transforms-Element muss mindestens eine Transformation enthalten.|  
|SAMLTokenNotSerialized|SamlAssertion konnte nicht nach XML serialisiert werden. Details finden Sie in der inneren Ausnahme.|  
|TraceCodeSecurityBindingOutgoingMessageSecured|Das Sicherheitsprotokoll hat die ausgehende Nachricht gesichert.|  
|KeyIdentifierClauseDoesNotSupportKeyCreation|Dieser SecurityKeyIdentifierClause unterstützt keine Schlüsselerstellung.|  
|UnableToResolveTokenReference|Die Tokenauflösung kann den bestimmten Tokenverweis nicht auflösen.|  
|UnsupportedEncryptionAlgorithm|Der angegebene Verschlüsselungsalgorithmus wird nicht unterstützt.|  
|SamlSerializerUnableToWriteSecurityKeyIdentifier|Der SamlSerializer enthält keinen SecurityTokenSerializer, der dazu fähig ist, den angegebenen SecurityKeyIdentifier zu serialisieren. Wenn Sie einen benutzerdefinierten SecurityKeyIdentifier verwenden, müssen Sie einen benutzerdefinierten SecurityTokenSerializer zur Verfügung stellen.|  
|SAMLAttributeShouldHaveOneValue|Es wurden keine Attributwerte gefunden. Ein SamlAttribute-Attribut muss mindestens über einen Attributwert verfügen.|  
|TraceCodeSecurityBindingVerifyIncomingMessageFailure|Das Sicherheitsprotokoll kann die eingehende Nachricht nicht prüfen.|  
|SamlSigningTokenMissing|Die an den SamlSecurityTokenAuthenticator übergebene SamlAssertion enthält kein Signiertoken.|  
|NoPrivateKeyAvailable|Es ist kein privater Schlüssel verfügbar.|  
|ValueMustBeOne|Der Wert dieses Arguments muss 1 sein.|  
|TraceCodeSecurityPendingServerSessionRemoved|Der Server hat eine ausstehende Sicherheitssitzung aktiviert.|  
|TraceCodeImportSecurityChannelBindingExit|Sicherheits-ImportChannelBinding abgeschlossen.|  
|X509CertStoreLocationNotValid|StoreLocation muss entweder LocalMachine oder CurrentUser sein.|  
|SettingdMayBeModifiedOnlyWhenTheWriterIsInStartState|Die Writer-Einstellungen dürfen nur geändert werden, wenn der Writer im Start-Zustand ist.|  
|ArgumentInvalidCertificate|Das Zertifikat ist ungültig.|  
|DigestVerificationFailedForReference|Digestüberprüfung für den angegebenen Verweis ist fehlgeschlagen.|  
|SAMLAuthorityBindingRequiresBinding|Das auf der SamlAuthorityBinding angegebene Attribut „Binding“ darf nicht NULL sein oder die Länge 0 (null) haben.|  
|AESInsufficientOutputBuffer|Der Ausgabepuffer muss größer als die angegebene Bytezahl sein.|  
|SAMLAuthorityBindingMissingBindingOnRead|Das für eine SamlAuthorityBinding gelesene Attribut „Binding“ fehlt oder hat die Länge 0 (null).|  
|SAMLAuthorityBindingInvalidAuthorityKind|Die SamlAuthorityBinding, die gelesen wird, besitzt eine ungültige AuthorityKind. Das Format von AuthorityKind muss ein QName sein.|  
|ProvidedNetworkCredentialsForKerberosHasInvalidUserName|Die für das Kerberos-Token angegebenen NetworkCredentials besitzen keinen gültigen Benutzernamen.|  
|SSPIPackageNotSupported|Das angegebene SSPI-Paket wird nicht unterstützt.|  
|TokenCancellationNotSupported|Der angegebene Tokenanbieter unterstützt keine Tokenstornierung.|  
|UnboundPrefixInQName|Ein ungebundenes Präfix wird im angegebenen qualifizierten Namen verwendet.|  
|SAMLAuthorizationDecisionResourceRequired|Die für die SamlAuthorizationDecisionStatement angegebene "Resource" darf nicht NULL sein oder die Länge 0 (null) haben.|  
|TraceCodeSecurityNegotiationProcessingFailure|Fehler bei der Dienstsicherheitsaushandlung.|  
|SAMLAssertionIssuerRequired|Der für eine SamlAssertion angegebene "Issuer" darf nicht NULL oder leer sein.|  
|UnableToCreateHashAlgorithmFromAsymmetricCrypto|Konnte keinen Hashalgorithmus für den angegebenen Algorithmus aus der angegebenen asymmetrischen Kryptografie erstellen.|  
|SamlUnableToExtractSubjectKey|Der SecurityKeyIdentifier, der im SamlSubject gefunden wurde, kann nicht zu einem SecurityToken aufgelöst werden. Der SecurityTokenResolver muss ein SecurityToken enthalten, auf das der SecurityKeyIdentifier aufgelöst wird.|  
|ChildNodeTypeMissing|Das angegebene XML-Element besitzt kein untergeordnetes Element des angegebenen Typs.|  
|TraceCodeSecurityPendingServerSessionClosed|Die ausstehende Sicherheitssitzung wurde vom Server geschlossen.|  
|TraceCodeSecuritySessionClosedResponseSent|Die Serversicherheitssitzung hat eine "Schließen"-Antwort an den Client gesendet.|  
|TraceCodeSecurityIdentityHostNameNormalizationFailure|Der Hostnamenteil einer Endpunktadresse kann nicht normalisiert werden.|  
|FailAcceptSecurityContext|Der AcceptSecurityContext ist fehlgeschlagen.|  
|EmptyXmlElementError|Das angegebene Element kann nicht leer sein.|  
|PrefixNotDefinedForNamespace|In diesem Kontext wird kein Präfix für den angegebenen Namespace definiert und kann auch nicht deklariert werden.|  
|SAMLAuthorizationDecisionHasMoreThanOneEvidence|Es wurde herausgefunden, dass das SamlAuthorizationDecisionStatement, das gelesen wurde, mehr als einen Beweis enthält. Dies ist nicht zulässig.|  
|SamlTokenAuthenticatorCanOnlyProcessSamlTokens|Der SamlSecurityTokenAuthenticator kann nur SamlSecurityTokens verarbeiten. Der angegebene SecurityTokenType wurde empfangen.|  
|SAMLAttributeStatementMissingAttributeOnRead|Das SamlAttributeStatement, das gelesen wird, enthält keine "SamlAttribute"-Elemente. Dies ist nicht zulässig.|  
|CouldNotFindNamespaceForPrefix|Kann den Namespace für das angegebene Präfix nicht nachschlagen.|  
|TraceCodeExportSecurityChannelBindingExit|Sicherheits-ExportChannelBinding abgeschlossen.|  
|AESCryptDecryptFailed|Konnte die angegebenen Daten nicht entschlüsseln.|  
|SAMLAttributeNamespaceAttributeRequired|Der für ein SamlAttribute angegebene "Namespace" darf nicht Null sein oder die Länge 0 (null) haben.|  
|TraceCodeSpnegoServiceNegotiationCompleted|Die SSPI-Aushandlung wurde von SpnegoTokenAuthenticator abgeschlossen.|  
|TraceCodeSecurityServerSessionRenewalFaultSent|Die Serversicherheitssitzung hat einen Schlüsselerneuerungsfehler an den Client gesendet.|  
|AlgorithmMismatchForTransform|Auf dem Algorithmus für die Transformation ist ein Konflikt aufgetreten.|  
|UserNameAuthenticationFailed|Die Authentifizierung eines Benutzernamens/Kennworts mit dem angegebenen Mechanismus ist fehlgeschlagen. Der Benutzer ist nicht authentifiziert.|  
|SamlInvalidSigningToken|Die SamlAssertion wurde mit einem Token signiert, das nicht nach dem Protokoll überprüft wurde. Wenn Sie X.509-Zertifikate verwenden, untersuchen Sie die Validierungssemantik.|  
|TraceCodeSecurityServerSessionKeyUpdated|Der Sicherheitssitzungsschlüssel wurde vom Server aktualisiert.|  
|TraceCodeSecurityServerSessionCloseReceived|Die Serversicherheitssitzung hat eine "Schließen"-Antwort vom Client empfangen.|  
|SAMLAuthenticationStatementMissingSubject|Dem SamlAuthenticationStatement fehlt das erforderliche SamlSubjectStatement.|  
|UnexpectedEndOfFile|Unerwartetes Dateiende.|  
|UnsupportedAlgorithmForCryptoOperation|Der angegebene Algorithmus wird für den angegebenen Vorgang nicht unterstützt.|  
|XmlLangAttributeMissing|Das erforderliche Attribut "xml:lang" fehlt.|  
|TraceCodeSecurityImpersonationSuccess|Der Sicherheitsidentitätswechsel auf dem Server wurde erfolgreich ausgeführt.|  
|SAMLAuthorityBindingMissingLocationOnRead|Das für eine SamlAuthorityBinding gelesene Attribut "Location" fehlt oder hat die Länge 0 (null).|  
|SAMLAttributeStatementMissingSubjectOnRead|Das Element "SamlSubject" für SamlAttributeStatement fehlt.|  
|SAMLAuthorizationDecisionStatementMissingSubjectOnRead|Das für SamlAuthorizationDecisionStatement gelesene Element "SamlSubject" fehlt.|  
|SAMLBadSchema|Beim Lesen einer SamlAssertion wurde herausgefunden, dass das angegebene Element nicht dem Schema entspricht.|  
|SAMLAssertionIDIsInvalid|Die angegebene "assertionId" für SamlAssertion muss mit einem Buchstaben oder "_" beginnen.|  
|TraceCodeSecurityActiveServerSessionRemoved|Eine aktive Sicherheitssitzung wurde vom Server gelöscht.|  
|UnableToCreateKeyedHashAlgorithmFromSymmetricCrypto|Konnte keinen keyedHashAlgorithm für den angegebenen Algorithmus aus der angegebenen symmetrischen Kryptografie erstellen.|  
|SAMLAuthenticationStatementMissingAuthenticationMethod|Die für eine SamlAuthenticationStatement gelesene "AuthenticationMethod" darf nicht Null sein oder die Länge 0 (null) haben.|  
|TraceCodeSecurityImpersonationFailure|Sicherheitsidentitätswechsel am Server fehlgeschlagen.|  
|Standard|(Standardwert)|  
|UnsupportedNodeTypeInReader|Der angegebene Knotentyp mit dem angegebenen Namen wird nicht unterstützt.|
