---
title: Wählen eines Typs von Anmeldeinformationen
description: Erfahren Sie mehr über Anmelde Informationen, wie Sie in WCF verwendet werden, und wie Sie die richtigen Anmelde Informationen für Ihre Anwendung auswählen, um eine beanspruchte Identität oder Funktionen einzurichten.
ms.date: 03/30/2017
ms.assetid: bf707063-3f30-4304-ab53-0e63413728a8
ms.openlocfilehash: c5a47bf95ab8e22cda1beb7eeca7cb77bfc2a169
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253972"
---
# <a name="selecting-a-credential-type"></a>Wählen eines Typs von Anmeldeinformationen

*Anmelde* Informationen sind die Daten Windows Communication Foundation (WCF) verwendet, um entweder eine beanspruchte Identität oder Funktionen einzurichten. Ein Ausweis ist beispielsweise ein mit Anmeldeinformationen vergleichbares Dokument, das ein Staat ausgibt, damit seine Bürger ihre Staatsbürgerschaft nachweisen können. In WCF können Anmelde Informationen viele Formulare annehmen, z. b. Benutzernamen Token und X. 509-Zertifikate. In diesem Thema werden Anmelde Informationen, ihre Verwendung in WCF und die Auswahl der richtigen Anmelde Informationen für Ihre Anwendung erläutert.  
  
 In vielen Ländern und Regionen ist ein Führerschein ein Beispiel für einen Identitätsnachweis. Ein Führerschein enthält Daten, die die Identität und erworbene Berechtigungen einer Person nachweisen. Der rechtmäßige Besitz wird mithilfe eines Bilds des Inhabers nachgewiesen. Ein Führerschein oder Ausweis wird von einer vertrauenswürdigen Stelle ausgegeben, in der Regel von einer dafür zuständigen Behörde. Der Führerschein wird eingeschweißt und enthält ggf. ein Hologramm, wodurch sichergestellt wird, dass er nicht manipuliert oder gefälscht wurde.  
  
 Das Vorlegen eines Identitätsnachweises umfasst das Angeben der Daten und den Nachweis, dass sich die Daten rechtmäßig im Besitz des Inhabers befinden. WCF unterstützt eine Vielzahl von Anmelde Informationstypen auf Transport-und Nachrichten Sicherheitsebene. Nehmen wir beispielsweise an, dass zwei Arten von Anmelde Informationen in WCF unterstützt werden: Benutzername und (X. 509) Zertifikat Anmelde Informationen.  
  
 Beim Benutzernamenteil der Anmeldeinformationen stellt der Benutzername die beanspruchte Identität und das Kennwort den Nachweis des rechtmäßigen Besitzes dar. Die vertrauenswürdige Stelle ist in diesem Fall das System, das den Benutzernamen und das Kennwort überprüft.  
  
 Mit einem X. 509-Zertifikat Anmelde Informationen können der Antragsteller Name, der alternative Antragsteller Name oder bestimmte Felder innerhalb des Zertifikats als Identitäts Ansprüche verwendet werden, während andere Felder, wie z. b. das `Valid From` -Feld und das-Feld `Valid To` , die Gültigkeit des Zertifikats angeben.  
  
## <a name="transport-credential-types"></a>Transportieren von Anmeldeinformationen-Typen  

 Die folgende Tabelle zeigt die möglichen Typen von Clientanmeldeinformationen, die von einer Bindung im Transportsicherheitsmodus verwendet werden können. Legen Sie die `ClientCredentialType`-Eigenschaft beim Erstellen eines Dienstes auf einen dieser Werte fest, um den Typ der Anmeldeinformationen anzugeben, den der Client zum Kommunizieren mit Ihrem Dienst bereitstellen muss. Sie können die Typen entweder im Code oder in Konfigurationsdateien festlegen.  
  
|Einstellung|BESCHREIBUNG|  
|-------------|-----------------|  
|Keine|Gibt an, dass der Client keine Anmeldeinformationen präsentieren muss. Dies führt zur Verwendung eines anonymen Clients.|  
|Basic|Gibt die Standardauthentifizierung für den Client an. Weitere Informationen finden Sie unter RFC2617 –[http Authentication: Basic and Digest Authentication](ftp://ftp.rfc-editor.org/in-notes/rfc2617.txt).|  
|Digest|Gibt die Hashwertauthentifizierung für den Client an. Weitere Informationen finden Sie unter RFC2617 –[http Authentication: Basic and Digest Authentication](ftp://ftp.rfc-editor.org/in-notes/rfc2617.txt).|  
|Ntlm|Gibt die NT-LAN-Managerauthentifizierung (NTLM) an. Wird verwendet, wenn Sie aus bestimmten Gründen keine Kerberos-Authentifizierung verwenden können. Sie können die Verwendung auch als Fall Back deaktivieren, indem Sie die- <xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A> Eigenschaft auf festlegen `false` . Dies bewirkt, dass WCF bei Verwendung von NTLM einen Best-Effort-Vorgang auslöst, um eine Ausnahme auszulösen. Durch das Festlegen dieser Eigenschaft auf `false` wird unter Umständen nicht verhindert, dass NTLM-Anmeldeinformationen über die Verbindung gesendet werden.|  
|Windows|Gibt die Windows-Authentifizierung an. Um für eine Windows-Domäne nur das Kerberos-Protokoll anzugeben, legen Sie die <xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A>-Eigenschaft auf `false` fest (die Standardeinstellung ist `true`).|  
|Zertifikat|Führt die Clientauthentifizierung mit einem X.509-Zertifikat aus.|  
|Kennwort|Benutzer müssen einen Benutzernamen und ein Kennwort angeben. Überprüfen Sie das Benutzername/Kennwort-Paar mithilfe der Windows-Authentifizierung oder einer anderen benutzerdefinierten Lösung.|  
  
### <a name="message-client-credential-types"></a>Typen von Nachrichtenclient-Anmeldeinformationen  

 Die folgende Tabelle zeigt die möglichen Typen von Anmeldeinformationen, die Sie beim Erstellen einer Anwendung verwenden können, die die Nachrichtensicherheit nutzt. Sie können diese Werte entweder im Code oder in Konfigurationsdateien festlegen.  
  
|Einstellung|BESCHREIBUNG|  
|-------------|-----------------|  
|Keine|Gibt an, dass der Client keine Anmeldeinformationen bereitstellen muss. Dies führt zur Verwendung eines anonymen Clients.|  
|Windows|Ermöglicht unter dem mit Windows-Anmeldeinformationen eingerichteten Sicherheitskontext den Austausch von SOAP-Nachrichten.|  
|Username|Ermöglicht es dem Dienst zu fordern, dass sich der Client per Benutzername authentifiziert. Beachten Sie, dass WCF Kryptografievorgänge mit Benutzernamen nicht zulässt, wie z. b. das Erzeugen einer Signatur oder das Verschlüsseln von Daten. WCF stellt sicher, dass der Transport geschützt ist, wenn Benutzernamen-Anmelde Informationen verwendet werden.|  
|Zertifikat|Ermöglicht es dem Dienst zu fordern, dass der Client mithilfe eines X.509-Zertifikats authentifiziert wird.|  
|Ausgestelltes Token (Issued Token)|Ein benutzerdefinierter nach einer Sicherheitsrichtlinie konfigurierter Tokentyp. Der Standardtokentyp ist SAML (Security Assertions Markup Language). Das Token wird von einem sicheren Tokendienst ausgegeben. Weitere Informationen finden Sie unter Verbund [-und ausgestellte Token](federation-and-issued-tokens.md).|  
  
### <a name="negotiation-model-of-service-credentials"></a>Aushandlungsmodell von Dienstanmeldeinformationen  

 *Aushandlung* ist das Einrichten der Vertrauensstellung zwischen einem Client und einem Dienst durch Austauschen von Anmelde Informationen. Der Prozess wird iterativ zwischen dem Client und dem Dienst durchgeführt, damit jeweils nur die Informationen offengelegt werden, die für den nächsten Schritt des Aushandlungsprozesses erforderlich sind. In der Praxis ist das Endergebnis die Zustellung der Anmeldeinformationen eines Dienstes an den Client, damit diese bei nachfolgenden Vorgängen verwendet werden können.  
  
 Mit einer Ausnahme werden standardmäßig die vom System bereitgestellten Bindungen in WCF die Dienst Anmelde Informationen automatisch aushandeln, wenn die Sicherheit auf Nachrichten Ebene verwendet wird. (Die Ausnahme ist die <xref:System.ServiceModel.BasicHttpBinding> , die die Sicherheit nicht standardmäßig aktiviert.) Um dieses Verhalten zu deaktivieren, finden Sie weitere Informationen unter den <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.NegotiateServiceCredential%2A> Eigenschaften und.  
  
> [!NOTE]
> Wenn SSL-Sicherheit mit .NET Framework 3,5 und höher verwendet wird, verwendet ein WCF-Client sowohl die zwischen Zertifikate im Zertifikat Speicher als auch die zwischen Zertifikate, die während der SSL-Aushandlung empfangen werden, um die Überprüfung der Zertifikat Kette für das Dienst Zertifikat durchzuführen. Bei .NET Framework 3.0 werden nur die im lokalen Zertifikatspeicher installierten Zwischenzertifikate verwendet.  
  
#### <a name="out-of-band-negotiation"></a>Out-of-Band-Aushandlung  

 Wenn die automatische Aushandlung deaktiviert ist, müssen die Dienstanmeldeinformationen auf dem Client bereitgestellt werden, bevor Nachrichten an den Dienst gesendet werden. Dies wird auch als out- *of-Band-* Bereitstellung bezeichnet. Wenn es sich beim angegebenen Typ der Anmeldeinformationen um ein Zertifikat handelt und die automatische Aushandlung deaktiviert ist, muss sich der Client an den Besitzer des Dienstes wenden, um das Zertifikat zu erhalten und auf dem Computer zu installieren, auf dem die Clientanwendung ausgeführt wird. Sie können dies zum Beispiel nutzen, wenn Sie genau steuern möchten, welche Clients in einem Business-to-Business-Szenario auf einen Dienst zugreifen können. Diese Out-of-Band-Aushandlung kann per e-Mail erfolgen, und das X. 509-Zertifikat wird im Windows-Zertifikat Speicher mithilfe eines Tools wie dem MMC-Zertifikat-Snap-in (Microsoft Management Console) gespeichert.  
  
> [!NOTE]
> Die <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>-Eigenschaft wird verwendet, um den Dienst mit einem Zertifikat bereitzustellen, das per Out-of-Band-Aushandlung beschafft wurde. Dies ist erforderlich, wenn Sie die <xref:System.ServiceModel.BasicHttpBinding>-Klasse verwenden, da die Bindung keine automatisierte Aushandlung zulässt. Die Eigenschaft wird auch in einem nicht korrelierten Duplexszenario verwendet. Dies ist ein Szenario, bei dem ein Server eine Nachricht an den Client sendet, ohne dass der Client zuerst eine Anforderung an den Server senden muss. Da der Server nicht über eine Anforderung des Clients verfügt, muss er das Zertifikat des Clients verwenden, um die Nachricht an den Client zu verschlüsseln.  
  
## <a name="setting-credential-values"></a>Festlegen der Werte von Anmeldeinformationen  

 Nachdem Sie einen Sicherheitsmodus ausgewählt haben, müssen Sie die eigentlichen Anmeldeinformationen angeben. Wenn der Typ der Anmeldeinformationen zum Beispiel auf "Zertifikat" festgelegt ist, müssen Sie dem Dienst bzw. dem Client spezielle Anmeldeinformationen (wie ein spezifisches X.509-Zertifikat) zuordnen.  
  
 Die Methode zum Festlegen des Werts der Anmeldeinformationen unterscheidet sich in Abhängigkeit davon leicht, ob Sie einen Dienst oder einen Client programmieren.  
  
### <a name="setting-service-credentials"></a>Festlegen von Dienstanmeldeinformationen  

 Wenn Sie den Transportmodus verwenden und HTTP als Transportart nutzen, müssen Sie entweder Internetinformationsdienste (IIS) verwenden oder den Anschluss mit einem Zertifikat konfigurieren. Weitere Informationen finden Sie unter [Übersicht über die Transportsicherheit](transport-security-overview.md) und [HTTP-Transportsicherheit](http-transport-security.md).  
  
 Um einen Dienst im Code mit Anmeldeinformationen auszustatten, erstellen Sie eine Instanz der <xref:System.ServiceModel.ServiceHost>-Klasse und geben die geeigneten Anmeldeinformationen an, indem Sie die <xref:System.ServiceModel.Description.ServiceCredentials>-Klasse verwenden, auf die mithilfe der <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>-Eigenschaft zugegriffen wird.  
  
#### <a name="setting-a-certificate"></a>Festlegen eines Zertifikats  

 Um einen Dienst mit einem X.509-Zertifikat auszustatten, das zur Authentifizierung des Dienstes für Clients genutzt wird, verwenden Sie die <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>-Klasse.  
  
 Um einen Dienst mit einem Clientzertifikat bereitzustellen, verwenden Sie die <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>-Klasse.  
  
#### <a name="setting-windows-credentials"></a>Festlegen der Windows-Anmeldeinformationen  

 Wenn der Client einen gültigen Benutzernamen und ein Kennwort angibt, werden diese Anmeldeinformationen zum Authentifizieren des Clients verwendet. Andernfalls werden die Anmeldeinformationen des momentan angemeldeten Benutzers verwendet.  
  
### <a name="setting-client-credentials"></a>Festlegen von Clientanmeldeinformationen  

 In WCF verwenden Client Anwendungen einen WCF-Client, um eine Verbindung mit Diensten herzustellen. Jeder Client ist von der <xref:System.ServiceModel.ClientBase%601>-Klasse abgeleitet, und die <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>-Eigenschaft auf dem Client ermöglicht die Angabe verschiedener Werte für Clientanmeldeinformationen.  
  
#### <a name="setting-a-certificate"></a>Festlegen eines Zertifikats  

 Um einen Dienst mit einem X.509-Zertifikat auszustatten, das zum Authentifizieren des Clients für einen Dienst genutzt wird, verwenden Sie die <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>-Methode der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>-Klasse.  
  
## <a name="how-client-credentials-are-used-to-authenticate-a-client-to-the-service"></a>Verwenden von Clientanmeldeinformationen zum Authentifizieren eines Clients für einen Dienst  

 Sie stellen Clientanmeldeinformationen, die für die Kommunikation mit einem Dienst erforderlich sind, bereit, indem Sie entweder die <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>-Eigenschaft oder die <xref:System.ServiceModel.ChannelFactory.Credentials%2A>-Eigenschaft verwenden. Der Sicherheitskanal verwendet diese Informationen, um den Client für den Dienst zu authentifizieren. Die Authentifizierung erfolgt in einem von zwei Modi:  
  
- Die Client Anmelde Informationen werden einmalig verwendet, bevor die erste Nachricht gesendet wird, wobei die WCF-Client Instanz verwendet wird, um einen Sicherheitskontext einzurichten. Alle Anwendungsnachrichten werden dann über den Sicherheitskontext geschützt.  
  
- Die Clientanmeldeinformationen werden verwendet, um alle Anwendungsnachrichten zu authentifizieren, die an den Dienst gesendet werden. In diesem Fall wird zwischen dem Client und dem Dienst kein Kontext eingerichtet.  
  
### <a name="established-identities-cannot-be-changed"></a>Eingerichtete Identitäten können nicht geändert werden  

 Wenn die erste Methode verwendet wird, wird der eingerichtete Kontext dauerhaft der Clientidentität zugeordnet. Dies bedeutet, dass die dem Client zugeordnete Identität nicht geändert werden kann, nachdem der Sicherheitskontext eingerichtet wurde.  
  
> [!IMPORTANT]
> Wenn die Identität nicht gewechselt werden kann (also wenn das Einrichten eines Sicherheitskontexts aktiviert ist (Standardeinstellung)), kann ein bestimmtes Verhalten auftreten. Wenn Sie einen Dienst erstellen, der mit einem zweiten Dienst kommuniziert, kann die Identität, die zum Öffnen des WCF-Clients für den zweiten Dienst verwendet wird, nicht geändert werden. Dies wird zu einem Problem, wenn mehrere Clients den ersten Dienst verwenden dürfen und der Dienst die Identität der Clients annimmt, wenn er auf den anderen Dienst zugreift. Wenn der Dienst denselben Client für alle Aufrufer wiederverwendet, erfolgen alle Aufrufe des anderen Dienstes unter der Identität des ersten Aufrufers, der zum Öffnen des Clients für den anderen Dienst verwendet wurde. Anders ausgedrückt: Der Dienst verwendet die Identität des ersten Clients für alle Clients, um mit dem anderen Dienst zu kommunizieren. Dies kann zur Erweiterung von Berechtigungen führen. Wenn dies nicht das für den Dienst erwünschte Verhalten darstellt, müssen Sie jeden Aufrufer verfolgen und für jeden Aufrufer einen neuen Client für den anderen Dienst erstellen. Außerdem müssen Sie sicherstellen, dass der Dienst nur den richtigen Client für den jeweiligen Aufrufer verwendet, um mit dem zweiten Dienst zu kommunizieren.  
  
 Weitere Informationen zu Anmelde Informationen und sicheren Sitzungen finden Sie unter [Sicherheitsüberlegungen für sichere Sitzungen](security-considerations-for-secure-sessions.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpMessageSecurity.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityOverMsmq.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.SetCertificate%2A?displayProperty=nameWithType>
- [Sicherheitskonzepte](security-concepts.md)
- [Sichern von Diensten und Clients](securing-services-and-clients.md)
- [Programmieren der WCF-Sicherheit](programming-wcf-security.md)
- [HTTP-Transportsicherheit](http-transport-security.md)
