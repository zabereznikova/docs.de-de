---
title: Sichern von Diensten
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF], securing services
- WCF security
- WCF, security
ms.assetid: f0ecc6f7-f4b5-42a4-9cb1-b02e28e26620
ms.openlocfilehash: f2a8e10aaf9c1dbe3065344963fcc712776cd2db
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242226"
---
# <a name="securing-services"></a>Sichern von Diensten

Die Sicherheit eines Windows Communication Foundation (WCF)-Diensts besteht aus zwei primären Anforderungen: Übertragungssicherheit und Autorisierung. (Eine dritte Anforderung, das Überwachen von Sicherheits Ereignissen, wird unter Überwachung [beschrieben.)](./feature-details/auditing-security-events.md) Die Übertragungssicherheit beinhaltet die Authentifizierung (Überprüfung der Identität des Diensts und des Clients), Vertraulichkeit (Nachrichten Verschlüsselung) und Integrität (digitales Signieren zum Erkennen von Manipulationen). Autorisierung ist die Steuerung des Ressourcenzugriffs, beispielsweise wird nur Benutzern mit entsprechenden Berechtigungen das Lesen einer Datei ermöglicht. Mithilfe der Features von WCF sind die beiden primären Anforderungen problemlos implementiert.  
  
 Mit Ausnahme der- <xref:System.ServiceModel.BasicHttpBinding> Klasse (oder des- [\<basicHttpBinding>](../configure-apps/file-schema/wcf/basichttpbinding.md) Elements in der Konfiguration) ist die Übertragungssicherheit für alle vordefinierten Bindungen standardmäßig aktiviert. Die Themen in diesem Abschnitt behandeln zwei grundlegende Szenarien: das Implementieren von Übertragungssicherheit und die Autorisierung in einem Intranetdienst, der von Internetinformationsdienste (IIS) gehostet wird, sowie das Implementieren von Übertragungssicherheit und Autorisierung in einem von IIS gehosteten Dienst.  
  
> [!NOTE]
> Windows XP Home unterstützt keine Windows-Authentifizierung. Deshalb sollten Sie keinen Dienst auf diesem System ausführen.  
  
## <a name="security-basics"></a>Grundlagen zur Sicherheit  

 Sicherheit basiert auf *Anmeldeinformationen*. Anmeldeinformationen beweisen, dass es sich bei einer Entität tatsächlich um die angegebene Entität handelt. (Eine *Entität* kann eine Person, ein Softwareprozess, ein Unternehmen oder etwas sein, das autorisiert werden kann.) Ein Client eines Dienstanbieter nimmt z. b. einen *Identitäts* *Anspruch* , und die Anmelde Informationen beweisen diesen Anspruch auf irgendeine Weise. In einem typischen Szenario tritt ein Austausch von Anmeldeinformationen auf. Zunächst erklärt ein Dienst seinen Identitätsanspruch und erbringt dem Client in Form von Anmeldeinformationen den entsprechenden Nachweis. Umgekehrt erklärt der Client einen Identitätsanspruch und legt dem Dienst seine Anmeldeinformationen vor. Wenn die beiden Parteien die Anmeldeinformationen der jeweils anderen Partei als vertrauenswürdig einstufen, kann ein *sicherer Kontext* eingerichtet werden, in dem alle Nachrichten vertraulich ausgetauscht werden, und in dem alle Nachrichten zum Schutz ihrer Integrität signiert werden. Nach der Einrichtung der Clientidentität durch den Dienst können die Ansprüche in den Anmeldeinformationen mit einer *Rolle* oder *Mitgliedschaft* in einer Gruppe abgeglichen werden. In beiden Fällen *autorisiert* der Dienst den Client mit der Rolle oder der Gruppe, zu der der Client gehört, für die Durchführung einer begrenzten Anzahl von Vorgängen auf Grundlage der Rollen- oder Gruppenberechtigungen.  
  
## <a name="windows-security-mechanisms"></a>Windows-Sicherheitsmechanismen  

 Befinden sich sowohl der Client als auch der Dienstcomputer in einer Windows-Domäne, die den Client und den Computer zur Anmeldung am Netzwerk auffordert, werden die Anmeldeinformationen von der Windows-Infrastruktur bereitgestellt. In diesem Fall werden die Anmeldeinformationen angegeben, wenn sich ein Computerbenutzer am Netzwerk anmeldet. Jeder Benutzer und Computer im Netzwerk muss so überprüft werden, als ob er zur vertrauenswürdigen Benutzer- und Computergruppe gehört. Auf einem Windows-System werden jeder derartige Benutzer und Computer auch als *Sicherheitsprinzipal* bezeichnet.  
  
 In einer durch einen *Kerberos* -Controller gesicherten Windows-Domäne wird ein Schema verwendet, das auf dem Gewähren von Tickets für jeden Sicherheitsprinzipal basiert. Die vom Controller gewährten Tickets werden von anderen Komponenten im System, die Tickets gewähren, als vertrauenswürdig eingestuft. Wenn eine Entität versucht, einen Vorgang auszuführen oder auf eine *Ressource* zuzugreifen, (wie eine Datei oder ein Verzeichnis auf einem Computer), wird das Ticket auf seine Gültigkeit überprüft. Bei Bestehen der Gültigkeitsprüfung wird dem Prinzipal ein weiteres Ticket für den Vorgang gewährt. Diese Methode der Ticketgewährung ist effizienter als die Überprüfung des Prinzipals bei jedem Vorgang.  
  
 Ein älterer, auf Windows-Domänen verwendeter und weniger sicherer Mechanismus ist NT-LAN-Manager (NTLM). In Fällen, in denen Kerberos nicht verwendbar ist (normalerweise außerhalb einer Windows-Domäne, zum Beispiel in einer Arbeitsgruppe), kann alternativ NTLM verwendet werden. NTLM ist auch als Sicherheitsoption für IIS verfügbar.  
  
 Auf einem Windows-System funktioniert die Autorisierung durch Zuweisen jedes Computers und Benutzers zu einem Rollen- oder Gruppensatz. Beispielsweise muss jeder Windows-Computer von einer Person (oder Gruppe von Personen) in der Rolle des *Administrators* eingerichtet und gesteuert werden. Eine andere Rolle ist die des *Benutzers*, der über einen weitaus stärker eingeschränkten Berechtigungssatz verfügt. Zusätzlich zur Rolle werden Benutzer Gruppen zugewiesen. Eine Gruppe ermöglicht mehreren Benutzern, Vorgänge in derselben Rolle auszuführen. In der Praxis wird ein Windows-Computer daher durch Zuweisen von Benutzern zu Gruppen verwaltet. Beispielsweise können mehrere Benutzer der Gruppe von Computerbenutzern zugewiesen werden, und eine weitaus stärker begrenzte Benutzergruppe kann der Administratorgruppe hinzugefügt werden. Auf einem lokalen Computer kann ein Administrator auch neue Gruppen erstellen und der Gruppe andere Benutzern zuweisen (oder auch andere Gruppen).  
  
 Auf einem Computer, der unter Windows ausgeführt wird, kann jeder Ordner in einem Verzeichnis geschützt werden. Dies bedeutet, dass Sie einen Ordner auswählen und steuern können, wer auf die Dateien zugreifen darf und ob das Kopieren oder (bei den am weitesten reichenden Berechtigungen) Ändern und Löschen der Datei bzw. das Hinzufügen von Dateien zum Ordner zulässig sind. Dies wird als Zugriffssteuerung bezeichnet, und der entsprechende Mechanismus ist unter dem Namen Zugriffssteuerungsliste (ACL) bekannt. Beim Erstellen der Zugriffssteuerungsliste können jeder beliebigen Gruppe sowie einzelnen Mitgliedern einer Domäne Zugriffsberechtigungen erteilt werden.  
  
 Die WCF-Infrastruktur ist für die Verwendung dieser Windows-Sicherheitsmechanismen konzipiert. Beim Erstellen eines Diensts, der in einem Intranet bereitgestellt wird, und dessen Clients auf Mitglieder der Windows-Domäne beschränkt sind, wird die Sicherheit problemlos implementiert. Nur gültige Benutzer können sich an der Domäne anmelden. Nach der Anmeldung der Benutzer ermöglicht der Kerberos-Controller jedem Benutzer die Einrichtung sicherer Kontexte mit einem beliebigen Computer oder einer Anwendung. Auf einem lokalen Computer können problemlos Gruppen erstellt werden, und beim Schutz von bestimmten Ordnern können mit diesen Gruppen Zugriffsberechtigungen auf dem Computer zugewiesen werden.  
  
## <a name="implementing-windows-security-on-intranet-services"></a>Implementieren von Windows-Sicherheit auf Intranetdiensten  

 Soll eine Anwendung gesichert werden, die exklusiv auf einer Windows-Domäne ausgeführt wird, können die Standardsicherheitseinstellungen von entweder der <xref:System.ServiceModel.WSHttpBinding> -Bindung oder der <xref:System.ServiceModel.NetTcpBinding> -Bindung verwendet werden. Standardmäßig kann jeder Benutzer in derselben Windows-Domäne auf WCF-Dienste zugreifen. Da sich diese Benutzer am Netzwerk angemeldet haben, werden sie als vertrauenswürdig eingestuft. Die Nachrichten zwischen einem Dienst und einem Client werden aus Vertraulichkeitsgründen verschlüsselt und zu Integritätszwecken signiert. Weitere Informationen zum Erstellen eines Diensts, der die Windows-Sicherheit verwendet, finden Sie unter Vorgehens [Weise: Sichern eines Diensts mit Windows-Anmelde](how-to-secure-a-service-with-windows-credentials.md)Informationen.  
  
### <a name="authorization-using-the-principalpermissionattribute-class"></a>Autorisierung mithilfe der PrincipalPermissionAttribute-Klasse  

 Muss der Zugriff auf die Ressourcen auf einem Computer beschränkt werden, besteht die einfachste Möglichkeit in der Verwendung der <xref:System.Security.Permissions.PrincipalPermissionAttribute> -Klasse. Mit diesem Attribut können Aufrufe von Dienstvorgängen eingeschränkt werden, indem gefordert wird, dass sich der Benutzer in einer angegebenen Windows-Gruppe oder -Rolle befinden oder ein bestimmter Benutzer sein muss. Weitere Informationen finden Sie unter Gewusst [wie: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](how-to-restrict-access-with-the-principalpermissionattribute-class.md).  
  
### <a name="impersonation"></a>Identitätswechsel  

 Der Identitätswechsel ist ein weiterer Mechanismus, mit dem Sie den Zugriff auf Ressourcen steuern können. Standardmäßig wird ein von IIS gehosteter Dienst unter der Identität des ASPNET-Kontos ausgeführt. Das ASPNET-Konto kann nur auf die Ressourcen zugreifen, für die es eine entsprechende Berechtigung besitzt. Allerdings kann die Zugriffssteuerungsliste für einen Ordner so festgelegt werden, dass das ASPNET-Dienstkonto ausgeschlossen wird, bestimmten anderen Identitäten jedoch der Zugriff auf den Ordner gewährt wird. Die Frage ist nun, wie diesen Benutzer Zugriff auf den Ordner gewährt wird, falls das ASPNET-Konto nicht dazu berechtigt ist. Dies wird durch den Identitätswechsel ermöglicht, bei dem der Dienst die Anmeldeinformationen des Clients für den Zugriff auf eine bestimmte Ressource verwenden darf. Ein weiteres Beispiel ist der Zugriff auf eine SQL Server-Datenbank, auf die nur bestimmte Benutzer zugreifen dürfen. Weitere Informationen zum Verwenden des Identitäts Wechsels finden Sie unter Gewusst [wie: annehmen der Identität eines Clients bei einem Dienst](how-to-impersonate-a-client-on-a-service.md) und [Delegierung und](./feature-details/delegation-and-impersonation-with-wcf.md)Identitätswechsel.  
  
## <a name="security-on-the-internet"></a>Sicherheit im Internet  

 Bei der Sicherheit im Internet gelten dieselben Anforderungen wie bei der Sicherheit in einem Intranet. Ein Dienst muss zum Nachweis seiner Authentizität seine Anmeldeinformationen angeben, und Clients müssen dem Dienst ihre Identität nachweisen. Wurde die Identität eines Clients nachgewiesen, kann der Umfang des Ressourcenzugriffs für den Client vom Dienst gesteuert werden. Aufgrund des heterogenen Charakters des Internets unterscheiden sich die angegebenen Anmeldeinformationen von denen, die in einer Windows-Domäne verwendet werden. Während ein Kerberos-Controller die Authentifizierung von Benutzern in einer Domäne mit Tickets für Anmeldeinformationen verarbeitet, nutzen Dienste und Clients im Internet eine der mehreren verschiedenen Möglichkeiten zur Angabe von Anmeldeinformationen. Das Ziel dieses Themas ist jedoch die Darstellung eines allgemeinen Ansatzes, der es Ihnen ermöglicht, einen WCF-Dienst zu erstellen, der über das Internet zugänglich ist.  
  
### <a name="using-iis-and-aspnet"></a>Verwenden von IIS und ASP.NET  

 Die Anforderungen der Internetsicherheit und die Mechanismen für die Problemlösung sind nicht neu. IIS ist der Microsoft-Webserver für das Internet und bietet zahlreiche Sicherheitsfeatures, die diese Probleme beheben. Außerdem umfasst ASP.NET Sicherheitsfunktionen, die von WCF-Diensten verwendet werden können. Um diese Sicherheitsfeatures nutzen zu können, hosten Sie einen WCF-Dienst unter IIS.  
  
#### <a name="using-aspnet-membership-and-role-providers"></a>Verwenden von ASP.NET-Mitgliedschaft und Rollenanbietern  

 ASP.NET beinhaltet eine Mitgliedschaft und einen Rollenanbieter. Der Anbieter ist eine Datenbank mit Benutzernamen-/Kennwortpaaren für die Authentifizierung von Aufrufenden, mit der auch die Zugriffsberechtigungen jedes Aufrufenden angegeben werden können. Mit WCF können Sie mithilfe der Konfiguration problemlos eine bereits vorhandene Mitgliedschaft und einen Rollen Anbieter verwenden. Eine Beispielanwendung, die dies veranschaulicht, finden Sie im Beispiel [Membership and Role Provider](./samples/membership-and-role-provider.md) .  
  
### <a name="credentials-used-by-iis"></a>Von IIS verwendete Anmeldeinformationen  

 Im Gegensatz zu einer Windows-Domäne, die von einem Kerberos-Controller gesichert wird, ist das Internet eine Umgebung ohne einen Controller zur Verwaltung der jederzeit stattfindenden Anmeldungen von Millionen von Benutzern. Stattdessen werden Anmeldeinformationen im Internet meist in Form von X.509-Zertifikaten (auch als Secure Sockets Layer- oder SSL-Zertifikate) angegeben. Diese Zertifikate werden normalerweise von einer *Zertifizierungsstelle* ausgestellt, bei der es sich um ein drittes Unternehmen handeln kann, das für die Authentizität des Zertifikats und der Person, für die das Zertifikat ausgestellt wurde, bürgt. Soll der Dienst im Internet verfügbar gemacht werden, muss zur Authentifizierung des Diensts auch ein derartiges vertrauenswürdiges Zertifikat bereitgestellt werden.  
  
 An diesem Punkt stellt sich die Frage, wie man ein solches Zertifikat erhält. Wenn Sie den Dienst bereitstellen können, besteht die Möglichkeit, sich an eine dritte Zertifizierungsstelle zu wenden (zum Beispiel Authenticode oder VeriSign) und ein Zertifikat für den Dienst zu erwerben. Wenn Sie sich jedoch in der Entwicklungsphase mit WCF befinden und noch nicht bereit sind, ein Zertifikat zu erwerben, sind Tools und Techniken für das Erstellen von X. 509-Zertifikaten vorhanden, die Sie zum Simulieren einer Produktions Bereitstellung verwenden können. Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](./feature-details/working-with-certificates.md).  
  
## <a name="security-modes"></a>Sicherheitsmodi  

 Das Programmieren der WCF-Sicherheit erfordert einige wichtige Entscheidungspunkte. Von grundlegender Bedeutung ist hier die Wahl des *Sicherheitsmodus*. Die zwei Hauptsicherheitsmodi sind der *Transportmodus* und der *Nachrichtenmodus*.  
  
 Ein dritter Modus, der die Semantik der beiden Hauptmodi kombiniert, ist der *Transport mit dem Modus für Nachrichtenanmeldeinformationen*.  
  
 Mit dem Sicherheitsmodus wird die Sicherungsform der Nachrichten bestimmt, wobei jede gewählte Variante Vor- und Nachteile aufweist (siehe unten). Weitere Informationen zum Festlegen des Sicherheitsmodus finden Sie unter Gewusst [wie: Festlegen des Sicherheitsmodus](how-to-set-the-security-mode.md).  
  
#### <a name="transport-mode"></a>Transportmodus  

 Zwischen dem Netzwerk und der Anwendung befinden sich mehrere Ebenen. Eine dieser Ebenen ist die *Transportebene* ,*die* die Übertragung von Nachrichten zwischen Endpunkten verwaltet. Zum jetzigen Zweck ist es nur erforderlich, dass Sie wissen, dass WCF mehrere Transportprotokolle verwendet, die jeweils die Übertragung von Nachrichten sichern können. (Weitere Informationen zu Transporten finden Sie unter [Transporte](./feature-details/transports.md).)  
  
 Ein häufig verwendetes Protokoll ist HTTP, ein weiteres TCP. Mit jedem dieser Protokolle kann Nachrichtenübertragung durch einen protokollspezifischen Mechanismus (oder Mechanismen) gesichert werden. Zum Beispiel wird das HTTP-Protokoll mit SSL über HTTP (im Allgemeinen als "HTTPS" bezeichnet) gesichert. Wird aus Sicherheitsgründen der Transportmodus gewählt, wird daher der Mechanismus entsprechend der Vorgabe durch das Protokoll verwendet. Wird beispielsweise die <xref:System.ServiceModel.WSHttpBinding> -Klasse ausgewählt und der Sicherheitsmodus auf Transport festgelegt, wählen Sie als Sicherheitsmechanismus SSL über HTTP (HTTPS). Der Vorteil des Transportmodus besteht in seiner im Vergleich zum Nachrichtenmodus höheren Effizienz, die durch die Integration der Sicherheit auf einer relativ niedrigen Ebene erzielt wird. Bei Verwendung des Transportmodus muss der Sicherheitsmodus gemäß den Angaben für den Transport implementiert werden. Dadurch wird gewährleistet, dass Nachrichten beim Transport sicher übertragen werden, und zwar nur von einem Punkt zu einem anderen Punkt (Point-to-Point).  
  
#### <a name="message-mode"></a>Nachrichtenmodus  

 Im Gegensatz dazu gewährleistet der Nachrichtenmodus Sicherheit durch Einbeziehen der Sicherheitsdaten als Teil jeder Nachricht. Mit XML- und SOAP-Sicherheitsheadern werden die Anmeldeinformationen und andere Daten, die zur Sicherstellung der Integrität und Vertraulichkeit der Nachricht erforderlich sind, in jede Nachricht eingefügt. Die Leistung wird beeinträchtigt, da jede Nachricht Sicherheitsdaten beinhaltet und jede Nachricht einzeln verarbeitet werden muss. (Im Transportmodus werden nach der Sicherung der Transportschicht alle Nachrichten frei übertragen.) Die Nachrichten Sicherheit hat jedoch gegenüber der Transportsicherheit einen Vorteil: Sie ist flexibler. Das heißt, dass die Sicherheitsanforderungen nicht vom Transport bestimmt werden. Sie können jeden Typ der Clientanmeldeinformationen zum Sichern der Nachricht verwenden. (Im Transportmodus bestimmt das Transportprotokoll den Typ der Clientanmeldeinformationen, die Sie verwenden können.)  
  
#### <a name="transport-with-message-credentials"></a>Transport mit Nachrichtenanmeldeinformationen  

 Der dritte Modus vereint die Vorteile der Transport- und der Nachrichtensicherheit. In diesem Modus wird Transportsicherheit verwendet, um die Vertraulichkeit und die Integrität jeder Nachricht effizient sicherzustellen. Gleichzeitig beinhaltet jede Nachricht ihre Anmeldeinformationsdaten, wodurch die Authentifizierung der Nachricht ermöglicht wird. Mit der Authentifizierung kann auch die Autorisierung implementiert werden. Durch Authentifizieren eines Absenders kann der Zugriff auf Ressourcen entsprechend der Identität des Absenders gewährt (oder verweigert) werden.  
  
## <a name="specifying-the-client-credential-type-and-credential-value"></a>Angeben von Anmeldeinformationstyp und -wert für den Client  

 Nach Auswahl eines Sicherheitsmodus können Sie auf Wunsch auch einen Clientanmeldeinformationstyp angeben. Der Clientanmeldeinformationstyp gibt an, welchen Typ ein Client verwenden muss, um sich selbst beim Server authentifizieren zu können.  
  
 Allerdings erfordern nicht alle Szenarien einen Clientanmeldeinformationstyp. Bei Verwendung von SSL über HTTP (HTTPS) authentifiziert sich ein Dienst beim Client. Im Rahmen dieser Authentifizierung wird das Zertifikat des Diensts in einem als *Aushandlung* bezeichneten Prozess an den Client gesendet. Der durch SSL gesicherte Transport gewährleistet, dass alle Nachrichten vertraulich sind.  
  
 Wird ein Dienst erstellt, der eine Authentifizierung des Clients erfordert, hängt die Wahl eines Clientanmeldeinformationstypen vom ausgewählten Transport und Modus ab. Bei Verwendung des HTTP-Transports und bei Auswahl des Transportmodus stehen Ihnen mehrere Möglichkeiten zur Verfügung, wie zum Beispiel Basic, Digest usw. (Weitere Informationen zu diesen Anmelde Informationstypen finden Sie Untergrund Legendes zur [http-Authentifizierung](./feature-details/understanding-http-authentication.md).)  
  
 Wird ein Dienst in einer Windows-Domäne erstellt, der nur anderen Benutzern des Netzwerks zur Verfügung steht, empfiehlt sich die Verwendung des Windows-Clientanmeldeinformationstyps. Allerdings muss für den Dienst ggf. auch ein Zertifikat erworben werden. Dieser Vorgang wird in [How to: Specify Client Credential Values](how-to-specify-client-credential-values.md)beschrieben.  
  
#### <a name="credential-values"></a>Anmeldeinformationswerte  

 Bei einem *Anmeldeinformationswert* handelt es sich um die tatsächlichen Anmeldeinformationen, die vom Dienst verwendet werden. Nach Angabe eines Anmeldeinformationstyps muss der Dienst unter Umständen auch mit den tatsächlichen Anmeldeinformationen konfiguriert werden. Wurde Windows ausgewählt (und wird der Dienst in einer Windows-Domäne ausgeführt), wird kein tatsächlicher Anmeldeinformationswert angegeben.  
  
## <a name="identity"></a>Identity  

 In WCF hat der Begriff *Identität* andere Bedeutungen für den Server und den Client. Zusammenfassend bedeutet dies, dass beim Ausführen eines Diensts dem Sicherheitskontext nach der Authentifizierung eine Identität zugewiesen wird. Um die tatsächliche Identität anzuzeigen, überprüfen Sie die <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> -Eigenschaft und die <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> -Eigenschaft der <xref:System.ServiceModel.ServiceSecurityContext> -Klasse. Weitere Informationen finden Sie unter Gewusst [wie: Überprüfen des Sicherheits Kontexts](how-to-examine-the-security-context.md).  
  
 Im Gegensatz dazu wird mit der Identität der Dienst geprüft. Zur Entwurfszeit kann ein Client Entwickler das- [\<identity>](../configure-apps/file-schema/wcf/identity.md) Element auf einen Wert festlegen, der vom Dienst abgerufen wird. Während der Laufzeit gleicht der Client den Wert des Elements mit der tatsächlichen Identität des Diensts ab. Bei fehlerhafter Prüfung wird die Kommunikation vom Client beendet. Der Wert kann ein Benutzerprinzipalname sein (UPN), falls der Dienst unter einer bestimmten Benutzeridentität ausgeführt wird oder ein Dienstprinzipalname (SPN), falls der Dienst unter einem Computerkonto ausgeführt wird. Weitere Informationen finden Sie unter [Dienst Identität und-Authentifizierung](./feature-details/service-identity-and-authentication.md). Die Anmeldeinformationen können auch ein Zertifikat oder ein Feld auf einem Zertifikat sein, mit dem das Zertifikat identifiziert wird.  
  
## <a name="protection-levels"></a>Schutzebenen  

 Die `ProtectionLevel` -Eigenschaft tritt auf mehreren Attributklassen (zum Beispiel der <xref:System.ServiceModel.ServiceContractAttribute> -Klasse und der <xref:System.ServiceModel.OperationContractAttribute> -Klasse) auf. Die Schutzebene ist ein Wert, der angibt, ob die Meldungen (oder Meldungsteile), die einen Dienst unterstützen, signiert, signiert und verschlüsselt oder ohne Signaturen und Verschlüsselung gesendet werden. Weitere Informationen zur-Eigenschaft finden Sie Untergrund Legendes zur [Schutz Ebene](understanding-protection-level.md). Informationen zu Programmier Beispielen finden Sie unter Gewusst [wie: Festlegen der Schutzlevel-Eigenschaft](how-to-set-the-protectionlevel-property.md). Weitere Informationen zum Entwerfen eines Dienstvertrags mit `ProtectionLevel` im Kontext finden Sie unter [Entwerfen von Dienstverträgen](designing-service-contracts.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [Dienstidentität und Authentifizierung](./feature-details/service-identity-and-authentication.md)
- [Grundlagen der Schutzebene](understanding-protection-level.md)
- [Delegierung und Identitätswechsel](./feature-details/delegation-and-impersonation-with-wcf.md)
- [Entwerfen von Dienstverträgen](designing-service-contracts.md)
- [Security](./feature-details/security.md)
- [Sicherheitsübersicht](./feature-details/security-overview.md)
- [Vorgehensweise: Festlegen der ProtectionLevel-Eigenschaft](how-to-set-the-protectionlevel-property.md)
- [Vorgehensweise: Sichern eines Diensts mit Windows-Anmeldeinformationen](how-to-secure-a-service-with-windows-credentials.md)
- [Vorgehensweise: Festlegen des Sicherheitsmodus](how-to-set-the-security-mode.md)
- [Vorgehensweise: Angeben des Typs von Clientanmeldeinformationen](how-to-specify-the-client-credential-type.md)
- [Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](how-to-restrict-access-with-the-principalpermissionattribute-class.md)
- [Vorgehensweise: Annahme der Clientidentität durch einen Dienst](how-to-impersonate-a-client-on-a-service.md)
- [Vorgehensweise: Prüfen des Sicherheitskontexts](how-to-examine-the-security-context.md)
