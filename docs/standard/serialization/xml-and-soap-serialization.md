---
title: XML- und SOAP-Serialisierung
description: In dieser Übersicht wird die XML-Serialisierung erläutert, mit der Objekte in XML-Streams serialisiert werden können, die der SOAP-Spezifikation entsprechen.
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: 6b7d6f59694a28207758fa7772781eed073917e4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379545"
---
# <a name="xml-and-soap-serialization"></a><span data-ttu-id="1dce5-103">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1dce5-103">XML and SOAP serialization</span></span>

<span data-ttu-id="1dce5-104">Bei der XML-Serialisierung werden die öffentlichen Felder und Eigenschaften eines Objekts bzw. die Parameter und Rückgabewerte von Methoden in einen XML-Stream konvertiert (serialisiert), der einem bestimmtem XSD (XML Schema Definition)-Dokument entspricht.</span><span class="sxs-lookup"><span data-stu-id="1dce5-104">XML serialization converts (serializes) the public fields and properties of an object, and the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="1dce5-105">Die XML-Serialisierung führt zu stark typisierten Klassen mit öffentlichen Eigenschaften und Feldern, die in ein serielles Format (hier XML) konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="1dce5-105">XML serialization results in strongly typed classes with public properties and fields that are converted to a serial format (in this case, XML) for storage or transport.</span></span>

<span data-ttu-id="1dce5-106">Weil XML ein offener Standard ist, kann der XML-Stream plattformunabhängig bei Bedarf von jeder Anwendung verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="1dce5-106">Because XML is an open standard, the XML stream can be processed by any application, as needed, regardless of platform.</span></span> <span data-ttu-id="1dce5-107">Beispielsweise verwenden mit ASP.NET erstellte Webdienste die <xref:System.Xml.Serialization.XmlSerializer>-Klasse zum Erstellen von XML-Sstreams, die zur Übermittlung von Daten zwischen XML-Webdienstanwendungen über das Internet oder ein Intranet dienen.</span><span class="sxs-lookup"><span data-stu-id="1dce5-107">For example, XML Web services created using ASP.NET use the <xref:System.Xml.Serialization.XmlSerializer> class to create XML streams that pass data between XML Web service applications throughout the Internet or on intranets.</span></span> <span data-ttu-id="1dce5-108">Umgekehrt wird bei der Deserialisierung das Objekt aus einem XML-Stream rekonstruiert.</span><span class="sxs-lookup"><span data-stu-id="1dce5-108">Conversely, deserialization takes such an XML stream and reconstructs the object.</span></span>

<span data-ttu-id="1dce5-109">Durch die XML-Serialisierung können auch Objekte in XML-Streams serialisiert werden, die der SOAP-Spezifikation entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1dce5-109">XML serialization can also be used to serialize objects into XML streams that conform to the SOAP specification.</span></span> <span data-ttu-id="1dce5-110">SOAP ist ein auf XML basierendes Protokoll, das speziell für die Weitergabe von Prozeduraufrufen unter Verwendung von XML entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="1dce5-110">SOAP is a protocol based on XML, designed specifically to transport procedure calls using XML.</span></span>

<span data-ttu-id="1dce5-111">Sie können mithilfe der <xref:System.Xml.Serialization.XmlSerializer>-Klasse Objekte serialisieren und deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="1dce5-111">To serialize or deserialize objects, use the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span> <span data-ttu-id="1dce5-112">Verwenden Sie das XML Schema Definition-Tool, um die zu serialisierenden Klassen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1dce5-112">To create the classes to be serialized, use the XML Schema Definition tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="1dce5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1dce5-113">See also</span></span>

- [<span data-ttu-id="1dce5-114">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1dce5-114">Binary Serialization</span></span>](binary-serialization.md)
- <span data-ttu-id="1dce5-115">[Mit ASP.NET- und XML-Webdienstclients erstellte XML-Webdienste](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1dce5-115">[XML Web Services created using ASP.NET and XML Web Service clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>
