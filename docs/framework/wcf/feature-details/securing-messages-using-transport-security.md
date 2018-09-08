---
title: Sichern von Nachrichten mit Transportsicherheit
ms.date: 03/30/2017
ms.assetid: 9029771a-097e-448a-a13a-55d2878330b8
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 0ab04326404a4b90e30036594a7152e6118c2138
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44129140"
---
# <a name="securing-messages-using-transport-security"></a>Sichern von Nachrichten mit Transportsicherheit
In diesem Abschnitt wird die Message Queuing (MSMQ)-Transportsicherheit näher erläutert, mit der Sie an eine Warteschlange gesendete Nachrichten sichern können.  
  
> [!NOTE]
>  In diesem Thema lesen, es wird empfohlen, vor Sie lesen [Sicherheitskonzepte](../../../../docs/framework/wcf/feature-details/security-concepts.md).  
  
 Die folgende Abbildung zeigt ein konzeptionelles Modell einer warteschlangenkommunikation mithilfe von Windows Communication Foundation (WCF). Diese Abbildung und die Terminologie dienen zum Beschreiben von Transportsicherheitskonzepten:  
  
 ![In der Warteschlange Anwendungsdiagramm](../../../../docs/framework/wcf/feature-details/media/distributed-queue-figure.jpg "Distributed-Warteschlange-Abbildung")  
  
 Beim Senden von Nachrichten in der Warteschlange mithilfe von WCF mit <xref:System.ServiceModel.NetMsmqBinding>, die WCF-Nachricht als Textkörper der MSMQ-Nachricht angefügt ist. Mit der Transportsicherheit wird die gesamte MSMQ-Nachricht (MSMQ-Nachrichtenheader oder Nachrichteneigenschaften und der Textkörper) gesichert. Da es sich um den Text der MSMQ-Nachricht handelt, sichert mithilfe der transportsicherheit auch die WCF-Nachricht.  
  
 Das Kernkonzept hinter der Transportsicherheit besteht darin, dass der Client die Sicherheitsanforderungen erfüllen muss, um die Nachricht in die Zielwarteschlange zu stellen. Bei der Nachrichtensicherheit hingegen wird die Nachricht für die Anwendung gesichert, die die Nachricht empfängt.  
  
 Durch den Einsatz der Transportsicherheit mit <xref:System.ServiceModel.NetMsmqBinding> und <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> wird bestimmt, wie MSMQ-Nachrichten bei der Übertragung von der Übertragungswarteschlange zur Zielwarteschlange gesichert werden. Sicherheit bedeutet hier:  
  
-   Signieren der Nachricht, um sicherzustellen, dass sie nicht verfälscht wurde.  
  
-   Verschlüsseln der Nachricht, um sicherzustellen, dass sie nicht angezeigt oder verfälscht werden kann. Dies wird empfohlen, ist jedoch optional.  
  
-   Der Zielwarteschlangenmanager, der überprüft, dass der Sender der Nachricht wirklich der Absender ist.  
  
 In MSMQ hat die Zielwarteschlange, unabhängig von der Authentifizierung, eine Access Control List (ACL), anhand der überprüft wird, ob der Client die Berechtigung hat, die Nachricht an die Zielwarteschlange zu senden. Die Empfängeranwendung wird ebenfalls daraufhin überprüft, ob sie die Berechtigung hat, die Nachricht aus der Zielwarteschlange zu empfangen.  
  
## <a name="wcf-msmq-transport-security-properties"></a>WCF MSMQ-Transportsicherheitseigenschaften  
 MSMQ verwendet bei der Authentifizierung die Windows-Sicherheit. Es verwendet die Windows-Sicherheits-ID (SID), um den Client zu identifizieren, und nutzt beim Authentifizieren des Clients den Active Directory-Verzeichnisdienst als Zertifizierungsstelle. Dabei muss MSMQ mit Active Directory-Integration installiert sein. Da die Windows-Domänen-SID zum Identifizieren des Clients verwendet wird, ist diese Sicherheitsoption nur dann sinnvoll, wenn der Client und der Dienst Teil der gleichen Windows-Domäne sind.  
  
 MSMQ bietet zudem die Möglichkeit, ein Zertifikat an die Nachricht, die nicht beim Active Directory registriert ist, anzuhängen. In diesem Fall wird dadurch sichergestellt, dass die Nachricht mit dem angehängten Zertifikat signiert wurde.  
  
 WCF stellt diese beiden Optionen werden als Teil des MSMQ-transportsicherheit bereit, und sie sind ein wichtiger Aspekt für die transportsicherheit.  
  
 Die Transportsicherheit ist standardmäßig aktiviert.  
  
 Auf diesen Grundlagen basierend werden in den folgenden Abschnitten die Transportsicherheitseigenschaften gebündelt mit <xref:System.ServiceModel.NetMsmqBinding> und <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> näher vorgestellt.  
  
#### <a name="msmq-authentication-mode"></a>MSMQ-Authentifizierungsmodus  
 Der <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> bestimmt, ob die Windows-Domänensicherheit oder eine externe Zertifikats-basierte Sicherheit zum Sichern der Nachricht verwendet werden soll. In beiden Authentifizierungsmodi verwendet der WCF-Warteschlangentransport-Kanal die `CertificateValidationMode` in der Dienstkonfiguration angegeben. Der Zertifikatsvalidierungsmodus legt den zu verwendenden Mechanismus fest, um die Gültigkeit des Zertifikats zu überprüfen.  
  
 Wenn die Transportsicherheit aktiviert ist, ist die Standardeinstellung <xref:System.ServiceModel.MsmqAuthenticationMode.WindowsDomain>.  
  
#### <a name="windows-domain-authentication-mode"></a>Windows-Domänenauthentifizierungsmodus  
 Um die Windows-Sicherheit verwenden zu können, ist die Active Directory-Integration erforderlich. <xref:System.ServiceModel.MsmqAuthenticationMode.WindowsDomain> ist der standardmäßige Transportsicherheitsmodus. Wenn dies festgelegt ist, wird der WCF-Kanal fügt die Windows-SID an die MSMQ-Nachricht und verwendet das interne Zertifikat, das von Active Directory abgerufen. MSMQ verwendet dieses interne Zertifikat, um die Nachricht zu sichern. Der Warteschlangenmanager, der die Nachricht empfängt, verwendet Active Directory, um ein entsprechendes Zertifikat zu suchen, mit dem der Client authentifiziert werden kann. Zugleich wird dadurch überprüft, dass die SID auch der des Clients entspricht. Dieser Authentifizierungsschritt wird ausgeführt, wenn ein Zertifikat, sei es intern erstellt worden wie im Fall des `WindowsDomain`-Authentifizierungsmodus, oder extern wie im Fall des `Certificate`-Authentifizierungsmodus, an die Nachricht angehängt wird, selbst wenn für die Zielwarteschlange nicht festgelegt wurde, dass eine Authentifizierung notwendig ist.  
  
> [!NOTE]
>  Beim Erstellen einer Warteschlange können Sie die Warteschlange als authentifizierte Warteschlange kennzeichnen, um anzugeben, dass für die Warteschlange eine Authentifizierung des Clients, der die Nachricht an die Warteschlange sendet, erforderlich ist. Dadurch wird sichergestellt, dass keine nicht authentifizierten Nachrichten in die Warteschlange aufgenommen werden.  
  
 Die an die Nachricht angehängte SID wird ebenfalls zum Überprüfen der Zielwarteschlange anhand der ACL verwendet, um sicherzustellen, dass der Client die Berechtigung hat, die Nachrichten an die Warteschlange zu senden.  
  
#### <a name="certificate-authentication-mode"></a>Zertifikatsauthentifizierungsmodus  
 Für den Zertifikatsauthentifizierungsmodus ist keine Active Directory-Integration erforderlich. In einigen Fällen, z. B. wenn MSMQ im Arbeitsgruppenmodus installiert ist (ohne Active Directory-Integration) oder wenn zum Senden von Nachrichten an die Warteschlange das SOAP Reliable Messaging Protocol (SRMP)-Übertragungsprotokoll verwendet wird, kann nur der <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate> eingesetzt werden.  
  
 Beim Senden einer WCF-Nachricht mit <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate>, der WCF-Kanal eine Windows-SID an die MSMQ-Nachricht wird nicht angefügt werden. Daher muss die Zielwarteschlangen-ACL den `Anonymous` Benutzerzugriff zum Senden an die Warteschlange zulassen. Der empfangende Warteschlangenmanager überprüft, ob die MSMQ-Nachricht mit dem Zertifikat signiert wurde, führt jedoch keine Authentifizierung durch.  
  
 Das Zertifikat mit den enthaltenen Ansprüchen und Identitätsinformationen wird aufgefüllt, der <xref:System.ServiceModel.ServiceSecurityContext> von der WCF-Warteschlangentransport-Kanal. Der Dienst kann diese Informationen zum Durchführen der eigenen Authentifizierung des Absenders verwenden.  
  
### <a name="msmq-protection-level"></a>MSMQ-Schutzebene  
 Die Schutzebene bestimmt, wie die MSMQ-Nachricht geschützt werden soll, um sicherzustellen, dass sie nicht manipuliert wird. Sie wird in der <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>-Eigenschaft angegeben. Der Standardwert ist <xref:System.Net.Security.ProtectionLevel.Sign>.  
  
#### <a name="sign-protection-level"></a>Signatur-Schutzebene  
 Die MSMQ-Nachricht wird mit dem intern generierten Zertifikat im `WindowsDomain`-Authentifizierungsmodus bzw. mit einem extern generierten Zertifikat im `Certificate`-Authentifizierungsmodus signiert.  
  
#### <a name="sign-and-encrypt-protection-level"></a>Signatur- und Verschlüsselsungsschutzebene  
 Die MSMQ-Nachricht wird mit dem intern generierten Zertifikat im `WindowsDomain`-Authentifizierungsmodus bzw. mit einem extern generierten Zertifikat im `Certificate`-Authentifizierungsmodus signiert.  
  
 Zusätzlich zum Signieren der Nachricht wird die MSMQ-Nachricht mit dem öffentlichen Schlüssel des Zertifikats aus Active Directory verschlüsselt, das zum empfangenden Warteschlangenmanager gehört, der Host der Zielwarteschlange ist. Der sendende Warteschlangenmanager stellt sicher, dass die MSMQ-Nachricht bei der Übertragung verschlüsselt ist. Der empfangende Warteschlangenmanager verschlüsselt die MSMQ-Nachricht mit dem privaten Schlüssel des internen Zertifikats und speichert die Nachricht in der Warteschlange (bei Authentifizierung und Autorisierung) als Klartext.  
  
> [!NOTE]
>  Zum Verschlüsseln der Nachricht ist ein Active Directory-Zugriff erforderlich (`UseActiveDirectory`-Eigenschaft von <xref:System.ServiceModel.NetMsmqBinding> muss auf `true` festgelegt werden), der wiederum mit <xref:System.ServiceModel.MsmqAuthenticationMode.Certificate> und <xref:System.ServiceModel.MsmqAuthenticationMode.WindowsDomain> verwendet werden kann.  
  
#### <a name="none-protection-level"></a>Ohne Schutzebene  
 Dies wird impliziert, wenn <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> auf <xref:System.Net.Security.ProtectionLevel.None> festgelegt wurde. Dies ist kein gültiger Wert für andere Authentifizierungsmodi.  
  
> [!NOTE]
>  Wenn die MSMQ-Nachricht signiert wurde, überprüft MSMQ, ob die Nachricht mit dem angehängten Zertifikat (intern oder extern), das vom Status der Warteschlange (authentifiziert oder nicht authentifiziert) unabhängig ist, signiert wurde.  
  
### <a name="msmq-encryption-algorithm"></a>MSMQ-Verschlüsselungsalgorithmus  
 Der Verschlüsselungsalgorithmus gibt den Algorithmus an, mit dem die MSMQ-Nachricht bei der Übertragung verschlüsselt werden soll. Diese Eigenschaft wird nur verwendet, wenn <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> auf <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> festgelegt wurde.  
  
 Unterstützte Algorithmen sind:`RC4Stream` und `AES`, wobei `RC4Stream` der Standardwert ist.  
  
 Sie können den `AES`-Algorithmus nur verwenden, wenn der Sender MSMQ 4.0 installiert hat. Darüber hinaus muss die Zielwarteschlange auf MSMQ 4.0 gehostet werden.  
  
### <a name="msmq-hash-algorithm"></a>MSMQ-Hashalgorithmus  
 Der Hashalgorithmus bestimmt den Algorithmus, mit dem eine digitale Signatur der MSMQ-Nachricht erstellt wird. Der empfangende Warteschlangenmanager verwendet den gleichen Algorithmus zum Authentifizieren der MSMQ-Nachricht. Diese Eigenschaft wird nur verwendet, wenn <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> auf <xref:System.Net.Security.ProtectionLevel.Sign> oder <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> festgelegt wurde.  
  
 Es werden die folgenden Algorithmen unterstützt: `MD5`, `SHA1`, `SHA256` und `SHA512`. Die Standardeinstellung ist `SHA1`.  
  
## <a name="see-also"></a>Siehe auch  
 [Message Queuing-](https://msdn.microsoft.com/library/ff917e87-05d5-478f-9430-0f560675ece1)  
 [Begriffe der Sicherheit](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
 [Sichern von Diensten und Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
