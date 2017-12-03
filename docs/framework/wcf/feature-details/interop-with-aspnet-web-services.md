---
title: "Interoperabilität mit ASP.NET-Webdiensten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fd30b2d62d3ecf21027c0225490da6f31113cb07
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="interoperability-with-aspnet-web-services"></a><span data-ttu-id="2e482-102">Interoperabilität mit ASP.NET-Webdiensten</span><span class="sxs-lookup"><span data-stu-id="2e482-102">Interoperability with ASP.NET Web Services</span></span>
<span data-ttu-id="2e482-103">Eine Interoperabilität zwischen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Webdiensten und den Webdiensten von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] kann erreicht werden, indem Sie sicherstellen, dass implementierte Dienste, die beide Technologien verwenden, der Spezifikation für WS-I Basic Profile 1.1 entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2e482-103">Interoperability between [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services and [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web services can be achieved by ensuring that services implemented using both technologies conform to the WS-I Basic Profile 1.1 specification.</span></span> [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="2e482-104">-Webdienste, die die WS-I Basic Profile 1.1-Spezifikation erfüllen, können mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients über die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellte Bindung (<xref:System.ServiceModel.BasicHttpBinding>) interagieren.</span><span class="sxs-lookup"><span data-stu-id="2e482-104"> Web services that conform to WS-I Basic Profile 1.1 are interoperable with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients by using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] system-provided binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
 <span data-ttu-id="2e482-105">Verwenden Sie wie im folgenden Beispielcode gezeigt die in [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] gebotene Möglichkeit, das <xref:System.Web.Services.WebService>-Attribut und das <xref:System.Web.Services.WebMethodAttribute>-Attribut zu einer Schnittstelle anstatt zu einer Klasse hinzuzufügen und zum Implementieren der Schnittstelle eine Klasse zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="2e482-105">Use [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] option of adding the <xref:System.Web.Services.WebService> and <xref:System.Web.Services.WebMethodAttribute> attributes to an interface rather than to a class, and writing a class to implement the interface, as shown in the following sample code.</span></span>  
  
```  
[WebService]  
public interface IEcho  
{  
    [WebMethod]  
    string Echo(string input);  
}  
  
public class Service : IEcho  
{  
  
   public string Echo(string input)  
   {  
        return input;  
    }  
}  
```  
  
 <span data-ttu-id="2e482-106">Die Verwendung dieser Option wird empfohlen, da die Schnittstelle mit dem <xref:System.Web.Services.WebService>-Attribut einen Vertrag für die vom Dienst ausgeführten Vorgänge darstellt. Dieser Vertrag kann wiederholt für verschiedene Klassen verwendet werden, die den gleichen Vertrag möglicherweise auf unterschiedliche Art und Weise implementieren.</span><span class="sxs-lookup"><span data-stu-id="2e482-106">Using this option is preferred, because the interface with the <xref:System.Web.Services.WebService> attribute constitutes a contract for the operations performed by the service that can be reused with various classes that might implement that same contract in different ways.</span></span>  
  
 <span data-ttu-id="2e482-107">Verwenden Sie das <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute>-Attribut nicht, um Nachrichten basierend auf dem voll qualifizierten Namen des Textelements der SOAP-Nachricht anstatt des `SOAPAction`-HTTP-Headers an Methoden weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="2e482-107">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the `SOAPAction` HTTP header.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2e482-108"> verwendet den `SOAPAction`-HTTP-Header zum Weiterleiten von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="2e482-108"> uses the `SOAPAction` HTTP header for routing messages.</span></span>  
  
 <span data-ttu-id="2e482-109">Die XML, in die <xref:System.Xml.Serialization.XmlSerializer> standardmäßig einen Typ serialisiert, ist semantisch identisch mit der XML, in die <xref:System.Runtime.Serialization.DataContractSerializer> einen Typ serialisiert, vorausgesetzt, der Namespace ist für die XML explizit definiert.</span><span class="sxs-lookup"><span data-stu-id="2e482-109">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="2e482-110">Wenn Sie einen Datentyp für die Verwendung mit definieren [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Webdienste in antizipation einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="2e482-110">When defining a data type for use with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Web services in anticipation of adopting [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], do the following:</span></span>  
  
-   <span data-ttu-id="2e482-111">Definieren Sie den Typ mit .NET Framework-Klassen und nicht mit dem XML-Schema.</span><span class="sxs-lookup"><span data-stu-id="2e482-111">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
-   <span data-ttu-id="2e482-112">Fügen Sie der Klasse lediglich <xref:System.SerializableAttribute> und <xref:System.Xml.Serialization.XmlRootAttribute> hinzu, wobei Sie mit dem zweiten Attribut den Namespace für den Typ explizit definieren.</span><span class="sxs-lookup"><span data-stu-id="2e482-112">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="2e482-113">Fügen Sie keine zusätzlichen Attribute aus dem <xref:System.Xml.Serialization>-Namespace hinzu, um die Übersetzung der .NET Framework-Klasse in XML zu steuern.</span><span class="sxs-lookup"><span data-stu-id="2e482-113">Do not add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
-   <span data-ttu-id="2e482-114">Wenn Sie diese Vorgehensweise wählen, sollte es später kein Problem darstellen, die .NET-Klassen in Datenverträge umzuwandeln, indem Sie <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> hinzufügen, ohne die XML erheblich zu ändern, in die die Klassen für die Übertragung serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e482-114">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="2e482-115">Die von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Webdiensten verwendeten Typen können von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] als Datenverträge verarbeitet werden, was u.&#160;a. zu einer besseren Leistung bei [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen führt.</span><span class="sxs-lookup"><span data-stu-id="2e482-115">The types used in messages by [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services can be processed as data contracts by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications, yielding, among other benefits, better performance in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
 <span data-ttu-id="2e482-116">Vermeiden Sie die Verwendung der von den Internetinformationsdiensten (IIS) bereitgestellten Authentifizierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="2e482-116">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="2e482-117">Diese werden von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e482-117">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients do not support them.</span></span> <span data-ttu-id="2e482-118">Falls ein Dienst geschützt werden muss, verwenden Sie die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellten Funktionen, da diese Optionen robuster sind und auf Standardprotokollen basieren.</span><span class="sxs-lookup"><span data-stu-id="2e482-118">If a service must be secured, use the options provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], because these options are robust and are based on standard protocols.</span></span>  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a><span data-ttu-id="2e482-119">Durch das Laden von ServiceModel HttpModule verursachte Leistungsbeeinträchtigungen</span><span class="sxs-lookup"><span data-stu-id="2e482-119">Performance impact caused by loading the ServiceModel HttpModule</span></span>  
 <span data-ttu-id="2e482-120">In .NET Framework&#160;3.0 wurde das WCF-`HttpModule`-Element in der Stammdatei Web.config installiert, sodass jede ASP.NET-Anwendung WCF unterstützte.</span><span class="sxs-lookup"><span data-stu-id="2e482-120">In the .NET Framework 3.0, the WCF `HttpModule` was installed in the root Web.config file such that every ASP.NET application was WCF enabled.</span></span> <span data-ttu-id="2e482-121">Dies kann die Leistung beeinträchtigen. Sie können daher `ServiceModel` für die Datei Web.config entfernen, wie im folgenden Bespiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2e482-121">This might affect performance, so you can remove `ServiceModel` for the Web.config file as shown in the following example.</span></span>  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
<httpModules/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e482-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e482-122">See Also</span></span>  
 [<span data-ttu-id="2e482-123">Vorgehensweise: Konfigurieren von WCF-Dienst für die Zusammenarbeit mit ASP.NET Webdienstclients</span><span class="sxs-lookup"><span data-stu-id="2e482-123">How to: Configure WCF Service to Interoperate with ASP.NET Web Service Clients</span></span>](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
