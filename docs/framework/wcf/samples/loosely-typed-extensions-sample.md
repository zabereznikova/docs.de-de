---
title: Beispiel zu lose typisierten Erweiterungen
ms.date: 03/30/2017
ms.assetid: 56ce265b-8163-4b85-98e7-7692a12c4357
ms.openlocfilehash: 94e01970502223febd3ff03e30be7b17d9019d93
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264887"
---
# <a name="loosely-typed-extensions-sample"></a><span data-ttu-id="d134b-102">Beispiel zu lose typisierten Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="d134b-102">Loosely-Typed Extensions Sample</span></span>

<span data-ttu-id="d134b-103">Das Syndication-Objektmodell bietet umfangreiche Unterstützung zum Arbeiten mit Erweiterungsdaten – Informationen, die in der XML-Darstellung eines Syndication-Feeds vorhanden, jedoch nicht explizit durch Klassen wie <xref:System.ServiceModel.Syndication.SyndicationFeed> und <xref:System.ServiceModel.Syndication.SyndicationItem> verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d134b-103">The Syndication object model provides rich support for working with extension data—information that is present in a syndication feed's XML representation but not explicitly exposed by classes such as <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem>.</span></span> <span data-ttu-id="d134b-104">Dieses Beispiel veranschaulicht die grundlegenden Techniken zum Arbeiten mit Erweiterungsdaten.</span><span class="sxs-lookup"><span data-stu-id="d134b-104">This sample illustrates the basic techniques for working with extension data.</span></span>  
  
 <span data-ttu-id="d134b-105">Für das Beispiel wird die <xref:System.ServiceModel.Syndication.SyndicationFeed>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="d134b-105">The sample uses the <xref:System.ServiceModel.Syndication.SyndicationFeed> class for the purposes of the example.</span></span> <span data-ttu-id="d134b-106">Die in diesem Beispiel gezeigten Muster können jedoch mit allen Syndication-Klassen verwendet werden, die Erweiterungsdaten unterstützen:</span><span class="sxs-lookup"><span data-stu-id="d134b-106">However, the patterns demonstrated in this sample can be used with all of the Syndication classes that support extension data:</span></span>  
  
 <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
 <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
 <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
 <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
 <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
## <a name="sample-xml"></a><span data-ttu-id="d134b-107">Beispiel-XML</span><span class="sxs-lookup"><span data-stu-id="d134b-107">Sample XML</span></span>  

 <span data-ttu-id="d134b-108">Zu Referenzzwecken wird in diesem Beispiel das folgende XML-Dokument verwendet.</span><span class="sxs-lookup"><span data-stu-id="d134b-108">For reference, the following XML document is used in this sample.</span></span>  
  
```xml  
<?xml version="1.0" encoding="IBM437"?>  
<feed myAttribute="someValue" xmlns="http://www.w3.org/2005/Atom">  
  <title type="text"></title>  
  <id>uuid:8f60c7b3-a3c0-4de7-a642-2165d77ce3c1;id=1</id>  
  <updated>2007-09-07T22:15:34Z</updated>  
  <simpleString xmlns="">hello, world!</simpleString>  
  <simpleString xmlns="">another simple string</simpleString>  
  <DataContractExtension xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.d  
atacontract.org/2004/07/Microsoft.Syndication.Samples">  
    <Key>X</Key>  
    <Value>4</Value>  
  </DataContractExtension>  
  <XmlSerializerExtension xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://ww  
w.w3.org/2001/XMLSchema" xmlns="">  
    <Key>Y</Key>  
    <Value>8</Value>  
  </XmlSerializerExtension>  
  <xElementExtension xmlns="">  
    <Key attr1="someValue">Z</Key>  
    <Value attr1="someValue">15</Value>  
  </xElementExtension>  
</feed>  
```  
  
 <span data-ttu-id="d134b-109">Dieses Dokument enthält die folgenden einzelnen Erweiterungsdaten:</span><span class="sxs-lookup"><span data-stu-id="d134b-109">This document contains the following pieces of extension data:</span></span>  
  
- <span data-ttu-id="d134b-110">Das `myAttribute`-Attribut des `<feed>`-Elements.</span><span class="sxs-lookup"><span data-stu-id="d134b-110">The `myAttribute` attribute of the `<feed>` element.</span></span>  
  
- <span data-ttu-id="d134b-111">`<simpleString>`-Element.</span><span class="sxs-lookup"><span data-stu-id="d134b-111">`<simpleString>` element.</span></span>  
  
- <span data-ttu-id="d134b-112">`<DataContractExtension>`-Element.</span><span class="sxs-lookup"><span data-stu-id="d134b-112">`<DataContractExtension>` element.</span></span>  
  
- <span data-ttu-id="d134b-113">`<XmlSerializerExtension>`-Element.</span><span class="sxs-lookup"><span data-stu-id="d134b-113">`<XmlSerializerExtension>` element.</span></span>  
  
- <span data-ttu-id="d134b-114">`<xElementExtension>`-Element.</span><span class="sxs-lookup"><span data-stu-id="d134b-114">`<xElementExtension>` element.</span></span>  
  
## <a name="writing-extension-data"></a><span data-ttu-id="d134b-115">Schreiben von Erweiterungsdaten</span><span class="sxs-lookup"><span data-stu-id="d134b-115">Writing Extension Data</span></span>  

 <span data-ttu-id="d134b-116">Attributerweiterungen werden erstellt, indem man der <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A>-Auflistung Einträge hinzufügt, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d134b-116">Attribute extensions are created by adding entries to the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> collection as shown in the following sample code.</span></span>  
  
```csharp  
//Attribute extensions are stored in a dictionary indexed by
// XmlQualifiedName  
feed.AttributeExtensions.Add(new XmlQualifiedName("myAttribute", ""), "someValue");  
```  
  
 <span data-ttu-id="d134b-117">Elementerweiterungen werden erstellt, indem man der <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A>-Auflistung Einträge hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="d134b-117">Element extensions are created by adding entries to the <xref:System.ServiceModel.Syndication.SyndicationFeed.ElementExtensions%2A> collection.</span></span> <span data-ttu-id="d134b-118">Diese Erweiterungen können einfache Werte (wie Zeichenfolgen), XML-Serialisierungen von .NET Framework-Objekten oder manuell codierte XML-Knoten sein.</span><span class="sxs-lookup"><span data-stu-id="d134b-118">These extensions can by basic values such as strings, XML serializations of .NET Framework objects, or XML nodes coded by hand.</span></span>  
  
 <span data-ttu-id="d134b-119">Im folgenden Beispielcode wird ein Erweiterungselement namens `simpleString` erstellt.</span><span class="sxs-lookup"><span data-stu-id="d134b-119">The following sample code creates an extension element named `simpleString`.</span></span>  
  
```csharp  
feed.ElementExtensions.Add("simpleString", "", "hello, world!");  
```  
  
 <span data-ttu-id="d134b-120">Der XML-Namespace für dieses Element ist der leere Namespace (""), und sein Wert ist ein Textknoten, der die Zeichenfolge "Hello, World!" enthält.</span><span class="sxs-lookup"><span data-stu-id="d134b-120">The XML namespace for this element is the empty namespace ("") and its value is a text node that contains the string "hello, world!".</span></span>  
  
 <span data-ttu-id="d134b-121">Eine Möglichkeit zum Erstellen komplexer Elementerweiterungen, die aus vielen verschachtelten Elementen bestehen, wäre die Verwendung der .NET Framework-APIs zur Serialisierung (sowohl <xref:System.Runtime.Serialization.DataContractSerializer> als auch <xref:System.Xml.Serialization.XmlSerializer> werden unterstützt), wie in den folgenden Beispielen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d134b-121">One way to create complex element extensions that consist of many nested elements is to use the .NET Framework APIs for serialization (both the <xref:System.Runtime.Serialization.DataContractSerializer> and the <xref:System.Xml.Serialization.XmlSerializer> are supported) as shown in the following examples.</span></span>  
  
```csharp  
feed.ElementExtensions.Add( new DataContractExtension() { Key = "X", Value = 4 } );  
feed.ElementExtensions.Add( new XmlSerializerExtension { Key = "Y", Value = 8 }, new XmlSerializer( typeof( XmlSerializerExtension ) ) );  
```  
  
 <span data-ttu-id="d134b-122">In diesem Beispiel sind `DataContractExtension` und `XmlSerializerExtension` benutzerdefinierte, zur Verwendung mit einem Serialisierer geschriebene Typen.</span><span class="sxs-lookup"><span data-stu-id="d134b-122">In this example, the `DataContractExtension` and `XmlSerializerExtension` are custom types written for use with a serializer.</span></span>  
  
 <span data-ttu-id="d134b-123">Elementerweiterungen können auch mithilfe der <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection>-Klasse aus einer <xref:System.Xml.XmlReader>-Instanz erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d134b-123">The <xref:System.ServiceModel.Syndication.SyndicationElementExtensionCollection> class can also be used to create element extensions from an <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="d134b-124">Dies erlaubt eine einfache Integration in APIs für die Verarbeitung von XML (wie <xref:System.Xml.Linq.XElement>), wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d134b-124">This allows for easy integration with XML processing APIs such as <xref:System.Xml.Linq.XElement> as shown in the following sample code.</span></span>  
  
```csharp  
feed.ElementExtensions.Add(new XElement("xElementExtension",  
        new XElement("Key", new XAttribute("attr1", "someValue"), "Z"),  
        new XElement("Value", new XAttribute("attr1", "someValue"),
        "15")).CreateReader());  
```  
  
## <a name="reading-extension-data"></a><span data-ttu-id="d134b-125">Lesen von Erweiterungsdaten</span><span class="sxs-lookup"><span data-stu-id="d134b-125">Reading Extension Data</span></span>  

 <span data-ttu-id="d134b-126">Die Werte für Attributerweiterungen können erhalten werden, indem das Attribut in der <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A>-Auflistung anhand seines <xref:System.Xml.XmlQualifiedName> nachgeschlagen wird, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d134b-126">The values for attribute extensions can be obtained by looking up the attribute in the <xref:System.ServiceModel.Syndication.SyndicationFeed.AttributeExtensions%2A> collection by its <xref:System.Xml.XmlQualifiedName> as shown in the following sample code.</span></span>  
  
```csharp  
Console.WriteLine( feed.AttributeExtensions[ new XmlQualifiedName( "myAttribute", "" )]);  
```  
  
 <span data-ttu-id="d134b-127">Der Zugriff auf Elementerweiterungen erfolgt mit der `ReadElementExtensions<T>`-Methode.</span><span class="sxs-lookup"><span data-stu-id="d134b-127">Element extensions are accessed using the `ReadElementExtensions<T>` method.</span></span>  
  
```csharp  
foreach( string s in feed2.ElementExtensions.ReadElementExtensions<string>("simpleString", ""))  
{  
    Console.WriteLine(s);  
}  
  
foreach (DataContractExtension dce in feed2.ElementExtensions.ReadElementExtensions<DataContractExtension>("DataContractExtension",  
"http://schemas.datacontract.org/2004/07/SyndicationExtensions"))  
{  
    Console.WriteLine(dce.ToString());  
}  
  
foreach (XmlSerializerExtension xse in feed2.ElementExtensions.ReadElementExtensions<XmlSerializerExtension>("XmlSerializerExtension", "", new XmlSerializer(typeof(XmlSerializerExtension))))  
{  
    Console.WriteLine(xse.ToString());  
}  
```  
  
 <span data-ttu-id="d134b-128">Es ist auch möglich, einen `XmlReader` bei einzelnen Elementerweiterungen mithilfe der <xref:System.ServiceModel.Syndication.SyndicationElementExtension.GetReader>-Methode abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d134b-128">It is also possible to obtain an `XmlReader` at individual element extensions by using the <xref:System.ServiceModel.Syndication.SyndicationElementExtension.GetReader> method.</span></span>  
  
```csharp  
foreach (SyndicationElementExtension extension in feed2.ElementExtensions.Where<SyndicationElementExtension>(x => x.OuterName == "xElementExtension"))  
{  
    XNode xelement = XElement.ReadFrom(extension.GetReader());  
    Console.WriteLine(xelement.ToString());  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d134b-129">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="d134b-129">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="d134b-130">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="d134b-130">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="d134b-131">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="d134b-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="d134b-132">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d134b-132">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d134b-133">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d134b-133">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d134b-134">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d134b-134">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="d134b-135">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d134b-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d134b-136">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d134b-136">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\LooselyTypedExtensions`  
  
## <a name="see-also"></a><span data-ttu-id="d134b-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d134b-137">See also</span></span>

- [<span data-ttu-id="d134b-138">Stark typisierte Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="d134b-138">Strongly typed Extensions</span></span>](strongly-typed-extensions-sample.md)
- [<span data-ttu-id="d134b-139">WCF Syndication</span><span class="sxs-lookup"><span data-stu-id="d134b-139">WCF Syndication</span></span>](../feature-details/wcf-syndication.md)
