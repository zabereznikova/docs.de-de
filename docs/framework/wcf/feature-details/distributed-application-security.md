---
title: Sicherheit bei verteilten Anwendungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- distributed application security [WCF]
- security [WCF], transfer
ms.assetid: 53928a10-e474-46d0-ab90-5f98f8d7b668
caps.latest.revision: "32"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 1e67c5da534e7b35d4d27c0164d9389c8afe252b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="distributed-application-security"></a>Sicherheit bei verteilten Anwendungen
Die Sicherheit wird in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in drei funktionelle Hauptbereiche unterteilt: Übertragungssicherheit, Zugriffssteuerung und Überwachung. Durch die Übertragungssicherheit werden Integrität, Vertraulichkeit und Authentifizierung bereitgestellt. Die Übertragungssicherheit wird durch eine der folgenden Funktionen bereitgestellt: Transportsicherheit, Nachrichtensicherheit oder `TransportWithMessageCredential`.  
  
 Eine Übersicht über [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nachrichtensicherheit, finden Sie unter [Sicherheitsübersicht](../../../../docs/framework/wcf/feature-details/security-overview.md). [!INCLUDE[crabout](../../../../includes/crabout-md.md)]die anderen beiden Teile einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Sicherheit, finden Sie unter [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md) und [Überwachung](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
## <a name="transfer-security-scenarios"></a>Szenarien für die Übertragungssicherheit  
 Zu den üblichen Szenarien, in denen die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Übertragungssicherheit eingesetzt wird, gehören folgende Situationen:  
  
-   Sichere Übertragung mittels Windows: Ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client und ein WCF-Dienst werden in einer Windows-Domäne (oder einer Windows-Gesamtstruktur) bereitgestellt. Da die Nachrichten persönliche Daten enthalten, sind unter anderem eine gegenseitige Authentifizierung von Client und Dienst sowie die Integrität und Vertraulichkeit der Nachrichten erforderlich. Darüber hinaus muss belegt werden, dass eine bestimmte Transaktion stattgefunden hat. So sollten beim Empfänger der Nachricht zum Beispiel Signaturinformationen aufgezeichnet werden.  
  
-   Sichere Übertragung mittels `UserName` und HTTPS: Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client und der WCF-Dienst müssen so entwickelt werden, dass sie über das Internet kommunizieren können. Die Clientanmeldeinformationen werden anhand einer Datenbank mit Benutzername-/Kennwort-Paaren authentifiziert. Der Dienst wird unter einer HTTPS-Adresse mithilfe eines vertrauenswürdigen SSL-Zertifikats (SSL = Secure Sockets Layer) bereitgestellt. Da die Nachrichten über das Internet gesendet werden, müssen sich Client und Dienst gegenseitig authentifizieren und die Integrität und Vertraulichkeit der Nachrichten muss während der Übertragung gewahrt werden.  
  
-   Sichere Übertragung mittels Zertifikaten: Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client und der WCF-Dienst müssen so entwickelt werden, dass sie über das öffentliche Internet kommunizieren können. Client und Dienst verfügen beide über Zertifikate, mit denen die Nachrichten geschützt werden können. Client und Dienst verwenden das Internet, um miteinander zu kommunizieren und Transaktionen von hohem Wert auszuführen, für die Nachrichtenintegrität, Vertraulichkeit und eine gegenseitige Authentifizierung erforderlich sind.  
  
## <a name="integrity-confidentiality-and-authentication"></a>Integrität, Vertraulichkeit und Authentifizierung  
 Die drei Funktionen Integrität, Vertraulichkeit und Authentifizierung ergeben zusammen die Übertragungssicherheit. Durch die Übertragungssicherheit werden die Funktionen bereitgestellt, die Ihnen dabei helfen, die Bedrohungen für eine verteilte Anwendung zu mindern. In der folgenden Tabelle werden kurz die drei Funktionen beschrieben, aus denen sich die Übertragungssicherheit zusammensetzt.  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|Integrität|*Integrität* ist die Zusicherung, dass Daten vollständig und richtig sind, vor allem, sobald sie von einem Punkt in eine andere durchlaufen, und möglicherweise von vielen Parteien gelesen wurden. Die Integrität muss gewahrt werden, um eine Manipulation der Daten zu vermeiden. Dieses Ziel wird in der Regel durch das digitale Signieren von Nachrichten erreicht.|  
|Vertraulichkeit|*Vertraulichkeit* ist die Zusicherung, die eine Nachricht nicht vom beabsichtigten Empfänger gelesen wurde. So müssen zum Beispiel Kreditkartennummern, die über das Internet gesendet werden, vertraulich behandelt werden. Vertraulichkeit wird häufig durch Verschlüsselung der Daten mit einem Schema aus öffentlichem und privatem Schlüssel bereitgestellt.|  
|Authentifizierung|*Authentifizierung* ist die Überprüfung einer beanspruchten Identität. So muss beispielsweise bei Bankkonten gewährleistet sein, dass nur die tatsächlichen Kontoinhaber Geld abheben können. Es gibt viele Möglichkeiten, eine Authentifizierung bereitzustellen. Eine häufig verwendete Methode ist das Benutzer-/Kennwortsystem. Eine andere ist die Verwendung eines von einem Drittanbieter bereitgestellten X.509-Zertifikats.|  
  
## <a name="security-modes"></a>Sicherheitsmodi  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gibt es mehrere Modi für die Übertragungssicherheit, die in der folgenden Tabelle beschrieben werden.  
  
|Modus|Beschreibung|  
|----------|-----------------|  
|Keiner|Auf Transport- bzw. Nachrichtenebene wird keine Sicherheit bereitgestellt. Keiner der vordefinierten Bindungen verwenden Sie diesen Modus standardmäßig mit Ausnahme der [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) Element oder, bei der Verwendung von Code, der <xref:System.ServiceModel.BasicHttpBinding> Klasse.|  
|Transport|Es wird ein sicherer Transport wie HTTPS zur Gewährleistung von Integrität, Vertraulichkeit und gegenseitiger Authentifizierung verwendet.|  
|Meldung|Es wird die SOAP-Nachrichtensicherheit zur Gewährleistung von Integrität, Vertraulichkeit und gegenseitiger Authentifizierung verwendet. SOAP-Nachrichten werden gemäß den Standards für die WS-Sicherheit geschützt.|  
|Gemischt|Es wird die Transportsicherheit zur Gewährleistung von Integrität und Vertraulichkeit sowie für die Serverauthentifizierung verwendet. Für die Clientauthentifizierung wird die Nachrichtensicherheit (WS-Sicherheit und andere Standards) eingesetzt.<br /><br /> (Der Enumerationswert für diesen Modus ist `TransportWithMessageCredential`.)|  
|Beides|Schutz und Authentifizierung finden auf beiden Ebenen statt. Dieser Modus steht nur in der [ \<NetMsmqBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md) Element.|  
  
## <a name="credentials-and-transfer-security"></a>Identitätsnachweis (Anmeldeinformationen) und Übertragungssicherheit  
 Ein *Anmeldeinformationen* Daten, die angezeigt werden, um entweder eine beanspruchte Identität bzw. beanspruchte Befähigungen belegt wird. Das Vorlegen eines Identitätsnachweises umfasst das Angeben der Daten und den Nachweis, dass sich die Daten rechtmäßig im Besitz des Inhabers befinden. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt verschiedene Arten von Anmeldeinformationen auf der Transport- und Nachrichtensicherheitsebene. Sie können für eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Bindung die Art der Anmeldeinformationen (das heißt des Identitätsnachweises) angeben.  
  
 In vielen Ländern bzw. Regionen ist der Führerschein ein Beispiel für einen Identitätsnachweis. Ein Führerschein enthält Daten, die die Identität und Befähigungen einer Person belegen. Der rechtmäßige Besitz wird mithilfe eines Bilds des Inhabers nachgewiesen. Der Führerschein wird von einer vertrauenswürdigen Stelle ausgegeben, in der Regel von einer dafür zuständigen Regierungsbehörde. Der Führerschein wird eingeschweißt und enthält ggf. ein Hologramm, wodurch sichergestellt wird, dass er nicht manipuliert oder gefälscht wurde.  
  
 Nehmen Sie als Beispiel zwei Arten von Identitätsnachweis (Anmeldeinformationen), die in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt werden: der Identitätsnachweis mittels Benutzername und Zertifikat (X.509).  
  
 Beim Identitätsnachweis mittels Benutzername stellt der Benutzername die beanspruchte Identität dar, und das Kennwort ist der Nachweis des rechtmäßigen Besitzes. Die vertrauenswürdige Stelle ist in diesem Fall das System, das den Benutzernamen und das Kennwort überprüft.  
  
 Beim Identitätsnachweis mittels Zertifikat können die beanspruchte Identität bzw. die beanspruchten Befähigungen durch den Antragstellernamen, den alternativen Antragstellernamen oder spezielle Felder im Zertifikat belegt werden. Der Nachweis des rechtmäßigen Besitzes der Daten erfolgt durch eine Signatur, die mit dem zugehörigen privaten Schlüssel erzeugt wird.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Programmieren von übertragungssicherheit und bestimmten Anmeldeinformationen finden Sie unter [Bindungen und Sicherheit](../../../../docs/framework/wcf/feature-details/bindings-and-security.md) und [Sicherheitsverhalten](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md).  
  
### <a name="transport-client-credential-types"></a>Arten von Clientanmeldeinformationen bei der Transportsicherheit  
 In der folgenden Tabelle finden Sie die möglichen Werte, die Sie beim Erstellen einer Anwendung verwenden können, die die Übertragungssicherheit nutzt. Sie können diese Werte entweder im Code oder in Bindungseinstellungen festlegen.  
  
|Einstellung|Beschreibung|  
|-------------|-----------------|  
|Keine|Gibt an, dass der Client keine Anmeldeinformationen präsentieren muss. Dies führt zur Verwendung eines anonymen Clients.|  
|Standard|Gibt die Standardauthentifizierung an.  Weitere Informationen finden Sie unter RFC 2617, "[HTTP Authentication: Basic and Digest Authentication](http://go.microsoft.com/fwlink/?LinkId=88313)."|  
|Digest|Gibt die Hashwertauthentifizierung an.  Weitere Informationen finden Sie unter RFC 2617, "[HTTP Authentication: Basic and Digest Authentication](http://go.microsoft.com/fwlink/?LinkId=88313)."|  
|Ntlm|Gibt die Windows-Authentifizierung mit SSPI-Aushandlung auf einer Windows-Domäne an.<br /><br /> Die SSPI-Aushandlung führt dazu, dass entweder das Kerberos-Protokoll oder NT LanMan (NTLM) verwendet wird.|  
|Windows|Gibt die Windows-Authentifizierung mit SSPI auf einer Windows-Domäne an. SSPI wählt entweder das Kerberos-Protokoll oder NTLM als Authentifizierungsdienst aus.<br /><br /> Zuerst wird das Kerberos-Protokoll angewendet, wenn dies scheitert, wird NTLM verwendet.|  
|Zertifikat|Führt die Clientauthentifizierung mit einem Zertifikat (in der Regel X.509) durch.|  
  
### <a name="message-client-credential-types"></a>Typen von Nachrichtenclient-Anmeldeinformationen  
 In der folgenden Tabelle finden Sie die möglichen Werte, die Sie beim Erstellen einer Anwendung verwenden können, die die Nachrichtensicherheit nutzt. Sie können diese Werte entweder im Code oder in Bindungseinstellungen festlegen.  
  
|Einstellung|Beschreibung|  
|-------------|-----------------|  
|Keiner|Ermöglicht dem Dienst die Interaktion mit anonymen Clients.|  
|Windows|Ermöglicht den SOAP-Nachrichtenaustausch im Rahmen des authentifizierten Kontexts von Windows-Anmeldeinformationen. Es wird mittels SSPI-Aushandlung entweder das Kerberos-Protokoll oder NTLM als Authentifizierungsdienst ausgewählt.|  
|Benutzername|Ermöglicht es dem Dienst zu fordern, dass sich der Client per Benutzername authentifiziert. Beachten Sie, dass in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] keine kryptografischen Vorgänge mit dem Benutzernamen wie das Erzeugen einer Signatur oder das Verschlüsseln von Daten zulässig sind. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] setzt prinzipiell durch, dass der Transport geschützt wird, wenn der Identitätsnachweis über den Benutzernamen erfolgt.|  
|Zertifikat|Ermöglicht dem Dienst, die Forderung zu stellen, dass der Client über ein Zertifikat authentifiziert werden muss.|  
|[!INCLUDE[infocard](../../../../includes/infocard-md.md)]|Ermöglicht dem Dienst die Forderung, dass der Client über eine [!INCLUDE[infocard](../../../../includes/infocard-md.md)] authentifiziert werden muss.|  
  
### <a name="programming-credentials"></a>Programmieren von Anmeldeinformationen  
 Bei allen Arten von Clientanmeldeinformationen haben Sie im [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Programmiermodell die Möglichkeit, die Werte und Validierungen für die Anmeldeinformationen mithilfe von Dienstverhalten und von Kanalverhalten festzulegen.  
  
 Die Sicherheit in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet zwei Arten von Anmeldeinformationen: Verhalten für Dienstanmeldeinformationen und Verhalten für Kanalanmeldeinformationen. Durch die Anmeldeinformationsverhalten in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] werden die eigentlichen Daten angegeben, das heißt die Anmeldeinformationen, mit denen die durch Bindungen ausgedrückten Sicherheitsvoraussetzungen erfüllt werden. In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ist eine Clientklasse die Laufzeitkomponente, über die die Umsetzung zwischen Vorgangsaufruf und Nachrichten erfolgt. Alle Clients erben von der <xref:System.ServiceModel.ClientBase%601>-Klasse. Über die <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>-Eigenschaft der Basisklasse können Sie verschiedene Werte für die Clientanmeldeinformationen angeben.  
  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sind Dienstverhalten Attribute, die auf die Klasse, die einen Dienstvertrag (Schnittstelle) implementiert, angewendet werden, um den Dienst programmatisch zu steuern. Über die <xref:System.ServiceModel.Description.ServiceCredentials>-Klasse können Sie Zertifikate für Dienstanmeldeinformationen und Einstellungen für die Clientvalidierung für verschiedene Arten von Clientanmeldeinformationen festlegen.  
  
### <a name="negotiation-model-for-message-security"></a>Aushandlungsmodell für die Nachrichtensicherheit  
 Im Modus für die Nachrichtensicherheit können Sie die Übertragungssicherheit so ausüben, dass die Dienstanmeldeinformationen nach dem Out-of-Band-System auf dem Client konfiguriert werden. Wenn Sie beispielsweise ein im Windows-Zertifikatspeicher gespeichertes Zertifikat verwenden, müssen Sie ein Tool wie das MMC-Snap-In (Microsoft Management Console) verwenden.  
  
 Im Modus für die Nachrichtensicherheit können Sie die Übertragungssicherheit auch so ausüben, dass im Zuge einer anfänglichen Aushandlung ein Austausch der Dienstanmeldeinformationen mit dem Client erfolgt. Legen Sie die <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A>-Eigenschaft auf `true` fest, um die Aushandlung zu aktivieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Endpunkterstellung](../../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [Vom System bereitgestellte Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Sicherheitsmodell für Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
