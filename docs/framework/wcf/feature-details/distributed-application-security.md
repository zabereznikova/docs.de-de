---
title: Sicherheit bei verteilten Anwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- distributed application security [WCF]
- security [WCF], transfer
ms.assetid: 53928a10-e474-46d0-ab90-5f98f8d7b668
ms.openlocfilehash: 80878857145c7a4e09106b6e1c4cb9ad68b7680a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254245"
---
# <a name="distributed-application-security"></a>Sicherheit bei verteilten Anwendungen

Die Windows Communication Foundation (WCF)-Sicherheit ist in drei Haupt funktionale Bereiche unterteilt: Übertragungssicherheit, Zugriffs Steuerung und Überwachung. Durch die Übertragungssicherheit werden Integrität, Vertraulichkeit und Authentifizierung bereitgestellt. Die Übertragungssicherheit wird durch eine der folgenden Funktionen bereitgestellt: Transportsicherheit, Nachrichtensicherheit oder `TransportWithMessageCredential`.  
  
 Eine Übersicht über die WCF-Nachrichten Sicherheit finden Sie unter [Sicherheitsübersicht](security-overview.md). Weitere Informationen zu den anderen beiden Komponenten der [WCF-Sicherheit](auditing-security-events.md)finden Sie unter [Autorisierung](authorization-in-wcf.md) und Überwachung.  
  
## <a name="transfer-security-scenarios"></a>Szenarien für die Übertragungssicherheit  

 Häufige Szenarien, in denen WCF-Übertragungssicherheit eingesetzt wird, sind folgende:  
  
- Sichere Übertragung mittels Windows: Ein WCF-Client und-Dienst werden in einer Windows-Domäne (oder einer Windows-Gesamtstruktur) bereitgestellt. Da die Nachrichten persönliche Daten enthalten, sind unter anderem eine gegenseitige Authentifizierung von Client und Dienst sowie die Integrität und Vertraulichkeit der Nachrichten erforderlich. Darüber hinaus muss belegt werden, dass eine bestimmte Transaktion stattgefunden hat. So sollten beim Empfänger der Nachricht zum Beispiel Signaturinformationen aufgezeichnet werden.  
  
- Sichere Übertragung mittels `UserName` und HTTPS: Ein WCF-Client und-Dienst müssen so entwickelt werden, dass er über das Internet funktioniert. Die Clientanmeldeinformationen werden anhand einer Datenbank mit Benutzername-/Kennwort-Paaren authentifiziert. Der Dienst wird unter einer HTTPS-Adresse mithilfe eines vertrauenswürdigen SSL-Zertifikats (SSL = Secure Sockets Layer) bereitgestellt. Da die Nachrichten über das Internet gesendet werden, müssen sich Client und Dienst gegenseitig authentifizieren und die Integrität und Vertraulichkeit der Nachrichten muss während der Übertragung gewahrt werden.  
  
- Sichere Übertragung mittels Zertifikaten: Ein WCF-Client und-Dienst müssen so entwickelt werden, dass er über das öffentliche Internet funktioniert. Client und Dienst verfügen beide über Zertifikate, mit denen die Nachrichten geschützt werden können. Client und Dienst verwenden das Internet, um miteinander zu kommunizieren und Transaktionen von hohem Wert auszuführen, für die Nachrichtenintegrität, Vertraulichkeit und eine gegenseitige Authentifizierung erforderlich sind.  
  
## <a name="integrity-confidentiality-and-authentication"></a>Integrität, Vertraulichkeit und Authentifizierung  

 Die drei Funktionen Integrität, Vertraulichkeit und Authentifizierung ergeben zusammen die Übertragungssicherheit. Durch die Übertragungssicherheit werden die Funktionen bereitgestellt, die Ihnen dabei helfen, die Bedrohungen für eine verteilte Anwendung zu mindern. In der folgenden Tabelle werden kurz die drei Funktionen beschrieben, aus denen sich die Übertragungssicherheit zusammensetzt.  
  
|Funktion|BESCHREIBUNG|  
|--------------|-----------------|  
|Integrität|*Integrität* ist die Gewissheit, dass die Daten abgeschlossen und korrekt sind, insbesondere, wenn Sie von einem Punkt zu einem anderen durchlaufen und möglicherweise von vielen Akteuren gelesen wurden. Die Integrität muss gewahrt werden, um eine Manipulation der Daten zu vermeiden. Dieses Ziel wird in der Regel durch das digitale Signieren von Nachrichten erreicht.|  
|Vertraulichkeit|*Vertraulichkeit* ist die Zusicherung, dass eine Nachricht von anderen Personen als dem beabsichtigten Reader nicht gelesen wurde. So müssen zum Beispiel Kreditkartennummern, die über das Internet gesendet werden, vertraulich behandelt werden. Vertraulichkeit wird häufig durch Verschlüsselung der Daten mit einem Schema aus öffentlichem und privatem Schlüssel bereitgestellt.|  
|Authentifizierung|Bei der *Authentifizierung* handelt es sich um die Überprüfung einer beanspruchten Identität. So muss beispielsweise bei Bankkonten gewährleistet sein, dass nur die tatsächlichen Kontoinhaber Geld abheben können. Es gibt viele Möglichkeiten, eine Authentifizierung bereitzustellen. Eine häufig verwendete Methode ist das Benutzer-/Kennwortsystem. Eine andere ist die Verwendung eines von einem Drittanbieter bereitgestellten X.509-Zertifikats.|  
  
## <a name="security-modes"></a>Sicherheitsmodi  

 WCF verfügt über mehrere Modi der Übertragungssicherheit, die in der folgenden Tabelle beschrieben werden.  
  
|Mode|BESCHREIBUNG|  
|----------|-----------------|  
|Keine|Auf Transport- bzw. Nachrichtenebene wird keine Sicherheit bereitgestellt. Keine der vordefinierten Bindungen verwendet diesen Modus standardmäßig mit Ausnahme des- [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) Elements oder bei Verwendung von Code die- <xref:System.ServiceModel.BasicHttpBinding> Klasse.|  
|Transport|Es wird ein sicherer Transport wie HTTPS zur Gewährleistung von Integrität, Vertraulichkeit und gegenseitiger Authentifizierung verwendet.|  
|`Message`|Es wird die SOAP-Nachrichtensicherheit zur Gewährleistung von Integrität, Vertraulichkeit und gegenseitiger Authentifizierung verwendet. SOAP-Nachrichten werden gemäß den Standards für die WS-Sicherheit geschützt.|  
|Gemischter Modus|Es wird die Transportsicherheit zur Gewährleistung von Integrität und Vertraulichkeit sowie für die Serverauthentifizierung verwendet. Für die Clientauthentifizierung wird die Nachrichtensicherheit (WS-Sicherheit und andere Standards) eingesetzt.<br /><br /> (Der Enumerationswert für diesen Modus ist `TransportWithMessageCredential`.)|  
|Beide|Schutz und Authentifizierung finden auf beiden Ebenen statt. Dieser Modus ist nur im- [\<netMsmqBinding>](../../configure-apps/file-schema/wcf/netmsmqbinding.md) Element verfügbar.|  
  
## <a name="credentials-and-transfer-security"></a>Identitätsnachweis (Anmeldeinformationen) und Übertragungssicherheit  

 Anmelde *Informationen sind Daten* , die angezeigt werden, um entweder eine beanspruchte Identität oder Funktionen einzurichten. Das Vorlegen eines Identitätsnachweises umfasst das Angeben der Daten und den Nachweis, dass sich die Daten rechtmäßig im Besitz des Inhabers befinden. WCF unterstützt eine Vielzahl von Anmelde Informationstypen auf Transport-und Nachrichten Sicherheitsebene. Sie können einen Typ von Anmelde Informationen für eine WCF-Bindung angeben.  
  
 In vielen Ländern bzw. Regionen ist der Führerschein ein Beispiel für einen Identitätsnachweis. Ein Führerschein enthält Daten, die die Identität und Befähigungen einer Person belegen. Der rechtmäßige Besitz wird mithilfe eines Bilds des Inhabers nachgewiesen. Der Führerschein wird von einer vertrauenswürdigen Stelle ausgegeben, in der Regel von einer dafür zuständigen Regierungsbehörde. Der Führerschein wird eingeschweißt und enthält ggf. ein Hologramm, wodurch sichergestellt wird, dass er nicht manipuliert oder gefälscht wurde.  
  
 Sehen Sie sich als Beispiel zwei Arten von Anmelde Informationen an, die von WCF unterstützt werden: Benutzername und (X. 509) Zertifikat Anmelde Informationen.  
  
 Beim Identitätsnachweis mittels Benutzername stellt der Benutzername die beanspruchte Identität dar, und das Kennwort ist der Nachweis des rechtmäßigen Besitzes. Die vertrauenswürdige Stelle ist in diesem Fall das System, das den Benutzernamen und das Kennwort überprüft.  
  
 Beim Identitätsnachweis mittels Zertifikat können die beanspruchte Identität bzw. die beanspruchten Befähigungen durch den Antragstellernamen, den alternativen Antragstellernamen oder spezielle Felder im Zertifikat belegt werden. Der Nachweis des rechtmäßigen Besitzes der Daten erfolgt durch eine Signatur, die mit dem zugehörigen privaten Schlüssel erzeugt wird.  
  
 Weitere Informationen zum Programmieren der Sicherheit und zum Angeben von Anmelde Informationen finden Sie unter [Bindungen und Sicherheits](bindings-and-security.md) -und [Sicherheits Verhalten](security-behaviors-in-wcf.md).  
  
### <a name="transport-client-credential-types"></a>Arten von Clientanmeldeinformationen bei der Transportsicherheit  

 In der folgenden Tabelle finden Sie die möglichen Werte, die Sie beim Erstellen einer Anwendung verwenden können, die die Übertragungssicherheit nutzt. Sie können diese Werte entweder im Code oder in Bindungseinstellungen festlegen.  
  
|Einstellung|BESCHREIBUNG|  
|-------------|-----------------|  
|Keine|Gibt an, dass der Client keine Anmeldeinformationen präsentieren muss. Dies führt zur Verwendung eines anonymen Clients.|  
|Basic|Gibt die Standardauthentifizierung an. Weitere Informationen finden Sie unter RFC2617, "[http Authentication: Basic and Digest Authentication](http://schemas.xmlsoap.org/ws/2004/10/discovery/ws-discovery.pdf).|  
|Digest|Gibt die Digestauthentifizierung an. Weitere Informationen finden Sie unter RFC2617, "[http Authentication: Basic and Digest Authentication](http://schemas.xmlsoap.org/ws/2004/10/discovery/ws-discovery.pdf).|  
|Ntlm|Gibt die Windows-Authentifizierung mit SSPI-Aushandlung auf einer Windows-Domäne an.<br /><br /> Die SSPI-Aushandlung führt dazu, dass entweder das Kerberos-Protokoll oder NT LanMan (NTLM) verwendet wird.|  
|Windows|Gibt die Windows-Authentifizierung mit SSPI auf einer Windows-Domäne an. SSPI wählt entweder das Kerberos-Protokoll oder NTLM als Authentifizierungsdienst aus.<br /><br /> Zuerst wird das Kerberos-Protokoll angewendet, wenn dies scheitert, wird NTLM verwendet.|  
|Zertifikat|Führt die Clientauthentifizierung mit einem Zertifikat (in der Regel X.509) durch.|  
  
### <a name="message-client-credential-types"></a>Typen von Nachrichtenclient-Anmeldeinformationen  

 In der folgenden Tabelle finden Sie die möglichen Werte, die Sie beim Erstellen einer Anwendung verwenden können, die die Nachrichtensicherheit nutzt. Sie können diese Werte entweder im Code oder in Bindungseinstellungen festlegen.  
  
|Einstellung|BESCHREIBUNG|  
|-------------|-----------------|  
|Keine|Ermöglicht dem Dienst die Interaktion mit anonymen Clients.|  
|Windows|Ermöglicht den SOAP-Nachrichtenaustausch im Rahmen des authentifizierten Kontexts von Windows-Anmeldeinformationen. Es wird mittels SSPI-Aushandlung entweder das Kerberos-Protokoll oder NTLM als Authentifizierungsdienst ausgewählt.|  
|Username|Ermöglicht es dem Dienst zu fordern, dass sich der Client per Benutzername authentifiziert. Beachten Sie, dass WCF Kryptografievorgänge mit dem Benutzernamen nicht zulässt, wie z. b. das Erzeugen einer Signatur oder das Verschlüsseln von Daten. Daher erzwingt WCF, dass der Transport geschützt wird, wenn Benutzernamen-Anmelde Informationen verwendet werden.|  
|Zertifikat|Ermöglicht dem Dienst, die Forderung zu stellen, dass der Client über ein Zertifikat authentifiziert werden muss.|  
|CardSpace|Ermöglicht es dem Dienst zu verlangen, dass der Client mithilfe eines CardSpace authentifiziert werden muss.|  
  
### <a name="programming-credentials"></a>Programmieren von Anmeldeinformationen  

 Für jeden Client Anmelde Informationstyp können Sie mit dem WCF-Programmiermodell die Anmelde Informationswerte und Validierungs Steuerelement-Validierungs Steuerelemente mithilfe von Dienst Verhaltensweisen und channelverhaltensweisen angeben.  
  
 WCF-Sicherheit verfügt über zwei Arten von Anmelde Informationen: Verhalten von Dienst Anmelde Informationen und Verhalten von Kanal Anmelde Informationen. Anmelde Informationen Verhalten in WCF geben die eigentlichen Daten an, nämlich Anmelde Informationen, die verwendet werden, um die durch Bindungen ausgedrückten Sicherheitsanforderungen zu erfüllen. In WCF ist eine Client Klasse die Laufzeitkomponente, die zwischen Vorgangs aufrufen und Nachrichten konvertiert. Alle Clients erben von der <xref:System.ServiceModel.ClientBase%601>-Klasse. Über die <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>-Eigenschaft der Basisklasse können Sie verschiedene Werte für die Clientanmeldeinformationen angeben.  
  
 In WCF sind Dienst Verhaltensweisen Attribute, die auf die Klasse angewendet werden, die einen Dienstvertrag (Schnittstelle) implementiert, um den Dienstprogramm gesteuert zu steuern. Über die <xref:System.ServiceModel.Description.ServiceCredentials>-Klasse können Sie Zertifikate für Dienstanmeldeinformationen und Einstellungen für die Clientvalidierung für verschiedene Arten von Clientanmeldeinformationen festlegen.  
  
### <a name="negotiation-model-for-message-security"></a>Aushandlungsmodell für die Nachrichtensicherheit  

 Im Modus für die Nachrichtensicherheit können Sie die Übertragungssicherheit so ausüben, dass die Dienstanmeldeinformationen nach dem Out-of-Band-System auf dem Client konfiguriert werden. Wenn Sie beispielsweise ein im Windows-Zertifikatspeicher gespeichertes Zertifikat verwenden, müssen Sie ein Tool wie das MMC-Snap-In (Microsoft Management Console) verwenden.  
  
 Im Modus für die Nachrichtensicherheit können Sie die Übertragungssicherheit auch so ausüben, dass im Zuge einer anfänglichen Aushandlung ein Austausch der Dienstanmeldeinformationen mit dem Client erfolgt. Legen Sie die <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A>-Eigenschaft auf `true` fest, um die Aushandlung zu aktivieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die Endpunkterstellung](../endpoint-creation-overview.md)
- [Vom System bereitgestellte Bindungen](../system-provided-bindings.md)
- [Sicherheitsübersicht](security-overview.md)
- [Sicherheitsmodell für Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10))
