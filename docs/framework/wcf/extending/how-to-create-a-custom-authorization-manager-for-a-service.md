---
title: "Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers f&#252;r einen Dienst | Microsoft Docs"
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
  - "OperationRequirement-Klasse"
  - "Windows Communication Foundation, Erweitern"
ms.assetid: 6214afde-44c1-4bf5-ba07-5ad6493620ea
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers f&#252;r einen Dienst
Die Identitätsmodellinfrastruktur in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] unterstützt ein erweiterbares anspruchsbasiertes Autorisierungsmodell.Ansprüche werden aus Token extrahiert, wahlweise mit benutzerdefinierten Autorisierungsrichtlinien verarbeitet und dann in einem <xref:System.IdentityModel.Policy.AuthorizationContext> platziert.Die Ansprüche im <xref:System.IdentityModel.Policy.AuthorizationContext> werden von einem Autorisierungs\-Manager geprüft und als Grundlage für Autorisierungsentscheidungen herangezogen.  
  
 Standardmäßig werden Autorisierungsentscheidungen von der <xref:System.ServiceModel.ServiceAuthorizationManager>\-Klasse getroffen. Diese Entscheidungen können jedoch durch die Erstellung eines benutzerdefinierten Autorisierungs\-Managers außer Kraft gesetzt werden.Wenn Sie Ihren eigenen Autorisierungs\-Manager erstellen möchten, erstellen Sie eine Klasse, die von <xref:System.ServiceModel.ServiceAuthorizationManager> ableitet, und implementieren die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>\-Methode.Autorisierungsentscheidungen werden in der <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>\-Methode getroffen, von der `true` zurückgegeben wird, wenn Zugriff gewährt wurde, und `false`, wenn der Zugriff verweigert wurde.  
  
 Wenn die Autorisierungsentscheidung vom Inhalt des Nachrichtentexts abhängt, verwenden Sie die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>\-Methode.  
  
 Um Leistungseinbußen zu vermeiden, sollten Sie soweit möglich Ihre Anwendung neu entwerfen, sodass für die Autorisierungsentscheidung kein Zugriff auf den Nachrichtentext erforderlich ist.  
  
 Die Registrierung des benutzerdefinierten Autorisierungs\-Managers für einen Dienst kann im Code oder in der Konfiguration erfolgen.  
  
### So erstellen Sie einen benutzerdefinierten Autorisierungs\-Manager  
  
1.  Leiten Sie eine Klasse von der <xref:System.ServiceModel.ServiceAuthorizationManager>\-Klasse ab.  
  
     [!code-csharp[c_CustomAuthMgr#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#5)]
     [!code-vb[c_CustomAuthMgr#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#5)]  
  
2.  Überschreiben Sie die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29>\-Methode.  
  
     Verwenden Sie den an die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29>\-Methode übergebenen <xref:System.ServiceModel.OperationContext>, um Autorisierungsentscheidungen zu fällen.  
  
     Im folgenden Codebeispiel wird mit der <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29>\-Methode der benutzerdefinierte Anspruch `http://www.contoso.com/claims/allowedoperation` gesucht, um eine Autorisierungsentscheidung zu treffen.  
  
     [!code-csharp[c_CustomAuthMgr#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#6)]
     [!code-vb[c_CustomAuthMgr#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#6)]  
  
### So registrieren Sie einen benutzerdefinierten Autorisierungs\-Manager im Code  
  
1.  Erstellen Sie eine Instanz des benutzerdefinierten Autorisierungs\-Managers, und weisen Sie sie der <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A>\-Eigenschaft zu.  
  
     Auf <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> kann mit der <xref:System.ServiceModel.ServiceHostBase.Authorization%2A>\-Eigenschaft zugegriffen werden.  
  
     Im folgenden Codebeispiel wird der benutzerdefinierte `MyServiceAuthorizationManager`\-Autorisierungs\-Manager registriert.  
  
     [!code-csharp[c_CustomAuthMgr#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#4)]
     [!code-vb[c_CustomAuthMgr#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#4)]  
  
### So registrieren Sie einen benutzerdefinierten Autorisierungs\-Manager in der Konfiguration  
  
1.  Öffnen Sie die Konfigurationsdatei für den Dienst.  
  
2.  Fügen Sie ein [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) zum [\<Verhalten\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) hinzu.  
  
     Fügen Sie dem [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) ein `serviceAuthorizationManagerType`\-Attribut hinzu, und legen Sie als Wert für das Attribut den Typ fest, der den benutzerdefinierten Autorisierungs\-Manager repräsentiert.  
  
3.  Fügen Sie eine Bindung hinzu, durch die die Kommunikation zwischen Client und Dienst gesichert wird.  
  
     Die für diese Kommunikation gewählte Bindung bestimmt die Ansprüche, die zum <xref:System.IdentityModel.Policy.AuthorizationContext> hinzugefügt werden, der vom benutzerdefinierten Autorisierungs\-Manager verwendet wird, um Autorisierungsentscheidungen zu treffen.Ausführliche Informationen zu systemeigenen Bindungen finden Sie unter [Vom System bereitgestellte Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
4.  Ordnen Sie das Verhalten einem Dienstendpunkt zu, indem Sie ein [\<service\>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md)`behaviorConfiguration-Element hinzufügen, und legen Sie als Wert des` [\<Verhalten\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)\-Element fest.  
  
     Weitere Informationen zum Konfigurieren eines Dienstendpunkts finden Sie unter [Gewusst wie: Erstellen eines Dienstendpunkts in einer Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
     Im folgenden Codebeispiel wird der benutzerdefinierte Autorisierungs\-Manager `Samples.MyServiceAuthorizationManager` registriert.  
  
    ```  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service   
              name="Microsoft.ServiceModel.Samples.CalculatorService"  
              behaviorConfiguration="CalculatorServiceBehavior">  
            <host>  
              <baseAddresses>  
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
              </baseAddresses>  
            </host>  
            <endpoint address=""  
                      binding="wsHttpBinding_Calculator"  
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />  
          </service>  
        </services>  
        <bindings>  
          <WSHttpBinding>  
           <binding name = "wsHttpBinding_Calculator">  
             <security mode="Message">  
               <message clientCredentialType="Windows"/>  
             </security>  
            </binding>  
          </WSHttpBinding>  
    </bindings>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="CalculatorServiceBehavior">  
              <serviceAuthorization serviceAuthorizationManagerType="Samples.MyServiceAuthorizationManager,MyAssembly" />  
             </behavior>  
         </serviceBehaviors>  
       </behaviors>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
    > [!WARNING]
    >  Beachten Sie, dass die Zeichenfolge den vollqualifizierten Typnamen enthalten muss, wenn Sie serviceAuthorizationManagerType angeben.Kommas und der Name der Assembly, in der der Typ definiert ist.Wenn Sie den Assemblynamen auslassen, versucht WCF, den Typ aus System.ServiceModel.dll zu laden.  
  
## Beispiel  
 Das folgende Codebeispiel zeigt eine grundlegende Implementierung einer <xref:System.ServiceModel.ServiceAuthorizationManager>\-Klasse, bei der auch die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>\-Methode außer Kraft gesetzt \(überschrieben\) wird.Im Beispielcode wird der <xref:System.IdentityModel.Policy.AuthorizationContext> auf einen benutzerspezifischen Anspruch hin überprüft und `true` zurückgegeben, wenn die Ressource für diesen benutzerspezifischen Anspruch zum Aktionswert aus dem <xref:System.ServiceModel.OperationContext> passt.Eine umfassendere Implementierung einer <xref:System.ServiceModel.ServiceAuthorizationManager>\-Klasse finden Sie unter [Autorisierungsrichtlinie](../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
 [!code-csharp[c_CustomAuthMgr#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#2)]
 [!code-vb[c_CustomAuthMgr#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#2)]  
  
## Siehe auch  
 <xref:System.ServiceModel.ServiceAuthorizationManager>   
 [Autorisierungsrichtlinie](../../../../docs/framework/wcf/samples/authorization-policy.md)   
 [Autorisierungsrichtlinie](../../../../docs/framework/wcf/samples/authorization-policy.md)