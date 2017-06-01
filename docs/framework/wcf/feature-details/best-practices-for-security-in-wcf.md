---
title: "Best Practices f&#252;r Sicherheit in WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Bewährte Methoden [WCF], Sicherheit"
ms.assetid: 3639de41-1fa7-4875-a1d7-f393e4c8bd69
caps.latest.revision: 19
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 19
---
# Best Practices f&#252;r Sicherheit in WCF
In den folgenden Abschnitten werden die Best Practices aufgeführt, die beim Erstellen sicherer Anwendungen mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] zu berücksichtigen sind.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Sicherheit finden Sie unter [Sicherheitsüberlegungen](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md), [Sicherheitsüberlegungen zu Daten](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md) und [Sicherheitsüberlegungen für Metadaten](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md).  
  
## Identifizieren von Diensten mit Windows\-Authentifizierung mithilfe von SPNs  
 Dienste können entweder mit Benutzerprinzipalnamen \(User Principal Names, UPNs\) oder mit Dienstprinzipalnamen \(Service Principal Names, SPNs\) identifiziert werden.Dienste, die im Rahmen eines Computerkontos ausgeführt werden \(beispielsweise der Netzwerkdienst\), besitzen eine SPN\-Identität, die dem Computer entspricht, auf dem sie ausgeführt werden.Dienste, die im Rahmen eines Benutzerkontos ausgeführt werden, besitzen eine UPN\-Identität, die dem Benutzer entspricht, als der sie ausgeführt werden. Mithilfe des `setspn`\-Tool kann dem Benutzerkonto jedoch auch ein SPN zugewiesen werden.Wird ein Dienst so konfiguriert, dass er mittels SPN identifiziert werden kann, und werden die Clients, von denen eine Verbindung mit dem Dienst herstellt wird, für die Verwendung dieses SPN konfiguriert, lassen sich bestimmte Angriffe erschweren.Diese Anleitung gilt für Bindungen mit Kerberos\- oder SSPI\-Aushandlung.Für den Fall, dass von SSPI auf NTLM zurückgegriffen wird, sollte von den Clients auch weiterhin ein SPN angegeben werden.  
  
## Überprüfen von Dienstidentitäten in WSDL  
 WS\-SecurityPolicy ermöglicht es Diensten, Informationen zu ihren eigenen Identitäten in Metadaten zu veröffentlichen.Wenn diese Identitätsinformationen mittels `svcutil` oder mithilfe anderer Methoden wie <xref:System.ServiceModel.Description.WsdlImporter> abgerufen werden, werde die Daten in die Identitätseigenschaften der Endpunktadressen des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Diensts umgewandelt.Clients, von denen nicht geprüft wird, ob diese Dienstidentitäten korrekt und gültig sind, umgehen die Dienstauthentifizierung.Ein böswilliger Dienst kann solche Clients ausnutzen und Anmeldeinformationen weiterleiten oder andere Man\-In\-The\-Middle\-Angriffe ausführen, indem die in der WSDL angegebene Identität geändert wird.  
  
## Verwenden von X.509\-Zertifikaten anstelle von NTLM  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet zwei Mechanismen für die Peer\-to\-Peer\-Authentifizierung: X509\-Zertifikate \(die vom Peerkanal verwendet werden\) und Windows\-Authentifizierung, bei der eine SSPI\-Aushandlung von Kerberos zu NTLM herabgestuft wird.Die zertifikatbasierte Authentifizierung mit Schlüsselgrößen von 1024 Bits oder mehr wird gegenüber NTLM aus mehreren Gründen vorgezogen:  
  
-   Verfügbarkeit der gegenseitigen Authentifizierung  
  
-   Verwendung stärkerer Kryptografiealgorithmen  
  
-   Erschwerte Verwendung weitergeleiteter X509\-Anmeldeinformationen  
  
 Eine Übersicht über NTLM\-Weiterleitungsangriffe finden Sie unter [http:\/\/msdn.microsoft.com\/msdnmag\/issues\/06\/09\/SecureByDesign\/default.aspx](http://go.microsoft.com/fwlink/?LinkId=109571) \(möglicherweise in englischer Sprache\).  
  
## Stellen Sie nach Identitätswechseln immer die ursprüngliche Identität wieder her  
 Wenn Sie APIs verwenden, die den Identitätswechsel eines Clients ermöglichen, stellen Sie sicher, dass die ursprüngliche Identität wiederhergestellt wird.Beim Einsatz von <xref:System.Security.Principal.WindowsIdentity> und <xref:System.Security.Principal.WindowsImpersonationContext> verwenden Sie beispielsweise in C\# die `using`\-Anweisung oder die [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]`Using`\-Anweisung, wie im folgenden Code gezeigt.Die <xref:System.Security.Principal.WindowsImpersonationContext>\-Klasse implementiert die <xref:System.IDisposable>\-Schnittstelle, und daher stellt die CLR \(Common Language Runtime\) automatisch die ursprüngliche Identität wieder her, sobald die Ausführung des `using`\-Blocks abgeschlossen ist.  
  
 [!code-csharp[c_SecurityBestPractices#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securitybestpractices/cs/source.cs#1)]
 [!code-vb[c_SecurityBestPractices#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securitybestpractices/vb/source.vb#1)]  
  
## Nehmen Sie Identitätswechsel nur bei Bedarf vor  
 Mithilfe der <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>\-Methode der <xref:System.Security.Principal.WindowsIdentity>\-Klasse ist es möglich, Identitätswechsel in einem sehr eingeschränkten Bereich vorzunehmen.Dies steht im Gegensatz zum Einsatz der <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>\-Eigenschaft der <xref:System.ServiceModel.OperationBehaviorAttribute>\-Klasse, die Identitätswechsel im gesamten Vorgangsbereich zulässt.Wenn möglich, kontrollieren Sie mithilfe der präziseren <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>\-Methode den Bereich des Identitätswechsels.  
  
## Abrufen von Metadaten aus vertrauenswürdigen Quellen  
 Stellen Sie sicher, dass die Metadatenquelle vertrauenswürdig ist und dass die Metadaten nicht manipuliert wurden.Über das HTTP\-Protokoll abgerufene Metadaten werden im Klartext gesendet und können manipuliert werden.Wenn der Dienst die Eigenschaften <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> und <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> nutzt, verwenden Sie die URL, die der Dienstersteller zum Herunterladen der Daten über das HTTPS\-Protokoll angegeben hat.  
  
## Veröffentlichen von Metadaten unter Verwendung von Sicherheitsfeatures  
 Damit die veröffentlichten Metadaten eines Diensts nicht manipuliert werden können, schützen Sie den Endpunkt für den Metadatenaustausch mit Sicherheitsfeatures auf Transport\- oder Nachrichtenebene.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Veröffentlichen von Metadatenendpunkten](../../../../docs/framework/wcf/publishing-metadata-endpoints.md) und [Gewusst wie: Veröffentlichen von Metadaten für einen Dienst über den Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
## Sicherstellen der Verwendung eines lokalen Ausstellers  
 Wenn für eine bestimmte Bindung eine Ausstelleradresse und eine Bindung angegeben werden, wird der lokale Aussteller nicht für Endpunkte genutzt, die diese Bindung verwenden.Clients, die immer den lokalen Aussteller verwenden möchten, sollten sicherstellen, dass keine solche Bindung verwendet wird oder dass die Bindung so geändert wird, dass die Ausstelleradresse NULL lautet.  
  
## Größenkontingente für SAML\-Token  
 Wenn SAML \(Security Assertions Markup Language\)\-Token in Nachrichten serialisiert werden, z. B. wenn sie von einem Sicherheitstokendienst \(Security Token Service, STS\) ausgestellt werden oder von Clients im Rahmen der Authentifizierung an Dienste übergegeben werden, muss das Kontingent für die maximale Nachrichtengröße groß genug sein, um das SAML\-Token und die anderen Teile der Nachricht aufnehmen zu können.Normalerweise ist das Kontingent für Nachrichten in Standardgröße ausreichend.Wenn ein SAML\-Token allerdings sehr groß ist, weil es mehrere Hundert Ansprüche enthält, sollten Sie das Kontingent erhöhen, damit das serialisierte Token darin Platz findet.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu Kontingenten finden Sie unter [Sicherheitsüberlegungen zu Daten](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).  
  
## Festlegen von SecurityBindingElement.IncludeTimestamp für benutzerdefinierte Bindungen auf "True"  
 Wenn Sie eine benutzerdefinierte Bindung erstellen, müssen Sie <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> auf `true` festlegen.Wenn <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> auf `false` festgelegt ist und der Client ein auf einem asymmetrischen Schlüssel basierendes Token verwendet, z. B. ein X.509\-Zertifikat, wird die Nachricht nicht signiert.  
  
## Siehe auch  
 [Sicherheitsüberlegungen](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)   
 [Sicherheitsüberlegungen zu Daten](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)   
 [Sicherheitsüberlegungen für Metadaten](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)