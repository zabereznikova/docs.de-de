---
title: Dienstidentität und Authentifizierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [WCF], specifying the identity of a service
ms.assetid: a4c8f52c-5b30-45c4-a545-63244aba82be
ms.openlocfilehash: 834829d8eee95a8a62363a05b4af9430c435753b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586229"
---
# <a name="service-identity-and-authentication"></a>Dienstidentität und Authentifizierung
Eines Diensts *Endpunktidentität* ist ein Wert aus dem Web Services Description Language (WSDL)-Dienst generiert. Dieser an jeden Client weitergegebene Wert wird zum Authentifizieren des Diensts verwendet. Nachdem der Client eine Kommunikation mit einem Endpunkt initiiert und der Dienst sich gegenüber dem Client authentifiziert hat, vergleicht der Client den Wert der Endpunktidentität mit dem tatsächlichen Wert, den der Vorgang der Authentifizierung des Endpunkts zurückgegeben hat. Stimmen sie überein, kann der Client sicher sein, dass er Kontakt zu dem erwarteten Dienstendpunkt hergestellt hat. Diese fungiert als ein Schutz gegen *Phishing* durch die verhindert, dass eines Clients an einem von einem böswilligen Dienst gehosteten Endpunkt umgeleitet wird.  
  
 Eine beispielanwendung, die identitätseinstellung veranschaulicht, finden Sie unter [Dienstidentitätsbeispiel](../../../../docs/framework/wcf/samples/service-identity-sample.md). Weitere Informationen zu Endpunkten und Endpunktadressen finden Sie unter [Adressen](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md).  
  
> [!NOTE]
>  Wenn Sie NT&amp;#160;LanMan (NTLM) für die Authentifizierung verwenden, wird die Dienstidentität nicht überprüft, weil unter NTLM der Client den Server nicht authentifizieren kann. NTLM wird verwendet, wenn Computer Teil einer Windows-Arbeitsgruppe sind, oder sie eine ältere Version von Windows ausführen, die die Kerberos-Authentifizierung nicht unterstützt.  
  
 Wenn der Client einen sicheren Kanal zum Senden einer Nachricht an einen Dienst darauf initiiert, die Windows Communication Foundation (WCF)-Infrastruktur der Dienst authentifiziert und sendet die Nachricht nur, wenn die Identität des im Endpunkt angegebene Identität übereinstimmt Adresse des Clients verwendet.  
  
 Der Vorgang der Identitätsverarbeitung umfasst die folgenden Phasen:  
  
- Zur Entwurfszeit bestimmt der Cliententwickler die Identität des Diensts aus den (durch WSDL verfügbar gemachten) Metadaten der Endpunkte.  
  
- Zur Laufzeit überprüft die Clientanwendung die Ansprüche der Sicherheitsanmeldeinformationen des Diensts, bevor irgendwelche Meldungen an den Dienst gesendet werden.  
  
 Die Identitätsverarbeitung auf dem Client entspricht der Clientauthentifizierung des Diensts. Ein sicherer Dienst führt so lange keinen Code aus, bis die Anmeldeinformationen des Clients authentifiziert wurden. Entsprechend sendet der Client so lange keine Nachrichten an den Dienst, bis die Anmeldeinformationen des Diensts auf der Grundlage dessen, was aus den Metadaten des Diensts im Voraus bekannt ist, authentifiziert wurden.  
  
 Die <xref:System.ServiceModel.EndpointAddress.Identity%2A>-Eigenschaft der <xref:System.ServiceModel.EndpointAddress>-Klasse stellt die Identität des Diensts dar, der vom Client aufgerufen wird. Der Dienst veröffentlicht die <xref:System.ServiceModel.EndpointAddress.Identity%2A> in seinen Metadaten. Wenn der Entwickler des Clients ausgeführt wird die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) für den Dienstendpunkt enthält die generierte Konfiguration den Wert des Diensts <xref:System.ServiceModel.EndpointAddress.Identity%2A> Eigenschaft. Die WCF-Infrastruktur (sofern für Sicherheit konfiguriert) stellt sicher, dass der Dienst die angegebene Identität besitzt.  
  
> [!IMPORTANT]
>  Die Metadaten enthalten die erwartete Identität des Diensts. Daher wird empfohlen, die Metadaten des Diensts auf sichere Weise verfügbar zu machen, indem Sie beispielsweise einen HTTPS-Endpunkt für den Dienst erstellen. Weitere Informationen finden Sie unter [Vorgehensweise: Sichere Metadatenendpunkte](../../../../docs/framework/wcf/feature-details/how-to-secure-metadata-endpoints.md).  
  
## <a name="identity-types"></a>Identitätstypen  
 Ein Dienst kann es sich um sechs Typen von Identitäten bereitstellen. Jeder Identitätstyp entspricht einem Element, das im `<identity>`-Element der Konfiguration enthalten sein kann. Der verwendete Typ hängt vom Szenario und den Sicherheitsanforderungen des Diensts ab. In der folgenden Tabelle wird jeder dieser Identitätstypen beschrieben.  
  
|Identitätstyp|Beschreibung|Typisches Szenario|  
|-------------------|-----------------|----------------------|  
|DNS (Domain Name System)|Verwenden Sie dieses Element mit X.509-Zertifikaten oder Windows-Konten. Es vergleicht den in den Anmeldeinformationen angegebenen DNS-Namen mit dem in diesem Element angegebenen Wert.|Eine DNS-Prüfung ermöglicht Ihnen, Zertifikate mit DNS- oder Antragstellernamen zu verwenden. Wird ein Zertifikat erneut mit demselben DNS- oder Antragstellernamen ausgestellt, ist die Identitätsprüfung immer noch gültig. Bei der erneuten Ausstellung eines Zertifikats erhält es einen neuen RSA-Schlüssel, behält jedoch denselben DNS- oder Antragstellernamen. Dies bedeutet, dass Clients ihre Identitätsinformationen für den Dienst nicht aktualisieren müssen.|  
|Zertifikat. Der Standardwert, wenn `ClientCredentialType` auf Certificate festgelegt ist.|Dieses Element gibt einen Base64-codierten X.509-Zertifikatswert für den Vergleich mit dem Client an.<br /><br /> Verwenden Sie dieses Element auch dann, wenn Sie eine [!INCLUDE[infocard](../../../../includes/infocard-md.md)] für die Anmeldeinformationen zur Authentifizierung des Diensts verwenden.|Dieses Element schränkt die Authentifizierung auf ein einziges Zertifikat ein, dessen Fingerabdruckwert für die Authentifizierung verwendet wird. Dies ermöglicht eine strengere Authentifizierung, da Fingerabdruckwerte eindeutig sind. Dies ist eine Einschränkung verbunden: Wenn das Zertifikat mit dem gleichen Antragstellernamen erneut ausgestellt, hat es auch einen neuen Fingerabdruck. Daher können Clients den Dienst so lange nicht prüfen, bis der neue Fingerabdruck bekannt ist. Weitere Informationen zum Suchen eines Zertifikat Fingerabdrucks finden Sie unter [Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).|  
|Zertifikatsverweis|Identisch mit der vorher beschriebenen Zertifikatsoption. Jedoch erlaubt Ihnen dieses Element, einen Zertifikatsnamen und den Speicherort anzugeben, von dem das Zertifikat abgerufen werden kann.|Entspricht dem vorher beschriebenen Zertifikatsszenario.<br /><br /> Der Vorteil besteht darin, dass sich der Speicherort des Zertifikats ändern kann.|  
|RSA|Dieses Element gibt einen RSA-Schlüsselwert für den Vergleich mit dem Client an. Dies ist der Zertifikatsoption ähnlich, statt des Fingerabdrucks des Zertifikats wird jedoch dessen RSA-Schlüssel verwendet.|Eine RSA-Prüfung erlaubt Ihnen, die Authentifizierung speziell auf den RSA-Schlüssel eines einzigen Zertifikats zu beschränken. Dies ermöglicht eine strengere Authentifizierung eines bestimmten RSA-Schlüssels auf Kosten des Diensts, der nicht mehr mit vorhandenen Clients zusammenarbeitet, wenn sich der RSA-Schlüsselwert ändert.|  
|Benutzerprinzipalname (User Principal Name, UPN) Der Standard, wenn `ClientCredentialType` auf Windows festgelegt ist und der Dienstprozess nicht unter einem der Systemkonten ausgeführt wird.|Dieses Element gibt den UPN an, unter dem der Dienst ausgeführt wird. Finden Sie im Abschnitt Kerberos-Protokoll und Identität von [Überschreiben der Identität eines Dienstes zur Authentifizierung](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md).|Dies stellt sicher, dass der Dienst unter einem bestimmten Windows-Benutzerkonto ausgeführt wird. Das Benutzerkonto kann entweder das des momentan angemeldeten Benutzers sein, oder der des Diensts, der unter einem bestimmten Benutzerkonto ausgeführt wird.<br /><br /> Diese Einstellung nutzt die Vorteile der Kerberos-Sicherheit von Windows, wenn der Dienst unter einem Domänenkonto in einer Active Directory-Umgebung ausgeführt wird.|  
|Dienstprinzipalname (Service Principal Name, SPN) Der Standard, wenn `ClientCredentialType` auf Windows festgelegt ist und der Dienstprozess unter einem der Systemkonten &amp;#8211; LocalService, LocalSystem oder NetworkService &amp;#8211; ausgeführt wird.|Dieses Element gibt den dem Konto des Diensts zugeordneten SPN an. Finden Sie im Abschnitt Kerberos-Protokoll und Identität von [Überschreiben der Identität eines Dienstes zur Authentifizierung](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md).|Dies stellt sicher, dass der SPN und das bestimmte, dem SPN zugeordnete Windows-Konto den Dienst identifizieren.<br /><br /> Sie können das Tool Setspn.exe verwenden, um ein Computerkonto dem Benutzerkonto des Diensts zuzuordnen.<br /><br /> Diese Einstellung nutzt die Vorteile der Kerberos-Sicherheit von Windows, wenn der Dienst unter einem der Systemkonten oder unter einem Domänenkonto ausgeführt wird, dem ein SPN-Name zugeordnet ist, und der Computer Mitglied einer Domäne in einer Active Directory-Umgebung ist.|  
  
## <a name="specifying-identity-at-the-service"></a>Angeben der Identität für einen Dienst  
 In der Regel müssen Sie die Identität für einen Dienst nicht festlegen, da die Auswahl eines Clientanmeldeinformationstyps über den in den Dienstmetadaten angezeigten Identitätstyp entscheidet. Weitere Informationen dazu, wie Sie außer Kraft setzen oder Angeben der Dienstidentität finden Sie unter [Überschreiben der Identität eines Dienstes zur Authentifizierung](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md).  
  
## <a name="using-the-identity-element-in-configuration"></a>Mithilfe der \<Identity >-Element in der Konfiguration  
 Wenn Sie den Clientanmeldeinformationstyp in der zuvor gezeigten Bindung in `Certificate,` ändern, enthält die generierte WSDL ein serialisiertes Base64-X.509-Zertifikat als Identitätswert, wie im folgenden Code gezeigt. Dies ist der Standard für alle Clientanmeldeinformationstypen außer Windows.  

 Sie können den Wert der standardmäßigen Dienstidentität oder ändern den Typ der Identität mit der `<identity>` Element in der Konfiguration oder durch Festlegen der Identität im Code. Der folgende Konfigurationscode legt eine DNS-Identität (Domain Name System) mit dem Wert `contoso.com` fest.  

## <a name="setting-identity-programmatically"></a>Programmgesteuertes Festlegen der Identität  
 Ihr Dienst verfügt nicht explizit eine Identität angeben, da WCF automatisch bestimmt. WCF können Sie eine Identität für einen Endpunkt angeben möchten jedoch bei Bedarf. Mit dem folgenden Code wird ein neuer Dienstendpunkt mit einer bestimmten DNS-Identität hinzugefügt.  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="specifying-identity-at-the-client"></a>Angeben der Identität für einen Client  
 Zur Entwurfszeit verwendet ein Cliententwickler in der Regel die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Clientkonfiguration zu generieren. Die generierte Konfigurationsdatei (vorgesehen für die Verwendung durch den Client) enthält die Identität des Servers. Der folgende Code wurde z.&amp;#160;B. von einem Dienst generiert, der eine DNS-Identität angibt, wie im vorangehenden Beispiel gezeigt. Beachten Sie, dass der Endpunktidentitätswert des Clients dem des Diensts entspricht. Wenn in diesem Fall der Client die Windows (Kerberos)-Anmeldeinformationen für den Dienst erhält, erwartet er den Wert `contoso.com`.  

 Wenn der Dienst statt Windows ein Zertifikat als Clientanmeldeinformationstyp angibt, wird erwartet, dass die DNS-Eigenschaft des Zertifikats den Wert `contoso.com` hat. (Wenn aber die DNS-Eigenschaft den Wert `null` hat, muss der Antragstellername des Zertifikats `contoso.com` lauten.)  
  
#### <a name="using-a-specific-value-for-identity"></a>Verwenden eines bestimmten Werts für die Identität  
 Die folgende Clientkonfigurationsdatei zeigt, wie erwartet wird, dass die Identität des Diensts ein bestimmter Wert ist. Im folgenden Beispiel kann der Client mit zwei Endpunkten kommunizieren. Das erste wird mit einem Zertifikatsfingerabdruck, der zweite mit dem RSA-Schlüssel eines Zertifikats identifiziert. Somit also durch ein Zertifikat, das nur ein privates/öffentliches Schlüsselpaar enthält, jedoch nicht von einer vertrauenswürdige Stelle ausgegeben wurde.  

## <a name="identity-checking-at-run-time"></a>Identitätsprüfung zur Laufzeit  
 Zur Entwurfszeit bestimmt ein Cliententwickler die Identität des Servers durch dessen Metadaten. Zur Laufzeit wird die Identitätsprüfung ausgeführt, bevor irgendwelche Endpunkte auf dem Dienst aufgerufen werden.  
  
 Der Identitätswert ist an den von den Metadaten angegebenen Typ der Authentifizierung gebunden, mit anderen Worten, an den Typ der für den Dienst verwendeten Anmeldeinformationen.  
  
 Ist der Kanal für die Authentifizierung mithilfe von Secure Sockets Layer (SSL) auf Nachrichten- oder auf Transportebene mit X.509-Zertifikaten für die Authentifizierung konfiguriert, sind die folgenden Identitätswerte gültig:  
  
- DNS WCF wird sichergestellt, dass das während des SSL-Handshakes bereitgestellte Zertifikat ein DNS-Server enthält oder `CommonName` (CN)-Attribut gleich dem Wert in der DNS-Identität auf dem Client angegeben. Beachten Sie, dass diese Prüfungen zusätzlich zur Bestimmung der Gültigkeit des Serverzertifikats ausgeführt werden. Standardmäßig überprüft WCF an, dass das Serverzertifikat von einer vertrauenswürdigen Stammzertifizierungsstelle ausgestellt ist.  
  
- Zertifikat. Während des SSL-Handshakes wird Sie WCF sichergestellt, dass der Remoteendpunkt den Zertifikat-Wert, der in der Identität angegebenen bereitstellt.  
  
- Zertifikatsverweis. Ebenso wie Zertifikat.  
  
- RSA. Während der SSL-Handshake wird Sie WCF sichergestellt, dass der Remoteendpunkt, den genauen in der Identität angegebenen RSA-Schlüssel bereitstellt.  
  
 Authentifiziert der Dienst mithilfe von SSL auf Nachrichten- oder auf Transportebene mit Windows-Anmeldeinformationen und handelt er die Anmeldeinformationen aus, sind die folgenden Identitätswerte gültig:  
  
- DNS Die Aushandlung übergibt den SPN des Diensts, damit der DNS-Name überprüft werden kann. Der SPN hat die Form `host/<dns name>`.  
  
- SPN. Ein expliziter Dienst-SPN wird zurückgegeben, z.&amp;#160;B. `host/myservice`.  
  
- UPN. Der UPN des Dienstkontos. Der UPN wird in der Form `username` @ `domain`. Wenn der Dienst z.&amp;#160;B. mit einem Benutzerkonto ausgeführt wird, kann dies `username@contoso.com` sein.  
  
 Die programmgesteuerte Angabe der Identität (mithilfe der <xref:System.ServiceModel.EndpointAddress.Identity%2A>-Eigenschaft) ist optional. Wird keine Identität angegeben, und der Clientanmeldeinformationstyp ist Windows, wird als Standard ein SPN verwendet, dessen Wert auf den Hostnamen der Dienstendpunktadresse festgelegt ist, wobei dem Hostnamen das Zeichenfolgenliteral "host/" vorangestellt wird. Wenn keine Identität angegeben wird, und der Clientanmeldeinformationstyp ist ein Zertifikat, ist `Certificate` der Standard. Dies bezieht sich auf die Sicherheit sowohl auf der Nachrichtenebene als auch auf der Transportebene.  
  
## <a name="identity-and-custom-bindings"></a>Identität und benutzerdefinierte Bindungen  
 Da die Identität eines Diensts von dem verwendeten Bindungstyp abhängt, müssen Sie sicherstellen, dass bei der Erstellung einer benutzerdefinierten Bindung eine entsprechende Identität verfügbar gemacht wird. Im folgenden Codebeispiel ist die verfügbar gemachte Identität z.&amp;#160;B. nicht kompatibel mit dem Sicherheitstyp, weil die Identität für die sichere Konversations-Bootstrapbindung nicht mit der Identität für die Bindung am Endpunkt übereinstimmt. Die sicheren Konversationsbindung legt die DNS-Identität fest, während das <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement> die UPN- oder SPN-Identität festlegt.  
  
 [!code-csharp[C_Identity#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#8)]
 [!code-vb[C_Identity#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#8)]  
  
 Weitere Informationen über das stack-Bindung Elemente ordnungsgemäß für eine benutzerdefinierte Bindung, finden Sie unter [Erstellen benutzerdefinierter Bindungen](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md). Weitere Informationen zum Erstellen einer benutzerdefinierten Bindung mit der <xref:System.ServiceModel.Channels.SecurityBindingElement>, finden Sie unter [Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
- [Vorgehensweise: Erstellen einer benutzerdefinierten Clientidentitätsüberprüfung](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)
- [Ausählen eines Anmeldeinformationentyps](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [Arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Erstellen benutzerdefinierter Bindungen](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)
- [Vorgehensweise: Abrufen des Fingerabdrucks eines Zertifikats](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
