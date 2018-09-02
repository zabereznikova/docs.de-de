---
title: Sicherheit bei verteilten Anwendungen
ms.date: 03/30/2017
helpviewer_keywords:
- distributed application security [WCF]
- security [WCF], transfer
ms.assetid: 53928a10-e474-46d0-ab90-5f98f8d7b668
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 0dbc06afd4695b85f426fad2859b4c6d4b6684d6
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43402912"
---
# <a name="distributed-application-security"></a>Sicherheit bei verteilten Anwendungen
Windows Communication Foundation (WCF)-Sicherheit wird in drei funktionelle Hauptbereiche unterteilt: übertragungssicherheit, Zugriffssteuerung und Überwachung. Durch die Übertragungssicherheit werden Integrität, Vertraulichkeit und Authentifizierung bereitgestellt. Die Übertragungssicherheit wird durch eine der folgenden Funktionen bereitgestellt: Transportsicherheit, Nachrichtensicherheit oder `TransportWithMessageCredential`.  
  
 Eine Übersicht über WCF-nachrichtensicherheit, finden Sie unter [Sicherheitsübersicht](../../../../docs/framework/wcf/feature-details/security-overview.md). Weitere Informationen zu den anderen beiden Teilen der WCF-Sicherheit, finden Sie unter [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md) und [Überwachung](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
## <a name="transfer-security-scenarios"></a>Szenarien für die Übertragungssicherheit  
 Die folgenden: allgemeinen Szenarien, die Übertragung der WCF-Sicherheit einsetzen  
  
-   Sichere Übertragung mittels Windows: WCF-Client und Dienst werden in einer Windows-Domäne (oder einer Windows-Gesamtstruktur) bereitgestellt. Da die Nachrichten persönliche Daten enthalten, sind unter anderem eine gegenseitige Authentifizierung von Client und Dienst sowie die Integrität und Vertraulichkeit der Nachrichten erforderlich. Darüber hinaus muss belegt werden, dass eine bestimmte Transaktion stattgefunden hat. So sollten beim Empfänger der Nachricht zum Beispiel Signaturinformationen aufgezeichnet werden.  
  
-   Sichere Übertragung mittels `UserName` und HTTPS: Müssen einen WCF-Client und Dienst entwickelt werden, um über das Internet zu arbeiten. Die Clientanmeldeinformationen werden anhand einer Datenbank mit Benutzername-/Kennwort-Paaren authentifiziert. Der Dienst wird unter einer HTTPS-Adresse mithilfe eines vertrauenswürdigen SSL-Zertifikats (SSL = Secure Sockets Layer) bereitgestellt. Da die Nachrichten über das Internet gesendet werden, müssen sich Client und Dienst gegenseitig authentifizieren und die Integrität und Vertraulichkeit der Nachrichten muss während der Übertragung gewahrt werden.  
  
-   Sichere Übertragung mittels Zertifikaten: Müssen einen WCF-Client und Dienst entwickelt werden, um über das öffentliche Internet zu arbeiten. Client und Dienst verfügen beide über Zertifikate, mit denen die Nachrichten geschützt werden können. Client und Dienst verwenden das Internet, um miteinander zu kommunizieren und Transaktionen von hohem Wert auszuführen, für die Nachrichtenintegrität, Vertraulichkeit und eine gegenseitige Authentifizierung erforderlich sind.  
  
## <a name="integrity-confidentiality-and-authentication"></a>Integrität, Vertraulichkeit und Authentifizierung  
 Die drei Funktionen Integrität, Vertraulichkeit und Authentifizierung ergeben zusammen die Übertragungssicherheit. Durch die Übertragungssicherheit werden die Funktionen bereitgestellt, die Ihnen dabei helfen, die Bedrohungen für eine verteilte Anwendung zu mindern. In der folgenden Tabelle werden kurz die drei Funktionen beschrieben, aus denen sich die Übertragungssicherheit zusammensetzt.  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|Integrität|*Integrität* ist die Zusicherung, dass Daten vollständig und richtig sind, insbesondere dann, nachdem er von einem Punkt in eine andere durchlaufen, und möglicherweise von vielen Parteien gelesen wurden. Die Integrität muss gewahrt werden, um eine Manipulation der Daten zu vermeiden. Dieses Ziel wird in der Regel durch das digitale Signieren von Nachrichten erreicht.|  
|Vertraulichkeit|*Vertraulichkeit* ist die Zusicherung, die eine Nachricht nicht von jemand anderem als dem beabsichtigten Empfänger gelesen wurde. So müssen zum Beispiel Kreditkartennummern, die über das Internet gesendet werden, vertraulich behandelt werden. Vertraulichkeit wird häufig durch Verschlüsselung der Daten mit einem Schema aus öffentlichem und privatem Schlüssel bereitgestellt.|  
|Authentifizierung|*Authentifizierung* ist die Überprüfung einer beanspruchten Identität. So muss beispielsweise bei Bankkonten gewährleistet sein, dass nur die tatsächlichen Kontoinhaber Geld abheben können. Es gibt viele Möglichkeiten, eine Authentifizierung bereitzustellen. Eine häufig verwendete Methode ist das Benutzer-/Kennwortsystem. Eine andere ist die Verwendung eines von einem Drittanbieter bereitgestellten X.509-Zertifikats.|  
  
## <a name="security-modes"></a>Sicherheitsmodi  
 WCF bietet verschiedene Modi für die übertragungssicherheit, die in der folgenden Tabelle beschrieben werden.  
  
|Modus|Beschreibung|  
|----------|-----------------|  
|Keiner|Auf Transport- bzw. Nachrichtenebene wird keine Sicherheit bereitgestellt. Keine der vordefinierten Bindungen verwenden Sie diesen Modus wird standardmäßig mit Ausnahme der [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) Element oder, wenn der Code, mit der <xref:System.ServiceModel.BasicHttpBinding> Klasse.|  
|Transport|Es wird ein sicherer Transport wie HTTPS zur Gewährleistung von Integrität, Vertraulichkeit und gegenseitiger Authentifizierung verwendet.|  
|Meldung|Es wird die SOAP-Nachrichtensicherheit zur Gewährleistung von Integrität, Vertraulichkeit und gegenseitiger Authentifizierung verwendet. SOAP-Nachrichten werden gemäß den Standards für die WS-Sicherheit geschützt.|  
|Gemischt|Es wird die Transportsicherheit zur Gewährleistung von Integrität und Vertraulichkeit sowie für die Serverauthentifizierung verwendet. Für die Clientauthentifizierung wird die Nachrichtensicherheit (WS-Sicherheit und andere Standards) eingesetzt.<br /><br /> (Der Enumerationswert für diesen Modus ist `TransportWithMessageCredential`.)|  
|Beides|Schutz und Authentifizierung finden auf beiden Ebenen statt. Dieser Modus steht nur in der [ \<NetMsmqBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md) Element.|  
  
## <a name="credentials-and-transfer-security"></a>Identitätsnachweis (Anmeldeinformationen) und Übertragungssicherheit  
 Ein *Anmeldeinformationen* Daten angezeigt werden, um entweder eine beanspruchte Identität bzw. beanspruchte Befähigungen belegt wird. Das Vorlegen eines Identitätsnachweises umfasst das Angeben der Daten und den Nachweis, dass sich die Daten rechtmäßig im Besitz des Inhabers befinden. WCF unterstützt eine Vielzahl von Typen von Anmeldeinformationen auf der Transport- und nachrichtensicherheitsebene. Sie können einen Typ von Anmeldeinformationen für eine WCF-Bindung angeben.  
  
 In vielen Ländern bzw. Regionen ist der Führerschein ein Beispiel für einen Identitätsnachweis. Ein Führerschein enthält Daten, die die Identität und Befähigungen einer Person belegen. Der rechtmäßige Besitz wird mithilfe eines Bilds des Inhabers nachgewiesen. Der Führerschein wird von einer vertrauenswürdigen Stelle ausgegeben, in der Regel von einer dafür zuständigen Regierungsbehörde. Der Führerschein wird eingeschweißt und enthält ggf. ein Hologramm, wodurch sichergestellt wird, dass er nicht manipuliert oder gefälscht wurde.  
  
 Betrachten Sie beispielsweise zwei Typen von Anmeldeinformationen, die von WCF unterstützten: Zertifikatanmeldeinformationen für Benutzernamen und (x. 509).  
  
 Beim Identitätsnachweis mittels Benutzername stellt der Benutzername die beanspruchte Identität dar, und das Kennwort ist der Nachweis des rechtmäßigen Besitzes. Die vertrauenswürdige Stelle ist in diesem Fall das System, das den Benutzernamen und das Kennwort überprüft.  
  
 Beim Identitätsnachweis mittels Zertifikat können die beanspruchte Identität bzw. die beanspruchten Befähigungen durch den Antragstellernamen, den alternativen Antragstellernamen oder spezielle Felder im Zertifikat belegt werden. Der Nachweis des rechtmäßigen Besitzes der Daten erfolgt durch eine Signatur, die mit dem zugehörigen privaten Schlüssel erzeugt wird.  
  
 Weitere Informationen zur Programmierung übertragungssicherheit und finden Sie mit der Angabe von Anmeldeinformationen, [Bindungen und Sicherheit](../../../../docs/framework/wcf/feature-details/bindings-and-security.md) und [Sicherheitsverhalten](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md).  
  
### <a name="transport-client-credential-types"></a>Arten von Clientanmeldeinformationen bei der Transportsicherheit  
 In der folgenden Tabelle finden Sie die möglichen Werte, die Sie beim Erstellen einer Anwendung verwenden können, die die Übertragungssicherheit nutzt. Sie können diese Werte entweder im Code oder in Bindungseinstellungen festlegen.  
  
|Einstellung|Beschreibung|  
|-------------|-----------------|  
|Keine|Gibt an, dass der Client keine Anmeldeinformationen präsentieren muss. Dies führt zur Verwendung eines anonymen Clients.|  
|Standard|Gibt die Standardauthentifizierung an.  Weitere Informationen finden Sie unter RFC2617, "[HTTP-Authentifizierung: Standard- und Digestauthentifizierung](https://go.microsoft.com/fwlink/?LinkId=88313)."|  
|Digest|Gibt die Hashwertauthentifizierung an.  Weitere Informationen finden Sie unter RFC2617, "[HTTP-Authentifizierung: Standard- und Digestauthentifizierung](https://go.microsoft.com/fwlink/?LinkId=88313)."|  
|Ntlm|Gibt die Windows-Authentifizierung mit SSPI-Aushandlung auf einer Windows-Domäne an.<br /><br /> Die SSPI-Aushandlung führt dazu, dass entweder das Kerberos-Protokoll oder NT LanMan (NTLM) verwendet wird.|  
|Windows|Gibt die Windows-Authentifizierung mit SSPI auf einer Windows-Domäne an. SSPI wählt entweder das Kerberos-Protokoll oder NTLM als Authentifizierungsdienst aus.<br /><br /> Zuerst wird das Kerberos-Protokoll angewendet, wenn dies scheitert, wird NTLM verwendet.|  
|Zertifikat|Führt die Clientauthentifizierung mit einem Zertifikat (in der Regel X.509) durch.|  
  
### <a name="message-client-credential-types"></a>Typen von Nachrichtenclient-Anmeldeinformationen  
 In der folgenden Tabelle finden Sie die möglichen Werte, die Sie beim Erstellen einer Anwendung verwenden können, die die Nachrichtensicherheit nutzt. Sie können diese Werte entweder im Code oder in Bindungseinstellungen festlegen.  
  
|Einstellung|Beschreibung|  
|-------------|-----------------|  
|Keiner|Ermöglicht dem Dienst die Interaktion mit anonymen Clients.|  
|Windows|Ermöglicht den SOAP-Nachrichtenaustausch im Rahmen des authentifizierten Kontexts von Windows-Anmeldeinformationen. Es wird mittels SSPI-Aushandlung entweder das Kerberos-Protokoll oder NTLM als Authentifizierungsdienst ausgewählt.|  
|Benutzername|Ermöglicht es dem Dienst zu fordern, dass sich der Client per Benutzername authentifiziert. Beachten Sie, dass alle kryptografischen Vorgänge mit den Benutzernamen ein, z. B. das Erzeugen einer Signatur oder Verschlüsseln von Daten von WCF nicht zulässig ist. Daher setzt WCF an, dass der Transport geschützt wird, wenn der Identitätsnachweis über den Benutzernamen.|  
|Zertifikat|Ermöglicht dem Dienst, die Forderung zu stellen, dass der Client über ein Zertifikat authentifiziert werden muss.|  
|[!INCLUDE[infocard](../../../../includes/infocard-md.md)]|Ermöglicht dem Dienst die Forderung, dass der Client über eine [!INCLUDE[infocard](../../../../includes/infocard-md.md)] authentifiziert werden muss.|  
  
### <a name="programming-credentials"></a>Programmieren von Anmeldeinformationen  
 Für jeden der Typen von Clientanmeldeinformationen kann die WCF-Programmiermodell Sie zum Angeben der clientanmeldeinformationswerte und Validierungssteuerelemente mithilfe von Dienstverhalten und Kanalverhalten Anmeldeinformationen an.  
  
 WCF-Sicherheit verfügt über zwei Arten von Anmeldeinformationen: Verhalten für Dienstanmeldeinformationen und kanalanmeldeinformationen-service. Anmeldeinformationen-Verhalten in WCF Geben Sie die tatsächlichen Daten, d. h., Anmeldeinformationen für die durch Bindungen ausgedrückten sicherheitsanforderungen erfüllen. In WCF ist eine Clientklasse die Laufzeitkomponente, die zwischen Vorgangsaufruf und Nachrichten konvertiert. Alle Clients erben von der <xref:System.ServiceModel.ClientBase%601>-Klasse. Über die <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>-Eigenschaft der Basisklasse können Sie verschiedene Werte für die Clientanmeldeinformationen angeben.  
  
 In WCF sind Dienstverhalten Attribute, die auf die Klasse implementiert einen Dienstvertrag (Schnittstelle), um den Dienst programmgesteuert angewendet. Über die <xref:System.ServiceModel.Description.ServiceCredentials>-Klasse können Sie Zertifikate für Dienstanmeldeinformationen und Einstellungen für die Clientvalidierung für verschiedene Arten von Clientanmeldeinformationen festlegen.  
  
### <a name="negotiation-model-for-message-security"></a>Aushandlungsmodell für die Nachrichtensicherheit  
 Im Modus für die Nachrichtensicherheit können Sie die Übertragungssicherheit so ausüben, dass die Dienstanmeldeinformationen nach dem Out-of-Band-System auf dem Client konfiguriert werden. Wenn Sie beispielsweise ein im Windows-Zertifikatspeicher gespeichertes Zertifikat verwenden, müssen Sie ein Tool wie das MMC-Snap-In (Microsoft Management Console) verwenden.  
  
 Im Modus für die Nachrichtensicherheit können Sie die Übertragungssicherheit auch so ausüben, dass im Zuge einer anfänglichen Aushandlung ein Austausch der Dienstanmeldeinformationen mit dem Client erfolgt. Legen Sie die <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A>-Eigenschaft auf `true` fest, um die Aushandlung zu aktivieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Endpunkterstellung](../../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [Vom System bereitgestellte Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Sicherheitsmodell für Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
