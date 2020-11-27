---
title: 'Vorbereitungen für Windows Communication Foundation: einfachere Migration in der Zukunft'
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: ead28354a3687bcca22a1a0eb5ccc9f15f0c69d2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266570"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a><span data-ttu-id="27ef3-102">Vorbereitungen für Windows Communication Foundation: einfachere Migration in der Zukunft</span><span class="sxs-lookup"><span data-stu-id="27ef3-102">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>

<span data-ttu-id="27ef3-103">Wenn Sie heute ASP.NET verwenden und die Verwendung von WCF in Zukunft erwarten, bietet dieses Thema Anleitungen, um sicherzustellen, dass neue ASP.NET-Webdienste gemeinsam mit WCF-Anwendungen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="27ef3-103">If you use ASP.NET today, and anticipate using WCF in the future, this topic provides guidance to ensure that new ASP.NET Web services will work well together with WCF applications.</span></span>  
  
## <a name="general-recommendations"></a><span data-ttu-id="27ef3-104">Allgemeine Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="27ef3-104">General Recommendations</span></span>  

 <span data-ttu-id="27ef3-105">Übernehmen Sie ASP.NET 2.0 auch für neue Dienste.</span><span class="sxs-lookup"><span data-stu-id="27ef3-105">Adopt ASP.NET 2.0 for any new services.</span></span> <span data-ttu-id="27ef3-106">Dadurch stellen Sie den Zugriff auf die Verbesserungen und Erweiterungen der neuen Version bereit.</span><span class="sxs-lookup"><span data-stu-id="27ef3-106">Doing so will provide access to the improvements and enhancements of the new version.</span></span> <span data-ttu-id="27ef3-107">Allerdings ist es auch möglich, ASP.NET 2,0-Komponenten mit WCF-Komponenten in derselben Anwendung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="27ef3-107">However, it will also allow for the possibility of using ASP.NET 2.0 components together with WCF components in the same application.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="27ef3-108">Protokolle</span><span class="sxs-lookup"><span data-stu-id="27ef3-108">Protocols</span></span>  

 <span data-ttu-id="27ef3-109">Verwenden Sie die neue Funktion von ASP.NET 2.0 zum Überprüfen der Konformität mit WS-I Basic Profile 1.1:</span><span class="sxs-lookup"><span data-stu-id="27ef3-109">Use ASP.NET 2.0’s new facility for validating conformity to the WS-I Basic Profile 1.1:</span></span>  
  
```csharp  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 <span data-ttu-id="27ef3-110">ASP.NET-Webdienste, die dem WS-I Basic Profile 1,1 entsprechen, können mit WCF-Clients mithilfe der vordefinierten WCF-Bindung () interoperabel werden <xref:System.ServiceModel.BasicHttpBinding> .</span><span class="sxs-lookup"><span data-stu-id="27ef3-110">ASP.NET Web services that conform to WS-I Basic Profile 1.1 will be interoperable with WCF clients by using WCF predefined binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="27ef3-111">Dienstentwicklung</span><span class="sxs-lookup"><span data-stu-id="27ef3-111">Service Development</span></span>  

 <span data-ttu-id="27ef3-112">Verwenden Sie das <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute>-Attribut nicht, um Nachrichten basierend auf dem voll qualifizierten Namen des Textelements der SOAP-Nachricht anstatt des SOAPAction HTTP-Headers an Methoden weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="27ef3-112">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the SOAPAction HTTP header.</span></span> <span data-ttu-id="27ef3-113">WCF verwendet den SOAPAction-HTTP-Header zum Weiterleiten von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="27ef3-113">WCF uses the SOAPAction HTTP header for routing messages.</span></span>  
  
## <a name="data-representation"></a><span data-ttu-id="27ef3-114">Datendarstellung</span><span class="sxs-lookup"><span data-stu-id="27ef3-114">Data Representation</span></span>  

 <span data-ttu-id="27ef3-115">Die XML, in die <xref:System.Xml.Serialization.XmlSerializer> standardmäßig einen Typ serialisiert, ist semantisch identisch mit der XML, in die <xref:System.Runtime.Serialization.DataContractSerializer> einen Typ serialisiert, vorausgesetzt, der Namespace ist für die XML explizit definiert.</span><span class="sxs-lookup"><span data-stu-id="27ef3-115">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="27ef3-116">Wenn Sie einen Datentyp für die Verwendung mit ASP.NET-Webdiensten in Erwartung der Einführung von WCF in Zukunft definieren, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="27ef3-116">When defining a data type for use with ASP.NET Web services in anticipation of adopting WCF in the future, do the following:</span></span>  
  
1. <span data-ttu-id="27ef3-117">Definieren Sie den Typ mit .NET Framework-Klassen und nicht mit dem XML-Schema.</span><span class="sxs-lookup"><span data-stu-id="27ef3-117">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
2. <span data-ttu-id="27ef3-118">Fügen Sie der Klasse lediglich <xref:System.SerializableAttribute> und <xref:System.Xml.Serialization.XmlRootAttribute> hinzu, wobei Sie mit dem zweiten Attribut den Namespace für den Typ explizit definieren.</span><span class="sxs-lookup"><span data-stu-id="27ef3-118">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="27ef3-119">Fügen Sie keine zusätzlichen Attribute aus dem <xref:System.Xml.Serialization>-Namespace hinzu, um zu steuern, wie die .NET Framework-Klasse in XML übersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="27ef3-119">Do no add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
 <span data-ttu-id="27ef3-120">Wenn Sie diese Vorgehensweise wählen, sollte es später kein Problem darstellen, die .NET-Klassen in Datenverträge umzuwandeln, indem Sie <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> hinzufügen, ohne die XML erheblich zu ändern, in die die Klassen für die Übertragung serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="27ef3-120">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="27ef3-121">Die in Nachrichten von ASP.NET-Webdiensten verwendeten Typen können von WCF-Anwendungen als Datenverträge verarbeitet werden, was zu anderen Vorteilen zu einer besseren Leistung in WCF-Anwendungen führt.</span><span class="sxs-lookup"><span data-stu-id="27ef3-121">The types used in messages by ASP.NET Web services will be able to be processed as data contracts by WCF applications, yielding, amongst other benefits, better performance in WCF applications.</span></span>  
  
## <a name="security"></a><span data-ttu-id="27ef3-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="27ef3-122">Security</span></span>  

 <span data-ttu-id="27ef3-123">Vermeiden Sie die Verwendung der von den Internetinformationsdiensten (IIS) bereitgestellten Authentifizierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="27ef3-123">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="27ef3-124">WCF-Clients unterstützen diese nicht.</span><span class="sxs-lookup"><span data-stu-id="27ef3-124">WCF clients do not support them.</span></span> <span data-ttu-id="27ef3-125">Wenn ein Dienst geschützt werden muss, verwenden Sie die von WCF bereitgestellten Optionen, da diese Optionen umfangreicher sind und auf Standardprotokollen basieren.</span><span class="sxs-lookup"><span data-stu-id="27ef3-125">If a service needs to be secured, use the options provided by WCF, because these options are richer and are based on standard protocols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27ef3-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27ef3-126">See also</span></span>

- [<span data-ttu-id="27ef3-127">Vorbereitungen für Windows Communication Foundation: einfachere Integration in der Zukunft</span><span class="sxs-lookup"><span data-stu-id="27ef3-127">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>](anticipating-adopting-wcf-migration.md)
