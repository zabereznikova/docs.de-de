---
title: 'Vorbereitungen für Windows Communication Foundation: einfachere Integration in der Zukunft'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: 4492626c2cb0958f8aa79fa2b511d9aa9e90b16a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769511"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a><span data-ttu-id="abbc9-102">Vorbereitungen für Windows Communication Foundation: einfachere Integration in der Zukunft</span><span class="sxs-lookup"><span data-stu-id="abbc9-102">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>
<span data-ttu-id="abbc9-103">Führen Sie die vorherigen Empfehlungen als auch die folgenden Empfehlungen, um sicherzustellen, dass eine einfachere Migration neuer ASP.NET-Anwendungen zu WCF.</span><span class="sxs-lookup"><span data-stu-id="abbc9-103">To ensure an easier future migration of new ASP.NET applications to WCF, follow the preceding recommendations as well as the following recommendations.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="abbc9-104">Protokolle</span><span class="sxs-lookup"><span data-stu-id="abbc9-104">Protocols</span></span>  
 <span data-ttu-id="abbc9-105">Deaktivieren Sie die SOAP 1.2-Unterstützung von ASP.NET 2.0:</span><span class="sxs-lookup"><span data-stu-id="abbc9-105">Disable ASP.NET 2.0’s support for SOAP 1.2:</span></span>  
  
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
  
 <span data-ttu-id="abbc9-106">Auf diese Weise ist ratsam, da WCF Nachrichten an verschiedene Protokolle, wie SOAP 1.1 und SOAP 1.2 entsprechen verschiedene Endpunkte erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="abbc9-106">Doing so is advisable because WCF requires messages conforming to different protocols, like SOAP 1.1 and SOAP 1.2, to go by using different endpoints.</span></span> <span data-ttu-id="abbc9-107">Wenn eine ASP.NET 2.0 Web-Dienst für die Unterstützung sowohl SOAP 1.1- und SOAP 1.2, die in der Standardkonfiguration ist er kann nicht konfiguriert ist Weiterleitung mit einem einzigen WCF-Endpunkt, an der ursprünglichen Adresse migriert, das wäre mit aller der ASP.NET Web kompatibel sein vorhandene Clients des Diensts.</span><span class="sxs-lookup"><span data-stu-id="abbc9-107">If an ASP.NET 2.0 Web service is configured to support both SOAP 1.1 and SOAP 1.2, which is the default configuration, then it cannot be migrated forward to a single WCF endpoint at the original address that would be certainly be compatible with all of the ASP.NET Web service’s existing clients.</span></span> <span data-ttu-id="abbc9-108">Auch das Auswählen von SOAP 1.2 anstelle von 1.1 hat eine stärkere Einschränkung der Clients für den Dienst zur Folge.</span><span class="sxs-lookup"><span data-stu-id="abbc9-108">Also choosing SOAP 1.2 instead of 1.1 will more severely restrict the clientele of the service.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="abbc9-109">Dienstentwicklung</span><span class="sxs-lookup"><span data-stu-id="abbc9-109">Service Development</span></span>  
 <span data-ttu-id="abbc9-110">WCF ermöglicht es Ihnen, Definieren von Dienstverträgen durch Anwenden der <xref:System.ServiceModel.ServiceContractAttribute> auf Schnittstellen oder Klassen.</span><span class="sxs-lookup"><span data-stu-id="abbc9-110">WCF allows you to define service contracts by applying the <xref:System.ServiceModel.ServiceContractAttribute> either to interfaces or to classes.</span></span> <span data-ttu-id="abbc9-111">Es empfiehlt sich, das Attribut auf eine Schnittstelle (und nicht auf eine Klasse) anzuwenden, da hierdurch die Definition eines Vertrags erstellt wird, der von einer Reihe von Klassen auf unterschiedlichste Weise implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="abbc9-111">It is recommended to apply the attribute to an interface rather than to a class, because doing so creates a definition of a contract that can be variously implemented by any number of classes.</span></span> <span data-ttu-id="abbc9-112">Von ASP.NET 2.0 wird die Option zum Anwenden des <xref:System.Web.Services.WebService>-Attributs sowohl für Schnittstellen als auch für Klassen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="abbc9-112">ASP.NET 2.0 supports the option of applying the <xref:System.Web.Services.WebService> attribute to interfaces as well as classes.</span></span> <span data-ttu-id="abbc9-113">Wie jedoch bereits angesprochen: In ASP.NET 2.0 ist ein Fehler vorhanden, durch den der Namespace-Parameter des <xref:System.Web.Services.WebService>-Attributs keine Wirkung zeigt, wenn das Attribut auf eine Schnittstelle (und nicht auf eine Klasse) angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="abbc9-113">However, as mentioned already, there is a defect in ASP.NET 2.0, by which the Namespace parameter of the <xref:System.Web.Services.WebService> attribute has no effect when that attribute is applied to an interface rather than a class.</span></span> <span data-ttu-id="abbc9-114">Da es im Allgemeinen ratsam, so ändern Sie den Namespace eines Diensts aus der Standardwert ist `http://tempuri.org`, mit dem Namespace-Parameter von der <xref:System.Web.Services.WebService> -Attribut, eine sollten weiterhin Definieren von ASP.NET Web Services durch Anwenden der <xref:System.ServiceModel.ServiceContractAttribute> Attribut entweder auf Schnittstellen oder Klassen.</span><span class="sxs-lookup"><span data-stu-id="abbc9-114">Since it is generally advisable to modify the namespace of a service from the default value, `http://tempuri.org`, using the Namespace parameter of the <xref:System.Web.Services.WebService> attribute, one should continue defining ASP.NET Web Services by applying the <xref:System.ServiceModel.ServiceContractAttribute> attribute either to interfaces or to classes.</span></span>  
  
- <span data-ttu-id="abbc9-115">Verwenden Sie in den Methoden zum Definieren dieser Schnittstellen möglichst wenig Code.</span><span class="sxs-lookup"><span data-stu-id="abbc9-115">Have as little code as possible in the methods by which those interfaces are defined.</span></span> <span data-ttu-id="abbc9-116">Konfigurieren Sie sie so, dass deren Aufgaben an andere Klassen delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="abbc9-116">Have them delegate their work to other classes.</span></span> <span data-ttu-id="abbc9-117">Neue Typen von WCF-Dienst können dann auch substanziellen Arbeit an diese Klassen delegieren.</span><span class="sxs-lookup"><span data-stu-id="abbc9-117">New WCF service types could then also delegate their substantive work to those classes.</span></span>  
  
- <span data-ttu-id="abbc9-118">Geben Sie explizite Namen für die Vorgänge eines Diensts an. Verwenden Sie hierfür den `MessageName`-Parameter des <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="abbc9-118">Provide explicit names for the operations of a service using the `MessageName` parameter of the <xref:System.Web.Services.WebMethodAttribute>.</span></span>  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     <span data-ttu-id="abbc9-119">Auf diese Weise ist wichtig, da die Standardnamen für Vorgänge in ASP.NET den Standardnamen, die von WCF unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="abbc9-119">Doing so is important, because the default names for operations in ASP.NET are different from the default names supplied by WCF.</span></span> <span data-ttu-id="abbc9-120">Durch Angeben expliziter Namen müssen Sie sich nicht auf die Standardnamen verlassen.</span><span class="sxs-lookup"><span data-stu-id="abbc9-120">By providing explicit names, you avoid relying on the default ones.</span></span>  
  
- <span data-ttu-id="abbc9-121">Implementieren Sie Webdienstvorgänge auf ASP.NET nicht mit polymorphen Methoden, da WCF keine ASP.NET-Webdienstvorgänge mit polymorphen Methoden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="abbc9-121">Do not implement ASP.NET Web service operations with polymorphic methods, because WCF does not support implementing operations with polymorphic methods.</span></span>  
  
- <span data-ttu-id="abbc9-122">Verwenden Sie <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>, um explizite Werte für SOAPAction-HTTP-Header anzugeben, durch die HTTP-Anforderungen an Methoden geroutet werden.</span><span class="sxs-lookup"><span data-stu-id="abbc9-122">Use the <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> to provide explicit values for the SOAPAction HTTP headers by which HTTP requests will be routed to methods.</span></span>  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     <span data-ttu-id="abbc9-123">Bei diesem Ansatz wird umgehen SOAPAction-Werte, die von ASP.NET und WCF nicht identisch, verwendet die Standardeinstellung verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="abbc9-123">Taking this approach will circumvent having to rely on the default SOAPAction values used by ASP.NET and WCF being the same.</span></span>  
  
- <span data-ttu-id="abbc9-124">Verwenden Sie möglichst keine SOAP-Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="abbc9-124">Avoid using SOAP extensions.</span></span> <span data-ttu-id="abbc9-125">Wenn SOAP-Erweiterungen erforderlich sind, klicken Sie dann bestimmen Sie, ob es sich bei der Zweck, die für den sie in Betracht gezogen werden, ein Feature ist, die bereits von WCF bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="abbc9-125">If SOAP extensions are required, then determine whether the purpose for which they are being considered is a feature that is already provided by WCF.</span></span> <span data-ttu-id="abbc9-126">Überdenken Sie, wenn dies tatsächlich der Fall ist, klicken Sie dann die Möglichkeit, WCF nicht sofort zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="abbc9-126">If that is indeed the case, then reconsider the choice to not adopt WCF right away.</span></span>  
  
## <a name="state-management"></a><span data-ttu-id="abbc9-127">Zustandsverwaltung</span><span class="sxs-lookup"><span data-stu-id="abbc9-127">State Management</span></span>  
 <span data-ttu-id="abbc9-128">Verzichten Sie nach Möglichkeit darauf, Zustände in Diensten verwalten zu müssen.</span><span class="sxs-lookup"><span data-stu-id="abbc9-128">Avoid having to maintain state in services.</span></span> <span data-ttu-id="abbc9-129">Nicht nur Zustandsverwaltung neigt dazu, die Skalierbarkeit einer Anwendung beeinträchtigen, sondern die zustandsverwaltungsmechanismen von ASP.NET und WCF sind sehr verschieden, obwohl WCF die Mechanismen ASP.NET im ASP.NET-Kompatibilitätsmodus unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="abbc9-129">Not only does maintaining state tend to compromise the scalability of an application, but the state management mechanisms of ASP.NET and WCF are very different, although WCF does support the ASP.NET mechanisms in ASP.NET compatibility mode.</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="abbc9-130">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="abbc9-130">Exception Handling</span></span>  
 <span data-ttu-id="abbc9-131">Entwerfen Sie beim Ausarbeiten der Strukturen von Datentypen, die von einem Dienst gesendet und empfangen werden sollen, auch Strukturen für die verschiedenen Ausnahmetypen, die in einem an einen Client zu übermittelnden Dienst auftreten können.</span><span class="sxs-lookup"><span data-stu-id="abbc9-131">In designing the structures of the data types to be sent and received by a service, also design structures to represent the various types of exceptions that might occur within a service that one might wish to convey to a client.</span></span>  
  
```csharp  
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
  
 <span data-ttu-id="abbc9-132">Konfigurieren Sie Klassen dieser Art so, dass sie eigenständig zu XML serialisiert werden können:</span><span class="sxs-lookup"><span data-stu-id="abbc9-132">Give such classes the ability to serialize themselves to XML:</span></span>  
  
```csharp  
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
  
 <span data-ttu-id="abbc9-133">Die Klassen können anschließend zum Angeben der Details für explizit ausgelöste <xref:System.Web.Services.Protocols.SoapException>-Instanzen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="abbc9-133">The classes can then be used to provide the details for explicitly thrown <xref:System.Web.Services.Protocols.SoapException> instances:</span></span>  
  
```csharp  
AnctipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 <span data-ttu-id="abbc9-134">Diese Ausnahmeklassen werden sofort wieder verwendbare, mit den WCF <xref:System.ServiceModel.FaultException%601> Klasse, um ein neues auslösen `FaultException<AnticipatedException>(anticipatedException);`</span><span class="sxs-lookup"><span data-stu-id="abbc9-134">These exception classes will be readily reusable with the WCF <xref:System.ServiceModel.FaultException%601> class to throw a new `FaultException<AnticipatedException>(anticipatedException);`</span></span>  
  
## <a name="security"></a><span data-ttu-id="abbc9-135">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="abbc9-135">Security</span></span>  
 <span data-ttu-id="abbc9-136">Der folgende Abschnitt enthält einige Sicherheitsempfehlungen:</span><span class="sxs-lookup"><span data-stu-id="abbc9-136">The following are some security recommendations.</span></span>  
  
- <span data-ttu-id="abbc9-137">Vermeiden Sie mithilfe von ASP.NET 2.0-Profile, da durch deren Verwendung die Verwendung des ASP.NET-Integrationsmodus eingeschränkt wird, wenn der Dienst WCF migriert wurde.</span><span class="sxs-lookup"><span data-stu-id="abbc9-137">Avoid using ASP.NET 2.0 Profiles, as using them would restrict the use of ASP.NET Integration Mode if the service was migrated to WCF.</span></span>  
  
- <span data-ttu-id="abbc9-138">Verwenden Sie Zugriffssteuerungslisten zum Steuern des Zugriffs auf Dienste, wie ASP.NET Web Services unterstützt die Zugriffssteuerungslisten (Internet Information Services, IIS), WCF, jedoch nicht, da ASP.NET Web Services IIS zum Hosten von abhängig und WCF nicht unbedingt in IIS gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="abbc9-138">Avoid using ACLs to control access to services, as ASP.NET Web services supports ACLs using Internet Information Services (IIS), WCF does not—because ASP.NET Web services depend on IIS for hosting, and WCF does not necessarily have to be hosted in IIS.</span></span>  
  
- <span data-ttu-id="abbc9-139">Verwenden Sie ASP.NET 2.0-Rollenanbieter zum Autorisieren des Zugriffs auf die Ressource eines Diensts.</span><span class="sxs-lookup"><span data-stu-id="abbc9-139">Do consider using ASP.NET 2.0 Role Providers for authorizing access to the resources of a service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abbc9-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abbc9-140">See also</span></span>

- [<span data-ttu-id="abbc9-141">Vorbereitungen für Windows Communication Foundation: Einfachere Integration in der Zukunft</span><span class="sxs-lookup"><span data-stu-id="abbc9-141">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
