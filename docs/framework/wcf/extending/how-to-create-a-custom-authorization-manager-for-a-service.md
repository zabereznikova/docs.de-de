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
ms.openlocfilehash: 7fe392b2fcd2f8ccb00bfd6ffd7e917649f8280c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-custom-authorization-manager-for-a-service"></a><span data-ttu-id="76b1a-102">Vorgehensweise: Erstellen eines benutzerdefinierten Autorisierungs-Managers für einen Dienst</span><span class="sxs-lookup"><span data-stu-id="76b1a-102">How to: Create a Custom Authorization Manager for a Service</span></span>
<span data-ttu-id="76b1a-103">Die identitätsmodellinfrastruktur in Windows Communication Foundation (WCF) unterstützt eine erweiterbare anspruchsbasierte Autorisierung-Modell.</span><span class="sxs-lookup"><span data-stu-id="76b1a-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) supports an extensible claims-based authorization model.</span></span> <span data-ttu-id="76b1a-104">Ansprüche werden aus Token extrahiert, wahlweise mit benutzerdefinierten Autorisierungsrichtlinien verarbeitet und dann in einem <xref:System.IdentityModel.Policy.AuthorizationContext> platziert.</span><span class="sxs-lookup"><span data-stu-id="76b1a-104">Claims are extracted from tokens and optionally processed by custom authorization policies and then placed into an <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span> <span data-ttu-id="76b1a-105">Die Ansprüche im <xref:System.IdentityModel.Policy.AuthorizationContext> werden von einem Autorisierungs-Manager geprüft und als Grundlage für Autorisierungsentscheidungen herangezogen.</span><span class="sxs-lookup"><span data-stu-id="76b1a-105">An authorization manager examines the claims in the <xref:System.IdentityModel.Policy.AuthorizationContext> to make authorization decisions.</span></span>  
  
 <span data-ttu-id="76b1a-106">Standardmäßig werden Autorisierungsentscheidungen von der <xref:System.ServiceModel.ServiceAuthorizationManager>-Klasse getroffen. Diese Entscheidungen können jedoch durch die Erstellung eines benutzerdefinierten Autorisierungs-Managers außer Kraft gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="76b1a-106">By default, authorization decisions are made by the <xref:System.ServiceModel.ServiceAuthorizationManager> class; however these decisions can be overridden by creating a custom authorization manager.</span></span> <span data-ttu-id="76b1a-107">Wenn Sie Ihren eigenen Autorisierungs-Manager erstellen möchten, erstellen Sie eine Klasse, die von <xref:System.ServiceModel.ServiceAuthorizationManager> ableitet, und implementieren die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="76b1a-107">To create a custom authorization manager, create a class that derives from <xref:System.ServiceModel.ServiceAuthorizationManager> and implement <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="76b1a-108">Autorisierungsentscheidungen werden in der <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>-Methode getroffen, von der `true` zurückgegeben wird, wenn Zugriff gewährt wurde, und `false`, wenn der Zugriff verweigert wurde.</span><span class="sxs-lookup"><span data-stu-id="76b1a-108">Authorization decisions are made in the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method, which returns `true` when access is granted and `false` when access is denied.</span></span>  
  
 <span data-ttu-id="76b1a-109">Wenn die Autorisierungsentscheidung vom Inhalt des Nachrichtentexts abhängt, verwenden Sie die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="76b1a-109">If the authorization decision depends on the contents of the message body, use the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method.</span></span>  
  
 <span data-ttu-id="76b1a-110">Um Leistungseinbußen zu vermeiden, sollten Sie soweit möglich Ihre Anwendung neu entwerfen, sodass für die Autorisierungsentscheidung kein Zugriff auf den Nachrichtentext erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="76b1a-110">Because of performance issues, if possible you should redesign your application so that the authorization decision does not require access to the message body.</span></span>  
  
 <span data-ttu-id="76b1a-111">Die Registrierung des benutzerdefinierten Autorisierungs-Managers für einen Dienst kann im Code oder in der Konfiguration erfolgen.</span><span class="sxs-lookup"><span data-stu-id="76b1a-111">Registration of the custom authorization manager for a service can be done in code or configuration.</span></span>  
  
### <a name="to-create-a-custom-authorization-manager"></a><span data-ttu-id="76b1a-112">So erstellen Sie einen benutzerdefinierten Autorisierungs-Manager</span><span class="sxs-lookup"><span data-stu-id="76b1a-112">To create a custom authorization manager</span></span>  
  
1.  <span data-ttu-id="76b1a-113">Leiten Sie eine Klasse von der <xref:System.ServiceModel.ServiceAuthorizationManager>-Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="76b1a-113">Derive a class from the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>  
  
     [!code-csharp[c_CustomAuthMgr#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#5)]
     [!code-vb[c_CustomAuthMgr#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#5)]  
  
2.  <span data-ttu-id="76b1a-114">Überschreiben Sie die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29>-Methode.</span><span class="sxs-lookup"><span data-stu-id="76b1a-114">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> method.</span></span>  
  
     <span data-ttu-id="76b1a-115">Verwenden Sie den an die <xref:System.ServiceModel.OperationContext>-Methode übergebenen <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29>, um Autorisierungsentscheidungen zu fällen.</span><span class="sxs-lookup"><span data-stu-id="76b1a-115">Use the <xref:System.ServiceModel.OperationContext> that is passed to the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> method to make authorization decisions.</span></span>  
  
     <span data-ttu-id="76b1a-116">Im folgenden Codebeispiel wird mit der <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29>-Methode der benutzerdefinierte Anspruch `http://www.contoso.com/claims/allowedoperation` gesucht, um eine Autorisierungsentscheidung zu treffen.</span><span class="sxs-lookup"><span data-stu-id="76b1a-116">The following code example uses the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> method to find the custom claim `http://www.contoso.com/claims/allowedoperation` to make an authorization decision.</span></span>  
  
     [!code-csharp[c_CustomAuthMgr#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#6)]
     [!code-vb[c_CustomAuthMgr#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#6)]  
  
### <a name="to-register-a-custom-authorization-manager-using-code"></a><span data-ttu-id="76b1a-117">So registrieren Sie einen benutzerdefinierten Autorisierungs-Manager im Code</span><span class="sxs-lookup"><span data-stu-id="76b1a-117">To register a custom authorization manager using code</span></span>  
  
1.  <span data-ttu-id="76b1a-118">Erstellen Sie eine Instanz des benutzerdefinierten Autorisierungs-Managers, und weisen Sie sie der <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A>-Eigenschaft zu.</span><span class="sxs-lookup"><span data-stu-id="76b1a-118">Create an instance of the custom authorization manager and assign it to the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A> property.</span></span>  
  
     <span data-ttu-id="76b1a-119">Auf <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> kann mit der <xref:System.ServiceModel.ServiceHostBase.Authorization%2A>-Eigenschaft zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="76b1a-119">The <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> can be accessed using <xref:System.ServiceModel.ServiceHostBase.Authorization%2A> property.</span></span>  
  
     <span data-ttu-id="76b1a-120">Im folgenden Codebeispiel wird der benutzerdefinierte `MyServiceAuthorizationManager`-Autorisierungs-Manager registriert.</span><span class="sxs-lookup"><span data-stu-id="76b1a-120">The following code example registers the `MyServiceAuthorizationManager` custom authorization manager.</span></span>  
  
     [!code-csharp[c_CustomAuthMgr#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#4)]
     [!code-vb[c_CustomAuthMgr#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#4)]  
  
### <a name="to-register-a-custom-authorization-manager-using-configuration"></a><span data-ttu-id="76b1a-121">So registrieren Sie einen benutzerdefinierten Autorisierungs-Manager in der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="76b1a-121">To register a custom authorization manager using configuration</span></span>  
  
1.  <span data-ttu-id="76b1a-122">Öffnen Sie die Konfigurationsdatei für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="76b1a-122">Open the configuration file for the service.</span></span>  
  
2.  <span data-ttu-id="76b1a-123">Hinzufügen einer [ \<ServiceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) auf die [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="76b1a-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).</span></span>  
  
     <span data-ttu-id="76b1a-124">Um die [ \<ServiceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md), Hinzufügen einer `serviceAuthorizationManagerType` Attribut, und legen Sie den Wert in den Typ, der vom benutzerdefinierten Autorisierungs-Manager darstellt.</span><span class="sxs-lookup"><span data-stu-id="76b1a-124">To the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md), add a `serviceAuthorizationManagerType` attribute and set its value to the type that represents the custom authorization manager.</span></span>  
  
3.  <span data-ttu-id="76b1a-125">Fügen Sie eine Bindung hinzu, durch die die Kommunikation zwischen Client und Dienst gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="76b1a-125">Add a binding that secures the communication between the client and service.</span></span>  
  
     <span data-ttu-id="76b1a-126">Die für diese Kommunikation gewählte Bindung bestimmt die Ansprüche, die zum <xref:System.IdentityModel.Policy.AuthorizationContext> hinzugefügt werden, der vom benutzerdefinierten Autorisierungs-Manager verwendet wird, um Autorisierungsentscheidungen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="76b1a-126">The binding that is chosen for this communication determines the claims that are added to the <xref:System.IdentityModel.Policy.AuthorizationContext>, which the custom authorization manager uses to make authorization decisions.</span></span> <span data-ttu-id="76b1a-127">Weitere Informationen zu den vom System bereitgestellten Bindungen, finden Sie unter [sicherheitsbindungsarten Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="76b1a-127">For more details about the system-provided bindings, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
4.  <span data-ttu-id="76b1a-128">Ordnen Sie das Verhalten zu einem Dienstendpunkt durch Hinzufügen einer [ \<Service >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) Element und legen Sie den Wert von der `behaviorConfiguration` -Attributs auf den Wert des Namensattributs für die [ \<Verhalten >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) Element.</span><span class="sxs-lookup"><span data-stu-id="76b1a-128">Associate the behavior to a service endpoint, by adding a [\<service>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) element and set the value of the `behaviorConfiguration` attribute to the value of the name attribute for the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>  
  
     <span data-ttu-id="76b1a-129">Weitere Informationen zum Konfigurieren eines Dienstendpunkts finden Sie unter [Vorgehensweise: Erstellen eines Dienstendpunkts in der Konfiguration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="76b1a-129">For more information about configuring a service endpoint, see [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).</span></span>  
  
     <span data-ttu-id="76b1a-130">Im folgenden Codebeispiel wird der benutzerdefinierte Autorisierungs-Manager `Samples.MyServiceAuthorizationManager` registriert.</span><span class="sxs-lookup"><span data-stu-id="76b1a-130">The following code example registers the custom authorization manager `Samples.MyServiceAuthorizationManager`.</span></span>  
  
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
    >  <span data-ttu-id="76b1a-131">Beachten Sie, dass die Zeichenfolge den vollqualifizierten Typnamen enthalten muss, wenn Sie serviceAuthorizationManagerType angeben.</span><span class="sxs-lookup"><span data-stu-id="76b1a-131">Note that when you specify the serviceAuthorizationManagerType, the string must contain the fully qualified type name.</span></span> <span data-ttu-id="76b1a-132">ein Komma und der Name der Assembly, in der der Typ definiert ist.</span><span class="sxs-lookup"><span data-stu-id="76b1a-132">a comma, and the name of the assembly in which the type is defined.</span></span> <span data-ttu-id="76b1a-133">Wenn Sie den Assemblynamen auslassen, versucht WCF, den Typ aus System.ServiceModel.dll zu laden.</span><span class="sxs-lookup"><span data-stu-id="76b1a-133">If you leave out the assembly name, WCF will attempt to load the type from System.ServiceModel.dll.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76b1a-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="76b1a-134">Example</span></span>  
 <span data-ttu-id="76b1a-135">Das folgende Codebeispiel zeigt eine grundlegende Implementierung einer <xref:System.ServiceModel.ServiceAuthorizationManager>-Klasse, bei der auch die <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>-Methode außer Kraft gesetzt (überschrieben) wird.</span><span class="sxs-lookup"><span data-stu-id="76b1a-135">The following code example demonstrates a basic implementation of a <xref:System.ServiceModel.ServiceAuthorizationManager> class that includes overriding the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="76b1a-136">Im Beispielcode wird der <xref:System.IdentityModel.Policy.AuthorizationContext> auf einen benutzerspezifischen Anspruch hin überprüft und `true` zurückgegeben, wenn die Ressource für diesen benutzerspezifischen Anspruch zum Aktionswert aus dem <xref:System.ServiceModel.OperationContext> passt.</span><span class="sxs-lookup"><span data-stu-id="76b1a-136">The example code examines the <xref:System.IdentityModel.Policy.AuthorizationContext> for a custom claim and returns `true` when the resource for that custom claim matches the action value from the <xref:System.ServiceModel.OperationContext>.</span></span> <span data-ttu-id="76b1a-137">Für eine vollständige Implementierung der eine <xref:System.ServiceModel.ServiceAuthorizationManager> Klasse, finden Sie unter [Autorisierungsrichtlinie](../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="76b1a-137">For a more complete implementation of a <xref:System.ServiceModel.ServiceAuthorizationManager> class, see [Authorization Policy](../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
 [!code-csharp[c_CustomAuthMgr#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#2)]
 [!code-vb[c_CustomAuthMgr#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="76b1a-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76b1a-138">See Also</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [<span data-ttu-id="76b1a-139">Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="76b1a-139">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)  
 [<span data-ttu-id="76b1a-140">Autorisierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="76b1a-140">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)
