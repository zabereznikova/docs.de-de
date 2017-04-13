---
title: "W&#228;hlen eines Typs von Anmeldeinformationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bf707063-3f30-4304-ab53-0e63413728a8
caps.latest.revision: 25
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 25
---
# W&#228;hlen eines Typs von Anmeldeinformationen
*Anmeldeinformationen* sind die Daten, die [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] verwendet, um entweder eine beanspruchte Identität oder Funktionen einzurichten.  Ein Ausweis ist beispielsweise ein mit Anmeldeinformationen vergleichbares Dokument, das ein Staat ausgibt, damit seine Bürger ihre Staatsbürgerschaft nachweisen können.  In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] können Anmeldeinformationen viele Formate haben, zum Beispiel Benutzernamentoken und X.509\-Zertifikate.  In diesem Thema werden Anmeldeinformationen, ihre Verwendung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und die richtige Auswahl von Anmeldeinformationen für Ihre Anwendung beschrieben.  
  
 In vielen Ländern und Regionen ist ein Führerschein ein Beispiel für einen Identitätsnachweis.  Ein Führerschein enthält Daten, die die Identität und erworbene Berechtigungen einer Person nachweisen.  Der rechtmäßige Besitz wird mithilfe eines Bilds des Inhabers nachgewiesen.  Ein Führerschein oder Ausweis wird von einer vertrauenswürdigen Stelle ausgegeben, in der Regel von einer dafür zuständigen Behörde.  Der Führerschein wird eingeschweißt und enthält ggf. ein Hologramm, wodurch sichergestellt wird, dass er nicht manipuliert oder gefälscht wurde.  
  
 Das Vorlegen eines Identitätsnachweises umfasst das Angeben der Daten und den Nachweis, dass sich die Daten rechtmäßig im Besitz des Inhabers befinden.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt verschiedene Arten von Anmeldeinformationen auf der Transport\- und Nachrichtensicherheitsebene.  Sehen wir uns zum Beispiel zwei Typen von Anmeldeinformationen an, die in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt werden: Benutzername und Zertifikatsanmeldeinformationen \(X.509\).  
  
 Beim Benutzernamenteil der Anmeldeinformationen stellt der Benutzername die beanspruchte Identität und das Kennwort den Nachweis des rechtmäßigen Besitzes dar.  Die vertrauenswürdige Stelle ist in diesem Fall das System, das den Benutzernamen und das Kennwort überprüft.  
  
 Wenn ein X.509\-Zertifikat für die Anmeldeinformationen verwendet wird, können der Antragstellername, der alternative Antragstellername oder spezielle Felder im Zertifikat für die Beanspruchung der Identität verwendet werden, während andere Felder wie `Valid From` und `Valid To` die Gültigkeit des Zertifikats angeben.  
  
## Transportieren von Anmeldeinformationen\-Typen  
 Die folgende Tabelle zeigt die möglichen Typen von Clientanmeldeinformationen, die von einer Bindung im Transportsicherheitsmodus verwendet werden können.  Legen Sie die `ClientCredentialType`\-Eigenschaft beim Erstellen eines Dienstes auf einen dieser Werte fest, um den Typ der Anmeldeinformationen anzugeben, den der Client zum Kommunizieren mit Ihrem Dienst bereitstellen muss.  Sie können die Typen entweder im Code oder in Konfigurationsdateien festlegen.  
  
|Einstellung|Beschreibung|  
|-----------------|------------------|  
|Keine|Gibt an, dass der Client keine Anmeldeinformationen präsentieren muss.  Dies führt zur Verwendung eines anonymen Clients.|  
|Standard|Gibt die Standardauthentifizierung für den Client an.  Zusätzliche Informationen finden Sie unter RFC 2617, [HTTP\-Authentifizierung: Standard\- und Digestauthentifizierung](http://go.microsoft.com/fwlink/?LinkID=88313).|  
|Digest|Gibt die Digestauthentifizierung für den Client an.  Zusätzliche Informationen finden Sie unter RFC 2617, [HTTP\-Authentifizierung: Standard\- und Digestauthentifizierung](http://go.microsoft.com/fwlink/?LinkID=88313).|  
|Ntlm|Gibt die NT\-LAN\-Managerauthentifizierung \(NTLM\) an.  Wird verwendet, wenn Sie aus bestimmten Gründen keine Kerberos\-Authentifizierung verwenden können.  Sie können die Verwendung als Ausweichlösung auch deaktivieren, indem Sie die <xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A>\-Eigenschaft auf `false` festlegen, wodurch [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nach dem Best\-Effort\-Prinzip eine Ausnahme auslöst, wenn NTLM verwendet wird.  Durch das Festlegen dieser Eigenschaft auf `false` wird unter Umständen nicht verhindert, dass NTLM\-Anmeldeinformationen über die Verbindung gesendet werden.|  
|Windows|Gibt die Windows\-Authentifizierung an.  Um für eine Windows\-Domäne nur das Kerberos\-Protokoll anzugeben, legen Sie die <xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A>\-Eigenschaft auf `false` fest \(die Standardeinstellung ist `true`\).|  
|Zertifikat|Führt die Clientauthentifizierung mit einem X.509\-Zertifikat aus.|  
|Kennwort|Benutzer müssen einen Benutzernamen und ein Kennwort angeben.  Überprüfen Sie das Benutzername\/Kennwort\-Paar mithilfe der Windows\-Authentifizierung oder einer anderen benutzerdefinierten Lösung.|  
  
### Typen von Nachrichtenclient\-Anmeldeinformationen  
 Die folgende Tabelle zeigt die möglichen Typen von Anmeldeinformationen, die Sie beim Erstellen einer Anwendung verwenden können, die die Nachrichtensicherheit nutzt.  Sie können diese Werte entweder im Code oder in Konfigurationsdateien festlegen.  
  
|Einstellung|Beschreibung|  
|-----------------|------------------|  
|Keine|Gibt an, dass der Client keine Anmeldeinformationen bereitstellen muss.  Dies führt zur Verwendung eines anonymen Clients.|  
|Windows|Ermöglicht unter dem mit Windows\-Anmeldeinformationen eingerichteten Sicherheitskontext den Austausch von SOAP\-Nachrichten.|  
|Benutzername|Ermöglicht es dem Dienst zu fordern, dass sich der Client per Benutzername authentifiziert.  Beachten Sie, dass in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] keine kryptografischen Vorgänge mit den Benutzernamen wie das Erzeugen einer Signatur oder das Verschlüsseln von Daten zulässig sind.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt sicher, dass der Transport geschützt wird, wenn der Identitätsnachweis über den Benutzernamen erfolgt.|  
|Zertifikat|Ermöglicht es dem Dienst zu fordern, dass der Client mithilfe eines X.509\-Zertifikats authentifiziert wird.|  
|Ausgestelltes Token \(Issued Token\)|Ein benutzerdefinierter nach einer Sicherheitsrichtlinie konfigurierter Tokentyp.  Der Standardtokentyp ist SAML \(Security Assertions Markup Language\).  Das Token wird von einem sicheren Tokendienst ausgegeben.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Verbund und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).|  
  
### Aushandlungsmodell von Dienstanmeldeinformationen  
 Die *Aushandlung* ist der Prozess, durch den Austausch von Anmeldeinformationen Vertrauenswürdigkeit zwischen einem Client und einem Dienst zu erzielen.  Der Prozess wird iterativ zwischen dem Client und dem Dienst durchgeführt, damit jeweils nur die Informationen offengelegt werden, die für den nächsten Schritt des Aushandlungsprozesses erforderlich sind.  In der Praxis ist das Endergebnis die Zustellung der Anmeldeinformationen eines Dienstes an den Client, damit diese bei nachfolgenden Vorgängen verwendet werden können.  
  
 Dabei gilt eine Ausnahme: Die vom System bereitgestellten Bindungen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] handeln die Dienstanmeldeinformationen automatisch beim Verwenden der Nachrichtenebenensicherheit aus.  \(Die Ausnahme ist die <xref:System.ServiceModel.BasicHttpBinding>, die die Sicherheit standardmäßig nicht aktiviert.\) Um dieses Verhalten zu deaktivieren, können Sie die Eigenschaften <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> und <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.NegotiateServiceCredential%2A> verwenden.  
  
> [!NOTE]
>  Wenn SSL\-Sicherheit in Verbindung mit .NET Framework&\#160;3.5 und höher verwendet wird, verwenden [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clients zur Validierung des Dienstzertifikats mittels einer Zertifikatskette sowohl die Zwischenzertifikate aus dem lokalen Zertifikatspeicher als auch die Zwischenzertifikate, die sie im Rahmen der SSL\-Verhandlung empfangen haben.  Bei .NET Framework 3.0 werden nur die im lokalen Zertifikatspeicher installierten Zwischenzertifikate verwendet.  
  
#### Out\-of\-Band\-Aushandlung  
 Wenn die automatische Aushandlung deaktiviert ist, müssen die Dienstanmeldeinformationen auf dem Client bereitgestellt werden, bevor Nachrichten an den Dienst gesendet werden.  Dies wird auch als *Out\-of\-Band*\-Bereitstellung bezeichnet.  Wenn es sich beim angegebenen Typ der Anmeldeinformationen um ein Zertifikat handelt und die automatische Aushandlung deaktiviert ist, muss sich der Client an den Besitzer des Dienstes wenden, um das Zertifikat zu erhalten und auf dem Computer zu installieren, auf dem die Clientanwendung ausgeführt wird.  Sie können dies zum Beispiel nutzen, wenn Sie genau steuern möchten, welche Clients in einem Business\-to\-Business\-Szenario auf einen Dienst zugreifen können.  Diese Out\-of\-Band\-Aushandlung kann per E\-Mail erfolgen, und das X.509\-Zertifikat wird im Windows\-Zertifikatspeicher gespeichert. Dabei wird ein Tool wie das Microsoft Management Console \(MMC\)\-Zertifikat\-Snap\-In verwendet.  
  
> [!NOTE]
>  Die <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>\-Eigenschaft wird verwendet, um den Dienst mit einem Zertifikat bereitzustellen, das per Out\-of\-Band\-Aushandlung beschafft wurde.  Dies ist erforderlich, wenn Sie die <xref:System.ServiceModel.BasicHttpBinding>\-Klasse verwenden, da die Bindung keine automatisierte Aushandlung zulässt.  Die Eigenschaft wird auch in einem nicht korrelierten Duplexszenario verwendet.  Dies ist ein Szenario, bei dem ein Server eine Nachricht an den Client sendet, ohne dass der Client zuerst eine Anforderung an den Server senden muss.  Da der Server nicht über eine Anforderung des Clients verfügt, muss er das Zertifikat des Clients verwenden, um die Nachricht an den Client zu verschlüsseln.  
  
## Festlegen der Werte von Anmeldeinformationen  
 Nachdem Sie einen Sicherheitsmodus ausgewählt haben, müssen Sie die eigentlichen Anmeldeinformationen angeben.  Wenn der Typ der Anmeldeinformationen zum Beispiel auf "Zertifikat" festgelegt ist, müssen Sie dem Dienst bzw. dem Client spezielle Anmeldeinformationen \(wie ein spezifisches X.509\-Zertifikat\) zuordnen.  
  
 Die Methode zum Festlegen des Werts der Anmeldeinformationen unterscheidet sich in Abhängigkeit davon leicht, ob Sie einen Dienst oder einen Client programmieren.  
  
### Festlegen von Dienstanmeldeinformationen  
 Wenn Sie den Transportmodus verwenden und HTTP als Transportart nutzen, müssen Sie entweder Internetinformationsdienste \(IIS\) verwenden oder den Anschluss mit einem Zertifikat konfigurieren.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Übersicht über die Transportsicherheit](../../../../docs/framework/wcf/feature-details/transport-security-overview.md) und [HTTP\-Transportsicherheit](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 Um einen Dienst im Code mit Anmeldeinformationen auszustatten, erstellen Sie eine Instanz der <xref:System.ServiceModel.ServiceHost>\-Klasse und geben die geeigneten Anmeldeinformationen an, indem Sie die <xref:System.ServiceModel.Description.ServiceCredentials>\-Klasse verwenden, auf die mithilfe der <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>\-Eigenschaft zugegriffen wird.  
  
#### Festlegen eines Zertifikats  
 Um einen Dienst mit einem X.509\-Zertifikat auszustatten, das zur Authentifizierung des Dienstes für Clients genutzt wird, verwenden Sie die <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.SetCertificate%2A>\-Methode der <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>\-Klasse.  
  
 Um einen Dienst mit einem Clientzertifikat bereitzustellen, verwenden Sie die <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>\-Methode der <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>\-Klasse.  
  
#### Festlegen der Windows\-Anmeldeinformationen  
 Wenn der Client einen gültigen Benutzernamen und ein Kennwort angibt, werden diese Anmeldeinformationen zum Authentifizieren des Clients verwendet.  Andernfalls werden die Anmeldeinformationen des momentan angemeldeten Benutzers verwendet.  
  
### Festlegen von Clientanmeldeinformationen  
 In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwenden Clientanwendungen einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Client, um eine Verbindung mit Diensten herzustellen.  Jeder Client ist von der <xref:System.ServiceModel.ClientBase%601>\-Klasse abgeleitet, und die <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>\-Eigenschaft auf dem Client ermöglicht die Angabe verschiedener Werte für Clientanmeldeinformationen.  
  
#### Festlegen eines Zertifikats  
 Um einen Dienst mit einem X.509\-Zertifikat auszustatten, das zum Authentifizieren des Clients für einen Dienst genutzt wird, verwenden Sie die <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>\-Methode der <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>\-Klasse.  
  
## Verwenden von Clientanmeldeinformationen zum Authentifizieren eines Clients für einen Dienst  
 Sie stellen Clientanmeldeinformationen, die für die Kommunikation mit einem Dienst erforderlich sind, bereit, indem Sie entweder die <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>\-Eigenschaft oder die <xref:System.ServiceModel.ChannelFactory.Credentials%2A>\-Eigenschaft verwenden.  Der Sicherheitskanal verwendet diese Informationen, um den Client für den Dienst zu authentifizieren.  Die Authentifizierung erfolgt in einem von zwei Modi:  
  
-   Die Clientanmeldeinformationen werden einmal verwendet, bevor die erste Nachricht gesendet wird, indem mithilfe der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientinstanz ein Sicherheitskontext eingerichtet wird.  Alle Anwendungsnachrichten werden dann über den Sicherheitskontext geschützt.  
  
-   Die Clientanmeldeinformationen werden verwendet, um alle Anwendungsnachrichten zu authentifizieren, die an den Dienst gesendet werden.  In diesem Fall wird zwischen dem Client und dem Dienst kein Kontext eingerichtet.  
  
### Eingerichtete Identitäten können nicht geändert werden  
 Wenn die erste Methode verwendet wird, wird der eingerichtete Kontext dauerhaft der Clientidentität zugeordnet.  Dies bedeutet, dass die dem Client zugeordnete Identität nicht geändert werden kann, nachdem der Sicherheitskontext eingerichtet wurde.  
  
> [!IMPORTANT]
>  Wenn die Identität nicht gewechselt werden kann \(also wenn das Einrichten eines Sicherheitskontexts aktiviert ist \(Standardeinstellung\)\), kann ein bestimmtes Verhalten auftreten.  Wenn Sie einen Dienst erstellen, der mit einem anderen Dienst kommuniziert, können Sie die Identität, die zum Öffnen des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clients für den anderen Dienst verwendet wird, nicht ändern.  Dies wird zu einem Problem, wenn mehrere Clients den ersten Dienst verwenden dürfen und der Dienst die Identität der Clients annimmt, wenn er auf den anderen Dienst zugreift.  Wenn der Dienst denselben Client für alle Aufrufer wiederverwendet, erfolgen alle Aufrufe des anderen Dienstes unter der Identität des ersten Aufrufers, der zum Öffnen des Clients für den anderen Dienst verwendet wurde.  Anders ausgedrückt: Der Dienst verwendet die Identität des ersten Clients für alle Clients, um mit dem anderen Dienst zu kommunizieren.  Dies kann zur Erweiterung von Berechtigungen führen.  Wenn dies nicht das für den Dienst erwünschte Verhalten darstellt, müssen Sie jeden Aufrufer verfolgen und für jeden Aufrufer einen neuen Client für den anderen Dienst erstellen. Außerdem müssen Sie sicherstellen, dass der Dienst nur den richtigen Client für den jeweiligen Aufrufer verwendet, um mit dem zweiten Dienst zu kommunizieren.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Anmeldeinformationen und Sicherheitssitzungen finden Sie unter [Sicherheitsüberlegungen für Sicherheitssitzungen](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md).  
  
## Siehe auch  
 <xref:System.ServiceModel.ClientBase%601?displayProperty=fullName>   
 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A?displayProperty=fullName>   
 <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A?displayProperty=fullName>   
 <xref:System.ServiceModel.BasicHttpMessageSecurity.ClientCredentialType%2A?displayProperty=fullName>   
 <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A?displayProperty=fullName>   
 <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A?displayProperty=fullName>   
 <xref:System.ServiceModel.MessageSecurityOverMsmq.ClientCredentialType%2A?displayProperty=fullName>   
 <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A?displayProperty=fullName>   
 <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A?displayProperty=fullName>   
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=fullName>   
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=fullName>   
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.SetCertificate%2A?displayProperty=fullName>   
 [Begriffe der Sicherheit](../../../../docs/framework/wcf/feature-details/security-concepts.md)   
 [Sichern von Diensten und Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Programmieren der WCF\-Sicherheit](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)   
 [HTTP\-Transportsicherheit](../../../../docs/framework/wcf/feature-details/http-transport-security.md)