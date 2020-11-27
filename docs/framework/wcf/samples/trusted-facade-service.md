---
title: Vertrauenswürdiger Fassadendienst
ms.date: 03/30/2017
ms.assetid: c34d1a8f-e45e-440b-a201-d143abdbac38
ms.openlocfilehash: 80f139ace43d5f8d2136528681386711bea7a1e5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295053"
---
# <a name="trusted-facade-service"></a><span data-ttu-id="03d68-102">Vertrauenswürdiger Fassadendienst</span><span class="sxs-lookup"><span data-stu-id="03d68-102">Trusted Facade Service</span></span>

<span data-ttu-id="03d68-103">Dieses Szenariobeispiel veranschaulicht, wie die Identitätsinformationen des Aufrufers mithilfe Windows Communication Foundation (WCF)-Sicherheitsinfrastruktur von einem Dienst zu einem anderen weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="03d68-103">This scenario sample demonstrates how to flow caller's identity information from one service to another using Windows Communication Foundation (WCF) security infrastructure.</span></span>  
  
 <span data-ttu-id="03d68-104">Ein allgemeines Entwurfsmuster besteht darin, dem öffentlichen Netzwerk die Funktionalität, die von einem Dienst bereitgestellt wird, mithilfe eines Fassadendiensts verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="03d68-104">It is a common design pattern to expose the functionality provided by a service to the public network using a façade service.</span></span> <span data-ttu-id="03d68-105">Der Fassadendienst befindet sich üblicherweise im Perimeternetzwerk (auch bekannt als DMZ (Demilitarized Zone; deutsch: entmilitarisierte Zone) und geschirmtes Unternetz) und kommuniziert mit einem Back-End-Dienst, der die Geschäftslogik implementiert und Zugriff auf interne Daten hat.</span><span class="sxs-lookup"><span data-stu-id="03d68-105">The façade service typically resides in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet) and communicates with a backend service that implements the business logic and has access to internal data.</span></span> <span data-ttu-id="03d68-106">Der Kommunikationskanal zwischen dem Fassadendienst und dem Back-End-Dienst führt durch eine Firewall und wird üblicherweise auf einen Zweck begrenzt.</span><span class="sxs-lookup"><span data-stu-id="03d68-106">The communication channel between the façade service and the backend service goes through a firewall and is usually limited for a single purpose only.</span></span>  
  
 <span data-ttu-id="03d68-107">Dieses Beispiel besteht aus den folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="03d68-107">This sample consists of the following components:</span></span>  
  
- <span data-ttu-id="03d68-108">Rechnerclient</span><span class="sxs-lookup"><span data-stu-id="03d68-108">Calculator client</span></span>  
  
- <span data-ttu-id="03d68-109">Rechnerfassadendienst</span><span class="sxs-lookup"><span data-stu-id="03d68-109">Calculator façade service</span></span>  
  
- <span data-ttu-id="03d68-110">Rechner-Back-End-Dienst</span><span class="sxs-lookup"><span data-stu-id="03d68-110">Calculator backend service</span></span>  
  
 <span data-ttu-id="03d68-111">Der Fassadendienst ist für die Überprüfung der Anforderung und die Authentifizierung des Aufrufers verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="03d68-111">The façade service is responsible for validating the request and authenticating the caller.</span></span> <span data-ttu-id="03d68-112">Nach erfolgreicher Authentifizierung und Validierung leitet er die Anforderung an den Back-End-Dienst mithilfe des gesteuerten Kommunikationskanals vom Perimeternetzwerk zum internen Netzwerk weiter.</span><span class="sxs-lookup"><span data-stu-id="03d68-112">After successful authentication and validation, it forwards the request to the backend service using the controlled communication channel from the perimeter network to the internal network.</span></span> <span data-ttu-id="03d68-113">Als Teil der weitergeleiteten Anforderung beinhaltet der Fassadendienst Informationen über die Identität des Aufrufers. So kann der Back-End-Dienst diese Informationen in der Verarbeitung verwenden.</span><span class="sxs-lookup"><span data-stu-id="03d68-113">As a part of the forwarded request, the façade service includes information about the caller's identity so that the backend service can use this information in its processing.</span></span> <span data-ttu-id="03d68-114">Die Identität des Aufrufers wird mit einem `Username` -Sicherheitstoken im Nachrichten- `Security` -Header gesendet.</span><span class="sxs-lookup"><span data-stu-id="03d68-114">The caller's identity is transmitted using a `Username` security token inside the message `Security` header.</span></span> <span data-ttu-id="03d68-115">Im Beispiel wird die WCF-Sicherheitsinfrastruktur verwendet, um diese Informationen aus dem-Header zu übertragen und zu extrahieren `Security` .</span><span class="sxs-lookup"><span data-stu-id="03d68-115">The sample uses the WCF security infrastructure to transmit and extract this information from the `Security` header.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="03d68-116">Der Back-End-Dienst vertraut darauf, dass der Fassadendienst den Aufrufer authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="03d68-116">The backend service trusts the façade service to authenticate the caller.</span></span> <span data-ttu-id="03d68-117">Daher authentifiziert der Back-End-Dienst den Aufrufer nicht erneut, sondern nutzt die Identitätsinformationen, die vom Fassadendienst in der weitergeleiteten Anforderung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="03d68-117">Because of this, the backend service does not authenticate the caller again; it uses the identity information provided by the façade service in the forwarded request.</span></span> <span data-ttu-id="03d68-118">Aufgrund dieser Vertrauensbeziehung muss der Back-End-Dienst den Fassadendienst authentifizieren, um sicherzustellen, dass die weitergeleitete Nachricht von einer vertrauenswürdigen Quelle stammt, in diesem Fall vom Fassadendienst.</span><span class="sxs-lookup"><span data-stu-id="03d68-118">Because of this trust relationship, the backend service must authenticate the façade service to ensure that the forwarded message comes from a trusted source - in this case, the façade service.</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="03d68-119">Implementierung</span><span class="sxs-lookup"><span data-stu-id="03d68-119">Implementation</span></span>  

 <span data-ttu-id="03d68-120">Es gibt zwei Kommunikationspfade in diesem Beispiel.</span><span class="sxs-lookup"><span data-stu-id="03d68-120">There are two communication paths in this sample.</span></span> <span data-ttu-id="03d68-121">Der erste Kommunikationspfad besteht zwischen dem Client und dem Fassadendienst, der zweite zwischen dem Fassadendienst und dem Back-End-Dienst.</span><span class="sxs-lookup"><span data-stu-id="03d68-121">First is between the client and the façade service, the second is between the façade service and the backend service.</span></span>  
  
### <a name="communication-path-between-client-and-faade-service"></a><span data-ttu-id="03d68-122">Kommunikationspfad zwischen Client und Fassadendienst</span><span class="sxs-lookup"><span data-stu-id="03d68-122">Communication Path between Client and Façade Service</span></span>  

 <span data-ttu-id="03d68-123">Der Kommunikationspfad zwischen Client und Fassadendienst nutzt `wsHttpBinding` mit einem `UserName` -Clientanmeldeinformationstyp.</span><span class="sxs-lookup"><span data-stu-id="03d68-123">The client to the façade service communication path uses `wsHttpBinding` with a `UserName` client credential type.</span></span> <span data-ttu-id="03d68-124">Dies bedeutet, dass der Client Benutzername und Kennwort für die Authentifizierung zum Fassadendienst nutzt und der Fassadendienst die X.509-Zertifizierung für die Authentifizierung zum Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="03d68-124">This means that the client uses username and password to authenticate to the façade service and the façade service uses X.509 certificate to authenticate to the client.</span></span> <span data-ttu-id="03d68-125">Die Bindungskonfiguration sieht wie das folgende Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="03d68-125">The binding configuration looks like the following example.</span></span>  
  
```xml  
<bindings>  
  <wsHttpBinding>  
    <binding name="Binding1">  
      <security mode="Message">  
        <message clientCredentialType="UserName"/>  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="03d68-126">Der Fassadendienst authentifiziert den Aufrufer mithilfe benutzerdefinierter `UserNamePasswordValidator` -Implementierung.</span><span class="sxs-lookup"><span data-stu-id="03d68-126">The façade service authenticates the caller using custom `UserNamePasswordValidator` implementation.</span></span> <span data-ttu-id="03d68-127">Zu Demonstrationszwecken stellt die Authentifizierung nur sicher, dass der Benutzername des Aufrufers zum vorgelegten Kennwort passt.</span><span class="sxs-lookup"><span data-stu-id="03d68-127">For demonstration purposes, the authentication only ensures that the caller's username matches the presented password.</span></span> <span data-ttu-id="03d68-128">In realen Situationen wird der Benutzer wahrscheinlich mithilfe von Active Directory oder einem benutzerdefinierten ASP.NET-Mitgliedschaftsanbieter authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="03d68-128">In the real world situation, the user is probably authenticated using Active Directory or custom ASP.NET Membership provider.</span></span> <span data-ttu-id="03d68-129">Die Implementierung des Validierungssteuerelements befindet sich in der Datei `FacadeService.cs` .</span><span class="sxs-lookup"><span data-stu-id="03d68-129">The validator implementation resides in `FacadeService.cs` file.</span></span>  
  
```csharp  
public class MyUserNamePasswordValidator : UserNamePasswordValidator  
{  
    public override void Validate(string userName, string password)  
    {  
        // check that username matches password  
        if (null == userName || userName != password)  
        {  
            Console.WriteLine("Invalid username or password");  
            throw new SecurityTokenValidationException(  
                       "Invalid username or password");  
        }  
    }  
}  
```  
  
 <span data-ttu-id="03d68-130">Das benutzerdefinierte Validierungssteuerelement ist so konfiguriert, dass es innerhalb des `serviceCredentials` -Verhaltens in der Konfigurationsdatei des Fassadendiensts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="03d68-130">The custom validator is configured to be used inside the `serviceCredentials` behavior in the façade service configuration file.</span></span> <span data-ttu-id="03d68-131">Dieses Verhalten wird darüber hinaus verwendet, um das X.509-Zertifikat des Diensts zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="03d68-131">This behavior is also used to configure the service's X.509 certificate.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="FacadeServiceBehavior">  
      <!--The serviceCredentials behavior allows you to define -->  
      <!--a service certificate. -->  
      <!--A service certificate is used by the service to  -->  
      <!--authenticate itself to its clients and to provide  -->  
      <!--message protection. -->  
      <!--This configuration references the "localhost"  -->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate
               findValue="localhost"
               storeLocation="LocalMachine"
               storeName="My"
               x509FindType="FindBySubjectName" />  
        <userNameAuthentication userNamePasswordValidationMode="Custom"  
            customUserNamePasswordValidatorType=  
           "Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator,  
            FacadeService"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
### <a name="communication-path-between-faade-service-and-backend-service"></a><span data-ttu-id="03d68-132">Kommunikationspfad zwischen Fassadendienst und Back-End-Dienst</span><span class="sxs-lookup"><span data-stu-id="03d68-132">Communication Path between Façade Service and Backend Service</span></span>  

 <span data-ttu-id="03d68-133">Der Kommunikationspfad zwischen Fassadendienst und Back-End-Dienst nutzt die `customBinding` , die aus mehreren Bindungselementen besteht.</span><span class="sxs-lookup"><span data-stu-id="03d68-133">The façade service to the backend service communication path uses a `customBinding` that consists of several binding elements.</span></span> <span data-ttu-id="03d68-134">Diese Bindung erfüllt zwei Zwecke.</span><span class="sxs-lookup"><span data-stu-id="03d68-134">This binding accomplishes two things.</span></span> <span data-ttu-id="03d68-135">Sie authentifiziert den Fassadendienst und den Back-End-Dienst, um sicherzustellen, dass die Kommunikation sicher ist und aus einer vertrauenswürdigen Quelle stammt.</span><span class="sxs-lookup"><span data-stu-id="03d68-135">It authenticates the façade service and backend service to ensure that the communication is secure and is coming from a trusted source.</span></span> <span data-ttu-id="03d68-136">Darüber hinaus überträgt sie die Identität des ursprünglichen Aufrufers im `Username` -Sicherheitstoken.</span><span class="sxs-lookup"><span data-stu-id="03d68-136">Additionally, it also transmits the initial caller's identity inside the `Username` security token.</span></span> <span data-ttu-id="03d68-137">In diesem Fall wird nur der Benutzername des ursprünglichen Aufrufers zum Back-End-Dienst übertragen. Das Kennwort ist in der Nachricht nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="03d68-137">In this case, only the initial caller's username is transmitted to the backend service, the password is not included in the message.</span></span> <span data-ttu-id="03d68-138">Grund hierfür ist, dass der Back-End-Dienst dem Fassadendienst die Authentifizierung des Aufrufers anvertraut, bevor die Anforderung weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="03d68-138">This is because the backend service trusts the façade service to authenticate the caller before forwarding the request to it.</span></span> <span data-ttu-id="03d68-139">Da der Fassadendienst sich selbst gegenüber dem Back-End-Dienst authentifiziert, kann der Back-End-Dienst die in der weitergeleiteten Anforderung enthaltenen Informationen als vertrauenswürdig einstufen.</span><span class="sxs-lookup"><span data-stu-id="03d68-139">Because the façade service authenticates itself to the backend service, the backend service can trust the information contained in the forwarded request.</span></span>  
  
 <span data-ttu-id="03d68-140">Im Folgenden ist die Bindungskonfiguration für diesen Kommunikationspfad dargestellt.</span><span class="sxs-lookup"><span data-stu-id="03d68-140">The following is the binding configuration for this communication path.</span></span>  
  
```xml  
<bindings>  
  <customBinding>  
    <binding name="ClientBinding">  
      <security authenticationMode="UserNameOverTransport"/>  
      <windowsStreamSecurity/>  
      <tcpTransport/>  
    </binding>  
  </customBinding>  
</bindings>  
```  
  
 <span data-ttu-id="03d68-141">Das [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) Bindungs Element übernimmt die Übertragung und Extraktion des ersten Benutzernamens des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="03d68-141">The [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) binding element takes care of the initial caller's username transmission and extraction.</span></span> <span data-ttu-id="03d68-142">[\<windowsStreamSecurity>](../../configure-apps/file-schema/wcf/windowsstreamsecurity.md)Und [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) kümmern sich um die Authentifizierung von Fassaden-und Back-End-Diensten und Nachrichten Schutz.</span><span class="sxs-lookup"><span data-stu-id="03d68-142">The [\<windowsStreamSecurity>](../../configure-apps/file-schema/wcf/windowsstreamsecurity.md) and [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) take care of authenticating façade and backend services and message protection.</span></span>  
  
 <span data-ttu-id="03d68-143">Um die Anforderung weiterzuleiten, muss die Fassaden Dienst Implementierung den Benutzernamen des ursprünglichen Aufrufers bereitstellen, damit die WCF-Sicherheitsinfrastruktur dies in die weitergeleitete Nachricht versetzen kann.</span><span class="sxs-lookup"><span data-stu-id="03d68-143">To forward the request, the façade service implementation must provide the initial caller's username so that WCF security infrastructure can place this into the forwarded message.</span></span> <span data-ttu-id="03d68-144">Der Benutzername des ursprünglichen Aufrufers wird in der Fassadendienstimplementierung bereitgestellt, indem er in der `ClientCredentials` -Eigenschaft auf der Clientproxyinstanz festgelegt wird, die der Fassadendienst für die Kommunikation mit dem Back-End-Dienst nutzt.</span><span class="sxs-lookup"><span data-stu-id="03d68-144">The initial caller's username is provided in the façade service implementation by setting it in the `ClientCredentials` property on the client proxy instance that façade service uses to communicate with the backend service.</span></span>  
  
 <span data-ttu-id="03d68-145">Der folgende Code zeigt, wie die `GetCallerIdentity` -Methode auf dem Fassadendienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="03d68-145">The following code shows how `GetCallerIdentity` method is implemented on the façade service.</span></span> <span data-ttu-id="03d68-146">Andere Methoden verwenden das gleiche Muster.</span><span class="sxs-lookup"><span data-stu-id="03d68-146">Other methods use the same pattern.</span></span>  
  
```csharp  
public string GetCallerIdentity()  
{  
    CalculatorClient client = new CalculatorClient();  
    client.ClientCredentials.UserName.UserName = ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    string result = client.GetCallerIdentity();  
    client.Close();  
    return result;  
}  
```  
  
 <span data-ttu-id="03d68-147">Wie bereits im vorherigen Code gezeigt, ist das Kennwort nicht für die `ClientCredentials` -Eigenschaft festgelegt, sondern nur der Benutzername.</span><span class="sxs-lookup"><span data-stu-id="03d68-147">As shown in the previous code, the password is not set on the `ClientCredentials` property, only the username is set.</span></span> <span data-ttu-id="03d68-148">Die WCF-Sicherheitsinfrastruktur erstellt in diesem Fall ein Benutzernamen-Sicherheits Token ohne Kennwort. Dies ist genau das, was in diesem Szenario erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="03d68-148">WCF security infrastructure creates a username security token without a password in this case, which is exactly what is required in this scenario.</span></span>  
  
 <span data-ttu-id="03d68-149">Auf dem Back-End-Dienst müssen die Informationen authentifiziert werden, die im Benutzernamen-Sicherheitstoken enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="03d68-149">On the backend service, the information contained in the username security token must be authenticated.</span></span> <span data-ttu-id="03d68-150">Standardmäßig versucht die WCF-Sicherheit, den Benutzer mit dem bereitgestellten Kennwort einem Windows-Konto zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="03d68-150">By default, WCF security attempts to map the user to a Windows account using the provided password.</span></span> <span data-ttu-id="03d68-151">In diesem Fall ist kein Kennwort angegeben, und der Back-End-Dienst muss den Benutzernamen nicht authentifizieren, da die Authentifizierung bereits vom Fassadendienst durchgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="03d68-151">In this case, there is no password provided and the backend service is not required to authenticate the username because the authentication was already performed by the façade service.</span></span> <span data-ttu-id="03d68-152">Um diese Funktionalität in WCF zu implementieren, wird ein benutzerdefiniertes `UserNamePasswordValidator` bereitgestellt, das nur erzwingt, dass ein Benutzername im Token angegeben ist, und keine zusätzliche Authentifizierung ausführt.</span><span class="sxs-lookup"><span data-stu-id="03d68-152">To implement this functionality in WCF, a custom `UserNamePasswordValidator` is provided that only enforces that a username is specified in the token and does not perform any additional authentication.</span></span>  
  
```csharp  
public class MyUserNamePasswordValidator : UserNamePasswordValidator  
{  
    public override void Validate(string userName, string password)  
    {  
        // Ignore the password because it is empty,
        // we trust the facade service to authenticate the client.  
        // Accept the username information here so that the
        // application gets access to it.  
        if (null == userName)  
        {  
            Console.WriteLine("Invalid username");  
            throw new
             SecurityTokenValidationException("Invalid username");  
        }  
    }  
}  
```  
  
 <span data-ttu-id="03d68-153">Das benutzerdefinierte Validierungssteuerelement ist so konfiguriert, dass es innerhalb des `serviceCredentials` -Verhaltens in der Konfigurationsdatei des Fassadendiensts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="03d68-153">The custom validator is configured to be used inside the `serviceCredentials` behavior in the façade service configuration file.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="BackendServiceBehavior">  
      <serviceCredentials>  
        <userNameAuthentication userNamePasswordValidationMode="Custom"  
           customUserNamePasswordValidatorType=  
          "Microsoft.ServiceModel.Samples.MyUserNamePasswordValidator,
           BackendService"/>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="03d68-154">Zur Extraktion der Benutzernameninformationen und der Informationen über das vertrauenswürdige Fassadendienstkonto nutzt die Back-End-Dienst-Implementierung die `ServiceSecurityContext` -Klasse.</span><span class="sxs-lookup"><span data-stu-id="03d68-154">To extract the username information and information about the trusted façade service account, the backend service implementation uses the `ServiceSecurityContext` class.</span></span> <span data-ttu-id="03d68-155">Im folgenden Codebeispiel wird die Implementierung der `GetCallerIdentity` -Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="03d68-155">The following code shows how the `GetCallerIdentity` method is implemented.</span></span>  
  
```csharp  
public string GetCallerIdentity()  
{  
    // Facade service is authenticated using Windows authentication.  
    //Its identity is accessible.  
    // On ServiceSecurityContext.Current.WindowsIdentity.  
    string facadeServiceIdentityName =
          ServiceSecurityContext.Current.WindowsIdentity.Name;  
  
    // The client name is transmitted using Username authentication on
    //the message level without the password  
    // using a supporting encrypted UserNameToken.  
    // Claims extracted from this supporting token are available in
    // ServiceSecurityContext.Current.AuthorizationContext.ClaimSets
    // collection.  
    string clientName = null;  
    foreach (ClaimSet claimSet in
        ServiceSecurityContext.Current.AuthorizationContext.ClaimSets)  
    {  
        foreach (Claim claim in claimSet)  
        {  
            if (claim.ClaimType == ClaimTypes.Name &&
                                   claim.Right == Rights.Identity)  
            {  
                clientName = (string)claim.Resource;  
                break;  
            }  
        }  
    }  
    if (clientName == null)  
    {  
        // In case there was no UserNameToken attached to the request.  
        // In the real world implementation the service should reject
        // this request.  
        return "Anonymous caller via " + facadeServiceIdentityName;  
    }  
  
    return clientName + " via " + facadeServiceIdentityName;  
}  
```  
  
 <span data-ttu-id="03d68-156">Die Informationen über das Fassadendienstkonto werden mithilfe der `ServiceSecurityContext.Current.WindowsIdentity` -Eigenschaft extrahiert.</span><span class="sxs-lookup"><span data-stu-id="03d68-156">The façade service account information is extracted using the `ServiceSecurityContext.Current.WindowsIdentity` property.</span></span> <span data-ttu-id="03d68-157">Um auf die Informationen über den ursprünglichen Aufrufer zuzugreifen, verwendet der Back-End-Dienst die `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="03d68-157">To access the information about the initial caller the backend service uses the `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` property.</span></span> <span data-ttu-id="03d68-158">Hier wird nach einem `Identity` -Anspruch mit dem Typ `Name`gesucht.</span><span class="sxs-lookup"><span data-stu-id="03d68-158">It looks for an `Identity` claim with a type `Name`.</span></span> <span data-ttu-id="03d68-159">Dieser Anspruch wird automatisch von der WCF-Sicherheitsinfrastruktur aus den Informationen generiert, die im- `Username` Sicherheits Token enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="03d68-159">This claim is automatically generated by WCF security infrastructure from the information contained in the `Username` security token.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="03d68-160">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="03d68-160">Running the sample</span></span>  

 <span data-ttu-id="03d68-161">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="03d68-161">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="03d68-162">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="03d68-162">Press ENTER in the client window to shut down the client.</span></span> <span data-ttu-id="03d68-163">Sie können die EINGABETASTE in den Konsolenfenstern des Fassaden- und Back-End-Diensts drücken, um die Dienste zu schließen.</span><span class="sxs-lookup"><span data-stu-id="03d68-163">You can press ENTER in the façade and backend service console windows to shut down the services.</span></span>  
  
```console  
Username authentication required.  
Provide a valid machine or domain ac  
   Enter username:  
user  
   Enter password:  
****  
user via MyMachine\testaccount  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="03d68-164">Die im Beispiel zu Szenarios mit vertrauenswürdigen Fassaden enthaltene Batchdatei "Setup.bat" ermöglicht es Ihnen, den Server mit einem relevanten Zertifikat zu konfigurieren, damit der Fassadendienst ausgeführt wird, der zertifikatbasierte Sicherheit für die eigene Authentifizierung gegenüber dem Client erfordert.</span><span class="sxs-lookup"><span data-stu-id="03d68-164">The Setup.bat batch file included with the Trusted Facade scenario sample enables you to configure the server with a relevant certificate to run the façade service that requires certificate-based security to authenticate itself to the client.</span></span> <span data-ttu-id="03d68-165">Weitere Informationen finden Sie in der Setupprozedur am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="03d68-165">See the setup procedure at the end of this topic for details.</span></span>  
  
 <span data-ttu-id="03d68-166">Im Folgenden wird eine kurze Übersicht über die verschiedenen Abschnitte der Batchdateien bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="03d68-166">The following provides a brief overview of the different sections of the batch files.</span></span>  
  
- <span data-ttu-id="03d68-167">Erstellen des Serverzertifikats.</span><span class="sxs-lookup"><span data-stu-id="03d68-167">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="03d68-168">Mit den folgenden Zeilen aus der Batchdatei "Setup.bat" wird das zu verwendende Serverzertifikat erstellt.</span><span class="sxs-lookup"><span data-stu-id="03d68-168">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```console  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="03d68-169">Die `%SERVER_NAME%` -Variable gibt den Servernamen an – der Standardwert ist "localhost".</span><span class="sxs-lookup"><span data-stu-id="03d68-169">The `%SERVER_NAME%` variable specifies the server name - the default value is localhost.</span></span> <span data-ttu-id="03d68-170">Das Zertifikat wird im LocalMachine-Speicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="03d68-170">The certificate is stored in the LocalMachine store.</span></span>  
  
- <span data-ttu-id="03d68-171">Installieren des Fassadendienstzertifikats im Speicher für vertrauenswürdige Zertifikate des Clients.</span><span class="sxs-lookup"><span data-stu-id="03d68-171">Installing the façade service's certificate into the client's trusted certificate store.</span></span>  
  
     <span data-ttu-id="03d68-172">Die folgenden Zeilen kopieren das Fassadendienstzertifikat in den Clientspeicher für vertrauenswürdige Personen.</span><span class="sxs-lookup"><span data-stu-id="03d68-172">The following line copies the façade service's certificate into the client trusted people store.</span></span> <span data-ttu-id="03d68-173">Dieser Schritt ist erforderlich, da von "Makecert.exe" generierte Zertifikate nicht implizit vom Clientsystem als vertrauenswürdig eingestuft werden.</span><span class="sxs-lookup"><span data-stu-id="03d68-173">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="03d68-174">Wenn Sie bereits über ein Zertifikat verfügen, das von einem vertrauenswürdigen Clientstammzertifikat stammt (z. B. ein von Microsoft ausgegebenes Zertifikat), ist dieser Schritt zum Füllen des Clientzertifikatspeichers mit dem Serverzertifikat nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="03d68-174">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```console  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="03d68-175">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="03d68-175">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="03d68-176">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="03d68-176">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="03d68-177">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="03d68-177">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="03d68-178">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="03d68-178">To run the sample on the same machine</span></span>  
  
1. <span data-ttu-id="03d68-179">Stellen Sie sicher, dass der Pfad den Ordner enthält, indem sich "Makecert.exe" befindet.</span><span class="sxs-lookup"><span data-stu-id="03d68-179">Ensure that the path includes the folder where Makecert.exe is located.</span></span>  
  
2. <span data-ttu-id="03d68-180">Führen Sie "Setup.bat" im Beispielinstallationsordner aus.</span><span class="sxs-lookup"><span data-stu-id="03d68-180">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="03d68-181">Hiermit werden alle Zertifikate installiert, die zum Ausführen des Beispiels erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="03d68-181">This installs all the certificates required for running the sample.</span></span>  
  
3. <span data-ttu-id="03d68-182">Starten Sie "BackendService.exe" aus dem Verzeichnis "\BackendService\bin" in einem separaten Konsolenfenster</span><span class="sxs-lookup"><span data-stu-id="03d68-182">Launch the BackendService.exe from \BackendService\bin directory in a separate console window</span></span>  
  
4. <span data-ttu-id="03d68-183">Starten Sie "FacadeService.exe" aus dem Verzeichnis "\FacadeService\bin" in einem separaten Konsolenfenster</span><span class="sxs-lookup"><span data-stu-id="03d68-183">Launch the FacadeService.exe from \FacadeService\bin directory in a separate console window</span></span>  
  
5. <span data-ttu-id="03d68-184">Starten Sie Client.exe aus dem Ordner \client\bin.</span><span class="sxs-lookup"><span data-stu-id="03d68-184">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="03d68-185">In der Clientkonsolenanwendung wird Clientaktivität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="03d68-185">Client activity is displayed on the client console application.</span></span>  
  
6. <span data-ttu-id="03d68-186">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="03d68-186">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="03d68-187">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="03d68-187">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="03d68-188">Führen Sie Cleanup.bat im Beispielordner aus, nachdem Sie das Beispiel fertig ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="03d68-188">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="03d68-189">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="03d68-189">The samples may already be installed on your machine.</span></span> <span data-ttu-id="03d68-190">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="03d68-190">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="03d68-191">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="03d68-191">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="03d68-192">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="03d68-192">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\TrustedFacade`
