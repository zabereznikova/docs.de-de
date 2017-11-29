---
title: "Vorbereitungen für Windows Communication Foundation: Einfachere Integration in der Zukunft"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8f60b2566895acfd7d2b749729fab9c3f5deb20c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a><span data-ttu-id="2138c-102">Vorbereitungen für Windows Communication Foundation: Einfachere Integration in der Zukunft</span><span class="sxs-lookup"><span data-stu-id="2138c-102">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>
<span data-ttu-id="2138c-103">Wenn Sie heute ASP.NET verwenden und vorhaben, zukünftig [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zu verwenden, bietet dieses Thema Tipps, die gewährleisten, dass neue ASP.NET-Webdienste mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen ordnungsgemäß zusammenwirken.</span><span class="sxs-lookup"><span data-stu-id="2138c-103">If you use ASP.NET today, and anticipate using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in the future, this topic provides guidance to ensure that new ASP.NET Web services will work well together with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="general-recommendations"></a><span data-ttu-id="2138c-104">Allgemeine Empfehlungen</span><span class="sxs-lookup"><span data-stu-id="2138c-104">General Recommendations</span></span>  
 <span data-ttu-id="2138c-105">Übernehmen Sie ASP.NET 2.0 auch für neue Dienste.</span><span class="sxs-lookup"><span data-stu-id="2138c-105">Adopt ASP.NET 2.0 for any new services.</span></span> <span data-ttu-id="2138c-106">Dadurch stellen Sie den Zugriff auf die Verbesserungen und Erweiterungen der neuen Version bereit.</span><span class="sxs-lookup"><span data-stu-id="2138c-106">Doing so will provide access to the improvements and enhancements of the new version.</span></span> <span data-ttu-id="2138c-107">Sie erhalten so auch die Möglichkeit, ASP.NET 2.0-Komponenten zusammen mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Komponenten in derselben Anwendung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2138c-107">However, it will also allow for the possibility of using ASP.NET 2.0 components together with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] components in the same application.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="2138c-108">Protokolle</span><span class="sxs-lookup"><span data-stu-id="2138c-108">Protocols</span></span>  
 <span data-ttu-id="2138c-109">Verwenden Sie die neue Funktion von ASP.NET 2.0 zum Überprüfen der Konformität mit WS-I Basic Profile 1.1:</span><span class="sxs-lookup"><span data-stu-id="2138c-109">Use ASP.NET 2.0’s new facility for validating conformity to the WS-I Basic Profile 1.1:</span></span>  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 <span data-ttu-id="2138c-110">ASP.NET-Webdienste, die mit WS-I Basic Profile 1.1 übereinstimmen, sind mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients interoperabel, wenn die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] vordefinierte <xref:System.ServiceModel.BasicHttpBinding>-Bindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2138c-110">ASP.NET Web services that conform to WS-I Basic Profile 1.1 will be interoperable with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients by using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] predefined binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="2138c-111">Dienstentwicklung</span><span class="sxs-lookup"><span data-stu-id="2138c-111">Service Development</span></span>  
 <span data-ttu-id="2138c-112">Verwenden Sie das <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute>-Attribut nicht, um Nachrichten basierend auf dem voll qualifizierten Namen des Textelements der SOAP-Nachricht anstatt des SOAPAction HTTP-Headers an Methoden weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="2138c-112">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the SOAPAction HTTP header.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2138c-113"> verwendet den SOAPAction-HTTP-Header zum Weiterleiten von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="2138c-113"> uses the SOAPAction HTTP header for routing messages.</span></span>  
  
## <a name="data-representation"></a><span data-ttu-id="2138c-114">Datendarstellung</span><span class="sxs-lookup"><span data-stu-id="2138c-114">Data Representation</span></span>  
 <span data-ttu-id="2138c-115">Die XML, in die <xref:System.Xml.Serialization.XmlSerializer> standardmäßig einen Typ serialisiert, ist semantisch identisch mit der XML, in die <xref:System.Runtime.Serialization.DataContractSerializer> einen Typ serialisiert, vorausgesetzt, der Namespace ist für die XML explizit definiert.</span><span class="sxs-lookup"><span data-stu-id="2138c-115">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="2138c-116">Wenn ein Datentyp für die Verwendung mit ASP.NET-Webdiensten in Antizipation einer zukünftigen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Integration definiert wird, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="2138c-116">When defining a data type for use with ASP.NET Web services in anticipation of adopting [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in the future, do the following:</span></span>  
  
1.  <span data-ttu-id="2138c-117">Definieren Sie den Typ mit .NET Framework-Klassen und nicht mit dem XML-Schema.</span><span class="sxs-lookup"><span data-stu-id="2138c-117">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
2.  <span data-ttu-id="2138c-118">Fügen Sie der Klasse lediglich <xref:System.SerializableAttribute> und <xref:System.Xml.Serialization.XmlRootAttribute> hinzu, wobei Sie mit dem zweiten Attribut den Namespace für den Typ explizit definieren.</span><span class="sxs-lookup"><span data-stu-id="2138c-118">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="2138c-119">Fügen Sie keine zusätzlichen Attribute aus dem <xref:System.Xml.Serialization>-Namespace hinzu, um zu steuern, wie die .NET Framework-Klasse in XML übersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="2138c-119">Do no add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
 <span data-ttu-id="2138c-120">Wenn Sie diese Vorgehensweise wählen, sollte es später kein Problem darstellen, die .NET-Klassen in Datenverträge umzuwandeln, indem Sie <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> hinzufügen, ohne die XML erheblich zu ändern, in die die Klassen für die Übertragung serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="2138c-120">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="2138c-121">Die von den ASP.NET-Webdiensten verwendeten Typen können von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] als Datenverträge verarbeitet werden, was u.&#160;a. zu einer höheren Leistung der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen führt.</span><span class="sxs-lookup"><span data-stu-id="2138c-121">The types used in messages by ASP.NET Web services will be able to be processed as data contracts by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications, yielding, amongst other benefits, better performance in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="security"></a><span data-ttu-id="2138c-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="2138c-122">Security</span></span>  
 <span data-ttu-id="2138c-123">Vermeiden Sie die Verwendung der von den Internetinformationsdiensten (IIS) bereitgestellten Authentifizierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="2138c-123">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="2138c-124">Diese werden von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2138c-124">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients do not support them.</span></span> <span data-ttu-id="2138c-125">Falls ein Dienst gesichert werden muss, verwenden Sie die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellten Optionen, da diese Optionen leistungsstärker sind und auf Standardprotokollen basieren.</span><span class="sxs-lookup"><span data-stu-id="2138c-125">If a service needs to be secured, use the options provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], because these options are richer and are based on standard protocols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2138c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2138c-126">See Also</span></span>  
 [<span data-ttu-id="2138c-127">Vorbereitungen für Windows Communication Foundation: Einfachere Migration in der Zukunft</span><span class="sxs-lookup"><span data-stu-id="2138c-127">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
