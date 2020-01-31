---
title: WCF-Sicherheitsterminologie
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], terminology
- security glossary [WCF]
- security terms [WCF]
ms.assetid: 68dde024-8e51-40ba-804f-ec52d85e9ca9
ms.openlocfilehash: 6751513b72f732bd7392de11a203467a9ead1bce
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743344"
---
# <a name="wcf-security-terminology"></a>WCF-Sicherheitsterminologie
Einige der Begriffe, die im Zusammenhang mit Sicherheitsaspekten von Bedeutung sind, sind möglicherweise nicht allgemein bekannt. In diesem Thema werden daher einige Sicherheitsbegriffe kurz erläutert, ohne alle Facetten des jeweiligen Begriffs zu beleuchten.  
  
 Weitere Informationen zu den in der Windows Communication Foundation (WCF)-Dokumentation verwendeten Begriffen finden Sie unter [grundlegende Windows Communication Foundation Konzepte](../../../../docs/framework/wcf/fundamental-concepts.md).  
  
 Zugriffssteuerungsliste  
 Eine Liste mit den Arten von Sicherheitsschutz, der auf ein Objekt angewendet wird. (Bei einem Objekt kann es sich um eine Datei, einen Prozess, ein Ereignis oder eine beliebige andere Sicherheits Beschreibung handeln.) Ein Eintrag in einer ACL ist ein Zugriffs Steuerungs Eintrag (ACE). Es gibt zwei Typen von Zugriffssteuerungslisten: freigegebene Zugriffssteuerungslisten und Systemzugriffssteuerungslisten.  
  
 Authentifizierung  
 Der Prozess, in dem ein Benutzer, ein Computer, ein Dienst oder ein Prozess auf Übereinstimmung mit der vorgegebenen Identität überprüft werden.  
  
 Autorisierung  
 Die Kontrolle des Zugriffs auf und der Rechte für eine Ressource, Beispielsweise können die Mitglieder einer Gruppe eine Datei lesen, während die Mitglieder einer anderen Gruppe diese auch bearbeiten dürfen.  
  
 Zertifizierungsstellenzertifikat  
 Identifiziert die Zertifizierungsstelle, die Zertifikate zur Authentifizierung von Clients und Servern ausstellt, die von diesen angefordert werden. Da Sie einen öffentlichen Schlüssel enthält, der in digitalen Signaturen verwendet wird, wird Sie auch als *Signaturzertifikat*bezeichnet. Wenn die Zertifizierungsstelle eine Stamm Zertifizierungsstelle ist, wird das Zertifizierungsstellen Zertifikat möglicherweise als Stamm *Zertifikat*bezeichnet. Wird manchmal auch als *Site Zertifikat*bezeichnet.  
  
 Zertifizierungsstellenhierarchie  
 Eine Zertifizierungsstellenhierarchie enthält mehrere Zertifizierungsstellen. Es ist so organisiert, dass jede Zertifizierungsstelle von einer anderen Zertifizierungsstelle auf einer höheren Ebene der Hierarchie zertifiziert wird, bis der obere Teil der Hierarchie, auch bekannt als Stamm Zertifizierungs *Stelle, erreicht*wird.  
  
 certificate  
 Eine digital signierte Anweisung mit Informationen über eine Entität und ihren öffentlichen Schlüssel, die zwei Informationen verbindet. Zertifikate werden von vertrauenswürdigen Organisationen (oder Entitäten) ausgestellt, die auch als Zertifizierungsstellen bezeichnet werden, nachdem die Zertifizierungsstelle die vorgegebene Identität überprüft hat.  
  
 Zertifikate können verschiedene Datentypen enthalten. Beispielsweise enthält ein X.509-Zertifikat folgende Zertifikatdaten: Format, Seriennummer, Algorithmus der Signatur, Name der ausstellenden Zertifizierungsstelle, Name und öffentlicher Schlüssel der Entität, die das Zertifikat anfordert, sowie Signatur der Zertifizierungsstelle.  
  
 Zertifikatspeicher  
 Normalerweise handelt es sich um einen permanenten Speicher, in dem Zertifikate, Zertifikatsperrlisten (CRL) und Zertifikatvertrauenslisten (CTL) gespeichert werden. Zertifikatspeicher können jedoch auch ausschließlich im Speicher erstellt und geöffnet werden, wenn Sie Zertifikate verwenden, die nicht im permanenten Speicher abgelegt werden müssen.  
  
 Ansprüche  
 Informationen, die zur Feststellung der Identität des Absenders von einer Entität an eine andere übergeben werden, wie z. B. ein Benutzername und ein Kennworttoken oder ein X.509-Zertifikat.  
  
 Clientzertifikat  
 Ein Zertifikat, das zur Clientauthentifizierung verwendet wird, beispielsweise zur Authentifizierung eines Webbrowsers auf einem Webserver. Beim Versuch eines Webbrowserclients, auf einen sicheren Webserver zuzugreifen, sendet der Client sein Zertifikat an den Server, um seine Identität prüfen zu lassen.  
  
 credentials  
 Authentifizierte Anmeldedaten, die von einem Sicherheitsprinzipal verwendet werden, um die eigene Identität festzustellen, beispielsweise ein Kennwort oder ein Kerberos-Protokollticket. Mit den Anmeldeinformationen wird der Zugriff auf Ressourcen gesteuert.  
  
 digestedData  
 Ein Dateninhaltstyp, der durch den Public Key Cryptographic Standard (PKCS) #7 definiert wird und aus einem beliebigen Datentyp sowie einem Nachrichtenhash (Hashwert) des Inhalts besteht.  
  
 Digitale Signatur  
 Daten, durch die die Identität eines Absenders an die gesendeten Informationen gebunden wird. Digitale Signaturen können zusammen mit jeder Nachricht, Datei oder allen anderen digitalen Informationen sowie separat gesendet werden. Digitale Signaturen werden in Umgebungen für öffentliche Schlüssel verwendet und stellen Authentifizierungs- und Integritätsdienste bereit.  
  
 encoding  
 Die Umwandlung von Daten in einen Bitstream. Die Codierung ist Bestandteil der Serialisierung, bei der Daten in einen Datenstream aus Nullen und Einsen konvertiert werden.  
  
 Austauschschlüsselpaar  
 Ein Paar aus einem öffentlichen und einem privaten Schlüssel für die Verschlüsselung von Sitzungsschlüsseln zum sicheren Speichern und Austauschen mit anderen Benutzern.  
  
 hash  
 Ein numerischer Wert fester Größe, der durch Anwendung einer mathematischen Funktion (siehe Hashalgorithmus) auf eine beliebige Datenmenge ermittelt wird. Die Daten enthalten in der Regel zufällige Daten, die als *Nonce*bezeichnet werden. Dienst und Client steuern eine Nonce zum Austausch bei, um die Komplexität des Ergebnisses zu erhöhen. Das Ergebnis wird auch als *Nachrichten Digest*bezeichnet. Das Senden eines Hashwerts ist sicherer als der Einsatz sensibler Daten wie Kennwörter, auch wenn diese verschlüsselt sind. Sender und Empfänger müssen sich auf einen Hashalgorithmus und Nonces verständigen, um den Hashalgorithmus nach dem Empfang überprüfen zu können.  
  
 Hashalgorithmus  
 Ein Algorithmus zur Erzeugung eines Hashwerts aus Daten, beispielsweise aus einer Nachricht oder aus einem Sitzungsschlüssel. Typische Hashalgorithmen sind MD2, MD4, MD5 und SHA-1.  
  
 Kerberos-Protokoll  
 Ein Protokoll, mit dem die Interaktion von Clients und Netzwerkauthentifizierungsdiensten definiert wird. Clients erhalten Tickets vom Kerberos Key Distribution Center (KDC), die sie beim Herstellen einer Verbindung an den Server übergeben. Kerberos-Tickets stellen die Netzwerkanmeldeinformationen des Clients dar.  
  
 Lokale Sicherheitsauthorität (LSA)  
 Ein geschütztes Subsystem zur Authentifizierung und Anmeldung von Benutzern beim lokalen System. Darüber hinaus verwaltet die LSA auch alle Informationen bezüglich der lokalen Systemsicherheit in einer lokalen Systemsicherheitsrichtlinie.  
  
 Negotiate  
 Ein Sicherheitsunterstützungsanbieter (SSP), der als Anwendungsschicht zwischen der Security Support Provider Interface (SSPI) und anderen SSPs fungiert. Wenn eine SSPI zur Anmeldung bei einem Netzwerk von einer Anwendung aufgerufen wird, kann ein SSP zur Verarbeitung der Anforderung angegeben werden. Wenn `Negotiate` von der Anwendung angegeben wird, wird die Anforderung von `Negotiate` analysiert, und anhand der benutzerdefinierten Sicherheitsrichtlinie wird der am besten zur Behandlung der Anforderung geeignete SSP ausgewählt.  
  
 Nonce  
 Ein zufällig generierter Wert, mit dem wiederholte Angriffe vereitelt werden.  
  
 Nichtabstreitbarkeit  
 Die Möglichkeit zur Identifizierung von Benutzern, die bestimmte Aktionen ausgeführt haben, um diese daran zu hindern, die Verantwortung abzustreiten. Beispielsweise kann ein System immer dann die ID eines Benutzers aufzeichnen, wenn eine Datei gelöscht wird.  
  
 Public Key Cryptography Standard (PKCS)  
 Spezifikationen von RSA Data Security Inc. und internationalen Entwicklern sicherer Systeme zur schnelleren Bereitstellung einer Verschlüsselung für öffentliche Schlüssel.  
  
 PKCS #7  
 Der Cryptographic Message Syntax (CMS)-Standard. Eine allgemeine Syntax für Daten, bei denen Kryptografie eingesetzt werden könnte, beispielsweise digitale Signaturen und Verschlüsselungen. Außerdem wird damit eine Syntax zur Verteilung von Zertifikaten oder Zertifikatsperrlisten und anderen Nachrichtenattributen wie Zeitstempeln bereitgestellt.  
  
 Klartext  
 Eine unverschlüsselte Nachricht. Nur-Text-Nachrichten werden manchmal als *Klartext* -Nachrichten bezeichnet.  
  
 Berechtigung  
 Das Recht eines Benutzers zur Durchführung verschiedener Systemvorgänge wie Herunterfahren des Systems, Laden von Gerätetreibern oder Ändern der Systemzeit. Das Zugriffstoken eines Benutzers enthält eine Liste der Berechtigungen des Benutzers oder der Benutzergruppe.  
  
 Private Schlüssel  
 Der geheime Teil eines Schlüsselpaars, das in einem Algorithmus für öffentliche Schlüssel verwendet wird. Private Schlüssel werden normalerweise zur Verschlüsselung von symmetrischen Sitzungsschlüsseln, zur digitalen Signierung von Nachrichten oder zur Entschlüsselung von Nachrichten, die mit dem entsprechenden öffentlichen Schlüssel verschlüsselt wurden, verwendet. Siehe auch "Öffentlicher Schlüssel".  
  
 Prozess  
 Der Sicherheitskontext, in dem eine Anwendung ausgeführt wird. Der Sicherheitskontext ist normalerweise einem Benutzer zugeordnet, sodass alle Anwendungen, die unter einem bestimmten Prozess ausgeführt werden, die Rechte und Berechtigungen des entsprechenden Benutzers übernehmen.  
  
 Paar aus privatem und öffentlichem Schlüssel  
 Ein Satz kryptografischer Schlüssel für eine Kryptografie mit öffentlichen Schlüsseln. Kryptografiedienstanbieter (CSPs) verwalten für jeden Benutzer normalerweise zwei Paare aus öffentlichen und privaten Schlüsseln: ein Austauschschlüsselpaar sowie ein Signaturschlüsselpaar. Beide Schlüsselpaare werden sitzungsübergreifend beibehalten.  
  
 Öffentlicher Schlüssel  
 Ein kryptografischer Schlüssel, der normalerweise zum Entschlüsseln eines Sitzungsschlüssels oder einer digitalen Signatur verwendet wird. Der öffentliche Schlüssel kann auch zum Verschlüsseln einer Nachricht verwendet werden. Dadurch wird sichergestellt, dass nur die Person mit dem entsprechenden privaten Schlüssel die Nachricht entschlüsseln kann.  
  
 Verschlüsselung mit öffentlichem Schlüssel  
 Eine Verschlüsselung mit Schlüsselpaaren: Mit einem Schlüssel werden die Daten verschlüsselt, mit dem anderen entschlüsselt. Bei symmetrischen Verschlüsselungsalgorithmen wird hingegen der gleiche Schlüssel sowohl zur Verschlüsselung als auch zur Entschlüsselung verwendet. Die Verschlüsselung mit öffentlichem Schlüssel wird in aller Regel zum Schutz des Sitzungsschlüssels für einen symmetrischen Verschlüsselungsalgorithmus verwendet. In diesem Fall wird der Sitzungsschlüssel, mit dem Daten verschlüsselt wurden, mit dem öffentlichen Schlüssel verschlüsselt, und der private Schlüssel wird zum Entschlüsseln der Daten verwendet. Neben dem Schutz von Sitzungsschlüsseln kann die Verschlüsselung mit öffentlichem Schlüssel noch zum digitalen Signieren von Nachrichten (mit dem privaten Schlüssel) sowie zum Überprüfen der Signatur (mit dem öffentlichen Schlüssel) verwendet werden.  
  
 Public Key-Infrastruktur (PKI)  
 Eine Infrastruktur aus integrierten Diensten und Verwaltungstools zum Erstellen, Bereitstellen und Verwalten von Anwendungen für öffentliche Schlüssel.  
  
 Nichtanerkennung  
 Die Möglichkeit eines Benutzers, die Verantwortung für die Durchführung einer Aktion von sich zu weisen, ohne dass das Gegenteil bewiesen werden kann. Beispiel: Ein Benutzer löscht eine Datei, behauptet aber erfolgreich, dass dem nicht so sei.  
  
 Stammzertifizierungsstelle  
 Die Zertifizierungsstelle an der Spitze der Zertifizierungsstellenhierarchie. Die Stammzertifizierungsstelle zertifiziert Zertifizierungsstellen in der nächsten Hierarchieebene.  
  
 Secure Hash Algorithm (SHA)  
 Ein Hashalgorithmus, der einen Nachrichtenhash generiert. Der SHA wird u. a. zusammen mit dem Digital Signature Algorithm (DSA) im Digital Signature Standard (DSS) verwendet. Es gibt vier Arten von SHAs: SHA-1, SHA-256, SHA-384 und SHA-512. SHA-1 generiert einen 160-Bit-Nachrichtenhash. SHA-256, SHA-384 und SHA-512 generieren 256-Bit-, 384-Bit- bzw. 512-Bit-Nachrichtenhashes. Der SHA wurde vom National Institute of Standards and Technology (NIST) und von der National Security Agency (NSA) entwickelt.  
  
 Secure Sockets Layer (SSL)  
 Ein Protokoll für die sichere Netzwerkkommunikationen mit einer Kombination aus öffentlicher und privater Schlüsseltechnologie.  
  
 Sicherheitskontext  
 Die aktuell geltenden Sicherheitsattribute oder -regeln. z. B. der Benutzer, der derzeit am Computer angemeldet ist, oder die PIN, die vom Smartcard-Benutzer eingegeben wurde. Im Hinblick auf die SSPI stellt ein Sicherheitskontext eine nicht transparente Datenstruktur mit Sicherheitsdaten für eine Verbindung dar, beispielsweise einen Sitzungsschlüssel oder eine Angabe der Sitzungsdauer.  
  
 Sicherheitsprinzipal  
 Eine Entität, die vom Sicherheitssystem erkannt wird. Prinzipale können menschliche Benutzer sowie autonome Prozesse einschließen.  
  
 Sicherheitsunterstützungsanbieter (SSP)  
 Eine Dynamic Link Library (DLL), die eine SSPI durch Bereitstellen eines oder mehrerer Sicherheitspakete für Anwendungen implementiert. Jedes Sicherheitspaket stellt Zuordnungen zwischen Aufrufen der SSPI-Funktion einer Anwendung und den Funktionen eines tatsächlichen Sicherheitsmodells bereit. Sicherheitspakete unterstützen Sicherheitsprotokolle wie die Kerberos-Authentifizierung sowie den Microsoft LAN-Manager (LanMan).  
  
 Security Support Provider Interface (SSPI)  
 Eine allgemeine Schnittstelle zwischen Anwendungen der Transportebene wie der Remoteprozeduraufruf (RPC) von Microsoft und Sicherheitsanbietern wie Windows Distributed Security. SSPI ermöglicht einer Transportanwendung, einen Sicherheitsanbieter zum Herstellen einer authentifizierten Verbindung auszuwählen. Diese Aufrufe erfordern keine Detailkenntnisse bezüglich des Sicherheitsprotokolls.  
  
 Sicherheitstokendienst  
 Dienste zur Ausgabe und Verwaltung von benutzerdefinierten Sicherheitstokens (ausgestellte Tokens) in einem Szenario mit mehreren Diensten. Die benutzerdefinierten Tokens sind normalerweise Security Assertions Markup Language (SAML)-Tokens mit benutzerdefinierten Anmeldeinformationen.  
  
 Serverzertifikat  
 Ein Zertifikat, das zur Serverauthentifizierung verwendet wird, beispielsweise zur Authentifizierung eines Webservers gegenüber einem Webbrowser. Wenn ein Webbrowserclient versucht, auf einen sicheren Webserver zuzugreifen, sendet der Server sein Zertifikat an den Browser, um seine Identität prüfen zu lassen.  
  
 Sitzung verknüpfen  
 Ein durch eine einzelne Schlüsselinformation geschützter Nachrichtenaustausch. SSL-Sitzungen verwenden beispielsweise einen einzelnen Schlüssel, um mehrere Nachrichten hin- und herzusenden.  
  
 Sitzungsschlüssel  
 Ein zufällig generierter Schlüssel, der einmal verwendet und dann verworfen wird. Sitzungsschlüssel sind symmetrisch (d. h. sie werden sowohl für die Verschlüsselung als auch für die Entschlüsselung verwendet). Sitzungsschlüssel werden mit der Nachricht gesendet und durch die Verschlüsselung mit einem öffentlichen Schlüssel des vorgesehenen Empfängers geschützt. Ein Sitzungsschlüssel besteht aus einer zufälligen Anzahl an Bits (40 bis 2000).  
  
 Ergänzende Anmeldeinformationen  
 Anmeldeinformationen für die Authentifizierung eines Sicherheitsprinzipals gegenüber fremden Sicherheitsdomänen.  
  
 Symmetrische Verschlüsselung  
 Ein Schlüssel wird sowohl für die Verschlüsselung als auch für die Entschlüsselung verwendet. Die symmetrische Verschlüsselung wird bevorzugt, wenn große Datenmengen verschlüsselt werden sollen. Häufig verwendete symmetrische Verschlüsselungsalgorithmen sind RC2, RC sowie DES (Data Encryption Standard).  
  
 Siehe auch "Verschlüsselung mit öffentlichem Schlüssel".  
  
 Symmetrischer Schlüssel  
 Ein Schlüssel wird sowohl für die Verschlüsselung als auch für die Entschlüsselung verwendet. Sitzungsschlüssel sind normalerweise symmetrisch.  
  
 Token (Zugriffstoken)  
 Ein Zugriffstoken enthält die Sicherheitsinformationen für eine Anmeldesitzung. Wenn sich ein Benutzer anmeldet, wird vom System ein Zugriffstoken erstellt. Alle Prozesse, die vom Benutzer ausgelöst werden, weisen dann eine Kopie des Tokens auf. Das Token identifiziert den Benutzer, die Gruppen des Benutzers und die Rechte des Benutzers. Mithilfe des Tokens steuert das System den Zugriff auf sicherungsfähige Objekte sowie die Durchführung von Systemvorgängen auf dem lokalen Computer durch den Benutzer. Es gibt zwei Arten von Zugriffstoken: primäre Token und Identitätswechseltoken.  
  
 Transportebene  
 Die Netzwerkebene für die Servicequalität und die exakte Informationsübermittlung. Auf dieser Ebene werden u. a. Fehler erkannt und korrigiert.  
  
 Zertifikatvertrauensliste (CTL)  
 Eine vordefinierte Liste mit Elementen, die von einer vertrauenswürdigen Entität signiert wurden. Eine Zertifikatvertrauensliste kann beispielsweise eine Hashliste mit Zertifikaten sein oder eine Liste mit Dateinamen. Alle Elemente in der Liste werden von der signierenden Entität authentifiziert (genehmigt).  
  
 Vertrauensanbieter  
 Die Software, die entscheidet, ob eine Datei als vertrauenswürdig eingestuft wird. Diese Entscheidung basiert auf dem Zertifikat, das der Datei zugeordnet ist.  
  
 Benutzerprinzipalname (UPN)  
 Einen Benutzerkonto Namen (manchmal auch als *Benutzer Anmelde Name*bezeichnet) und einen Domänen Namen, der die Domäne identifiziert, in der sich das Benutzerkonto befindet. Dies ist das Standardverfahren für die Anmeldung an einer Windows-Domäne. Das Format ist: someone@example.com (wie bei einer e-Mail-Adresse).  
  
> [!NOTE]
> Zusätzlich zum Standard-UPN-Formular akzeptiert WCF UPNs in Form von UPN, z. b. cohowinery. com\someone.  
  
 X.509  
 Ein international anerkannter Zertifikatstandard zur Definition erforderlicher Bestandteile.  
  
## <a name="see-also"></a>Siehe auch

- [Wesentliche Windows Communication Foundation-Begriffe](../../../../docs/framework/wcf/fundamental-concepts.md)
- [Begriffe der Sicherheit](../../../../docs/framework/wcf/feature-details/security-concepts.md)
- [Sicherheitsmodell für Windows Server-App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
