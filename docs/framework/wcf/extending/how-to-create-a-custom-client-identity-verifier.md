---
title: "Vorgehensweise: Erstellen einer benutzerdefinierten Clientidentit&#228;ts&#252;berpr&#252;fung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f2d34e43-fa8b-46d2-91cf-d2960e13e16b
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Vorgehensweise: Erstellen einer benutzerdefinierten Clientidentit&#228;ts&#252;berpr&#252;fung
Die neue *Identitätsfunktion* von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ermöglicht einem Client das vorzeitige Angeben der erwarteten Identität des Diensts.  Bei jeder Authentifizierung eines Servers beim Client wird die Identität mit der erwarteten Identität verglichen.  \(Eine Erläuterung der Identität und ihrer Funktionsweise finden Sie unter [Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).\)  
  
 Sofern erforderlich, kann die Überprüfung mit einer benutzerdefinierten Identitätsüberprüfung angepasst werden.  Zum Beispiel können Sie zusätzliche Dienstidentitätsüberprüfungen durchführen.  In diesem Beispiel überprüft die benutzerdefinierte Identitätsprüfung zusätzliche Ansprüche in dem X.509\-Zertifikat, das vom Server zurückgegeben wird.  Eine Beispielanwendung finden Sie unter [Dienstidentitätsbeispiel](../../../../docs/framework/wcf/samples/service-identity-sample.md).  
  
### So erweitern Sie die EndpointIdentity\-Klasse:  
  
1.  Definieren Sie eine neue Klasse, die von der <xref:System.ServiceModel.EndpointIdentity>\-Klasse abgeleitet wird.  In diesem Beispiel wird die Erweiterung `OrgEndpointIdentity` genannt.  
  
2.  Fügen Sie private Member mit Eigenschaften hinzu, die von der erweiterten <xref:System.ServiceModel.Security.IdentityVerifier>\-Klasse zum Ausführen der Identitätsprüfung anhand der Ansprüche im vom Dienst zurückgegebenen Sicherheitstoken verwendet wird.  Dieses Beispiel definiert eine Eigenschaft: die `OrganizationClaim`\-Eigenschaft.  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
     [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
### So erweitern Sie die IdentityVerifier\-Klasse:  
  
1.  Definieren Sie eine neue Klasse, die von <xref:System.ServiceModel.Security.IdentityVerifier> abgeleitet wird.  In diesem Beispiel wird die Erweiterung `CustomIdentityVerifier` genannt.  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#7)]
     [!code-vb[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#7)]  
  
2.  Überschreiben Sie die <xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A>\-Methode.  Mit dieser Methode wird bestimmt, ob die Identitätsprüfung erfolgreich war oder fehlgeschlagen ist.  
  
3.  Die `CheckAccess`\-Methode verfügt über zwei Parameter.  Der erste Parameter ist eine Instanz der <xref:System.ServiceModel.EndpointIdentity>\-Klasse.  Der zweite Parameter ist eine Instanz der <xref:System.IdentityModel.Policy.AuthorizationContext>\-Klasse.  
  
     Prüfen Sie in der Methodenimplementierung die Auflistung der von der <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A>\-Eigenschaft der <xref:System.IdentityModel.Policy.AuthorizationContext>\-Klasse zurückgegebenen Ansprüche, und führen Sie gemäß Bedarf Authentifizierungsprüfungen aus.  Dieses Beispiel beginnt durch Suchen eines Anspruchs vom Typ "Distinguished Name" und anschließendes Vergleichen des Namens mit der Erweiterung von <xref:System.ServiceModel.EndpointIdentity> \(`OrgEndpointIdentity`\).  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#1)]
     [!code-vb[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#1)]  
  
### So implementieren Sie die TryGetIdentity\-Methode:  
  
1.  Implementieren Sie die <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A>\-Methode, mit der bestimmt wird, ob vom Client eine Instanz der <xref:System.ServiceModel.EndpointIdentity>\-Klasse zurückgegeben werden kann.  Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Infrastruktur ruft die Implementierung der `TryGetIdentity`\-Methode auf, um zunächst die Identität des Diensts aus der Nachricht abzurufen.  Anschließend ruft die Infrastruktur die `CheckAccess`\-Implementierung mit der zurückgegebenen `EndpointIdentity` und dem zurückgegebenen <xref:System.IdentityModel.Policy.AuthorizationContext> auf.  
  
2.  Fügen Sie in die `TryGetIdentity`\-Methode folgenden Code ein:  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#2)]
     [!code-vb[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#2)]  
  
### So implementieren Sie eine benutzerdefinierte Bindung und legen den benutzerdefinierten IdentityVerifier fest:  
  
1.  Erstellen Sie eine Methode, von der ein <xref:System.ServiceModel.Channels.Binding>\-Objekt zurückgegeben wird.  In diesem Beispiel wird zunächst eine Instanz der <xref:System.ServiceModel.WSHttpBinding>\-Klasse erstellt und der Sicherheitsmodus auf <xref:System.ServiceModel.SecurityMode> und der <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> auf <xref:System.ServiceModel.MessageCredentialType> festgelegt.  
  
2.  Erstellen Sie mit der <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>\-Methode <xref:System.ServiceModel.Channels.BindingElementCollection>.  
  
3.  Geben Sie <xref:System.ServiceModel.Channels.SecurityBindingElement> aus der Auflistung zurück, und wandeln Sie sie in eine <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>\-Variable um.  
  
4.  Legen Sie die <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A>\-Eigenschaft der <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>\-Klasse auf eine neue Instanz der zuvor erstellten `CustomIdentityVerifier`\-Klasse fest.  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#3)]
     [!code-vb[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#3)]  
  
5.  Mit der benutzerdefinierten Bindung, die zurückgegeben wird, wird eine Instanz des Clients und der Klasse erstellt.  Der Client kann anschließend eine benutzerdefinierte Identitätsprüfung des Diensts gemäß der Anzeige im folgenden Code ausführen.  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#4)]
     [!code-vb[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#4)]  
  
## Beispiel  
 Im folgenden Beispiel wird eine vollständige Implementierung der <xref:System.ServiceModel.Security.IdentityVerifier>\-Klasse gezeigt.  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#5)]
 [!code-vb[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#5)]  
  
## Beispiel  
 Im folgenden Beispiel wird eine vollständige Implementierung der <xref:System.ServiceModel.EndpointIdentity>\-Klasse gezeigt.  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
 [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
## Siehe auch  
 <xref:System.ServiceModel.ServiceAuthorizationManager>   
 <xref:System.ServiceModel.EndpointIdentity>   
 <xref:System.ServiceModel.Security.IdentityVerifier>   
 [Dienstidentitätsbeispiel](../../../../docs/framework/wcf/samples/service-identity-sample.md)   
 [Autorisierungsrichtlinie](../../../../docs/framework/wcf/samples/authorization-policy.md)   
 [Autorisierungsrichtlinie](../../../../docs/framework/wcf/samples/authorization-policy.md)