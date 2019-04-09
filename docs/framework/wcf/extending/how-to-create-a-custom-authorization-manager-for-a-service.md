---
title: 'Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Communication Foundation, extending
- OperationRequirement class
ms.assetid: 6214afde-44c1-4bf5-ba07-5ad6493620ea
ms.openlocfilehash: 6a168902b79bd27345c9d9e2371947cc9d64233c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156493"
---
# <a name="how-to-create-a-custom-authorization-manager-for-a-service"></a>Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst
Die identitätsmodellinfrastruktur in Windows Communication Foundation (WCF) unterstützt eine erweiterbare anspruchsbasierte Autorisierung-Modell. Ansprüche werden aus Token extrahiert, wahlweise mit benutzerdefinierten Autorisierungsrichtlinien verarbeitet und dann in einem <xref:System.IdentityModel.Policy.AuthorizationContext> platziert. Die Ansprüche im <xref:System.IdentityModel.Policy.AuthorizationContext> werden von einem Autorisierungs-Manager geprüft und als Grundlage für Autorisierungsentscheidungen herangezogen.  
  
 Standardmäßig werden Autorisierungsentscheidungen von der <xref:System.ServiceModel.ServiceAuthorizationManager>-Klasse getroffen. Diese Entscheidungen können jedoch durch die Erstellung eines benutzerdefinierten Autorisierungs-Managers außer Kraft gesetzt werden. Wenn Sie Ihren eigenen Autorisierungs-Manager erstellen möchten, erstellen Sie eine Klasse, die von <xref:System.ServiceModel.ServiceAuthorizationManager> ableitet, und implementieren die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>-Methode. Autorisierungsentscheidungen werden in der <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>-Methode getroffen, von der `true` zurückgegeben wird, wenn Zugriff gewährt wurde, und `false`, wenn der Zugriff verweigert wurde.  
  
 Wenn die Autorisierungsentscheidung vom Inhalt des Nachrichtentexts abhängt, verwenden Sie die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>-Methode.  
  
 Um Leistungseinbußen zu vermeiden, sollten Sie soweit möglich Ihre Anwendung neu entwerfen, sodass für die Autorisierungsentscheidung kein Zugriff auf den Nachrichtentext erforderlich ist.  
  
 Die Registrierung des benutzerdefinierten Autorisierungs-Managers für einen Dienst kann im Code oder in der Konfiguration erfolgen.  
  
### <a name="to-create-a-custom-authorization-manager"></a>So erstellen Sie einen benutzerdefinierten Autorisierungs-Manager  
  
1.  Leiten Sie eine Klasse von der <xref:System.ServiceModel.ServiceAuthorizationManager>-Klasse ab.  
  
     [!code-csharp[c_CustomAuthMgr#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#5)]
     [!code-vb[c_CustomAuthMgr#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#5)]  
  
2.  Überschreiben Sie die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29>-Methode.  
  
     Verwenden Sie den an die <xref:System.ServiceModel.OperationContext>-Methode übergebenen <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29>, um Autorisierungsentscheidungen zu fällen.  
  
     Im folgenden Codebeispiel wird mit der <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29>-Methode der benutzerdefinierte Anspruch `http://www.contoso.com/claims/allowedoperation` gesucht, um eine Autorisierungsentscheidung zu treffen.  
  
     [!code-csharp[c_CustomAuthMgr#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#6)]
     [!code-vb[c_CustomAuthMgr#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#6)]  
  
### <a name="to-register-a-custom-authorization-manager-using-code"></a>So registrieren Sie einen benutzerdefinierten Autorisierungs-Manager im Code  
  
1.  Erstellen Sie eine Instanz des benutzerdefinierten Autorisierungs-Managers, und weisen Sie sie der <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A>-Eigenschaft zu.  
  
     Auf <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> kann mit der <xref:System.ServiceModel.ServiceHostBase.Authorization%2A>-Eigenschaft zugegriffen werden.  
  
     Im folgenden Codebeispiel wird der benutzerdefinierte `MyServiceAuthorizationManager`-Autorisierungs-Manager registriert.  
  
     [!code-csharp[c_CustomAuthMgr#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#4)]
     [!code-vb[c_CustomAuthMgr#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#4)]  
  
### <a name="to-register-a-custom-authorization-manager-using-configuration"></a>So registrieren Sie einen benutzerdefinierten Autorisierungs-Manager in der Konfiguration  
  
1.  Öffnen Sie die Konfigurationsdatei für den Dienst.  
  
2.  Hinzufügen einer [ \<ServiceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) auf die [ \<Verhaltensweisen >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).  
  
     Um die [ \<ServiceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md), Hinzufügen einer `serviceAuthorizationManagerType` Attribut, und legen Sie dessen Wert in den Typ, der den benutzerdefinierten Autorisierungs-Manager darstellt.  
  
3.  Fügen Sie eine Bindung hinzu, durch die die Kommunikation zwischen Client und Dienst gesichert wird.  
  
     Die für diese Kommunikation gewählte Bindung bestimmt die Ansprüche, die zum <xref:System.IdentityModel.Policy.AuthorizationContext> hinzugefügt werden, der vom benutzerdefinierten Autorisierungs-Manager verwendet wird, um Autorisierungsentscheidungen zu treffen. Weitere Informationen zu den vom System bereitgestellten Bindungen finden Sie unter [System-provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
4.  Ordnen Sie das Verhalten einem Dienstendpunkt, durch das Hinzufügen einer [ \<Service >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) Element, und legen Sie den Wert des der `behaviorConfiguration` -Attributs auf den Wert des Attributs "Name" für die [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) Element.  
  
     Weitere Informationen zum Konfigurieren eines Dienstendpunkts finden Sie unter [Vorgehensweise: Erstellen eines Dienstendpunkts in der Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
     Im folgenden Codebeispiel wird der benutzerdefinierte Autorisierungs-Manager `Samples.MyServiceAuthorizationManager` registriert.  
  
    ```xml  
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
    >  Beachten Sie, dass die Zeichenfolge den vollqualifizierten Typnamen enthalten muss, wenn Sie serviceAuthorizationManagerType angeben. ein Komma und der Name der Assembly, in der der Typ definiert ist. Wenn Sie den Assemblynamen auslassen, versucht WCF, den Typ aus System.ServiceModel.dll zu laden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt eine grundlegende Implementierung einer <xref:System.ServiceModel.ServiceAuthorizationManager>-Klasse, bei der auch die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>-Methode außer Kraft gesetzt (überschrieben) wird. Im Beispielcode wird der <xref:System.IdentityModel.Policy.AuthorizationContext> auf einen benutzerspezifischen Anspruch hin überprüft und `true` zurückgegeben, wenn die Ressource für diesen benutzerspezifischen Anspruch zum Aktionswert aus dem <xref:System.ServiceModel.OperationContext> passt. Eine vollständige Implementierung von einem <xref:System.ServiceModel.ServiceAuthorizationManager> Klasse, finden Sie unter [Autorisierungsrichtlinie](../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
 [!code-csharp[c_CustomAuthMgr#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#2)]
 [!code-vb[c_CustomAuthMgr#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [Autorisierungsrichtlinie](../../../../docs/framework/wcf/samples/authorization-policy.md)
