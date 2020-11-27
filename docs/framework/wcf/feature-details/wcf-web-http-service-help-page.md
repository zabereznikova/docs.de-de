---
title: Hilfeseite zum WCF-Web-HTTP-Dienst
ms.date: 03/30/2017
ms.assetid: 63c7c695-44b6-4f31-bb9c-00f2763f525e
ms.openlocfilehash: fe6b22c6ebd637d3aa2bcd3744cb6b73e71c9482
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266934"
---
# <a name="wcf-web-http-service-help-page"></a><span data-ttu-id="613d6-102">Hilfeseite zum WCF-Web-HTTP-Dienst</span><span class="sxs-lookup"><span data-stu-id="613d6-102">WCF Web HTTP Service Help Page</span></span>

[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="613d6-103">stellt eine automatische Hilfeseite für WCF-WEB-HTTP-Dienste bereit.</span><span class="sxs-lookup"><span data-stu-id="613d6-103">provides an automatic help page for WCF WEB HTTP services.</span></span> <span data-ttu-id="613d6-104">Auf dieser Hilfeseite sind Beschreibungen der einzelnen Vorgänge, Anforderungs- und Antwortformate sowie Schemas aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="613d6-104">This help page lists a description of each operation, request and response formats, and schemas.</span></span> <span data-ttu-id="613d6-105">Diese Funktionalität ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="613d6-105">This functionality is turned off by default.</span></span> <span data-ttu-id="613d6-106">Wenn ein Benutzer einen WCF-Web-HTTP-Dienst durchsucht und "/Help" an das Ende der URL anfügt, wird beispielsweise `http://localhost:8000/Customers/Help` eine Hilfeseite wie die folgende angezeigt.</span><span class="sxs-lookup"><span data-stu-id="613d6-106">When a user browses to a WCF WEB HTTP service and appends "/Help" on to the end of the URL, for example `http://localhost:8000/Customers/Help`, a help page like the following is displayed.</span></span>  
  
 ![Ein Browser mit der WCF-Rest-Hilfeseite geöffnet.](./media/wcf-web-http-service-help-page/windows-communication-foundation-rest-help-page.gif)  
  
 <span data-ttu-id="613d6-108">Benutzer können dann auf alle Methoden klicken, die auf der Hilfeseite aufgeführt sind. Außerdem wird für den jeweiligen Vorgang eine Seite angezeigt, die weitere Informationen zur Methode enthält, beispielsweise Nachrichtenformate und Beispielantworten.</span><span class="sxs-lookup"><span data-stu-id="613d6-108">The user can then click any method listed in the help page and detailed page for that operation is displayed showing more information about the method, including message formats and example responses.</span></span> <span data-ttu-id="613d6-109">Das folgende Bild ist ein Beispiel für eine Hilfeseite einer Methode.</span><span class="sxs-lookup"><span data-stu-id="613d6-109">The following image is an example of a help page for a method.</span></span>  
  
 ![Ein Browser mit den Details der WCF-Rest-Hilfeseite für die GetCustomers-Methode wurde geöffnet.](./media/wcf-web-http-service-help-page/windows-communication-foundation-rest-help-page-detail.gif)  
  
## <a name="using-the-wcf-web-http-help-page"></a><span data-ttu-id="613d6-111">Verwenden der WCF-Web-HTTP-Hilfeseite</span><span class="sxs-lookup"><span data-stu-id="613d6-111">Using the WCF Web HTTP Help Page</span></span>  

 <span data-ttu-id="613d6-112">Die WCF-WEB-HTTP-Hilfeseite zeigt für jeden Vorgang eine kurze Beschreibung an, sofern Sie mithilfe von <xref:System.ComponentModel.DescriptionAttribute> eine Beschreibung angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="613d6-112">The WCF WEB HTTP Help page displays a short description for each operation provided that you specify one using the <xref:System.ComponentModel.DescriptionAttribute>.</span></span> <span data-ttu-id="613d6-113">Dieses Attribut verwendet eine Zeichenfolge, die eine kurze Beschreibung des Vorgangs enthält, auf den es angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="613d6-113">This attribute takes a string that contains a short description of the operation it is applied to.</span></span> <span data-ttu-id="613d6-114">Der folgende Code veranschaulicht z. B., wie Sie <xref:System.ComponentModel.DescriptionAttribute> verwenden, um eine kurze Beschreibung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="613d6-114">For example, the following code shows how to use the <xref:System.ComponentModel.DescriptionAttribute> to provide a short description.</span></span>  
  
```csharp
[OperationContract]  
[WebGet(UriTemplate="/template1", BodyStyle = WebMessageBodyStyle.Bare)]  
[Description("Description for GET /template1")]  
SyndicationFeedFormatter GetTemplate1();  
```  
  
 <span data-ttu-id="613d6-115">Um die WCF-WEB-HTTP-Hilfeseite zu aktivieren, müssen Sie den Endpunkten des Diensts ein Endpunktverhalten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="613d6-115">To turn on the WCF WEB HTTP Help page, you must add an endpoint behavior to your service's endpoints.</span></span> <span data-ttu-id="613d6-116">Dies kann per Konfiguration oder im Code erfolgen.</span><span class="sxs-lookup"><span data-stu-id="613d6-116">This can be done in configuration or code.</span></span> <span data-ttu-id="613d6-117">Um die WCF-WEB-HTTP-Hilfeseite per Konfiguration zu aktivieren, fügen Sie ein Endpunktverhalten mit einem `<webHttp>`-Element hinzu, legen `enableHelp` auf `true` fest und fügen einen Endpunkt hinzu, für den Sie die Verwendung des Endpunktverhaltens konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="613d6-117">To enable the WCF WEB HTTP Help age in configuration, add an endpoint behavior with a `<webHttp>` element, set `enableHelp` to `true`, and add an endpoint and configure it to use the endpoint behavior.</span></span> <span data-ttu-id="613d6-118">Dies ist im folgenden Konfigurationscode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="613d6-118">The following configuration code shows how to do this.</span></span>  
  
```xml  
<endpointBehaviors>  
   <behavior name="RESTEndpointBehavior">  
      <webHttp enableHelp="true"/>  
   </behavior>  
</endpointBehaviors>  
<!-- ... -->  
<services>  
   <service behaviorConfiguration="RESTWebServiceBehavior" name="RESTWebService">      <endpoint address="" kind="webHttpEndpoint" behaviorConfiguration="RESTEndpointBehavior" contract="IHello" />  
  
      <!-- ... -->  
   </service>  
</services>  
```  
  
 <span data-ttu-id="613d6-119">Um die WCF-Web-HTTP-Hilfeseite im Code zu aktivieren, fügen Sie einen Dienstendpunkt hinzu, fügen der Endpunkteinstellung <xref:System.ServiceModel.Description.WebHttpBehavior> hinzu und legen  <xref:System.ServiceModel.Description.WebHttpBehavior.HelpEnabled%2A> auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="613d6-119">To enable the WCF Web HTTP Help page in code, add a service endpoint and add a <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint setting <xref:System.ServiceModel.Description.WebHttpBehavior.HelpEnabled%2A> to `true`.</span></span> <span data-ttu-id="613d6-120">Dies wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="613d6-120">The following code shows how to do this.</span></span>  
  
```csharp
using (WebServiceHost host = new WebServiceHost(typeof(Service), new Uri("http://localhost:8000/Customers")))  
{  
   host.AddServiceEndpoint(typeof(ICustomerCollection), new WebHttpBinding(), "");
   host.Description.Endpoints[0].Behaviors.Add(new WebHttpBehavior { EnableHelp = true });  
   // ...  
}  
```  
  
 <span data-ttu-id="613d6-121">Die Hilfeseite verfügt über das Format XHTML mit Markup, das die verschiedenen Teile der Seite identifiziert.</span><span class="sxs-lookup"><span data-stu-id="613d6-121">The help page is XHTML based with mark-up that identifies the different parts of the page.</span></span> <span data-ttu-id="613d6-122">Dies ermöglicht Clients den programmgesteuerten Zugriff auf die Seite, indem <xref:System.Xml.Linq.XElement> oder andere XLinq-APIs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="613d6-122">This enables clients to programmatically access the page using <xref:System.Xml.Linq.XElement> or other XLinq APIs.</span></span>  
  
## <a name="schemas-used-in-the-wcf-web-http-service-help-page"></a><span data-ttu-id="613d6-123">Auf der WCF-Web-HTTP-Hilfeseite für Dienste verwendete Schemas</span><span class="sxs-lookup"><span data-stu-id="613d6-123">Schemas Used in the WCF Web HTTP Service Help Page</span></span>  

 <span data-ttu-id="613d6-124">Die folgenden Schemas werden auf der WCF-Web-HTTP-Hilfeseite für Dienste verwendet.</span><span class="sxs-lookup"><span data-stu-id="613d6-124">The following schemas are used in the WCF Web HTTP service help page.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:tns="http://schemas.microsoft.com/2003/10/Serialization/" attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="http://schemas.microsoft.com/2003/10/Serialization/" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="anyType" nillable="true" type="xs:anyType" />  
  <xs:element name="anyURI" nillable="true" type="xs:anyURI" />  
  <xs:element name="base64Binary" nillable="true" type="xs:base64Binary" />  
  <xs:element name="boolean" nillable="true" type="xs:boolean" />  
  <xs:element name="byte" nillable="true" type="xs:byte" />  
  <xs:element name="dateTime" nillable="true" type="xs:dateTime" />  
  <xs:element name="decimal" nillable="true" type="xs:decimal" />  
  <xs:element name="double" nillable="true" type="xs:double" />  
  <xs:element name="float" nillable="true" type="xs:float" />  
  <xs:element name="int" nillable="true" type="xs:int" />  
  <xs:element name="long" nillable="true" type="xs:long" />  
  <xs:element name="QName" nillable="true" type="xs:QName" />  
  <xs:element name="short" nillable="true" type="xs:short" />  
  <xs:element name="string" nillable="true" type="xs:string" />  
  <xs:element name="unsignedByte" nillable="true" type="xs:unsignedByte" />  
  <xs:element name="unsignedInt" nillable="true" type="xs:unsignedInt" />  
  <xs:element name="unsignedLong" nillable="true" type="xs:unsignedLong" />  
  <xs:element name="unsignedShort" nillable="true" type="xs:unsignedShort" />  
  <xs:element name="char" nillable="true" type="tns:char" />  
  <xs:simpleType name="char">  
    <xs:restriction base="xs:int" />  
  </xs:simpleType>  
  <xs:element name="duration" nillable="true" type="tns:duration" />  
  <xs:simpleType name="duration">  
    <xs:restriction base="xs:duration">  
      <xs:pattern value="\-?P(\d*D)?(T(\d*H)?(\d*M)?(\d*(\.\d*)?S)?)?" />  
      <xs:minInclusive value="-P10675199DT2H48M5.4775808S" />  
      <xs:maxInclusive value="P10675199DT2H48M5.4775807S" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:element name="guid" nillable="true" type="tns:guid" />  
  <xs:simpleType name="guid">  
    <xs:restriction base="xs:string">  
      <xs:pattern value="[\da-fA-F]{8}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{12}" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:attribute name="FactoryType" type="xs:QName" />  
  <xs:attribute name="Id" type="xs:ID" />  
  <xs:attribute name="Ref" type="xs:IDREF" />  
</xs:schema>  
  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:tns="http://microsoft.com/wsdl/types/" elementFormDefault="qualified" targetNamespace="http://microsoft.com/wsdl/types/" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:simpleType name="guid">  
    <xs:restriction base="xs:string">  
      <xs:pattern value="[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="char">  
    <xs:restriction base="xs:unsignedShort" />  
  </xs:simpleType>  
</xs:schema>  
  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:tns="http://schemas.datacontract.org/2004/07/System" elementFormDefault="qualified" targetNamespace="http://schemas.datacontract.org/2004/07/System" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:import namespace="http://schemas.microsoft.com/2003/10/Serialization/" />  
  <xs:complexType name="DateTimeOffset">  
    <xs:annotation>  
      <xs:appinfo>  
        <IsValueType xmlns="http://schemas.microsoft.com/2003/10/Serialization/">true</IsValueType>  
      </xs:appinfo>  
    </xs:annotation>  
    <xs:sequence>  
      <xs:element name="DateTime" type="xs:dateTime" />  
      <xs:element name="OffsetMinutes" type="xs:short" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="DateTimeOffset" nillable="true" type="tns:DateTimeOffset" />  
  <xs:complexType name="DBNull">  
    <xs:sequence />  
  </xs:complexType>  
  <xs:element name="DBNull" nillable="true" type="tns:DBNull" />  
</xs:schema>  
  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:tns="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:ser="http://schemas.microsoft.com/2003/10/Serialization/" elementFormDefault="qualified" targetNamespace="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:import namespace="http://schemas.microsoft.com/2003/10/Serialization/" />  
  <xs:complexType name="ArrayOfboolean">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="boolean" type="xs:boolean" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfboolean" nillable="true" type="tns:ArrayOfboolean" />  
  <xs:complexType name="ArrayOfchar">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="char" type="ser:char" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfchar" nillable="true" type="tns:ArrayOfchar" />  
  <xs:complexType name="ArrayOfdateTime">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="dateTime" type="xs:dateTime" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfdateTime" nillable="true" type="tns:ArrayOfdateTime" />  
  <xs:complexType name="ArrayOfdecimal">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="decimal" type="xs:decimal" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfdecimal" nillable="true" type="tns:ArrayOfdecimal" />  
  <xs:complexType name="ArrayOfdouble">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="double" type="xs:double" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfdouble" nillable="true" type="tns:ArrayOfdouble" />  
  <xs:complexType name="ArrayOffloat">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="float" type="xs:float" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOffloat" nillable="true" type="tns:ArrayOffloat" />  
  <xs:complexType name="ArrayOfguid">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="guid" type="ser:guid" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfguid" nillable="true" type="tns:ArrayOfguid" />  
  <xs:complexType name="ArrayOfint">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="int" type="xs:int" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfint" nillable="true" type="tns:ArrayOfint" />  
  <xs:complexType name="ArrayOflong">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="long" type="xs:long" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOflong" nillable="true" type="tns:ArrayOflong" />  
  <xs:complexType name="ArrayOfshort">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="short" type="xs:short" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfshort" nillable="true" type="tns:ArrayOfshort" />  
  <xs:complexType name="ArrayOfstring">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="string" nillable="true" type="xs:string" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfstring" nillable="true" type="tns:ArrayOfstring" />  
  <xs:complexType name="ArrayOfduration">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="duration" type="ser:duration" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfduration" nillable="true" type="tns:ArrayOfduration" />  
  <xs:complexType name="ArrayOfunsignedInt">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="unsignedInt" type="xs:unsignedInt" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfunsignedInt" nillable="true" type="tns:ArrayOfunsignedInt" />  
  <xs:complexType name="ArrayOfunsignedLong">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="unsignedLong" type="xs:unsignedLong" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfunsignedLong" nillable="true" type="tns:ArrayOfunsignedLong" />  
  <xs:complexType name="ArrayOfunsignedShort">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="unsignedShort" type="xs:unsignedShort" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfunsignedShort" nillable="true" type="tns:ArrayOfunsignedShort" />  
  <xs:complexType name="ArrayOfQName">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="QName" nillable="true" type="xs:QName" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfQName" nillable="true" type="tns:ArrayOfQName" />  
</xs:schema>  
```  
  
 <span data-ttu-id="613d6-125">Weitere Informationen zum Serialisierungsschema des Daten Vertrags finden Sie unter [Daten Vertrags Schema-Referenz](data-contract-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="613d6-125">For more information about the data contract serialization schema, see [Data Contract Schema Reference](data-contract-schema-reference.md).</span></span>
