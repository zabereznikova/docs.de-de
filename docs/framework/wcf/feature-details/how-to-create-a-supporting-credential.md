---
title: "Vorgehensweise: Erstellen unterst&#252;tzender Anmeldeinformationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d0952919-8bb4-4978-926c-9cc108f89806
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Vorgehensweise: Erstellen unterst&#252;tzender Anmeldeinformationen
Sie können über ein benutzerdefiniertes Sicherheitsschema verfügen, für das mehrere Anmeldeinformationen erforderlich sind.  Beispielsweise kann ein Dienst vom Client nicht nur den Benutzernamen und das Kennwort fordern, sondern auch Anmeldeinformationen, die belegen, dass der Client älter als 18 Jahre ist.  Diese Anmeldeinformationen sind *unterstützende Anmeldeinformationen*.  In diesem Thema wird beschrieben, wie Sie solche Anmeldeinformationen in einem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Client implementieren.  
  
> [!NOTE]
>  Die Spezifikation für unterstützende Anmeldeinformationen ist Teil der WS\-SecurityPolicy\-Spezifikation.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Web Services Security Specifications](http://go.microsoft.com/fwlink/?LinkId=88537).  
  
## Unterstützende Token  
 Beim Verwenden der Nachrichtensicherheit wird die Nachricht immer mit *primären Anmeldeinformationen* gesichert \(z. B. mit einem X.509\-Zertifikat oder einem Kerberos\-Ticket\).  
  
 Wie durch die Spezifikation festgelegt, verwendet eine Bindung zur Sicherung des Nachrichtenaustauschs *Token*.  Ein *Token* ist eine Darstellung von Sicherheitsanmeldeinformationen.  
  
 Die Sicherheitsbindung verwendet zum Erstellen einer Signatur ein in ihrer Richtlinie identifiziertes primäres Token.  Diese Signatur wird als *Nachrichtensignatur* bezeichnet.  
  
 Es können zusätzliche Token angegeben werden, um die von dem der Nachrichtensignatur zugeordneten Token bereitgestellten Ansprüche zu erweitern.  
  
## Unterzeichnen, Signieren und Verschlüsseln  
 Als Ergebnis unterstützender Anmeldeinformationen wird ein *unterstützendes Token* innerhalb der Nachricht übertragen.  Die WS\-SecurityPolicy\-Spezifikation definiert vier Methoden zum Anhängen eines unterstützenden Tokens an die Nachricht, wie in der folgenden Tabelle beschrieben.  
  
|Zweck|Beschreibung|  
|-----------|------------------|  
|Signiert|Das unterstützende Token ist im Sicherheitsheader enthalten und wird durch die Nachrichtensignatur signiert.|  
|Unterzeichnend|Ein *unterzeichnendes Token* signiert die Nachrichtensignatur.|  
|Signiert und unterzeichnend|Signierte, unterzeichnende Token signieren das gesamte aus der Nachrichtensignatur erstellte `ds:Signature`\-Element und werden selbst durch die Nachrichtensignatur signiert; d. h., beide Token \(das für die Nachrichtensignatur verwendete Token und das signierte unterzeichnende Token\) signieren einander.|  
|Signiert und verschlüsselnd|Signierte, verschlüsselte unterstützende Token sind signierte unterstützende Token, die beim Anzeigen im `wsse:SecurityHeader` auch verschlüsselt werden.|  
  
## Programmieren von unterstützenden Anmeldeinformationen  
 Zum Erstellen eines Dienstes, der unterstützende Token verwendet, müssen Sie ein [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) erstellen.  \([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).\)  
  
 Der erste Schritt beim Erstellen einer benutzerdefinierten Bindung ist das Erstellen eines Sicherheitsbindungselements, das einer der folgenden drei Typen sein kann:  
  
-   <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 Alle Klassen erben vom <xref:System.ServiceModel.Channels.SecurityBindingElement>, das vier relevante Eigenschaften umfasst:  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.EndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OperationSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalEndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalOperationSupportingTokenParameters%2A>  
  
#### Bereiche  
 Für unterstützende Anmeldeinformationen existieren vier Bereiche:  
  
-   *Den Endpunkt unterstützende Token* unterstützen alle Vorgänge eines Endpunkts.  Die Anmeldeinformationen, die das unterstützende Token darstellt, können beim Aufrufen eines beliebigen Endpunktvorgangs verwendet werden.  
  
-   *Den Vorgang unterstützende Token* unterstützen nur einen bestimmten Endpunktvorgang.  
  
 Wie durch die Eigenschaftennamen angegeben, können unterstützende Anmeldeinformationen erforderlich oder optional sein.  Die unterstützenden Anmeldeinformationen werden verwendet, wenn sie vorhanden, aber nicht erforderlich sind; die Authentifizierung schlägt jedoch nicht fehl, wenn sie nicht vorhanden sind.  
  
## Verfahren  
  
#### So erstellen Sie eine benutzerdefinierte Bindung, die unterstützende Anmeldeinformationen enthält  
  
1.  Erstellen Sie ein Sicherheitsbindungselement.  Im nachfolgenden Beispiel wird ein <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> mit dem `UserNameForCertificate`\-Authentifizierungsmodus erstellt.  Verwenden Sie die <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>\-Methode.  
  
2.  Fügen Sie den unterstützenden Parameter der von der entsprechenden Eigenschaft \(`Endorsing`, `Signed`, `SignedEncrypted` oder `SignedEndorsed`\) zurückgegebenen Auflistung von Typen hinzu.  Die Typen im <xref:System.ServiceModel.Security.Tokens>\-Namespace umfassen häufig verwendete Typen wie die <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispiel wird eine Instanz des <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> erstellt und eine Instanz der <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters>\-Klasse der von der unterzeichenden Eigenschaft zurückgegebenen Auflistung hinzugefügt.  
  
### Code  
 [!code-csharp[c_SupportingCredential#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_supportingcredential/cs/source.cs#1)]  
  
## Siehe auch  
 [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)