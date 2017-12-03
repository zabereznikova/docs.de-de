---
title: "Vorbereitungen für Windows Communication Foundation: Einfachere Migration in der Zukunft"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2ecac6917d47604aa66e9cdc0d845e76ad2de5d2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a><span data-ttu-id="13338-102">Vorbereitungen für Windows Communication Foundation: Einfachere Migration in der Zukunft</span><span class="sxs-lookup"><span data-stu-id="13338-102">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>
<span data-ttu-id="13338-103">Berücksichtigen Sie die vorherigen sowie die folgenden Empfehlungen, um eine einfachere Migration neuer ASP.NET-Anwendungen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="13338-103">To ensure an easier future migration of new ASP.NET applications to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], follow the preceding recommendations as well as the following recommendations.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="13338-104">Protokolle</span><span class="sxs-lookup"><span data-stu-id="13338-104">Protocols</span></span>  
 <span data-ttu-id="13338-105">Deaktivieren Sie die SOAP 1.2-Unterstützung von ASP.NET 2.0:</span><span class="sxs-lookup"><span data-stu-id="13338-105">Disable ASP.NET 2.0’s support for SOAP 1.2:</span></span>  
  
```xml  
<configuration>  
     <system.web>  
      <webServices >  
          <protocols>  
           <remove name="HttpSoap12"/>  
          </protocols>    
      </webServices>  
     </system.web>   
</configuration>  
```  
  
 <span data-ttu-id="13338-106">Dieser Schritt empfiehlt sich, da Nachrichten für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit unterschiedlichen Protokollen (wie SOAP 1.1 und SOAP 1.2) konform sein müssen, damit verschiedene Endpunkte verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="13338-106">Doing so is advisable because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires messages conforming to different protocols, like SOAP 1.1 and SOAP 1.2, to go by using different endpoints.</span></span> <span data-ttu-id="13338-107">Sieht die Konfiguration eines ASP.NET 2.0-Webdiensts sowohl die Unterstützung von SOAP 1.1 als auch von SOAP 1.2 vor (entspricht der Standardkonfiguration), ist keine Vorwärtsmigration an einen einzelnen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunkt an der ursprünglichen Adresse möglich, die mit allen vorhandenen Clients des ASP.NET-Webdiensts kompatibel wäre.</span><span class="sxs-lookup"><span data-stu-id="13338-107">If an ASP.NET 2.0 Web service is configured to support both SOAP 1.1 and SOAP 1.2, which is the default configuration, then it cannot be migrated forward to a single [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint at the original address that would be certainly be compatible with all of the ASP.NET Web service’s existing clients.</span></span> <span data-ttu-id="13338-108">Auch das Auswählen von SOAP 1.2 anstelle von 1.1 hat eine stärkere Einschränkung der Clients für den Dienst zur Folge.</span><span class="sxs-lookup"><span data-stu-id="13338-108">Also choosing SOAP 1.2 instead of 1.1 will more severely restrict the clientele of the service.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="13338-109">Dienstentwicklung</span><span class="sxs-lookup"><span data-stu-id="13338-109">Service Development</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="13338-110"> ermöglicht das Definieren von Dienstverträgen durch Anwenden des <xref:System.ServiceModel.ServiceContractAttribute> auf Schnittstellen oder Klassen.</span><span class="sxs-lookup"><span data-stu-id="13338-110"> allows you to define service contracts by applying the <xref:System.ServiceModel.ServiceContractAttribute> either to interfaces or to classes.</span></span> <span data-ttu-id="13338-111">Es empfiehlt sich, das Attribut auf eine Schnittstelle (und nicht auf eine Klasse) anzuwenden, da hierdurch die Definition eines Vertrags erstellt wird, der von einer Reihe von Klassen auf unterschiedlichste Weise implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="13338-111">It is recommended to apply the attribute to an interface rather than to a class, because doing so creates a definition of a contract that can be variously implemented by any number of classes.</span></span> <span data-ttu-id="13338-112">Von ASP.NET 2.0 wird die Option zum Anwenden des <xref:System.Web.Services.WebService>-Attributs sowohl für Schnittstellen als auch für Klassen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="13338-112">ASP.NET 2.0 supports the option of applying the <xref:System.Web.Services.WebService> attribute to interfaces as well as classes.</span></span> <span data-ttu-id="13338-113">Wie jedoch bereits angesprochen: In ASP.NET 2.0 ist ein Fehler vorhanden, durch den der Namespace-Parameter des <xref:System.Web.Services.WebService>-Attributs keine Wirkung zeigt, wenn das Attribut auf eine Schnittstelle (und nicht auf eine Klasse) angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="13338-113">However, as mentioned already, there is a defect in ASP.NET 2.0, by which the Namespace parameter of the <xref:System.Web.Services.WebService> attribute has no effect when that attribute is applied to an interface rather than a class.</span></span> <span data-ttu-id="13338-114">Es empfiehlt sich im Allgemeinen, den Standardwert des Namespace eines Diensts (http://tempuri.org) mithilfe des Namespace-Parameters des <xref:System.Web.Services.WebService>-Attributs zu ändern. Dabei sollten ASP.NET-Webdienste auch weiterhin durch Anwenden des <xref:System.ServiceModel.ServiceContractAttribute>-Attributs auf Schnittstellen ODER Klassen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="13338-114">Since it is generally advisable to modify the namespace of a service from the default value, http://tempuri.org, using the Namespace parameter of the <xref:System.Web.Services.WebService> attribute, one should continue defining ASP.NET Web Services by applying the <xref:System.ServiceModel.ServiceContractAttribute> attribute either to interfaces or to classes.</span></span>  
  
-   <span data-ttu-id="13338-115">Verwenden Sie in den Methoden zum Definieren dieser Schnittstellen möglichst wenig Code.</span><span class="sxs-lookup"><span data-stu-id="13338-115">Have as little code as possible in the methods by which those interfaces are defined.</span></span> <span data-ttu-id="13338-116">Konfigurieren Sie sie so, dass deren Aufgaben an andere Klassen delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="13338-116">Have them delegate their work to other classes.</span></span> <span data-ttu-id="13338-117">Umfangreiche Aufgaben neuer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensttypen können dann ebenfalls an diese Klassen delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="13338-117">New [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service types could then also delegate their substantive work to those classes.</span></span>  
  
-   <span data-ttu-id="13338-118">Geben Sie explizite Namen für die Vorgänge eines Diensts an. Verwenden Sie hierfür den `MessageName`-Parameter des <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="13338-118">Provide explicit names for the operations of a service using the `MessageName` parameter of the <xref:System.Web.Services.WebMethodAttribute>.</span></span>  
  
    ```  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     <span data-ttu-id="13338-119">Dieser Schritt ist wichtig, da sich die Standardnamen für Vorgänge in ASP.NET von den Standardnamen aus [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="13338-119">Doing so is important, because the default names for operations in ASP.NET are different from the default names supplied by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="13338-120">Durch Angeben expliziter Namen müssen Sie sich nicht auf die Standardnamen verlassen.</span><span class="sxs-lookup"><span data-stu-id="13338-120">By providing explicit names, you avoid relying on the default ones.</span></span>  
  
-   <span data-ttu-id="13338-121">Implementieren Sie keine ASP.NET-Webdienstvorgänge mit polymorphen Methoden, da dies von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="13338-121">Do not implement ASP.NET Web service operations with polymorphic methods, because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not support implementing operations with polymorphic methods.</span></span>  
  
-   <span data-ttu-id="13338-122">Verwenden Sie <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>, um explizite Werte für SOAPAction-HTTP-Header anzugeben, durch die HTTP-Anforderungen an Methoden geroutet werden.</span><span class="sxs-lookup"><span data-stu-id="13338-122">Use the <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> to provide explicit values for the SOAPAction HTTP headers by which HTTP requests will be routed to methods.</span></span>  
  
    ```  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     <span data-ttu-id="13338-123">Mit dieser Vorgehensweise müssen Sie sich nicht darauf verlassen, dass die standardmäßig von ASP.NET und [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendeten SOAPAction-Werte übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="13338-123">Taking this approach will circumvent having to rely on the default SOAPAction values used by ASP.NET and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] being the same.</span></span>  
  
-   <span data-ttu-id="13338-124">Verwenden Sie möglichst keine SOAP-Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="13338-124">Avoid using SOAP extensions.</span></span> <span data-ttu-id="13338-125">Ist die Verwendung von SOAP-Erweiterungen erforderlich, überprüfen Sie, ob es sich beim geplanten Einsatzzweck möglicherweise um eine Funktion handelt, die bereits von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="13338-125">If SOAP extensions are required, then determine whether the purpose for which they are being considered is a feature that is already provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="13338-126">Ist dies der Fall, sollten Sie die Entscheidung, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nicht anzuwenden, nochmals überdenken.</span><span class="sxs-lookup"><span data-stu-id="13338-126">If that is indeed the case, then reconsider the choice to not adopt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] right away.</span></span>  
  
## <a name="state-management"></a><span data-ttu-id="13338-127">Zustandsverwaltung</span><span class="sxs-lookup"><span data-stu-id="13338-127">State Management</span></span>  
 <span data-ttu-id="13338-128">Verzichten Sie nach Möglichkeit darauf, Zustände in Diensten verwalten zu müssen.</span><span class="sxs-lookup"><span data-stu-id="13338-128">Avoid having to maintain state in services.</span></span> <span data-ttu-id="13338-129">Die Zustandsverwaltung neigt dazu, die Skalierbarkeit einer Anwendung zu beeinträchtigen. Darüber hinaus unterscheiden sich die Zustandsverwaltungsmechanismen von ASP.NET und [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] deutlich, obgleich die ASP.NET-Mechanismen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] im ASP.NET-Kompatibilitätsmodus unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="13338-129">Not only does maintaining state tend to compromise the scalability of an application, but the state management mechanisms of ASP.NET and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are very different, although [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does support the ASP.NET mechanisms in ASP.NET compatibility mode.</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="13338-130">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="13338-130">Exception Handling</span></span>  
 <span data-ttu-id="13338-131">Entwerfen Sie beim Ausarbeiten der Strukturen von Datentypen, die von einem Dienst gesendet und empfangen werden sollen, auch Strukturen für die verschiedenen Ausnahmetypen, die in einem an einen Client zu übermittelnden Dienst auftreten können.</span><span class="sxs-lookup"><span data-stu-id="13338-131">In designing the structures of the data types to be sent and received by a service, also design structures to represent the various types of exceptions that might occur within a service that one might wish to convey to a client.</span></span>  
  
```  
[Serializable]  
[XmlRoot(  
     Namespace="ExplicitNamespace", IsNullable=true)]  
    public partial class AnticipatedException {  
  
     private string anticipatedExceptionInformationField;  
  
     public string AnticipatedExceptionInformation {  
      get {  
          return this.anticipatedExceptionInformationField;  
          }  
      set {  
          this.anticipatedExceptionInformationField = value;  
          }  
     }  
}  
```  
  
 <span data-ttu-id="13338-132">Konfigurieren Sie Klassen dieser Art so, dass sie eigenständig zu XML serialisiert werden können:</span><span class="sxs-lookup"><span data-stu-id="13338-132">Give such classes the ability to serialize themselves to XML:</span></span>  
  
```  
public XmlNode ToXML()  
{  
     XmlSerializer serializer = new XmlSerializer(  
      typeof(AnticipatedException));  
     MemoryStream memoryStream = new MemoryStream();  
     XmlTextWriter writer = new XmlTextWriter(  
     memoryStream, UnicodeEncoding.UTF8);  
     serializer.Serialize(writer, this);  
     XmlDocument document = new XmlDocument();  
     document.LoadXml(new string(  
     UnicodeEncoding.UTF8.GetChars(  
     memoryStream.GetBuffer())).Trim());  
    return document.DocumentElement;  
}  
```  
  
 <span data-ttu-id="13338-133">Die Klassen können anschließend zum Angeben der Details für explizit ausgelöste <xref:System.Web.Services.Protocols.SoapException>-Instanzen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="13338-133">The classes can then be used to provide the details for explicitly thrown <xref:System.Web.Services.Protocols.SoapException> instances:</span></span>  
  
```  
AnctipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 <span data-ttu-id="13338-134">Diese Ausnahmeklassen können problemlos mit der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.ServiceModel.FaultException%601>-Klasse wiederverwendet werden, um eine neue `FaultException<AnticipatedException>(anticipatedException);` auszulösen.</span><span class="sxs-lookup"><span data-stu-id="13338-134">These exception classes will be readily reusable with the[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.ServiceModel.FaultException%601> class to throw a new `FaultException<AnticipatedException>(anticipatedException);`</span></span>  
  
## <a name="security"></a><span data-ttu-id="13338-135">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="13338-135">Security</span></span>  
 <span data-ttu-id="13338-136">Der folgende Abschnitt enthält einige Sicherheitsempfehlungen:</span><span class="sxs-lookup"><span data-stu-id="13338-136">The following are some security recommendations.</span></span>  
  
-   <span data-ttu-id="13338-137">Verwenden Sie nach Möglichkeit keine ASP.NET 2.0-Profile, da durch deren Verwendung die Verwendung des ASP.NET-Integrationsmodus eingeschränkt wird, nachdem der Dienst zu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] migriert wurde.</span><span class="sxs-lookup"><span data-stu-id="13338-137">Avoid using ASP.NET 2.0 Profiles, as using them would restrict the use of ASP.NET Integration Mode if the service was migrated to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
-   <span data-ttu-id="13338-138">Verwenden Sie möglichst keine ACLs zum Steuern des Dienstzugriffs, da von ASP.NET-Webdiensten ACLs unter Verwendung von Internetinformationsdienste (IIS) unterstützt werden, von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dagegen nicht. Der Grund: IIS ist für das Hosten von ASP.NET-Webdiensten erforderlich, wohingegen WCF nicht unbedingt in IIS gehostet werden muss.</span><span class="sxs-lookup"><span data-stu-id="13338-138">Avoid using ACLs to control access to services, as ASP.NET Web services supports ACLs using Internet Information Services (IIS), [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not—because ASP.NET Web services depend on IIS for hosting, and WCF does not necessarily have to be hosted in IIS.</span></span>  
  
-   <span data-ttu-id="13338-139">Verwenden Sie ASP.NET 2.0-Rollenanbieter zum Autorisieren des Zugriffs auf die Ressource eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="13338-139">Do consider using ASP.NET 2.0 Role Providers for authorizing access to the resources of a service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13338-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13338-140">See Also</span></span>  
 [<span data-ttu-id="13338-141">Vorbereitungen für Windows Communication Foundation: einfachere Integration in der Zukunft</span><span class="sxs-lookup"><span data-stu-id="13338-141">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
