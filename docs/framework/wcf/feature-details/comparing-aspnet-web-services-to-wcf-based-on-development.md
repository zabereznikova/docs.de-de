---
title: Vergleichen von ASP.NET-Webdiensten mit WCF auf Grundlage der Entwicklung
ms.date: 03/30/2017
ms.assetid: f362d00e-ce82-484f-9d4f-27e579d5c320
ms.openlocfilehash: c5a2145a6d7b631a666df94eb0c1fc53cbc3c55f
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202265"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-development"></a><span data-ttu-id="aacb4-102">Vergleichen von ASP.NET-Webdiensten mit WCF auf Grundlage der Entwicklung</span><span class="sxs-lookup"><span data-stu-id="aacb4-102">Comparing ASP.NET Web Services to WCF Based on Development</span></span>

<span data-ttu-id="aacb4-103">Windows Communication Foundation (WCF) verfügt über eine Option für den ASP.NET-Kompatibilitätsmodus, mit der WCF-Anwendungen wie ASP.NET-Webdienste programmiert und konfiguriert werden können und deren Verhalten imitiert wird.</span><span class="sxs-lookup"><span data-stu-id="aacb4-103">Windows Communication Foundation (WCF) has an ASP.NET compatibility mode option to enable WCF applications to be programmed and configured like ASP.NET Web services, and mimic their behavior.</span></span> <span data-ttu-id="aacb4-104">In den folgenden Abschnitten werden ASP.NET-Webdienste und WCF basierend auf dem, was zum Entwickeln von Anwendungen mit beiden Technologien erforderlich ist, verglichen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-104">The following sections compare ASP.NET Web services and WCF based on what is required to develop applications using both technologies.</span></span>

## <a name="data-representation"></a><span data-ttu-id="aacb4-105">Datendarstellung</span><span class="sxs-lookup"><span data-stu-id="aacb4-105">Data Representation</span></span>

<span data-ttu-id="aacb4-106">Die Entwicklung eines Webdiensts mit ASP.NET beginnt normalerweise mit der Definition aller komplexen Datentypen, die vom Dienst verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-106">The development of a Web service with ASP.NET typically begins with defining any complex data types the service is to use.</span></span> <span data-ttu-id="aacb4-107">ASP.NET verwendet <xref:System.Xml.Serialization.XmlSerializer>, um Daten, die von .NET Framework-Typen dargestellt werden, zur Übertragung an oder von einem Dienst in XML zu übersetzen und als XML empfangene Daten in .NET Framework-Objekte zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-107">ASP.NET relies on the <xref:System.Xml.Serialization.XmlSerializer> to translate data represented by .NET Framework types to XML for transmission to or from a service and to translate data received as XML into .NET Framework objects.</span></span> <span data-ttu-id="aacb4-108">Die Definition der komplexen Datentypen, die ein ASP.NET-Dienst verwenden soll, erfordert die Definition von .NET Framework-Klassen, die <xref:System.Xml.Serialization.XmlSerializer> in und aus XML serialisieren kann.</span><span class="sxs-lookup"><span data-stu-id="aacb4-108">Defining the complex data types that an ASP.NET service is to use requires the definition of .NET Framework classes that the <xref:System.Xml.Serialization.XmlSerializer> can serialize to and from XML.</span></span> <span data-ttu-id="aacb4-109">Derartige Klassen können manuell geschrieben oder aus Definitionen der Typen in XML-Schema generiert werden. Dies geschieht mithilfe von xsd.exe, dem Befehlszeilen-Unterstützungsprogramm für XML-Schemas/-Datentypen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-109">Such classes can be written manually, or generated from definitions of the types in XML Schema using the command-line XML Schemas/Data Types Support Utility, xsd.exe.</span></span>

<span data-ttu-id="aacb4-110">Nachfolgend finden Sie eine Auflistung wesentlicher Probleme, die beim Definieren von .NET Framework-Klassen auftreten können, die <xref:System.Xml.Serialization.XmlSerializer> in und aus XML serialisieren kann:</span><span class="sxs-lookup"><span data-stu-id="aacb4-110">The following is a list of key issues to know when defining .NET Framework classes that the <xref:System.Xml.Serialization.XmlSerializer> can serialize to and from XML:</span></span>

- <span data-ttu-id="aacb4-111">Nur die öffentlichen Felder und Eigenschaften von .NET Framework-Objekten werden in XML übersetzt.</span><span class="sxs-lookup"><span data-stu-id="aacb4-111">Only the public fields and properties of .NET Framework objects are translated into XML.</span></span>

- <span data-ttu-id="aacb4-112">Instanzen der Auflistungsklassen können nur in XML serialisiert werden, wenn die Klassen entweder die <xref:System.Collections.IEnumerable>-Schnittstelle oder die <xref:System.Collections.ICollection>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="aacb4-112">Instances of collection classes can be serialized into XML only if the classes implement either the <xref:System.Collections.IEnumerable> or <xref:System.Collections.ICollection> interface.</span></span>

- <span data-ttu-id="aacb4-113">Klassen, die die <xref:System.Collections.IDictionary>-Schnittstelle, zum Beispiel <xref:System.Collections.Hashtable>, implementieren, können nicht in XML serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-113">Classes that implement the <xref:System.Collections.IDictionary> interface, such as <xref:System.Collections.Hashtable>, cannot be serialized into XML.</span></span>

- <span data-ttu-id="aacb4-114">Die zahlreichen Attributtypen im <xref:System.Xml.Serialization>-Namespace können einer .NET Framework-Klasse und deren Membern hinzugefügt werden, um die Darstellung der Klasseninstanzen in XML zu steuern.</span><span class="sxs-lookup"><span data-stu-id="aacb4-114">The great many attribute types in the <xref:System.Xml.Serialization> namespace can be added to a .NET Framework class and its members to control how instances of the class are represented in XML.</span></span>

<span data-ttu-id="aacb4-115">Die Entwicklung von WCF-Anwendungen beginnt in der Regel auch mit der Definition komplexer Typen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-115">WCF application development usually also begins with the definition of complex types.</span></span> <span data-ttu-id="aacb4-116">WCF kann verwendet werden, um dieselben .NET Framework Typen wie ASP.NET-Webdienste zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-116">WCF can be made to use the same .NET Framework types as ASP.NET Web services.</span></span>

<span data-ttu-id="aacb4-117">Die WCF <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> können .NET Framework Typen hinzugefügt werden, um anzugeben, dass Instanzen des Typs in XML serialisiert werden sollen und welche speziellen Felder oder Eigenschaften des Typs serialisiert werden sollen, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="aacb4-117">The WCF<xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> can be added to .NET Framework types to indicate that instances of the type are to be serialized into XML, and which particular fields or properties of the type are to be serialized, as shown in the following sample code.</span></span>

```csharp
//Example One:
[DataContract]
public class LineItem
{
    [DataMember]
    public string ItemNumber;
    [DataMember]
    public decimal Quantity;
    [DataMember]
    public decimal UnitPrice;
}

//Example Two:
public class LineItem
{
    [DataMember]
    private string itemNumber;
    [DataMember]
    private decimal quantity;
    [DataMember]
    private decimal unitPrice;

    public string ItemNumber
    {
      get
      {
          return this.itemNumber;
      }

      set
      {
          this.itemNumber = value;
      }
    }

    public decimal Quantity
    {
        get
        {
            return this.quantity;
        }

        set
        {
            this.quantity = value;
        }
    }

    public decimal UnitPrice
    {
      get
      {
          return this.unitPrice;
      }

      set
      {
          this.unitPrice = value;
      }
    }
}

//Example Three:
public class LineItem
{
     private string itemNumber;
     private decimal quantity;
     private decimal unitPrice;

     [DataMember]
     public string ItemNumber
     {
       get
       {
          return this.itemNumber;
       }

       set
       {
           this.itemNumber = value;
       }
     }

     [DataMember]
     public decimal Quantity
     {
          get
          {
              return this.quantity;
          }

          set
          {
             this.quantity = value;
          }
     }

     [DataMember]
     public decimal UnitPrice
     {
          get
          {
              return this.unitPrice;
          }

          set
          {
              this.unitPrice = value;
          }
     }
}
```

<span data-ttu-id="aacb4-118"><xref:System.Runtime.Serialization.DataContractAttribute> gibt an, dass null oder mehr Felder oder Eigenschaften eines Typs serialisiert werden sollen. <xref:System.Runtime.Serialization.DataMemberAttribute> gibt dagegen an, dass ein bestimmtes Feld oder eine Eigenschaft serialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="aacb4-118">The <xref:System.Runtime.Serialization.DataContractAttribute> signifies that zero or more of a type’s fields or properties are to be serialized, while the <xref:System.Runtime.Serialization.DataMemberAttribute> indicates that a particular field or property is to be serialized.</span></span> <span data-ttu-id="aacb4-119"><xref:System.Runtime.Serialization.DataContractAttribute> kann für eine Klasse oder Struktur übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-119">The <xref:System.Runtime.Serialization.DataContractAttribute> can be applied to a class or structure.</span></span> <span data-ttu-id="aacb4-120"><xref:System.Runtime.Serialization.DataMemberAttribute> kann auf ein Feld oder eine Eigenschaft angewendet werden, und die Felder und Eigenschaften, für die das Attribut übernommen wird, können entweder öffentlich oder privat sein.</span><span class="sxs-lookup"><span data-stu-id="aacb4-120">The <xref:System.Runtime.Serialization.DataMemberAttribute> can be applied to a field or a property, and the fields and properties to which the attribute is applied can be either public or private.</span></span> <span data-ttu-id="aacb4-121">Instanzen von Typen, auf die <xref:System.Runtime.Serialization.DataContractAttribute> angewendet wird, werden in WCF als Datenverträge bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="aacb4-121">Instances of types that have the <xref:System.Runtime.Serialization.DataContractAttribute> applied to them are referred to as data contracts in WCF.</span></span> <span data-ttu-id="aacb4-122">Sie werden mit <xref:System.Runtime.Serialization.DataContractSerializer> in XML serialisiert.</span><span class="sxs-lookup"><span data-stu-id="aacb4-122">They are serialized into XML using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>

<span data-ttu-id="aacb4-123">Nachfolgend finden Sie eine Liste der wichtigen Unterschiede zwischen der Verwendung von <xref:System.Runtime.Serialization.DataContractSerializer> und der Verwendung von <xref:System.Xml.Serialization.XmlSerializer> sowie der verschiedenen Attribute des <xref:System.Xml.Serialization>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="aacb4-123">The following is a list of the important differences between using the <xref:System.Runtime.Serialization.DataContractSerializer> and using the <xref:System.Xml.Serialization.XmlSerializer> and the various attributes of the <xref:System.Xml.Serialization> namespace.</span></span>

- <span data-ttu-id="aacb4-124"><xref:System.Xml.Serialization.XmlSerializer> und die Attribute des <xref:System.Xml.Serialization>-Namespace ermöglichen das Zuordnen von .NET Framework-Typen zu jedem gültigen Typ, der in XML-Schema definiert ist. Dadurch ermöglichen sie eine außerordentlich genaue Steuerung der Darstellung eines Typs in XML.</span><span class="sxs-lookup"><span data-stu-id="aacb4-124">The <xref:System.Xml.Serialization.XmlSerializer> and the attributes of the <xref:System.Xml.Serialization> namespace are designed to allow you to map .NET Framework types to any valid type defined in XML Schema, and so they provide for very precise control over how a type is represented in XML.</span></span> <span data-ttu-id="aacb4-125"><xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> bieten nur sehr wenige Möglichkeiten zur Steuerung der Darstellung eines Typs in XML.</span><span class="sxs-lookup"><span data-stu-id="aacb4-125">The <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> provide very little control over how a type is represented in XML.</span></span> <span data-ttu-id="aacb4-126">Angegeben werden können nur die Namespaces und Namen, die zum Darstellen des Typs und der Felder oder Eigenschaften in XML verwendet werden, sowie die Reihenfolge, in der die Felder und Eigenschaften in XML angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="aacb4-126">You can only specify the namespaces and names used to represent the type and its fields or properties in the XML, and the sequence in which the fields and properties appear in the XML:</span></span>

  ```csharp
  [DataContract(
  Namespace="urn:Contoso:2006:January:29",
  Name="LineItem")]
  public class LineItem
  {
        [DataMember(Name="ItemNumber",IsRequired=true,Order=0)]
        public string itemNumber;
        [DataMember(Name="Quantity",IsRequired=false,Order = 1)]
        public decimal quantity;
        [DataMember(Name="Price",IsRequired=false,Order = 2)]
        public decimal unitPrice;
  }
  ```

  <span data-ttu-id="aacb4-127">Alle anderen Aspekte der Struktur von XML, mit der der .NET-Typ dargestellt wird, werden von <xref:System.Runtime.Serialization.DataContractSerializer> bestimmt.</span><span class="sxs-lookup"><span data-stu-id="aacb4-127">Everything else about the structure of the XML used to represent the .NET type is determined by the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>

- <span data-ttu-id="aacb4-128">Dadurch, dass keine umfassenden Möglichkeiten zur Steuerung der Darstellung eines Typs in XML gewährt werden, wird der Serialisierungsprozess für <xref:System.Runtime.Serialization.DataContractSerializer> leicht vorhersehbar und die Optimierung dadurch vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="aacb4-128">By not permitting much control over how a type is to be represented in XML, the serialization process becomes highly predictable for the <xref:System.Runtime.Serialization.DataContractSerializer>, and, thereby, easier to optimize.</span></span> <span data-ttu-id="aacb4-129">Ein praktischer Vorteil des Entwurfs von <xref:System.Runtime.Serialization.DataContractSerializer> ist eine um etwa zehn Prozent höhere Leistung.</span><span class="sxs-lookup"><span data-stu-id="aacb4-129">A practical benefit of the design of the <xref:System.Runtime.Serialization.DataContractSerializer> is better performance, approximately ten percent better performance.</span></span>

- <span data-ttu-id="aacb4-130">Die Attribute für die Verwendung mit <xref:System.Xml.Serialization.XmlSerializer> geben nicht an, welche Felder oder Eigenschaften des Typs in XML serialisiert werden, wohingegen <xref:System.Runtime.Serialization.DataMemberAttribute> für die Verwendung mit <xref:System.Runtime.Serialization.DataContractSerializer> explizit die zu serialisierenden Felder oder Eigenschaften anzeigt.</span><span class="sxs-lookup"><span data-stu-id="aacb4-130">The attributes for use with the <xref:System.Xml.Serialization.XmlSerializer> do not indicate which fields or properties of the type are serialized into XML, whereas the <xref:System.Runtime.Serialization.DataMemberAttribute> for use with the <xref:System.Runtime.Serialization.DataContractSerializer> shows explicitly which fields or properties are serialized.</span></span> <span data-ttu-id="aacb4-131">Daher handelt es sich bei den Datenverträgen um explizite Verträge über die Struktur der Daten, die von einer Anwendung gesendet und empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-131">Therefore, data contracts are explicit contracts about the structure of the data that an application is to send and receive.</span></span>

- <span data-ttu-id="aacb4-132"><xref:System.Xml.Serialization.XmlSerializer> kann nur die öffentlichen Member eines .NET-Objekts in XML übersetzen, und <xref:System.Runtime.Serialization.DataContractSerializer> kann die Member eines Objekts unabhängig von den Zugriffsmodifizierern dieser Member in XML übersetzen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-132">The <xref:System.Xml.Serialization.XmlSerializer> can only translate the public members of a .NET object into XML, the <xref:System.Runtime.Serialization.DataContractSerializer> can translate the members of objects into XML regardless of the access modifiers of those members.</span></span>

- <span data-ttu-id="aacb4-133">Da die nicht öffentlichen Member der Typen in XML serialisiert werden können, gelten für <xref:System.Runtime.Serialization.DataContractSerializer> weniger Einschränkungen bezüglich der Vielfalt der .NET-Typen, die in XML serialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="aacb4-133">As a consequence of being able to serialize the non-public members of types into XML, the <xref:System.Runtime.Serialization.DataContractSerializer> has fewer restrictions on the variety of .NET types that it can serialize into XML.</span></span> <span data-ttu-id="aacb4-134">Insbesondere ist eine Übersetzung in XML-Typen wie <xref:System.Collections.Hashtable> möglich, mit denen die <xref:System.Collections.IDictionary>-Schnittstelle implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="aacb4-134">In particular, it can translate into XML types like <xref:System.Collections.Hashtable> that implement the <xref:System.Collections.IDictionary> interface.</span></span> <span data-ttu-id="aacb4-135"><xref:System.Runtime.Serialization.DataContractSerializer> ist mit einer weitaus höheren Wahrscheinlichkeit in der Lage, die Instanzen eines beliebigen zuvor vorhandenen .NET-Typs in XML zu serialisieren, ohne entweder die Definition des Typs ändern oder einen Wrapper dafür entwickeln zu müssen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-135">The <xref:System.Runtime.Serialization.DataContractSerializer> is much more likely to be able to serialize the instances of any pre-existing .NET type into XML without having to either modify the definition of the type or develop a wrapper for it.</span></span>

- <span data-ttu-id="aacb4-136">Da <xref:System.Runtime.Serialization.DataContractSerializer> auf die nicht öffentlichen Member eines Typs zugreifen kann, ist im Gegensatz zu <xref:System.Xml.Serialization.XmlSerializer> zudem volle Vertrauenswürdigkeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="aacb4-136">Another consequence of the <xref:System.Runtime.Serialization.DataContractSerializer> being able to access the non-public members of a type is that it requires full trust, whereas the <xref:System.Xml.Serialization.XmlSerializer> does not.</span></span> <span data-ttu-id="aacb4-137">Die voll vertrauenswürdige Code Zugriffsberechtigung bietet vollständigen Zugriff auf alle Ressourcen auf einem Computer, auf den über die Anmelde Informationen zugegriffen werden kann, unter denen der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="aacb4-137">The Full Trust code access permission gives complete access to all resources on a machine that can be accessed using the credentials under which the code is executing.</span></span> <span data-ttu-id="aacb4-138">Diese Option sollte mit Bedacht verwendet werden, da vollständig vertrauenswürdiger Code auf alle Ressourcen auf Ihrem Computer zugreift.</span><span class="sxs-lookup"><span data-stu-id="aacb4-138">This option should be used with care as fully trusted code accesses all resources on your machine.</span></span>

- <span data-ttu-id="aacb4-139"><xref:System.Runtime.Serialization.DataContractSerializer> bietet einige Unterstützung für Versionsverwaltung:</span><span class="sxs-lookup"><span data-stu-id="aacb4-139">The <xref:System.Runtime.Serialization.DataContractSerializer> incorporates some support for versioning:</span></span>

  - <span data-ttu-id="aacb4-140"><xref:System.Runtime.Serialization.DataMemberAttribute> verfügt über eine <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>-Eigenschaft, der der Wert false für Member zugewiesen werden kann, die neuen Versionen eines Datenvertrags hinzugefügt werden, die in früheren Versionen noch nicht vorhanden waren. Dadurch wird Anwendungen mit der neueren Version des Vertrags das Verarbeiten früherer Versionen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="aacb4-140">The <xref:System.Runtime.Serialization.DataMemberAttribute> has an <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property that can be assigned a value of false for members that are added to new versions of a data contract that were not present in earlier versions, thereby allowing applications with the newer version of the contract to be able to process earlier versions.</span></span>

  - <span data-ttu-id="aacb4-141">Wenn mit einem Datenvertrag die <xref:System.Runtime.Serialization.IExtensibleDataObject>-Schnittstelle implementiert wird, kann <xref:System.Runtime.Serialization.DataContractSerializer> das Übergeben von Membern gestattet werden, die in neueren Versionen eines Datenvertrags durch Anwendungen mit älteren Versionen des Vertrags definiert sind.</span><span class="sxs-lookup"><span data-stu-id="aacb4-141">By having a data contract implement the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface, one can allow the <xref:System.Runtime.Serialization.DataContractSerializer> to pass members defined in newer versions of a data contract through applications with earlier versions of the contract.</span></span>

<span data-ttu-id="aacb4-142">Ungeachtet aller Unterschiede ist das XML, in das <xref:System.Xml.Serialization.XmlSerializer> standardmäßig einen Typ serialisiert, semantisch identisch mit dem XML, in das <xref:System.Runtime.Serialization.DataContractSerializer> einen Typ serialisiert, vorausgesetzt, dass der Namespace für das XML explizit definiert ist.</span><span class="sxs-lookup"><span data-stu-id="aacb4-142">Despite all of the differences, the XML into which the <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="aacb4-143">Die folgende Klasse, die über Attribute für die Verwendung mit beiden serialisierungssoren verfügt, wird von und von in semantisch identisches XML übersetzt <xref:System.Xml.Serialization.XmlSerializer> <xref:System.Runtime.Serialization.DataContractAttribute> :</span><span class="sxs-lookup"><span data-stu-id="aacb4-143">The following class, which has attributes for use with both of the serializers, is translated into semantically identical XML by the <xref:System.Xml.Serialization.XmlSerializer> and by the <xref:System.Runtime.Serialization.DataContractAttribute>:</span></span>

```csharp
[Serializable]
[XmlRoot(Namespace="urn:Contoso:2006:January:29")]
[DataContract(Namespace="urn:Contoso:2006:January:29")]
public class LineItem
{
     [DataMember]
     public string ItemNumber;
     [DataMember]
     public decimal Quantity;
     [DataMember]
     public decimal UnitPrice;
}
```

<span data-ttu-id="aacb4-144">Das Windows Software Development Kit (SDK) umfasst ein Befehlszeilen Tool namens [Service Model Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="aacb4-144">The Windows software development kit (SDK) includes a command-line tool called the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="aacb4-145">Wie das Tool XSD. exe, das mit ASP.NET-Webdiensten verwendet wird, kann Svcutil. exe Definitionen von .NET-Datentypen aus dem XML-Schema generieren.</span><span class="sxs-lookup"><span data-stu-id="aacb4-145">Like the xsd.exe tool used with ASP.NET Web services, Svcutil.exe can generate definitions of .NET data types from XML Schema.</span></span> <span data-ttu-id="aacb4-146">Bei den Typen handelt es sich um Datenverträge, sofern <xref:System.Runtime.Serialization.DataContractSerializer> XML in dem vom XML-Schema definierten Format ausgeben kann; andernfalls sind sie für die Serialisierung mithilfe von <xref:System.Xml.Serialization.XmlSerializer> vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-146">The types are data contracts if the <xref:System.Runtime.Serialization.DataContractSerializer> can emit XML in the format defined by the XML Schema; otherwise, they are intended for serialization using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="aacb4-147">Svcutil. exe kann auch ein XML-Schema aus Daten Verträgen mithilfe seines `dataContractOnly` Schalters generieren.</span><span class="sxs-lookup"><span data-stu-id="aacb4-147">Svcutil.exe can also generate an XML schema from data contracts by using its `dataContractOnly` switch.</span></span>

> [!NOTE]
> <span data-ttu-id="aacb4-148">Obwohl die ASP.NET-Webdienste den verwenden <xref:System.Xml.Serialization.XmlSerializer> , und der WCF ASP.NET-Kompatibilitätsmodus bewirkt, dass WCF-Dienste das Verhalten von ASP.NET-Webdiensten imitieren, schränkt die ASP.net-Kompatibilitäts Option nicht auf die Verwendung von ein <xref:System.Xml.Serialization.XmlSerializer> .</span><span class="sxs-lookup"><span data-stu-id="aacb4-148">Although ASP.NET Web services use the <xref:System.Xml.Serialization.XmlSerializer>, and WCF ASP.NET compatibility mode makes WCF services mimic the behavior of ASP.NET Web services, the ASP.NET compatibility option does not restrict one to using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="aacb4-149"><xref:System.Runtime.Serialization.DataContractSerializer> kann nach wie vor verwendet werden, während die Dienste im ASP.NET-Kompatibilitätsmodus ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-149">One can still use the <xref:System.Runtime.Serialization.DataContractSerializer> with services running in the ASP.NET compatibility mode.</span></span>

## <a name="service-development"></a><span data-ttu-id="aacb4-150">Dienstentwicklung</span><span class="sxs-lookup"><span data-stu-id="aacb4-150">Service Development</span></span>

<span data-ttu-id="aacb4-151">Soll ein Dienst mithilfe von ASP.NET entwickelt werden, wird einer Klasse üblicherweise das <xref:System.Web.Services.WebService>-Attribut hinzugefügt, und <xref:System.Web.Services.WebMethodAttribute> wird einer beliebigen Methode dieser Klasse, bei denen es sich um Vorgänge des Diensts handeln soll, hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="aacb4-151">To develop a service using ASP.NET, it has been customary to add the <xref:System.Web.Services.WebService> attribute to a class, and the <xref:System.Web.Services.WebMethodAttribute> to any of that class’ methods that are to be operations of the service:</span></span>

```csharp
[WebService]
public class Service : T:System.Web.Services.WebService
{
    [WebMethod]
    public string Echo(string input)
    {
       return input;
    }
}
```

<span data-ttu-id="aacb4-152">Seit ASP.NET 2.0 steht eine Option zur Verfügung, mit der der <xref:System.Web.Services.WebService> und das <xref:System.Web.Services.WebMethodAttribute> des Attributs einer Schnittstelle und nicht einer Klasse hinzugefügt werden und eine Klasse zum Implementieren der Schnittstelle geschrieben wird:</span><span class="sxs-lookup"><span data-stu-id="aacb4-152">ASP.NET 2.0 introduced the option of adding the attribute <xref:System.Web.Services.WebService> and <xref:System.Web.Services.WebMethodAttribute> to an interface rather than to a class, and writing a class to implement the interface:</span></span>

```csharp
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

<span data-ttu-id="aacb4-153">Die Verwendung dieser Option wird empfohlen, da die Schnittstelle mit dem <xref:System.Web.Services.WebService>-Attribut einen Vertrag für die vom Dienst ausgeführten Vorgänge darstellt. Dieser Vertrag kann erneut mit verschiedenen Klassen verwendet werden, die denselben Vertrag möglicherweise auf unterschiedliche Art und Weise implementieren.</span><span class="sxs-lookup"><span data-stu-id="aacb4-153">Using this option is to be preferred, because the interface with the <xref:System.Web.Services.WebService> attribute constitutes a contract for the operations performed by the service that can be reused with various classes that might implement that same contract in different ways.</span></span>

<span data-ttu-id="aacb4-154">Ein WCF-Dienst wird bereitgestellt, indem ein oder mehrere WCF-Endpunkte definiert werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-154">A WCF service is provided by defining one or more WCF endpoints.</span></span> <span data-ttu-id="aacb4-155">Ein Endpunkt wird durch eine Adresse, eine Bindung und einen Dienstvertrag definiert.</span><span class="sxs-lookup"><span data-stu-id="aacb4-155">An endpoint is defined by an address, a binding and a service contract.</span></span> <span data-ttu-id="aacb4-156">Die Adresse wird am Standort des Diensts definiert.</span><span class="sxs-lookup"><span data-stu-id="aacb4-156">The address defines where the service is located.</span></span> <span data-ttu-id="aacb4-157">Die Bindung gibt an, wie eine Kommunikation mit dem Dienst stattfindet.</span><span class="sxs-lookup"><span data-stu-id="aacb4-157">The binding specifies how to communicate with the service.</span></span> <span data-ttu-id="aacb4-158">Mit dem Dienstvertrag werden die Vorgänge, die der Dienst ausführen kann, definiert.</span><span class="sxs-lookup"><span data-stu-id="aacb4-158">The service contract defines the operations that the service can perform.</span></span>

<span data-ttu-id="aacb4-159">Der Dienstvertrag wird normalerweise zuerst definiert, indem einer Schnittstelle <xref:System.ServiceModel.ServiceContractAttribute> und <xref:System.ServiceModel.OperationContractAttribute> hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="aacb4-159">The service contract is usually defined first, by adding <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> to an interface:</span></span>

```csharp
[ServiceContract]
public interface IEcho
{
     [OperationContract]
     string Echo(string input);
}
```

<span data-ttu-id="aacb4-160">Der <xref:System.ServiceModel.ServiceContractAttribute> gibt an, dass die-Schnittstelle einen WCF-Dienstvertrag definiert, und <xref:System.ServiceModel.OperationContractAttribute> gibt an, welche, sofern vorhanden, der Methoden der-Schnittstelle Vorgänge des Dienstvertrags definieren.</span><span class="sxs-lookup"><span data-stu-id="aacb4-160">The <xref:System.ServiceModel.ServiceContractAttribute> specifies that the interface defines a WCF service contract, and the <xref:System.ServiceModel.OperationContractAttribute> indicates which, if any, of the methods of the interface define operations of the service contract.</span></span>

<span data-ttu-id="aacb4-161">Nach der Definition eines Dienstvertrags wird dieser in einer Klasse implementiert, indem die Klasse die Schnittstelle implementiert, nach der der Dienstvertrag definiert ist:</span><span class="sxs-lookup"><span data-stu-id="aacb4-161">Once a service contract has been defined, it is implemented in a class, by having the class implement the interface by which the service contract is defined:</span></span>

```csharp
public class Service : IEcho
{
    public string Echo(string input)
    {
       return input;
    }
}
```

<span data-ttu-id="aacb4-162">Eine Klasse, die einen Dienstvertrag implementiert, wird in WCF als Diensttyp bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="aacb4-162">A class that implements a service contract is referred to as a service type in WCF.</span></span>

<span data-ttu-id="aacb4-163">Der nächste Schritt besteht in der Zuordnung einer Adresse und einer Bindung zu einem Diensttyp.</span><span class="sxs-lookup"><span data-stu-id="aacb4-163">The next step is to associate an address and a binding with a service type.</span></span> <span data-ttu-id="aacb4-164">Dies erfolgt in der Regel in einer Konfigurationsdatei, entweder durch direktes Bearbeiten der Datei oder durch Verwendung eines mit WCF bereitgestellten Konfigurations-Editors.</span><span class="sxs-lookup"><span data-stu-id="aacb4-164">That is typically done in a configuration file, either by editing the file directly, or by using a configuration editor provided with WCF.</span></span> <span data-ttu-id="aacb4-165">Hier sehen Sie ein Beispiel einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="aacb4-165">Here is an example of a configuration file.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
     <system.serviceModel>
      <services>
      <service name="Service ">
       <endpoint
        address="EchoService"
        binding="basicHttpBinding"
        contract="IEchoService "/>
      </service>
      </services>
     </system.serviceModel>
</configuration>
```

<span data-ttu-id="aacb4-166">Die Bindung gibt den Satz der Protokolle für die Kommunikation mit der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="aacb4-166">The binding specifies the set of protocols for communicating with the application.</span></span> <span data-ttu-id="aacb4-167">In der folgenden Tabelle sind die vom System bereitgestellten Bindungen, die allgemeine Optionen darstellen, aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="aacb4-167">The following table lists the system-provided bindings that represent common options.</span></span>

|<span data-ttu-id="aacb4-168">Name</span><span class="sxs-lookup"><span data-stu-id="aacb4-168">Name</span></span>|<span data-ttu-id="aacb4-169">Zweck</span><span class="sxs-lookup"><span data-stu-id="aacb4-169">Purpose</span></span>|
|----------|-------------|
|<span data-ttu-id="aacb4-170">BasicHttpBinding</span><span class="sxs-lookup"><span data-stu-id="aacb4-170">BasicHttpBinding</span></span>|<span data-ttu-id="aacb4-171">Interoperabilität mit Webdiensten und Clients, die WS-BasicProfile 1.1 und Basic Security Profile 1.0 unterstützen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-171">Interoperability with Web services and clients supporting the WS-BasicProfile 1.1 and Basic Security Profile 1.0.</span></span>|
|<span data-ttu-id="aacb4-172">WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="aacb4-172">WSHttpBinding</span></span>|<span data-ttu-id="aacb4-173">Interoperabilität mit Webdiensten und Clients, die die Protokolle vom Typ WS-\* über HTTP unterstützen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-173">Interoperability with Web services and clients that support the WS-\* protocols over HTTP.</span></span>|
|<span data-ttu-id="aacb4-174">WSDualHttpBinding</span><span class="sxs-lookup"><span data-stu-id="aacb4-174">WSDualHttpBinding</span></span>|<span data-ttu-id="aacb4-175">Duplex-HTTP-Kommunikation, bei der der Empfänger einer ursprünglichen Nachricht nicht direkt dem ursprünglichen Absender antwortet, jedoch eine beliebige Anzahl von Antworten über einen bestimmten Zeitraum übertragen kann, indem er HTTP in Übereinstimmung mit WS-\*-Protokollen verwendet.</span><span class="sxs-lookup"><span data-stu-id="aacb4-175">Duplex HTTP communication, by which the receiver of an initial message does not reply directly to the initial sender, but may transmit any number of responses over a period of time by using HTTP in conformity with WS-\* protocols.</span></span>|
|<span data-ttu-id="aacb4-176">WSFederationBinding</span><span class="sxs-lookup"><span data-stu-id="aacb4-176">WSFederationBinding</span></span>|<span data-ttu-id="aacb4-177">HTTP-Kommunikation, in der der Zugriff auf Ressourcen eines Diensts auf Basis der Anmeldeinformationen gesteuert wird, die von einem explizit identifizierten Anmeldeinformationsanbieter ausgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-177">HTTP communication, in which access to the resources of a service can be controlled based on credentials issued by an explicitly-identified credential provider.</span></span>|
|<span data-ttu-id="aacb4-178">NetTcpBinding</span><span class="sxs-lookup"><span data-stu-id="aacb4-178">NetTcpBinding</span></span>|<span data-ttu-id="aacb4-179">Sichere, zuverlässige, leistungsstarke Kommunikation zwischen WCF-Software Entitäten in einem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="aacb4-179">Secure, reliable, high-performance communication between WCF software entities across a network.</span></span>|
|<span data-ttu-id="aacb4-180">NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="aacb4-180">NetNamedPipeBinding</span></span>|<span data-ttu-id="aacb4-181">Sichere, zuverlässige und leistungsstarke Kommunikation zwischen WCF-Software Entitäten auf dem gleichen Computer.</span><span class="sxs-lookup"><span data-stu-id="aacb4-181">Secure, reliable, high-performance communication between WCF software entities on the same machine.</span></span>|
|<span data-ttu-id="aacb4-182">NetMsmqBinding</span><span class="sxs-lookup"><span data-stu-id="aacb4-182">NetMsmqBinding</span></span>|<span data-ttu-id="aacb4-183">Kommunikation zwischen WCF-Software Entitäten mithilfe von MSMQ.</span><span class="sxs-lookup"><span data-stu-id="aacb4-183">Communication between WCF software entities by using MSMQ.</span></span>|
|<span data-ttu-id="aacb4-184">MsmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="aacb4-184">MsmqIntegrationBinding</span></span>|<span data-ttu-id="aacb4-185">Kommunikation zwischen einer WCF-Software Entität und einer anderen Software Entität unter Verwendung von MSMQ.</span><span class="sxs-lookup"><span data-stu-id="aacb4-185">Communication between a WCF software entity and another software entity by using MSMQ.</span></span>|
|<span data-ttu-id="aacb4-186">NetPeerTcpBinding</span><span class="sxs-lookup"><span data-stu-id="aacb4-186">NetPeerTcpBinding</span></span>|<span data-ttu-id="aacb4-187">Kommunikation zwischen WCF-Software Entitäten mithilfe von Windows-Peer-zu-Peer-Netzwerken.</span><span class="sxs-lookup"><span data-stu-id="aacb4-187">Communication between WCF software entities by using Windows Peer-to-Peer Networking.</span></span>|

<span data-ttu-id="aacb4-188">Mit der vom System bereitgestellten Bindung, <xref:System.ServiceModel.BasicHttpBinding>, wird der Satz der von ASP.NET-Webdiensten unterstützten Protokolle integriert.</span><span class="sxs-lookup"><span data-stu-id="aacb4-188">The system-provided binding, <xref:System.ServiceModel.BasicHttpBinding>, incorporates the set of protocols supported by ASP.NET Web services.</span></span>

<span data-ttu-id="aacb4-189">Benutzerdefinierte Bindungen für WCF-Anwendungen können problemlos als Auflistungen der Bindungs Element Klassen definiert werden, die von WCF zum Implementieren einzelner Protokolle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-189">Custom bindings for WCF applications are easily defined as collections of the binding element classes that WCF uses to implement individual protocols.</span></span> <span data-ttu-id="aacb4-190">Neue Bindungselemente können zur Darstellung zusätzlicher Protokolle geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-190">New binding elements can be written to represent additional protocols.</span></span>

<span data-ttu-id="aacb4-191">Das interne Verhalten der Diensttypen kann mithilfe der Eigenschaften einer Klassenfamilie mit der Bezeichnung Verhaltensweisen angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-191">The internal behavior of service types can be adjusted using the properties of a family of classes called behaviors.</span></span> <span data-ttu-id="aacb4-192">Hier wird mit der <xref:System.ServiceModel.ServiceBehaviorAttribute>-Klasse angegeben, dass der Diensttyp Multithread sein soll.</span><span class="sxs-lookup"><span data-stu-id="aacb4-192">Here, the <xref:System.ServiceModel.ServiceBehaviorAttribute> class is used to specify that the service type is to be multithreaded.</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple)]
public class DerivativesCalculatorServiceType: IDerivativesCalculator
```

<span data-ttu-id="aacb4-193">Einige Verhaltensweisen wie zum Beispiel <xref:System.ServiceModel.ServiceBehaviorAttribute> sind Attribute.</span><span class="sxs-lookup"><span data-stu-id="aacb4-193">Some behaviors, like <xref:System.ServiceModel.ServiceBehaviorAttribute>, are attributes.</span></span> <span data-ttu-id="aacb4-194">Andere Verhaltensweisen (diejenigen mit den Eigenschaften, die normalerweise von Administratoren festgelegt werden) können in der Konfiguration einer Anwendung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-194">Others, the ones with properties that administrators would want to set, can be modified in the configuration of an application.</span></span>

<span data-ttu-id="aacb4-195">In Programmierdiensttypen wird häufig die <xref:System.ServiceModel.OperationContext>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="aacb4-195">In programming service types, frequent use is made of the <xref:System.ServiceModel.OperationContext> class.</span></span> <span data-ttu-id="aacb4-196">Die statische <xref:System.ServiceModel.OperationContext.Current%2A>-Eigenschaft bietet Zugriff auf Informationen zu dem Kontext, in dem ein Vorgang ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="aacb4-196">Its static <xref:System.ServiceModel.OperationContext.Current%2A> property provides access to information about the context in which an operation is running.</span></span> <span data-ttu-id="aacb4-197"><xref:System.ServiceModel.OperationContext> ist für die Klassen <xref:System.Web.HttpContext> und <xref:System.EnterpriseServices.ContextUtil> ähnlich.</span><span class="sxs-lookup"><span data-stu-id="aacb4-197"><xref:System.ServiceModel.OperationContext> is similar to both the <xref:System.Web.HttpContext> and <xref:System.EnterpriseServices.ContextUtil> classes.</span></span>

## <a name="hosting"></a><span data-ttu-id="aacb4-198">Hosting</span><span class="sxs-lookup"><span data-stu-id="aacb4-198">Hosting</span></span>

<span data-ttu-id="aacb4-199">ASP.NET-Webdienste werden in eine Klassenbibliothekassembly kompiliert.</span><span class="sxs-lookup"><span data-stu-id="aacb4-199">ASP.NET Web services are compiled into a class library assembly.</span></span> <span data-ttu-id="aacb4-200">Eine als Dienstdatei bezeichnete Datei wird bereitgestellt, die die Erweiterung ASMX aufweist und eine `@ WebService`-Anweisung zur Identifizierung der Klasse mit dem Code für den Dienst und die Assembly beinhaltet, in der sich die Klasse befindet.</span><span class="sxs-lookup"><span data-stu-id="aacb4-200">A file called the service file is provided that has the extension .asmx and contains an `@ WebService` directive that identifies the class that contains the code for the service and the assembly in which it is located.</span></span>

`<%@ WebService Language="C#" Class="Service,ServiceAssembly" %>`

<span data-ttu-id="aacb4-201">Die Dienstdatei wird in das Stammverzeichnis einer ASP.NET-Anwendung in Internetinformationsdienste (IIS) und die Assembly in das \bin-Unterverzeichnis dieses Anwendungsstammverzeichnisses kopiert.</span><span class="sxs-lookup"><span data-stu-id="aacb4-201">The service file is copied into an ASP.NET application root in Internet Information Services (IIS), and the assembly is copied into the \bin subdirectory of that application root.</span></span> <span data-ttu-id="aacb4-202">Die Anwendung ist anschließend durch Angabe der URL (Uniform Resource Locator) der Dienstdatei im Stammverzeichnis der Anwendung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="aacb4-202">The application is then accessible by using the uniform resource locator (URL) of the service file in the application root.</span></span>

<span data-ttu-id="aacb4-203">WCF-Dienste können problemlos innerhalb von IIS 5,1 oder 6,0, dem Windows Process Activation Service (was) gehostet werden, der als Teil von IIS 7,0 und innerhalb einer beliebigen .NET-Anwendung bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="aacb4-203">WCF services can readily be hosted within IIS 5.1 or 6.0, the Windows Process Activation Service (WAS) that is provided as part of IIS 7.0, and within any .NET application.</span></span> <span data-ttu-id="aacb4-204">Soll ein Dienst in IIS 5.1 oder 6.0 gehostet werden, muss HTTP als Kommunikationstransportprotokoll verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-204">To host a service in IIS 5.1 or 6.0, the service must use HTTP as the communications transport protocol.</span></span>

<span data-ttu-id="aacb4-205">Soll ein Dienst innerhalb von IIS 5, 6.0 oder WAS gehostet werden, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="aacb4-205">To host a service within IIS 5.1, 6.0 or within WAS, use the follows steps:</span></span>

1. <span data-ttu-id="aacb4-206">Kompilieren Sie den Diensttyp in eine Klassenbibliothekassembly.</span><span class="sxs-lookup"><span data-stu-id="aacb4-206">Compile the service type into a class library assembly.</span></span>

2. <span data-ttu-id="aacb4-207">Erstellen Sie eine Dienstdatei mit einer SVC-Erweiterung und einer `@ ServiceHost`-Anweisung zur Identifizierung des Diensttyps:</span><span class="sxs-lookup"><span data-stu-id="aacb4-207">Create a service file with a .svc extension with an `@ ServiceHost` directive to identify the service type:</span></span>

    `<%@ServiceHost language="c#" Service="MyService" %>`

3. <span data-ttu-id="aacb4-208">Kopieren Sie die Dienstdatei in ein virtuelles Verzeichnis und die Assembly in das \bin-Unterverzeichnis des virtuellen Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="aacb4-208">Copy the service file into a virtual directory, and the assembly into the \bin subdirectory of that virtual directory.</span></span>

4. <span data-ttu-id="aacb4-209">Kopieren Sie die Konfigurationsdatei in das virtuelle Verzeichnis, und nennen Sie die Datei Web.config.</span><span class="sxs-lookup"><span data-stu-id="aacb4-209">Copy the configuration file into the virtual directory, and name it Web.config.</span></span>

<span data-ttu-id="aacb4-210">Die Anwendung ist anschließend durch Angabe der URL der Dienstdatei im Stammverzeichnis der Anwendung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="aacb4-210">The application is then accessible by using the URL of the service file in the application root.</span></span>

<span data-ttu-id="aacb4-211">Um einen WCF-Dienst in einer .NET-Anwendung zu hosten, kompilieren Sie den Diensttyp in eine Klassenbibliotheksassembly, auf die von der Anwendung verwiesen wird, und Programmieren Sie die Anwendung, um den Dienst <xref:System.ServiceModel.ServiceHost> mithilfe der</span><span class="sxs-lookup"><span data-stu-id="aacb4-211">To host a WCF service within a .NET application, compile the service type into a class library assembly referenced by the application, and program the application to host the service using the <xref:System.ServiceModel.ServiceHost> class.</span></span> <span data-ttu-id="aacb4-212">Nachfolgend finden Sie ein Beispiel für die erforderliche grundlegende Programmierung:</span><span class="sxs-lookup"><span data-stu-id="aacb4-212">The following is an example of the basic programming required:</span></span>

```csharp
string httpBaseAddress = "http://www.contoso.com:8000/";
string tcpBaseAddress = "net.tcp://www.contoso.com:8080/";

Uri httpBaseAddressUri = new Uri(httpBaseAddress);
Uri tcpBaseAddressUri = new Uri(tcpBaseAddress);

Uri[] baseAddresses = new Uri[] {
 httpBaseAddressUri,
 tcpBaseAddressUri};

using(ServiceHost host = new ServiceHost(
typeof(Service), //"Service" is the name of the service type baseAddresses))
{
     host.Open();

     […] //Wait to receive messages
     host.Close();
}
```

<span data-ttu-id="aacb4-213">In diesem Beispiel erfahren Sie, wie Adressen für mindestens ein Transportprotokoll bei der Erstellung von <xref:System.ServiceModel.ServiceHost> angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-213">This example shows how addresses for one or more transport protocols are specified in the construction of a <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="aacb4-214">Diese Adressen werden als Basisadressen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="aacb4-214">These addresses are referred to as base addresses.</span></span>

<span data-ttu-id="aacb4-215">Die Adresse, die für einen beliebigen Endpunkt eines WCF-Diensts bereitgestellt wird, ist eine Adresse relativ zur Basisadresse des Endpunkts des Endpunkts.</span><span class="sxs-lookup"><span data-stu-id="aacb4-215">The address provided for any endpoint of a WCF service is an address relative to a base address of the endpoint’s host.</span></span> <span data-ttu-id="aacb4-216">Der Host kann über eine Basisadresse für jedes Kommunikationstransportprotokoll verfügen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-216">The host can have one base address for each communication transport protocol.</span></span> <span data-ttu-id="aacb4-217">In der Beispielkonfiguration in der vorangegangenen Konfigurationsdatei verwendet die für den Endpunkt gewählte <xref:System.ServiceModel.BasicHttpBinding> HTTP als Transportprotokoll, sodass die Adresse des Endpunkts (`EchoService`) relativ zur HTTP-Basisadresse des Hosts ist.</span><span class="sxs-lookup"><span data-stu-id="aacb4-217">In the sample configuration in the preceding configuration file, the <xref:System.ServiceModel.BasicHttpBinding> selected for the endpoint uses HTTP as the transport protocol, so the address of the endpoint, `EchoService`, is relative to the host’s HTTP base address.</span></span> <span data-ttu-id="aacb4-218">Im Fall des Hosts im vorherigen Beispiel lautet die HTTP-Basisadresse `http://www.contoso.com:8000/` .</span><span class="sxs-lookup"><span data-stu-id="aacb4-218">In the case of the host in the preceding example, the HTTP base address is `http://www.contoso.com:8000/`.</span></span> <span data-ttu-id="aacb4-219">Für einen in IIS oder WAS gehosteten Dienst ist die Basisadresse die URL der Dienstdatei des Diensts.</span><span class="sxs-lookup"><span data-stu-id="aacb4-219">For a service hosted within IIS or WAS, the base address is the URL of the service’s service file.</span></span>

<span data-ttu-id="aacb4-220">Nur in IIS oder was gehostete Dienste, die ausschließlich mit HTTP als Transportprotokoll konfiguriert sind, können zur Verwendung der WCF ASP.NET Compatibility Mode-Option verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-220">Only services hosted in IIS or WAS, and which are configured with HTTP as the transport protocol exclusively, can be made to use WCF ASP.NET compatibility mode option.</span></span> <span data-ttu-id="aacb4-221">Das Aktivieren dieser Option erfordert die folgenden Schritte.</span><span class="sxs-lookup"><span data-stu-id="aacb4-221">Turning that option on requires the following steps.</span></span>

1. <span data-ttu-id="aacb4-222">Der Programmierer muss das <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute>-Attribut dem Diensttyp hinzufügen und angeben, dass der ASP.NET-Kompatibilitätsmodus entweder zulässig oder erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="aacb4-222">The programmer must add the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> attribute to the service type and specify that ASP.NET compatibility mode is either allowed or required.</span></span>

    ```csharp
    [System.ServiceModel.Activation.AspNetCompatibilityRequirements(
          RequirementsMode=AspNetCompatibilityRequirementsMode.Require)]
    public class DerivativesCalculatorServiceType: IDerivativesCalculator
    ```

2. <span data-ttu-id="aacb4-223">Der Administrator muss die Anwendung so konfigurieren, dass der ASP.NET-Kompatibilitätsmodus verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aacb4-223">The administrator must configure the application to use the ASP.NET compatibility mode.</span></span>

    ```xml
    <configuration>
         <system.serviceModel>
          <services>
          […]
          </services>
          <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
        </system.serviceModel>
    </configuration>
    ```

    <span data-ttu-id="aacb4-224">WCF-Anwendungen können auch so konfiguriert werden, dass Sie ASMX als Erweiterung für Ihre Dienst Dateien anstelle von SVC verwenden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-224">WCF applications can also be configured to use .asmx as the extension for their service files rather than .svc.</span></span>

    ```xml
    <system.web>
         <compilation>
          <compilation debug="true">
          <buildProviders>
           <remove extension=".asmx"/>
           <add extension=".asmx"
            type="System.ServiceModel.ServiceBuildProvider,
            System.ServiceModel,
            Version=3.0.0.0,
            Culture=neutral,
            PublicKeyToken=b77a5c561934e089" />
          </buildProviders>
          </compilation>
         </compilation>
    </system.web>
    ```

    <span data-ttu-id="aacb4-225">Diese Option kann Ihnen dabei ersparen, Clients zu ändern, die für die Verwendung der URLs von ASMX-Dienst Dateien konfiguriert sind, wenn Sie einen Dienst für die Verwendung von WCF ändern.</span><span class="sxs-lookup"><span data-stu-id="aacb4-225">That option can save you from having to modify clients that are configured to use the URLs of .asmx service files when modifying a service to use WCF.</span></span>

## <a name="client-development"></a><span data-ttu-id="aacb4-226">Cliententwicklung</span><span class="sxs-lookup"><span data-stu-id="aacb4-226">Client Development</span></span>

<span data-ttu-id="aacb4-227">Clients für ASP.NET-Webdienste werden mithilfe des Befehlszeilentools WSDL.exe generiert, das die URL der ASMX-Datei als Eingabe bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="aacb4-227">Clients for ASP.NET Web services are generated using the command-line tool, WSDL.exe, which provides the URL of the .asmx file as input.</span></span> <span data-ttu-id="aacb4-228">Das entsprechende von WCF bereitgestellte Tool ist das [Service Model Metadata Utility-Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="aacb4-228">The corresponding tool provided by WCF is [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="aacb4-229">Es generiert ein Codemodul mit der Definition des Dienstvertrags und der Definition einer WCF-Client Klasse.</span><span class="sxs-lookup"><span data-stu-id="aacb4-229">It generates a code module with the definition of the service contract and the definition of a WCF client class.</span></span> <span data-ttu-id="aacb4-230">Es generiert auch eine Konfigurationsdatei mit der Adresse und der Bindung des Diensts.</span><span class="sxs-lookup"><span data-stu-id="aacb4-230">It also generates a configuration file with the address and binding of the service.</span></span>

<span data-ttu-id="aacb4-231">Beim Programmieren eines Clients eines Remotediensts ist es in der Regel empfehlenswert, gemäß einem asynchronen Muster zu programmieren.</span><span class="sxs-lookup"><span data-stu-id="aacb4-231">In programming a client of a remote service it is generally advisable to program according to an asynchronous pattern.</span></span> <span data-ttu-id="aacb4-232">Der vom Tool WSDL.exe generierte Code beinhaltet standardmäßig sowohl ein synchrones als auch ein asynchrones Muster.</span><span class="sxs-lookup"><span data-stu-id="aacb4-232">The code generated by the WSDL.exe tool always provides for both a synchronous and an asynchronous pattern by default.</span></span> <span data-ttu-id="aacb4-233">Der durch das [Service Model Metadata Utility-Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generierte Code kann für beide Muster bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-233">The code generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) can provide for either pattern.</span></span> <span data-ttu-id="aacb4-234">Standardmäßig wird das synchrone Muster bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="aacb4-234">It provides for the synchronous pattern by default.</span></span> <span data-ttu-id="aacb4-235">Bei Ausführung des Tools mit `/async` wird durch den generierten Code das asynchrone Muster bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="aacb4-235">If the tool is executed with the `/async` switch, then the generated code provides for the asynchronous pattern.</span></span>

<span data-ttu-id="aacb4-236">Es gibt keine Garantie, dass Namen in den von ASP generierten WCF-Client Klassen vorhanden sind. Das Tool "WSDL. exe" von NET entspricht standardmäßig den Namen in WCF-Client Klassen, die vom Tool "Svcutil. exe" generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-236">There is no guarantee that names in the WCF client classes generated by ASP.NET’s WSDL.exe tool, by default, match the names in WCF client classes generated by the Svcutil.exe tool.</span></span> <span data-ttu-id="aacb4-237">Insbesondere wird den Namen der Eigenschaften von Klassen, die mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden müssen, standardmäßig die Suffixeigenschaft im vom Tool Svcutil.exe generierten Code zugewiesen. Beim Tool WSDL.exe ist dies nicht der Fall.</span><span class="sxs-lookup"><span data-stu-id="aacb4-237">In particular, the names of the properties of classes that have to be serialized using the <xref:System.Xml.Serialization.XmlSerializer> are, by default, given the suffix Property in the code generated by the Svcutil.exe tool, which is not the case with the WSDL.exe tool.</span></span>

## <a name="message-representation"></a><span data-ttu-id="aacb4-238">Nachrichtendarstellung</span><span class="sxs-lookup"><span data-stu-id="aacb4-238">Message Representation</span></span>

<span data-ttu-id="aacb4-239">Die Header der SOAP-Nachrichten, die von ASP.NET-Webdiensten gesendet und empfangen werden, können angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-239">The headers of the SOAP messages sent and received by ASP.NET Web services can be customized.</span></span> <span data-ttu-id="aacb4-240">Eine Klasse wird von <xref:System.Web.Services.Protocols.SoapHeader> abgeleitet, um die Struktur des Headers zu definieren. Anschließend wird mit <xref:System.Web.Services.Protocols.SoapHeaderAttribute> das Vorhandensein des Headers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="aacb4-240">A class is derived from <xref:System.Web.Services.Protocols.SoapHeader> to define the structure of the header, and then the <xref:System.Web.Services.Protocols.SoapHeaderAttribute> is used to indicate the presence of the header.</span></span>

```csharp
public class SomeProtocol : SoapHeader
{
     public long CurrentValue;
     public long Total;
}

[WebService]
public interface IEcho
{
     SomeProtocol ProtocolHeader
     {
      get;
     set;
     }

     [WebMethod]
     [SoapHeader("ProtocolHeader")]
     string PlaceOrders(PurchaseOrderType order);
}

public class Service: WebService, IEcho
{
     private SomeProtocol protocolHeader;

     public SomeProtocol ProtocolHeader
     {
         get
         {
              return this.protocolHeader;
         }

         set
         {
              this.protocolHeader = value;
         }
     }

     string PlaceOrders(PurchaseOrderType order)
     {
         long currentValue = this.protocolHeader.CurrentValue;
     }
}
```

<span data-ttu-id="aacb4-241">Der WCF stellt die Attribute,, und bereit, <xref:System.ServiceModel.MessageContractAttribute> <xref:System.ServiceModel.MessageHeaderAttribute> <xref:System.ServiceModel.MessageBodyMemberAttribute> um die Struktur der SOAP-Nachrichten zu beschreiben, die von einem Dienst gesendet und empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-241">The WCF provides the attributes, <xref:System.ServiceModel.MessageContractAttribute>, <xref:System.ServiceModel.MessageHeaderAttribute>, and <xref:System.ServiceModel.MessageBodyMemberAttribute> to describe the structure of the SOAP messages sent and received by a service.</span></span>

```csharp
[DataContract]
public class SomeProtocol
{
     [DataMember]
     public long CurrentValue;
     [DataMember]
     public long Total;
}

[DataContract]
public class Item
{
     [DataMember]
     public string ItemNumber;
     [DataMember]
     public decimal Quantity;
     [DataMember]
     public decimal UnitPrice;
}

[MessageContract]
public class ItemMessage
{
     [MessageHeader]
     public SomeProtocol ProtocolHeader;
     [MessageBody]
     public Item Content;
}

[ServiceContract]
public interface IItemService
{
     [OperationContract]
     public void DeliverItem(ItemMessage itemMessage);
}
```

<span data-ttu-id="aacb4-242">Diese Syntax ermöglicht eine explizite Darstellung der Nachrichtenstruktur, wohingegen die Struktur der Nachrichten vom Code eines ASP.NET-Webdiensts impliziert wird.</span><span class="sxs-lookup"><span data-stu-id="aacb4-242">This syntax yields an explicit representation of the structure of the messages, whereas the structure of messages is implied by the code of an ASP.NET Web service.</span></span> <span data-ttu-id="aacb4-243">Außerdem werden Nachrichten Header in der ASP.NET-Syntax als Eigenschaften des Dienstanbieter dargestellt, wie z. b. die- `ProtocolHeader` Eigenschaft im vorherigen Beispiel, wohingegen Sie in der WCF-Syntax genauer als Eigenschaften von Nachrichten dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-243">Also, in the ASP.NET syntax, message headers are represented as properties of the service, such as the `ProtocolHeader` property in the previous example, whereas in WCF syntax, they are more accurately represented as properties of messages.</span></span> <span data-ttu-id="aacb4-244">Außerdem ermöglicht WCF, dass Nachrichten Header der Konfiguration von Endpunkten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-244">Also, WCF allows message headers to be added to the configuration of endpoints.</span></span>

```xml
<service name="Service ">
     <endpoint
      address="EchoService"
      binding="basicHttpBinding"
      contract="IEchoService ">
      <headers>
      <dsig:X509Certificate
       xmlns:dsig="http://www.w3.org/2000/09/xmldsig#">
       ...
      </dsig:X509Certificate>
      </headers>
     </endpoint>
</service>
```

<span data-ttu-id="aacb4-245">Mit dieser Option muss im Code für einen Client oder Dienst kein Verweis auf infrastrukturbezogene Protokollheader angegeben werden: Die Header werden Nachrichten ausgehend von der Konfiguration des Endpunkts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="aacb4-245">That option allows you to avoid any reference to infrastructural protocol headers in the code for a client or service: the headers are added to messages because of how the endpoint is configured.</span></span>

## <a name="service-description"></a><span data-ttu-id="aacb4-246">Dienstbeschreibung</span><span class="sxs-lookup"><span data-stu-id="aacb4-246">Service Description</span></span>

<span data-ttu-id="aacb4-247">Bei einer HTTP GET-Anforderung für die ASMX-Datei eines ASP.NET-Webdiensts mit der Abfrage-WSDL generiert ASP.NET zur Beschreibung des Diensts WSDL.</span><span class="sxs-lookup"><span data-stu-id="aacb4-247">Issuing an HTTP GET request for the .asmx file of an ASP.NET Web service with the query WSDL causes ASP.NET to generate WSDL to describe the service.</span></span> <span data-ttu-id="aacb4-248">Diese WSDL wird als Antwort auf diese Anforderung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aacb4-248">It returns that WSDL as the response to the request.</span></span>

<span data-ttu-id="aacb4-249">Mit ASP.NET 2.0 kann überprüft werden, ob ein Dienst mit Basic Profile 1.1 von Web Services-Interoperability Organization (WS-I) kompatibel ist und ein Anspruch, mit dem der Dienst kompatibel ist, in WSDL eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-249">ASP.NET 2.0 made it possible to validate that a service is compliant with the Basic Profile 1.1 of the Web Services-Interoperability Organization (WS-I), and to insert a claim that the service is compliant into its WSDL.</span></span> <span data-ttu-id="aacb4-250">Dies wird mithilfe des `ConformsTo`-Parameters und des `EmitConformanceClaims`-Parameters des <xref:System.Web.Services.WebServiceBindingAttribute>-Attributs durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="aacb4-250">That is done using the `ConformsTo` and `EmitConformanceClaims` parameters of the <xref:System.Web.Services.WebServiceBindingAttribute> attribute.</span></span>

```csharp
[WebService(Namespace = "http://tempuri.org/")]
[WebServiceBinding(
     ConformsTo = WsiProfiles.BasicProfile1_1,
     EmitConformanceClaims=true)]
public interface IEcho
```

<span data-ttu-id="aacb4-251">Die WSDL, die ASP.NET für einen Dienst generiert, kann angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-251">The WSDL that ASP.NET generates for a service can be customized.</span></span> <span data-ttu-id="aacb4-252">Anpassungen werden durch Erstellen einer abgeleiteten Klasse von <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension> vorgenommen, um der WSDL Elemente hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-252">Customizations are made by creating a derived class of <xref:System.Web.Services.Description.ServiceDescriptionFormatExtension> to add items to the WSDL.</span></span>

<span data-ttu-id="aacb4-253">Wenn eine HTTP GET-Anforderung mit der Abfrage-WSDL für die SVC-Datei eines WCF-Dienstanbieter mit einem HTTP-Endpunkt ausgegeben wird, der in IIS 51, 6,0 oder was gehostet wird, antwortet WCF mit WSDL, um den Dienst zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="aacb4-253">Issuing an HTTP GET request with the query WSDL for the .svc file of a WCF service with an HTTP endpoint hosted within IIS 51, 6.0 or WAS causes WCF to respond with WSDL to describe the service.</span></span> <span data-ttu-id="aacb4-254">Das Richten einer HTTP GET-Anforderung mit der Abfrage-WSDL an die HTTP-Basisadresse eines in einer .NET-Anwendung gehosteten Diensts hat die gleiche Auswirkung, wenn "httpGetEnabled" auf "true" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="aacb4-254">Issuing an HTTP GET request with the query WSDL to the HTTP base address of a service hosted within a .NET application has the same effect if httpGetEnabled is set to true.</span></span>

<span data-ttu-id="aacb4-255">WCF antwortet jedoch auch auf WS-MetadataExchange-Anforderungen mit WSDL, die es generiert, um einen Dienst zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="aacb4-255">However, WCF also responds to WS-MetadataExchange requests with WSDL that it generates to describe a service.</span></span> <span data-ttu-id="aacb4-256">ASP.NET-Webdienste verfügen über keine integrierte Unterstützung für WS-MetadataExchange-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-256">ASP.NET Web services do not have built-in support for WS-MetadataExchange requests.</span></span>

<span data-ttu-id="aacb4-257">Die WSDL, die von WCF generiert wird, kann umfassend angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-257">The WSDL that WCF generates can be extensively customized.</span></span> <span data-ttu-id="aacb4-258">Die <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Klasse bietet einige Funktionen zum Anpassen der WSDL.</span><span class="sxs-lookup"><span data-stu-id="aacb4-258">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class provides some facilities for customizing the WSDL.</span></span> <span data-ttu-id="aacb4-259">WCF kann auch so konfiguriert werden, dass keine WSDL generiert wird, sondern stattdessen eine statische WSDL-Datei an einer bestimmten URL verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aacb4-259">The WCF can also be configured to not generate WSDL, but rather to use a static WSDL file at a given URL.</span></span>

```xml
<behaviors>
     <behavior name="DescriptionBehavior">
     <metadataPublishing
      enableMetadataExchange="true"
      enableGetWsdl="true"
      enableHelpPage="true"
      metadataLocation=
      "http://localhost/DerivativesCalculatorService/Service.WSDL"/>
     </behavior>
</behaviors>
```

## <a name="exception-handling"></a><span data-ttu-id="aacb4-260">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="aacb4-260">Exception Handling</span></span>

<span data-ttu-id="aacb4-261">In ASP.NET-Webdiensten werden nicht behandelte Ausnahmen den Clients als SOAP-Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aacb4-261">In ASP.NET Web services, unhandled exceptions are returned to clients as SOAP faults.</span></span> <span data-ttu-id="aacb4-262">Sie können auch explizit Instanzen der <xref:System.Web.Services.Protocols.SoapException>-Klasse auslösen und eine größere Kontrolle über den Inhalt des SOAP-Fehlers erlangen, der an den Client übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="aacb4-262">You can also explicitly throw instances of the <xref:System.Web.Services.Protocols.SoapException> class and have more control over the content of the SOAP fault that gets transmitted to the client.</span></span>

<span data-ttu-id="aacb4-263">In WCF-Diensten werden nicht behandelte Ausnahmen nicht als SOAP-Fehler an Clients zurückgegeben, um zu verhindern, dass vertrauliche Informationen durch die Ausnahmen versehentlich offengelegt werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-263">In WCF services, unhandled exceptions are not returned to clients as SOAP faults to prevent sensitive information being inadvertently exposed through the exceptions.</span></span> <span data-ttu-id="aacb4-264">Mit einer Konfigurationseinstellung werden nicht behandelte Ausnahmen zu Debugging-Zwecken an Clients zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="aacb4-264">A configuration setting is provided to have unhandled exceptions returned to clients for the purpose of debugging.</span></span>

<span data-ttu-id="aacb4-265">Sollen SOAP-Fehler an Clients zurückgegeben werden, können Instanzen des generischen Typs (<xref:System.ServiceModel.FaultException%601>) unter Verwendung des Datenvertragstyps als generischem Typ ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-265">To return SOAP faults to clients, you can throw instances of the generic type, <xref:System.ServiceModel.FaultException%601>, using the data contract type as the generic type.</span></span> <span data-ttu-id="aacb4-266">Sie können auch <xref:System.ServiceModel.FaultContractAttribute>-Attribute Vorgängen hinzufügen, um die Fehler anzugeben, die sich aus einem Vorgang ergeben können.</span><span class="sxs-lookup"><span data-stu-id="aacb4-266">You can also add <xref:System.ServiceModel.FaultContractAttribute> attributes to operations to specify the faults that an operation might yield.</span></span>

```csharp
[DataContract]
public class MathFault
{
     [DataMember]
     public string operation;
     [DataMember]
     public string problemType;
}

[ServiceContract]
public interface ICalculator
{
     [OperationContract]
     [FaultContract(typeof(MathFault))]
     int Divide(int n1, int n2);
}
```

<span data-ttu-id="aacb4-267">Dies führt dazu, dass mögliche Fehler in der WSDL für den Dienst angekündigt werden und Clientprogrammierer somit vorab wissen, welche Fehler sich aus einem Vorgang ergeben können. Auf Grundlage dieser Ankündigung haben die Programmierer die Möglichkeit, geeignete catch-Anweisungen zu verfassen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-267">Doing so results in the possible faults being advertised in the WSDL for the service, allowing client programmers to anticipate which faults can result from an operation, and write the appropriate catch statements.</span></span>

```csharp
try
{
     result = client.Divide(value1, value2);
}
catch (FaultException<MathFault> e)
{
 Console.WriteLine("FaultException<MathFault>: Math fault while doing "
  + e.Detail.operation
  + ". Problem: "
  + e.Detail.problemType);
}
```

## <a name="state-management"></a><span data-ttu-id="aacb4-268">Zustandsverwaltung</span><span class="sxs-lookup"><span data-stu-id="aacb4-268">State Management</span></span>

<span data-ttu-id="aacb4-269">Die Klasse, mit der ein ASP.NET-Webdienst implementiert wird, wird möglicherweise von <xref:System.Web.Services.WebService> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="aacb4-269">The class used to implement an ASP.NET Web service may be derived from <xref:System.Web.Services.WebService>.</span></span>

```csharp
public class Service : WebService, IEcho
{

 public string Echo(string input)
 {
  return input;
 }
}
```

<span data-ttu-id="aacb4-270">In diesem Fall kann die Klasse so programmiert werden, dass sie die <xref:System.Web.Services.WebService>-Kontexteigenschaft der Basisklasse für den Zugriff auf ein <xref:System.Web.HttpContext>-Objekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="aacb4-270">In that case, the class can be programmed to use the <xref:System.Web.Services.WebService> base class’ Context property to access a <xref:System.Web.HttpContext> object.</span></span> <span data-ttu-id="aacb4-271">Mit dem <xref:System.Web.HttpContext>-Objekt können Anwendungszustandsinformationen durch Verwendung der Anwendungseigenschaft aktualisiert und abgerufen werden. Außerdem können Sitzungszustandsinformationen durch Verwendung der Sitzungseigenschaft aktualisiert und abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-271">The <xref:System.Web.HttpContext> object can be used to update and retrieve application state information by using its Application property, and can be used to update and retrieve session state information by using its Session property.</span></span>

<span data-ttu-id="aacb4-272">ASP.NET bietet umfassende Funktionen zur Bestimmung des tatsächlichen Speicherorts der Sitzungszustandsinformationen, auf die mithilfe der Sitzungseigenschaft von <xref:System.Web.HttpContext> zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="aacb4-272">ASP.NET provides considerable control over where the session state information accessed by using the Session property of the <xref:System.Web.HttpContext> is actually stored.</span></span> <span data-ttu-id="aacb4-273">Die Informationen können in Cookies, einer Datenbank, im Speicher des aktuellen Servers oder im Speicher eines festgelegten Servers gespeichert sein.</span><span class="sxs-lookup"><span data-stu-id="aacb4-273">It may be stored in cookies, in a database, in the memory of the current server, or in the memory of a designated server.</span></span> <span data-ttu-id="aacb4-274">Die Auswahl wird in der Konfigurationsdatei des Diensts getroffen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-274">The choice is made in the service’s configuration file.</span></span>

<span data-ttu-id="aacb4-275">WCF stellt erweiterbare Objekte für die Zustands Verwaltung bereit.</span><span class="sxs-lookup"><span data-stu-id="aacb4-275">The WCF provides extensible objects for state management.</span></span> <span data-ttu-id="aacb4-276">Erweiterbare Objekte sind Objekte, mit denen <xref:System.ServiceModel.IExtensibleObject%601> implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="aacb4-276">Extensible objects are objects that implement <xref:System.ServiceModel.IExtensibleObject%601>.</span></span> <span data-ttu-id="aacb4-277">Die wichtigsten erweiterbaren Objekte sind <xref:System.ServiceModel.ServiceHostBase> und <xref:System.ServiceModel.InstanceContext>.</span><span class="sxs-lookup"><span data-stu-id="aacb4-277">The most important extensible objects are <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="aacb4-278">`ServiceHostBase` ermöglicht die Beibehaltung des Zustands, auf den alle Instanzen aller Diensttypen auf demselben Host zugreifen können, während `InstanceContext` das Beibehalten des Zustands ermöglicht, auf den mit jedem Code, der in derselben Instanz eines Diensttyps ausgeführt wird, zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="aacb4-278">`ServiceHostBase` allows you to maintain state that all of the instances of all of the service types on the same host can access, while `InstanceContext` allows you to maintain state that can be accessed by any code running within the same instance of a service type.</span></span>

<span data-ttu-id="aacb4-279">Hier verfügt der Diensttyp `TradingSystem` über einen, der <xref:System.ServiceModel.ServiceBehaviorAttribute> angibt, dass alle Aufrufe von derselben WCF-Client Instanz an dieselbe Instanz des Dienst Typs weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-279">Here, the service type, `TradingSystem`, has a <xref:System.ServiceModel.ServiceBehaviorAttribute> that specifies that all calls from the same WCF client instance are routed to the same instance of the service type.</span></span>

```csharp
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]
public class TradingSystem: ITradingService
```

<span data-ttu-id="aacb4-280">Die Klasse (`DealData`) definiert den Zustand, auf den mit jedem Code, der in derselben Instanz eines Diensttyps ausgeführt wird, zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="aacb4-280">The class, `DealData`, defines state that can be accessed by any code running in the same instance of a service type.</span></span>

```csharp
internal class DealData: IExtension<InstanceContext>
{
 public string DealIdentifier = null;
 public Trade[] Trades = null;
}
```

<span data-ttu-id="aacb4-281">Im Code des Diensttyps, mit dem einer der Vorgänge des Dienstvertrags implementiert wird, wird ein `DealData`-Statusobjekt dem Zustand der aktuellen Instanz des Diensttyps hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="aacb4-281">In the code of the service type that implements one of the operations of the service contract, a `DealData` state object is added to the state of the current instance of the service type.</span></span>

```csharp
string ITradingService.BeginDeal()
{
 string dealIdentifier = Guid.NewGuid().ToString();
 DealData state = new DealData(dealIdentifier);
 OperationContext.Current.InstanceContext.Extensions.Add(state);
 return dealIdentifier;
}
```

<span data-ttu-id="aacb4-282">Das Statusobjekt kann anschließend mit dem Code abgerufen und geändert werden, der einen anderen Dienstvertragsvorgang implementiert.</span><span class="sxs-lookup"><span data-stu-id="aacb4-282">That state object can then be retrieved and modified by the code that implements another of the service contract’s operations.</span></span>

```csharp
void ITradingService.AddTrade(Trade trade)
{
 DealData dealData =  OperationContext.Current.InstanceContext.Extensions.Find<DealData>();
 dealData.AddTrade(trade);
}
```

<span data-ttu-id="aacb4-283">Während ASP.net die Kontrolle darüber bereitstellt, wo Zustandsinformationen in der <xref:System.Web.HttpContext> Klasse tatsächlich gespeichert werden, bietet WCF, zumindest in seiner ursprünglichen Version, keine Kontrolle darüber, wo erweiterbare Objekte gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-283">Whereas ASP.NET provides control over where state information in the <xref:System.Web.HttpContext> class is actually stored, WCF, at least in its initial version, provides no control over where extensible objects are stored.</span></span> <span data-ttu-id="aacb4-284">Dies ist der beste Grund für die Auswahl des ASP.NET-Kompatibilitätsmodus für einen WCF-Dienst.</span><span class="sxs-lookup"><span data-stu-id="aacb4-284">That constitutes the very best reason for selecting the ASP.NET compatibility mode for a WCF service.</span></span> <span data-ttu-id="aacb4-285">Sofern eine konfigurierbare Zustandsverwaltung erforderlich ist, können Sie mit dem ASP.NET-Kompatibilitätsmodus die Funktionen der <xref:System.Web.HttpContext>-Klasse genau entsprechend ihrer Verwendung in ASP.NET nutzen und zudem den Speicherort der Zustandsinformationen konfigurieren, die mithilfe der <xref:System.Web.HttpContext>-Klasse verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-285">If configurable state management is imperative, then opting for the ASP.NET compatibility mode allows you to use the facilities of the <xref:System.Web.HttpContext> class exactly as they are used in ASP.NET, and also to configure where state information managed by using the <xref:System.Web.HttpContext> class is stored.</span></span>

## <a name="security"></a><span data-ttu-id="aacb4-286">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="aacb4-286">Security</span></span>

<span data-ttu-id="aacb4-287">Die Optionen für das Sichern der ASP.NET-Webdienste stimmen mit den Optionen für das Sichern einer beliebigen IIS-Anwendung überein.</span><span class="sxs-lookup"><span data-stu-id="aacb4-287">The options for securing ASP.NET Web services are those for securing any IIS application.</span></span> <span data-ttu-id="aacb4-288">Da WCF-Anwendungen nicht nur innerhalb von IIS, sondern auch innerhalb einer ausführbaren .NET-Datei gehostet werden können, müssen die Optionen zum Sichern von WCF-Anwendungen unabhängig von den Funktionen von IIS erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-288">Because WCF applications can be hosted not only within IIS but also within any .NET executable, the options for securing WCF applications must be made independent from the facilities of IIS.</span></span> <span data-ttu-id="aacb4-289">Die für ASP.NET-Webdienste bereitgestellten Funktionen sind jedoch auch für WCF-Dienste verfügbar, die im ASP.NET-Kompatibilitätsmodus ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-289">However, the facilities provided for ASP.NET Web services are also available for WCF services running in ASP.NET compatibility mode.</span></span>

### <a name="security-authentication"></a><span data-ttu-id="aacb4-290">Sicherheit: Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="aacb4-290">Security: Authentication</span></span>

<span data-ttu-id="aacb4-291">IIS bietet Funktionen für die Steuerung des Zugriffs auf Anwendungen, mit denen Sie entweder anonymen Zugriff oder eine Reihe von Authentifizierungsmodi auswählen können: Windows-Authentifizierung, Hashwertauthentifizierung, Standardauthentifizierung und .NET Passport-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="aacb4-291">IIS provides facilities for controlling access to applications by which you can select either anonymous access or a variety of modes of authentication: Windows Authentication, Digest Authentication, Basic Authentication, and .NET Passport Authentication.</span></span> <span data-ttu-id="aacb4-292">Die Option Windows-Authentifizierung kann verwendet werden, um Zugriff auf ASP.NET-Webdienste zu steuern.</span><span class="sxs-lookup"><span data-stu-id="aacb4-292">The Windows Authentication option can be used to control access to ASP.NET Web services.</span></span> <span data-ttu-id="aacb4-293">Wenn WCF-Anwendungen jedoch in IIS gehostet werden, muss IIS so konfiguriert werden, dass der anonyme Zugriff auf die Anwendung zugelassen wird, damit die Authentifizierung von WCF selbst verwaltet werden kann, was die Windows-Authentifizierung unter verschiedenen anderen Optionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aacb4-293">However, when WCF applications are hosted within IIS, IIS must be configured to permit anonymous access to the application, so that authentication can be managed by WCF itself, which does support Windows authentication among various other options.</span></span> <span data-ttu-id="aacb4-294">Zu den anderen integrierten Optionen zählen Benutzernamentoken, X.509-Zertifikate, SAML-Token und CardSpace-Karten, doch es können auch benutzerdefinierte Authentifizierungsmechanismen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-294">The other options that are built-in include username tokens, X.509 certificates, SAML tokens, and CardSpace card, but custom authentication mechanisms can also be defined.</span></span>

### <a name="security-impersonation"></a><span data-ttu-id="aacb4-295">Sicherheit: Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="aacb4-295">Security: Impersonation</span></span>

<span data-ttu-id="aacb4-296">ASP.NET verfügt über ein Identitätselement, mit dem ein ASP.NET-Webdienst für das Durchführen von Identitätswechseln konfiguriert werden kann, und zwar für einen bestimmten Benutzer oder einen beliebigen Benutzer, für den in der aktuellen Anforderung Anmeldeinformationen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-296">ASP.NET provides an identity element by which an ASP.NET Web service can be made to impersonate a particular user or whichever user’s credentials are provided with the current request.</span></span> <span data-ttu-id="aacb4-297">Dieses Element kann zum Konfigurieren des Identitäts Wechsels in WCF-Anwendungen verwendet werden, die im ASP.NET-Kompatibilitätsmodus ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-297">That element can be used to configure impersonation in WCF applications running in ASP.NET compatibility mode.</span></span>

<span data-ttu-id="aacb4-298">Das WCF-Konfigurationssystem stellt ein eigenes Identitätselement zum Festlegen eines bestimmten Benutzers bereit, dessen Identität angenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="aacb4-298">The WCF configuration system provides its own identity element for designating a particular user to impersonate.</span></span> <span data-ttu-id="aacb4-299">WCF-Clients und-Dienste können auch unabhängig für den Identitätswechsel konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-299">Also, WCF clients and services can be independently configured for impersonation.</span></span> <span data-ttu-id="aacb4-300">Clients können dafür konfiguriert werden, für den aktuellen Benutzer beim Übertragen von Anforderungen einen Identitätswechsel durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-300">Clients can be configured to impersonate the current user when they transmit requests.</span></span>

```xml
<behaviors>
     <behavior name="DerivativesCalculatorClientBehavior">
      <clientCredentials>
      <windows allowedImpersonationLevel="Impersonation"/>
      </clientCredentials>
     </behavior>
</behaviors>
```

<span data-ttu-id="aacb4-301">Dienstvorgänge können dafür konfiguriert werden, einen Identitätswechsel für einen beliebigen Benutzer durchzuführen, dessen Anmeldeinformationen in der aktuellen Anforderung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-301">Service operations can be configured to impersonate whichever user’s credentials are provided with the current request.</span></span>

```csharp
[OperationBehavior(Impersonation = ImpersonationOption.Required)]
public void Receive(Message input)
```

### <a name="security-authorization-using-access-control-lists"></a><span data-ttu-id="aacb4-302">Sicherheit: Autorisierung mithilfe von Zugriffssteuerungslisten</span><span class="sxs-lookup"><span data-stu-id="aacb4-302">Security: Authorization using Access Control Lists</span></span>

<span data-ttu-id="aacb4-303">Mit Zugriffssteuerungslisten (ACLs) kann der Zugriff auf ASMX-Dateien beschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-303">Access Control Lists (ACLs) can be used to restrict access to .asmx files.</span></span> <span data-ttu-id="aacb4-304">Allerdings werden ACLs in WCF. svc-Dateien ignoriert, außer im ASP.NET-Kompatibilitätsmodus.</span><span class="sxs-lookup"><span data-stu-id="aacb4-304">However, ACLs on WCF .svc files are ignored except in ASP.NET compatibility mode.</span></span>

### <a name="security-role-based-authorization"></a><span data-ttu-id="aacb4-305">Sicherheit: Rollenbasierte Autorisierung</span><span class="sxs-lookup"><span data-stu-id="aacb4-305">Security: Role-based Authorization</span></span>

<span data-ttu-id="aacb4-306">Die Option für Windows-Authentifizierung in IIS kann zusammen mit dem von der ASP.NET-Konfigurationssprache bereitgestellten Autorisierungselement verwendet werden, um rollenbasierte Autorisierung für ASP.NET-Webdienste auf Grundlage der Windows-Gruppen, denen Benutzer zugewiesen sind, zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="aacb4-306">The IIS Windows Authentication option can be used in conjunction with the authorization element provided by the ASP.NET configuration language to facilitate role-based authorization for ASP.NET Web services based on the Windows groups to which users are assigned.</span></span> <span data-ttu-id="aacb4-307">ASP.NET 2.0 verwendet einen allgemeineren rollenbasierten Autorisierungsmechanismus: Rollenanbieter.</span><span class="sxs-lookup"><span data-stu-id="aacb4-307">ASP.NET 2.0 introduced a more general role-based authorization mechanism: role providers.</span></span>

<span data-ttu-id="aacb4-308">Rollenanbieter sind Klassen, die alle eine Basisschnittstelle für die Abfrage der Rollen, denen ein Benutzer zugewiesen ist, implementieren. Allerdings können diese Informationen mit jedem Rollenanbieter von einer anderen Quelle abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-308">Role providers are classes that all implement a basic interface for enquiring about the roles to which a user is assigned, but each role provider knows how to retrieve that information from a different source.</span></span> <span data-ttu-id="aacb4-309">ASP.NET 2.0 verfügt über einen Rollenanbieter zum Abrufen von Rollenzuweisungen von einer Microsoft SQL Server-Datenbank und einen weiteren Rollenanbieter zum Abrufen von Rollenzuweisungen vom Windows Server 2003-Autorisierungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="aacb4-309">ASP.NET 2.0 provides a role provider that can retrieve role assignments from a Microsoft SQL Server database, and another that can retrieve role assignments from the Windows Server 2003 Authorization Manager.</span></span>

<span data-ttu-id="aacb4-310">Der Rollen Anbieter Mechanismus kann in einer beliebigen .NET-Anwendung, einschließlich einer WCF-Anwendung, tatsächlich unabhängig von ASP.NET verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-310">The role provider mechanism can actually be used independently of ASP.NET in any .NET application, including a WCF application.</span></span> <span data-ttu-id="aacb4-311">Die folgende Beispielkonfiguration für eine WCF-Anwendung zeigt, wie die Verwendung eines ASP.NET-Rollen Anbieters eine Option ist, die mithilfe von ausgewählt wird <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> .</span><span class="sxs-lookup"><span data-stu-id="aacb4-311">The following sample configuration for a WCF application shows how the use of an ASP.NET role provider is an option selected by means of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span></span>

```xml
<system.serviceModel>
     <services>
         <service name="Service.ResourceAccessServiceType"
             behaviorConfiguration="ServiceBehavior">
             <endpoint
              address="ResourceAccessService"
              binding="wsHttpBinding"
              contract="Service.IResourceAccessContract"/>
         </service>
     </services>
     <behaviors>
       <behavior name="ServiceBehavior">
       <serviceAuthorization principalPermissionMode="UseAspNetRoles"/>
      </behavior>
     </behaviors>
</system.serviceModel>
```

### <a name="security-claims-based-authorization"></a><span data-ttu-id="aacb4-312">Sicherheit: Anspruchbasierte Autorisierung</span><span class="sxs-lookup"><span data-stu-id="aacb4-312">Security: Claims-based Authorization</span></span>

<span data-ttu-id="aacb4-313">Eine der wichtigsten Innovationen von WCF ist die gründliche Unterstützung für die Autorisierungs des Zugriffs auf geschützte Ressourcen basierend auf Ansprüchen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-313">One of the most important innovations of WCF is its thorough support for authorizing access to protected resources based on claims.</span></span> <span data-ttu-id="aacb4-314">Ansprüche bestehen beispielsweise aus einem Typ, einem Recht, einem Wert sowie einer Treiberlizenz.</span><span class="sxs-lookup"><span data-stu-id="aacb4-314">Claims consist of a type, a right and a value, a drivers’ license, for example.</span></span> <span data-ttu-id="aacb4-315">Ein Satz von Ansprüchen bezüglich des Trägers wird erstellt. Einer dieser Ansprüche ist das Geburtsdatum des Trägers.</span><span class="sxs-lookup"><span data-stu-id="aacb4-315">It makes a set of claims about the bearer, one of which is the bearer’s date of birth.</span></span> <span data-ttu-id="aacb4-316">Der Typ des Anspruchs ist das Geburtsdatum, wohingegen der Wert des Anspruchs das Geburtsdatum des Treibers ist.</span><span class="sxs-lookup"><span data-stu-id="aacb4-316">The type of that claim is date of birth, while the value of the claim is the driver’s birth date.</span></span> <span data-ttu-id="aacb4-317">Das Recht, das ein Anspruch einem Träger überträgt, gibt an, wozu der Träger den Wert des Anspruchs verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="aacb4-317">The right that a claim confers on the bearer specifies what the bearer can do with the claim’s value.</span></span> <span data-ttu-id="aacb4-318">Beim Anspruch des Treibergeburtsdatums ist das Recht der Besitz: Der Treiber besitzt dieses Geburtsdatum, kann es jedoch nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="aacb4-318">In the case of the claim of the driver’s date of birth, the right is possession: the driver possesses that date of birth but cannot, for example, alter it.</span></span> <span data-ttu-id="aacb4-319">Anspruchbasierte Autorisierung umfasst rollenbasierte Autorisierung, da Rollen ein Anspruchstyp sind.</span><span class="sxs-lookup"><span data-stu-id="aacb4-319">Claims-based authorization encloses role-based authorization, because roles are a type of claim.</span></span>

<span data-ttu-id="aacb4-320">Bei der anspruchbasierten Autorisierung wird ein Anspruchsatz mit den Zugriffsanforderungen des Vorgangs verglichen. Dabei wird der Zugriff auf den Vorgang abhängig vom Ergebnis dieses Vergleichs gewährt oder verweigert.</span><span class="sxs-lookup"><span data-stu-id="aacb4-320">Authorization based on claims is accomplished by comparing a set of claims to the access requirements of the operation and, depending on the outcome of that comparison, granting or denying access to the operation.</span></span> <span data-ttu-id="aacb4-321">In WCF können Sie eine Klasse angeben, die zum Ausführen der Anspruchs basierten Autorisierung verwendet werden soll, indem Sie der-Eigenschaft von einen Wert zuweisen `ServiceAuthorizationManager` <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> .</span><span class="sxs-lookup"><span data-stu-id="aacb4-321">In WCF, you can specify a class to use to run claims-based authorization, once again by assigning a value to the `ServiceAuthorizationManager` property of <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>.</span></span>

```xml
<behaviors>
     <behavior name='ServiceBehavior'>
     <serviceAuthorization
     serviceAuthorizationManagerType=
                   'Service.AccessChecker, Service' />
     </behavior>
</behaviors>
```

<span data-ttu-id="aacb4-322">Klassen, die zum Ausführen anspruchsbasierter Autorisierung verwendet werden, müssen von <xref:System.ServiceModel.ServiceAuthorizationManager> abgeleitet werden, der nur eine Methode zum Überschreiben besitzt (`AccessCheck()`).</span><span class="sxs-lookup"><span data-stu-id="aacb4-322">Classes used to run claims-based authorization must derive from <xref:System.ServiceModel.ServiceAuthorizationManager>, which has just one method to override, `AccessCheck()`.</span></span> <span data-ttu-id="aacb4-323">WCF ruft diese Methode immer dann auf, wenn ein Dienst Vorgang aufgerufen wird, und stellt ein- <xref:System.ServiceModel.OperationContext> Objekt bereit, das die Ansprüche für den Benutzer in seiner- `ServiceSecurityContext.AuthorizationContext` Eigenschaft aufweist.</span><span class="sxs-lookup"><span data-stu-id="aacb4-323">WCF calls that method whenever an operation of the service is invoked and provides a <xref:System.ServiceModel.OperationContext> object, which has the claims for the user in its `ServiceSecurityContext.AuthorizationContext` property.</span></span> <span data-ttu-id="aacb4-324">WCF führt die Assemblierung von Ansprüchen über den Benutzer von dem Sicherheits Token aus, das der Benutzer für die Authentifizierung bereitgestellt hat. Dadurch wird der von der Aufgabe unterlassen, festzustellen, ob diese Ansprüche für den fraglichen Vorgang ausreichen.</span><span class="sxs-lookup"><span data-stu-id="aacb4-324">WCF does the work of assembling claims about the user from whatever security token the user provided for authentication, which leaves the of task of evaluating whether those claims suffice for the operation in question.</span></span>

<span data-ttu-id="aacb4-325">WCF führt die automatische assemblisierung von Ansprüchen aus jeder Art von Sicherheits Token als äußerst bedeutende Innovation aus, da der Code für die Autorisierung basierend auf den Ansprüchen vollständig unabhängig vom Authentifizierungsmechanismus ist.</span><span class="sxs-lookup"><span data-stu-id="aacb4-325">That WCF automatically assembles claims from any kind of security token is a highly significant innovation, because it makes the code for authorization based on the claims entirely independent of the authentication mechanism.</span></span> <span data-ttu-id="aacb4-326">Im Gegensatz dazu ist die Autorisierung mit Zugriffssteuerungslisten oder Rollen in ASP.NET eng an die Windows-Authentifizierung gebunden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-326">By contrast, authorization using ACLs or roles in ASP.NET is closely tied to Windows authentication.</span></span>

### <a name="security-confidentiality"></a><span data-ttu-id="aacb4-327">Sicherheit: Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="aacb4-327">Security: Confidentiality</span></span>

<span data-ttu-id="aacb4-328">Die Vertraulichkeit von Nachrichten, die mit ASP.NET-Webdiensten ausgetauscht werden, kann auf Transportebene dadurch sichergestellt werden, dass die Anwendung in IIS für die Verwendung von Secure Hypertext Transfer Protocol (HTTPS) konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="aacb4-328">The confidentiality of messages exchanged with ASP.NET Web services can be ensured at the transport level by configuring the application within IIS to use the Secure Hypertext Transfer Protocol (HTTPS).</span></span> <span data-ttu-id="aacb4-329">Dasselbe gilt für WCF-Anwendungen, die in IIS gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-329">The same can be done for WCF applications hosted within IIS.</span></span> <span data-ttu-id="aacb4-330">WCF-Anwendungen, die außerhalb von IIS gehostet werden, können jedoch auch für die Verwendung eines sicheren Transport Protokolls konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-330">However, WCF applications hosted outside of IIS can also be configured to use a secure transport protocol.</span></span> <span data-ttu-id="aacb4-331">Wichtiger ist, dass WCF-Anwendungen auch so konfiguriert werden können, dass die Nachrichten vor dem Transport mithilfe des WS-Security-Protokolls gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="aacb4-331">More important, WCF applications can also be configured to secure the messages before they are transported, using the WS-Security protocol.</span></span> <span data-ttu-id="aacb4-332">Wird nur der Text einer Nachricht mithilfe von WS-Sicherheit gesichert, ist eine vertrauliche Übertragung über Vermittler möglich, bevor das endgültige Ziel erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="aacb4-332">Securing just the body of a message using WS-Security allows it to be transmitted confidentially across intermediaries before reaching its final destination.</span></span>

## <a name="globalization"></a><span data-ttu-id="aacb4-333">Globalisierung</span><span class="sxs-lookup"><span data-stu-id="aacb4-333">Globalization</span></span>

<span data-ttu-id="aacb4-334">Die ASP.NET-Konfigurationssprache ermöglicht das Angeben der Kultur einzelner Dienste.</span><span class="sxs-lookup"><span data-stu-id="aacb4-334">The ASP.NET configuration language allows you to specify the culture for individual services.</span></span> <span data-ttu-id="aacb4-335">Diese Konfigurationseinstellung wird von WCF nicht unterstützt, mit Ausnahme des ASP.NET-Kompatibilitätsmodus.</span><span class="sxs-lookup"><span data-stu-id="aacb4-335">The WCF does not support that configuration setting except in ASP.NET compatibility mode.</span></span> <span data-ttu-id="aacb4-336">Um einen WCF-Dienst zu lokalisieren, der den ASP.NET-Kompatibilitätsmodus nicht verwendet, kompilieren Sie den Diensttyp in kulturspezifische Assemblys, und verwenden Sie für jede kulturspezifische Assembly separate kulturspezifische Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="aacb4-336">To localize a WCF service that does not use ASP.NET compatibility mode, compile the service type into culture-specific assemblies, and have separate culture-specific endpoints for each culture-specific assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="aacb4-337">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aacb4-337">See also</span></span>

- [<span data-ttu-id="aacb4-338">Vergleichen von ASP.NET-Webdiensten mit WCF nach Zweck und verwendeten Standards</span><span class="sxs-lookup"><span data-stu-id="aacb4-338">Comparing ASP.NET Web Services to WCF Based on Purpose and Standards Used</span></span>](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
