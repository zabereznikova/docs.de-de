---
title: "Vorgehensweise: Einrichten einer Signaturbest&#228;tigung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Signaturbestätigung"
  - "WCF, Sicherheit"
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Vorgehensweise: Einrichten einer Signaturbest&#228;tigung
*Signaturbestätigung* ist ein Mechanismus für einen Nachrichteninitiator, um sicherzustellen, dass eine empfangene Antwort als Antwort auf die ursprüngliche Nachricht des Absenders generiert wurde.Die Signaturbestätigung wird in der WS\-Sicherheit 1.1\-Spezifikation definiert.Wenn ein Endpunkt WS\-Sicherheit 1.0 unterstützt, können Sie keine Signaturbestätigung verwenden.  
  
 In den folgenden Verfahren wird beschrieben, wie die Signaturbestätigung mit <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> aktiviert wird.Sie können das gleiche Verfahren mit <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> verwenden.Das Verfahren baut auf den grundlegenden Schritten auf, die in [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md) beschrieben werden.  
  
### So aktivieren Sie die Signaturbestätigung in Code  
  
1.  Erstellen Sie eine Instanz der <xref:System.ServiceModel.Channels.BindingElementCollection>\-Klasse.  
  
2.  Erstellen Sie eine Instanz der <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>\-Klasse.  
  
3.  Legen Sie <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> auf `true` fest  
  
4.  Fügen Sie der Bindungsauflistung das Sicherheitselement hinzu.  
  
5.  Erstellen Sie eine benutzerdefinierte Bindung, wie in [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md) angegeben.  
  
### So aktivieren Sie die Signaturbestätigung in der Konfiguration  
  
1.  Fügen Sie dem `<customBinding>`\-Abschnitt der Konfigurationsdatei ein `<bindings>`\-Element hinzu.  
  
2.  Fügen Sie ein `<binding>`\-Element hinzu, und legen Sie das Namensattribut auf einen passenden Wert fest.  
  
3.  Fügen Sie ein entsprechendes Codierungselement hinzu.Im folgenden Beispiel wird ein `<TextMessageEncoding>`\-Element hinzugefügt.  
  
4.  Fügen Sie ein untergeordnetes `<security>``requireSignatureConfirmation-Element hinzu, und legen Sie das` `true-Attribut auf`  fest.  
  
5.  Optional.Wenn Sie die Signaturbestätigung während des Bootstraps aktivieren möchten, fügen Sie ein untergeordnetes [\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)\-Element hinzu, und legen Sie das `equireSignatureConfirmation`\-Attribut auf `true` fest.  
  
6.  Fügen Sie ein entsprechendes Transportelement hinzu.Im folgenden Beispiel wird ein [\<httpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) hinzugefügt:  
  
    ```  
    <bindings>  
      <customBinding>  
        <binding name="SignatureConfirmationBinding">  
          <security requireSignatureConfirmation="true">  
            <secureConversationBootstrap requireSignatureConfirmation="true" />  
              </security>  
           <textMessageEncoding />  
             <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## Beispiel  
 Der folgende Code erstellt eine Instanz von <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> und legt die <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A>\-Eigenschaft auf `true` fest.Beachten Sie, dass in diesem Beispiel das im vorangehenden Beispiel gezeigte `<secureConversationBootstrap>`\-Element nicht verwendet wird.In diesem Beispiel wird die Signaturbestätigung veranschaulicht, wenn ein Windows\-\(Kerberos\-Protokoll\)\-Token verwendet wird.In diesem Fall wird die Signatur des Clients in allen Antworten vom Dienst zurückgegeben und vom Client bestätigt.  
  
 [!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
 [!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]  
  
## Siehe auch  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>   
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>   
 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>   
 [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)   
 [Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)