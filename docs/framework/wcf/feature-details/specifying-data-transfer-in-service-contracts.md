---
title: Angeben von Datenübertragung in Dienstverträgen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], data transfer
ms.assetid: 7c5a26c8-89c9-4bcb-a4bc-7131e6d01f0c
ms.openlocfilehash: 47544cf74b4fa09fd8ee868ea940ef24a453840e
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834644"
---
# <a name="specifying-data-transfer-in-service-contracts"></a><span data-ttu-id="21285-102">Angeben von Datenübertragung in Dienstverträgen</span><span class="sxs-lookup"><span data-stu-id="21285-102">Specifying Data Transfer in Service Contracts</span></span>
<span data-ttu-id="21285-103">Die Windows Communication Foundation (WCF) kann als Messaging Infrastruktur betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="21285-103">The Windows Communication Foundation (WCF) can be thought of as a messaging infrastructure.</span></span> <span data-ttu-id="21285-104">Dienstvorgänge können Nachrichten empfangen, sie verarbeiten und ihnen Nachrichten schicken.</span><span class="sxs-lookup"><span data-stu-id="21285-104">Service operations can receive messages, process them, and send them messages.</span></span> <span data-ttu-id="21285-105">Nachrichten werden mit Vorgangsverträgen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="21285-105">Messages are described using operation contracts.</span></span> <span data-ttu-id="21285-106">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="21285-106">For example, consider the following contract.</span></span>  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    float GetAirfare(string fromCity, string toCity);  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
  
    <OperationContract()>  
    Function GetAirfare(fromCity As String, toCity As String) As Double  
End Interface  
```  
  
 <span data-ttu-id="21285-107">Hier akzeptiert der `GetAirfare`-Vorgang eine Nachricht mit Informationen über `fromCity` und `toCity` und gibt dann eine Nachricht zurück, die eine Zahl enthält.</span><span class="sxs-lookup"><span data-stu-id="21285-107">Here, the `GetAirfare` operation accepts a message with information about `fromCity` and `toCity`, and then returns a message that contains a number.</span></span>  
  
 <span data-ttu-id="21285-108">In diesem Thema werden die verschiedenen Möglichkeiten erläutert, wie ein Vorgangsvertrag Nachrichten beschreiben kann.</span><span class="sxs-lookup"><span data-stu-id="21285-108">This topic explains the various ways in which an operation contract can describe messages.</span></span>  
  
## <a name="describing-messages-by-using-parameters"></a><span data-ttu-id="21285-109">Beschreiben von Nachrichten mithilfe von Parametern</span><span class="sxs-lookup"><span data-stu-id="21285-109">Describing Messages by Using Parameters</span></span>  
 <span data-ttu-id="21285-110">Die einfachste Art zur Beschreibung einer Nachricht ist die Verwendung einer Parameterliste und des Rückgabewerts.</span><span class="sxs-lookup"><span data-stu-id="21285-110">The simplest way to describe a message is to use a parameter list and the return value.</span></span> <span data-ttu-id="21285-111">Im vorherigen Beispiel wurden der `fromCity`- und der `toCity`-Zeichenfolgenparameter zur Beschreibung der Anforderungsnachricht verwendet, und der Gleitkommarückgabewert wurde zur Beschreibung der Antwortnachricht verwendet.</span><span class="sxs-lookup"><span data-stu-id="21285-111">In the preceding example, the `fromCity` and `toCity` string parameters were used to describe the request message, and the float return value was used to describe the reply message.</span></span> <span data-ttu-id="21285-112">Wenn der Rückgabewert allein zur Beschreibung einer Antwortnachricht nicht ausreicht, können out-Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="21285-112">If the return value alone is not enough to describe a reply message, out parameters may be used.</span></span> <span data-ttu-id="21285-113">Der folgende Vorgang enthält z. B. `fromCity` und `toCity` in der Anforderungsnachricht und eine Zahl zusammen mit einer Währung in der Antwortnachricht:</span><span class="sxs-lookup"><span data-stu-id="21285-113">For example, the following operation has `fromCity` and `toCity` in its request message, and a number together with a currency in its reply message:</span></span>  
  
```csharp  
[OperationContract]  
float GetAirfare(string fromCity, string toCity, out string currency);  
```  
  
```vb  
<OperationContract()>  
    Function GetAirfare(fromCity As String, toCity As String) As Double  
```  
  
 <span data-ttu-id="21285-114">Sie können zusätzlich Verweisparameter verwenden, um einen Parameter sowohl zu einem Teil der Anforderungs- als auch der Antwortnachricht zu machen.</span><span class="sxs-lookup"><span data-stu-id="21285-114">Additionally, you may use reference parameters to make a parameter part of both the request and the reply message.</span></span> <span data-ttu-id="21285-115">Die Parameter müssen Typen angehören, die serialisiert (zu XML konvertiert) werden können.</span><span class="sxs-lookup"><span data-stu-id="21285-115">The parameters must be of types that can be serialized (converted to XML).</span></span> <span data-ttu-id="21285-116">Standardmäßig verwendet WCF eine Komponente, die als <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse bezeichnet wird, um diese Konvertierung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="21285-116">By default, WCF uses a component called the <xref:System.Runtime.Serialization.DataContractSerializer> class to perform this conversion.</span></span> <span data-ttu-id="21285-117">Die meisten primitiven Typen (z. B. `int`, `string`, `float` und `DateTime`) werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="21285-117">Most primitive types (such as `int`, `string`, `float`, and `DateTime`.) are supported.</span></span> <span data-ttu-id="21285-118">Benutzerdefinierte Typen müssen normalerweise einen Datenvertrag aufweisen.</span><span class="sxs-lookup"><span data-stu-id="21285-118">User-defined types must normally have a data contract.</span></span> <span data-ttu-id="21285-119">Weitere Informationen finden Sie unter [Verwenden von Daten Verträgen](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="21285-119">For more information, see [Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).</span></span>  
  
```csharp
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    float GetAirfare(Itinerary itinerary, DateTime date);  
  
    [DataContract]  
    public class Itinerary  
    {  
        [DataMember]  
        public string fromCity;  
        [DataMember]  
        public string toCity;  
   }  
}  
```  
  
```vb  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    GetAirfare(itinerary as Itinerary, date as DateTime) as Double  
  
    <DataContract()>  
    Class Itinerary  
  
        <DataMember()>  
        Public fromCity As String  
        <DataMember()>  
        Public toCity As String  
    End Class  
End Interface  
```  
  
 <span data-ttu-id="21285-120">Gelegentlich ist der `DataContractSerializer` nicht zur Serialisierung der Typen geeignet.</span><span class="sxs-lookup"><span data-stu-id="21285-120">Occasionally, the `DataContractSerializer` is not adequate to serialize your types.</span></span> <span data-ttu-id="21285-121">WCF unterstützt ein alternatives Serialisierungsmodul, das-<xref:System.Xml.Serialization.XmlSerializer>, das Sie auch zum Serialisieren von Parametern verwenden können.</span><span class="sxs-lookup"><span data-stu-id="21285-121">WCF supports an alternative serialization engine, the <xref:System.Xml.Serialization.XmlSerializer>, which you can also use to serialize parameters.</span></span> <span data-ttu-id="21285-122">Das <xref:System.Xml.Serialization.XmlSerializer> bietet mehr Kontrolle über den resultierenden XML-Code durch Verwendung von Attributen, wie z. B. `XmlAttributeAttribute`.</span><span class="sxs-lookup"><span data-stu-id="21285-122">The <xref:System.Xml.Serialization.XmlSerializer> allows you to use more control over the resultant XML using attributes such as the `XmlAttributeAttribute`.</span></span> <span data-ttu-id="21285-123">Um zur Verwendung von <xref:System.Xml.Serialization.XmlSerializer> für einen bestimmten Vorgang oder den gesamten Dienst überzugehen, wenden Sie das <xref:System.ServiceModel.XmlSerializerFormatAttribute>-Attribut auf einen Vorgang oder einen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="21285-123">To switch to using the <xref:System.Xml.Serialization.XmlSerializer> for a particular operation or for the entire service, apply the <xref:System.ServiceModel.XmlSerializerFormatAttribute> attribute to an operation or a service.</span></span> <span data-ttu-id="21285-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="21285-124">For example:</span></span>  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    [XmlSerializerFormat]  
    float GetAirfare(Itinerary itinerary, DateTime date);  
}  
public class Itinerary  
{  
    public string fromCity;  
    public string toCity;  
    [XmlAttribute]  
    public bool isFirstClass;  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    <XmlSerializerFormat>  
    GetAirfare(itinerary as Itinerary, date as DateTime) as Double  
  
End Interface  
  
Class Itinerary  
  
    Public fromCity As String  
    Public toCity As String  
    <XmlSerializerFormat()>  
    Public isFirstClass As Boolean  
End Class  
```  
  
 <span data-ttu-id="21285-125">Weitere Informationen finden Sie unter [Verwenden der XmlSerializer-Klasse](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md).</span><span class="sxs-lookup"><span data-stu-id="21285-125">For more information, see [Using the XmlSerializer Class](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md).</span></span> <span data-ttu-id="21285-126">Vergessen Sie nicht, dass ein manueller Wechsel zum <xref:System.Xml.Serialization.XmlSerializer>, wie hier dargestellt, nicht empfohlen wird, wenn nicht triftige Gründe dafür vorliegen, wie sie in diesem Thema ausführlich beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="21285-126">Remember that manually switching to the <xref:System.Xml.Serialization.XmlSerializer> as shown here is not recommended unless you have specific reasons to do so as detailed in that topic.</span></span>  
  
 <span data-ttu-id="21285-127">Zur Isolierung von .NET-Parameternamen von Vertragsnamen können Sie das <xref:System.ServiceModel.MessageParameterAttribute>-Attribut verwenden. Verwenden Sie die `Name`-Eigenschaft zur Festlegung des Vertragsnamens.</span><span class="sxs-lookup"><span data-stu-id="21285-127">To isolate .NET parameter names from contract names, you can use the <xref:System.ServiceModel.MessageParameterAttribute> attribute, and use the `Name` property to set the contract name.</span></span> <span data-ttu-id="21285-128">Der folgende Vorgangsvertrag entspricht z. B. dem ersten Beispiel in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="21285-128">For example, the following operation contract is equivalent to the first example in this topic.</span></span>  
  
```csharp  
[OperationContract]  
public float GetAirfare(  
    [MessageParameter(Name="fromCity")] string originCity,  
    [MessageParameter(Name="toCity")] string destinationCity);  
```  
  
```vb  
<OperationContract()>  
  Function GetAirfare(<MessageParameter(Name := "fromCity")> fromCity As String, <MessageParameter(Name := "toCity")> toCity As String) As Double  
```  
  
## <a name="describing-empty-messages"></a><span data-ttu-id="21285-129">Beschreiben von leeren Nachrichten</span><span class="sxs-lookup"><span data-stu-id="21285-129">Describing Empty Messages</span></span>  
 <span data-ttu-id="21285-130">Eine leere Anforderungsnachricht kann dadurch beschrieben werden, dass sie keine Eingabe- oder Verweisparameter aufweist.</span><span class="sxs-lookup"><span data-stu-id="21285-130">An empty request message can be described by having no input or reference parameters.</span></span> <span data-ttu-id="21285-131">Beispiel in C#:</span><span class="sxs-lookup"><span data-stu-id="21285-131">For example in C#:</span></span>  
  
 `[OperationContract]`  
  
 `public int GetCurrentTemperature();`  
  
 <span data-ttu-id="21285-132">Beispiel in VB:</span><span class="sxs-lookup"><span data-stu-id="21285-132">For example in VB:</span></span>  
  
 `<OperationContract()>`  
  
 `Function GetCurrentTemperature() as Integer`  
  
 <span data-ttu-id="21285-133">Eine leere Antwortnachricht kann dadurch beschrieben werden, dass sie einen `void`-Rückgabetyp und keine Ausgabe- oder Verweisparameter aufweist.</span><span class="sxs-lookup"><span data-stu-id="21285-133">An empty reply message can be described by having a `void` return type and no output or reference parameters.</span></span> <span data-ttu-id="21285-134">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="21285-134">For example in:</span></span>  
  
```csharp  
[OperationContract]  
public void SetTemperature(int temperature);  
```  
  
```vb  
<OperationContract()>  
Sub SetTemperature(temperature As Integer)  
```  
  
 <span data-ttu-id="21285-135">Dies unterscheidet sich von einem unidirektionalen Vorgang wie z. B.:</span><span class="sxs-lookup"><span data-stu-id="21285-135">This is different from a one-way operation, such as:</span></span>  
  
```csharp  
[OperationContract(IsOneWay=true)]  
public void SetLightbulbStatus(bool isOn);  
```  
  
```vb  
<OperationContract(IsOneWay:=True)>  
Sub SetLightbulbStatus(isOne As Boolean)  
```  
  
 <span data-ttu-id="21285-136">Der `SetTemperatureStatus`-Vorgang gibt eine leere Nachricht zurück.</span><span class="sxs-lookup"><span data-stu-id="21285-136">The `SetTemperatureStatus` operation returns an empty message.</span></span> <span data-ttu-id="21285-137">Er gibt stattdessen möglicherweise einen Fehler zurück, wenn es ein Problem beim Verarbeiten der Eingabenachricht gibt.</span><span class="sxs-lookup"><span data-stu-id="21285-137">It may return a fault instead if there is a problem processing the input message.</span></span> <span data-ttu-id="21285-138">Der `SetLightbulbStatus`-Vorgang gibt keinen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="21285-138">The `SetLightbulbStatus` operation returns nothing.</span></span> <span data-ttu-id="21285-139">Es gibt keine Möglichkeit, eine Fehlerbedingung dieses Vorgangs zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="21285-139">There is no way to communicate a fault condition from this operation.</span></span>  
  
## <a name="describing-messages-by-using-message-contracts"></a><span data-ttu-id="21285-140">Beschreiben von Nachrichten mithilfe von Nachrichtenverträgen</span><span class="sxs-lookup"><span data-stu-id="21285-140">Describing Messages by Using Message Contracts</span></span>  
 <span data-ttu-id="21285-141">Sie können einen einzelnen Typ verwenden, um die ganze Nachricht darzustellen.</span><span class="sxs-lookup"><span data-stu-id="21285-141">You may want to use a single type to represent the entire message.</span></span> <span data-ttu-id="21285-142">Es ist zwar möglich, für diesen Zweck einen Datenvertrag zu verwenden, empfohlen wird jedoch die Verwendung eines Nachrichtenvertrags – dadurch werden unnötige Wrappingebenen im resultierenden XML-Code vermieden.</span><span class="sxs-lookup"><span data-stu-id="21285-142">While it is possible to use a data contract for this purpose, the recommended way to do this is to use a message contract—this avoids unnecessary levels of wrapping in the resultant XML.</span></span> <span data-ttu-id="21285-143">Darüber hinaus ermöglichen Nachrichtenverträge eine bessere Kontrolle über die resultierenden Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="21285-143">Additionally, message contracts allow you to exercise more control over resultant messages.</span></span> <span data-ttu-id="21285-144">Sie können z. B. entscheiden, welche Informationen im Nachrichtentext und welche in den Nachrichtenheadern enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="21285-144">For instance, you can decide which pieces of information should be in the message body and which should be in the message headers.</span></span> <span data-ttu-id="21285-145">Im folgenden Beispiel wird die Verwendung von Nachrichtenverträgen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="21285-145">The following example shows the use of message contracts.</span></span>  
  
```csharp  
[ServiceContract]  
public interface IAirfareQuoteService  
{  
    [OperationContract]  
    GetAirfareResponse GetAirfare(GetAirfareRequest request);  
}  
  
[MessageContract]  
public class GetAirfareRequest  
{  
    [MessageHeader] public DateTime date;  
    [MessageBodyMember] public Itinerary itinerary;  
}  
  
[MessageContract]  
public class GetAirfareResponse  
{  
    [MessageBodyMember] public float airfare;  
    [MessageBodyMember] public string currency;  
}  
  
[DataContract]  
public class Itinerary  
{  
    [DataMember] public string fromCity;  
    [DataMember] public string toCity;  
}  
```  
  
```vb  
<ServiceContract()>  
Public Interface IAirfareQuoteService  
    <OperationContract()>  
    Function GetAirfare(request As GetAirfareRequest) As GetAirfareResponse  
End Interface  
  
<MessageContract()>  
Public Class GetAirfareRequest  
    <MessageHeader()>   
    Public Property date as DateTime  
    <MessageBodyMember()>  
    Public Property itinerary As Itinerary  
End Class  
  
<MessageContract()>  
Public Class GetAirfareResponse  
    <MessageBodyMember()>  
    Public Property airfare As Double  
    <MessageBodyMember()> Public Property currency As String  
End Class  
  
<DataContract()>  
Public Class Itinerary  
    <DataMember()> Public Property fromCity As String  
    <DataMember()> Public Property toCity As String  
End Class  
```  
  
 <span data-ttu-id="21285-146">Weitere Informationen finden Sie unter [Verwenden von Nachrichten Verträgen](../../../../docs/framework/wcf/feature-details/using-message-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="21285-146">For more information, see [Using Message Contracts](../../../../docs/framework/wcf/feature-details/using-message-contracts.md).</span></span>  
  
 <span data-ttu-id="21285-147">Im vorigen Beispiel wird die <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse noch standardmäßig verwendet.</span><span class="sxs-lookup"><span data-stu-id="21285-147">In the previous example, the <xref:System.Runtime.Serialization.DataContractSerializer> class is still used by default.</span></span> <span data-ttu-id="21285-148">Die <xref:System.Xml.Serialization.XmlSerializer>-Klasse kann auch in Verbindung mit Nachrichtenverträgen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="21285-148">The <xref:System.Xml.Serialization.XmlSerializer> class can also be used with message contracts.</span></span> <span data-ttu-id="21285-149">Zu diesem Zweck wenden Sie das <xref:System.ServiceModel.XmlSerializerFormatAttribute>-Attribut entweder auf den Vorgang oder auf den Vertrag an, und verwenden Sie Typen, die mit der <xref:System.Xml.Serialization.XmlSerializer>-Klasse in den Nachrichtenheadern und Textmembern kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="21285-149">To do this, apply the <xref:System.ServiceModel.XmlSerializerFormatAttribute> attribute to either the operation or the contract, and use types compatible with the <xref:System.Xml.Serialization.XmlSerializer> class in the message headers and body members.</span></span>  
  
## <a name="describing-messages-by-using-streams"></a><span data-ttu-id="21285-150">Beschreiben von Nachrichten mithilfe von Streams</span><span class="sxs-lookup"><span data-stu-id="21285-150">Describing Messages by Using Streams</span></span>  
 <span data-ttu-id="21285-151">Eine andere Möglichkeit zur Beschreibung von Nachrichten in Vorgängen ist die Verwendung der <xref:System.IO.Stream>-Klasse oder einer der von ihr abgeleiteten Klasse in einem Vorgangsvertrag oder als Textmember eines Nachrichtenvertrags (es muss sich in diesem Fall um den einzigen Member handeln).</span><span class="sxs-lookup"><span data-stu-id="21285-151">Another way to describe messages in operations is to use the <xref:System.IO.Stream> class or one of its derived classes in an operation contract or as a message contract body member (it must be the only member in this case).</span></span> <span data-ttu-id="21285-152">Für eingehende Nachrichten muss der Typ `Stream` sein – es können keine abgeleiteten Klassen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="21285-152">For incoming messages, the type must be `Stream`—you cannot use derived classes.</span></span>  
  
 <span data-ttu-id="21285-153">Anstatt das Serialisierungsprogramm aufzurufen, ruft WCF Daten aus einem Stream ab und fügt Sie direkt in eine ausgehende Nachricht ein oder ruft Daten aus einer eingehenden Nachricht ab und legt Sie direkt in einen Stream.</span><span class="sxs-lookup"><span data-stu-id="21285-153">Instead of invoking the serializer, WCF retrieves data from a stream and puts it directly into an outgoing message, or retrieves data from an incoming message and puts it directly into a stream.</span></span> <span data-ttu-id="21285-154">Im folgenden Beispiel wird die Verwendung von Streams veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="21285-154">The following sample shows the use of streams.</span></span>  
  
```csharp  
[OperationContract]  
public Stream DownloadFile(string fileName);  
```  
  
```vb  
<OperationContract()>  
Function DownloadFile(fileName As String) As String  
```  
  
 <span data-ttu-id="21285-155">Sie können `Stream`- und Nicht-Stream-Daten in einem einzelnen Nachrichtentext nicht kombinieren.</span><span class="sxs-lookup"><span data-stu-id="21285-155">You cannot combine `Stream` and non-stream data in a single message body.</span></span> <span data-ttu-id="21285-156">Verwenden Sie einen Nachrichtenvertrag, um die zusätzlichen Daten in Nachrichtenheader einzusetzen.</span><span class="sxs-lookup"><span data-stu-id="21285-156">Use a message contract to put the extra data in message headers.</span></span> <span data-ttu-id="21285-157">Im folgenden Beispiel wird die falsche Verwendung von Streams bei der Definition des Vorgangsvertrags veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="21285-157">The following example shows the incorrect usage of streams when defining the operation contract.</span></span>  
  
```csharp  
//Incorrect:  
// [OperationContract]  
// public void UploadFile (string fileName, Stream fileData);  
```  
  
```vb  
'Incorrect:  
    '<OperationContract()>  
    Public Sub UploadFile(fileName As String, fileData As StreamingContext)  
```  
  
 <span data-ttu-id="21285-158">Im folgenden Beispiel wird die korrekte Verwendung von Streams bei der Definition eines Vorgangsvertrags veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="21285-158">The following sample shows the correct usage of streams when defining an operation contract.</span></span>  
  
```csharp  
[OperationContract]  
public void UploadFile (UploadFileMessage message);  
//code omitted  
[MessageContract]  
public class UploadFileMessage  
{  
    [MessageHeader] public string fileName;  
    [MessageBodyMember] public Stream fileData;  
}  
```  
  
```vb  
<OperationContract()>  
Public Sub UploadFile(fileName As String, fileData As StreamingContext)  
'Code Omitted  
<MessageContract()>  
Public Class UploadFileMessage  
   <MessageHeader()>  
    Public Property fileName As String  
    <MessageBodyMember()>  
    Public Property fileData As Stream  
End Class  
```  
  
 <span data-ttu-id="21285-159">Weitere Informationen finden Sie unter [große Datenmengen und Streaming](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md).</span><span class="sxs-lookup"><span data-stu-id="21285-159">For more information, see [Large Data and Streaming](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md).</span></span>  
  
## <a name="using-the-message-class"></a><span data-ttu-id="21285-160">Verwenden der Message-Klasse</span><span class="sxs-lookup"><span data-stu-id="21285-160">Using the Message Class</span></span>  
 <span data-ttu-id="21285-161">Um umfassende programmgesteuerte Kontrolle über gesendete oder empfangene Nachrichten zu haben, können Sie die <xref:System.ServiceModel.Channels.Message>-Klasse direkt verwenden, wie im folgenden Beispielcode dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="21285-161">To have complete programmatic control over messages sent or received, you can use the <xref:System.ServiceModel.Channels.Message> class directly, as shown in the following example code.</span></span>  
  
```csharp  
[OperationContract]  
public void LogMessage(Message m);  
```  
  
```vb  
<OperationContract()>  
Sub LogMessage(m As Message)  
```  
  
 <span data-ttu-id="21285-162">Hierbei handelt es sich um ein erweitertes Szenario, das in [der Verwendung der Message-Klasse](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)ausführlich beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="21285-162">This is an advanced scenario, which is described in detail in [Using the Message Class](../../../../docs/framework/wcf/feature-details/using-the-message-class.md).</span></span>  
  
## <a name="describing-fault-messages"></a><span data-ttu-id="21285-163">Beschreiben von Fehlernachrichten</span><span class="sxs-lookup"><span data-stu-id="21285-163">Describing Fault Messages</span></span>  
 <span data-ttu-id="21285-164">Zusätzlich zu den Nachrichten, die durch den Rückgabewert und Ausgabe- oder Verweisparameter beschrieben werden, kann jeder nicht unidirektionale Vorgang mindestes zwei mögliche Nachrichten zurückgeben: die normale Antwortnachricht und eine Fehlernachricht.</span><span class="sxs-lookup"><span data-stu-id="21285-164">In addition to the messages that are described by the return value and output or reference parameters, any operation that is not one-way can return at least two possible messages: its normal response message and a fault message.</span></span> <span data-ttu-id="21285-165">Betrachten Sie den folgenden Vorgangsvertrag.</span><span class="sxs-lookup"><span data-stu-id="21285-165">Consider the following operation contract.</span></span>  
  
```csharp  
[OperationContract]  
float GetAirfare(string fromCity, string toCity, DateTime date);  
```  
  
```vb  
<OperationContract()>  
Function GetAirfare(fromCity As String, toCity As String, date as DateTime)  
```  
  
 <span data-ttu-id="21285-166">Dieser Vorgang kann entweder eine normale Nachricht zurückgeben, die eine `float`-Zahl enthält, oder eine Fehlernachricht, die einen Fehlercode und eine Beschreibung enthält.</span><span class="sxs-lookup"><span data-stu-id="21285-166">This operation may either return a normal message that contains a `float` number, or a fault message that contains a fault code and a description.</span></span> <span data-ttu-id="21285-167">Dies kann durch Auslösen einer <xref:System.ServiceModel.FaultException> in der Dienstimplementierung erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="21285-167">You can accomplish this by throwing a <xref:System.ServiceModel.FaultException> in your service implementation.</span></span>  
  
 <span data-ttu-id="21285-168">Sie können weitere mögliche Fehlermeldungen angeben, indem Sie das <xref:System.ServiceModel.FaultContractAttribute>-Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="21285-168">You can specify additional possible fault messages by using the <xref:System.ServiceModel.FaultContractAttribute> attribute.</span></span> <span data-ttu-id="21285-169">Die zusätzlichen Fehler müssen mit dem <xref:System.Runtime.Serialization.DataContractSerializer> serialisierbar sein, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="21285-169">The additional faults must be serializable using the <xref:System.Runtime.Serialization.DataContractSerializer>, as shown in the following example code.</span></span>  
  
```csharp  
[OperationContract]  
[FaultContract(typeof(ItineraryNotAvailableFault))]  
float GetAirfare(string fromCity, string toCity, DateTime date);  
  
//code omitted  
  
[DataContract]  
public class ItineraryNotAvailableFault  
{  
    [DataMember]  
    public bool IsAlternativeDateAvailable;  
  
    [DataMember]  
    public DateTime alternativeSuggestedDate;  
}  
```  
  
```vb  
<OperationContract()>  
<FaultContract(GetType(ItineraryNotAvailableFault))>  
Function GetAirfare(fromCity As String, toCity As String, date as DateTime) As Double  
  
'Code Omitted  
<DataContract()>  
Public Class  
  <DataMember()>  
  Public Property IsAlternativeDateAvailable As Boolean  
  <DataMember()>  
  Public Property alternativeSuggestedDate As DateTime  
End Class  
```  
  
 <span data-ttu-id="21285-170">Diese zusätzlichen Fehler können durch Auslösen einer <xref:System.ServiceModel.FaultException%601> des geeigneten Datenvertragstyps generiert werden.</span><span class="sxs-lookup"><span data-stu-id="21285-170">These additional faults can be generated by throwing a <xref:System.ServiceModel.FaultException%601> of the appropriate data contract type.</span></span> <span data-ttu-id="21285-171">Weitere Informationen finden Sie unter [Behandeln von Ausnahmen und Fehlern](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).</span><span class="sxs-lookup"><span data-stu-id="21285-171">For more information, see [Handling Exceptions and Faults](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).</span></span>  
  
 <span data-ttu-id="21285-172">Sie können die <xref:System.Xml.Serialization.XmlSerializer>-Klasse nicht verwenden, um Fehler zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="21285-172">You cannot use the <xref:System.Xml.Serialization.XmlSerializer> class to describe faults.</span></span> <span data-ttu-id="21285-173">Das <xref:System.ServiceModel.XmlSerializerFormatAttribute> hat keine Auswirkungen auf Fehlerverträge.</span><span class="sxs-lookup"><span data-stu-id="21285-173">The <xref:System.ServiceModel.XmlSerializerFormatAttribute> has no effect on fault contracts.</span></span>  
  
## <a name="using-derived-types"></a><span data-ttu-id="21285-174">Verwenden von abgeleiteten Typen</span><span class="sxs-lookup"><span data-stu-id="21285-174">Using Derived Types</span></span>  
 <span data-ttu-id="21285-175">Sie können einen Basistyp für einen Vorgangs- oder Nachrichtenvertrag verwenden und dann einen abgeleiteten Typ verwenden, wenn Sie den Vorgang tatsächlich aufrufen.</span><span class="sxs-lookup"><span data-stu-id="21285-175">You may want to use a base type in an operation or a message contract, and then use a derived type when actually invoking the operation.</span></span> <span data-ttu-id="21285-176">In diesem Fall müssen Sie entweder das <xref:System.ServiceModel.ServiceKnownTypeAttribute>-Attribut oder einen alternativen Mechanismus verwenden, um die Verwendung von abgeleiteten Typen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="21285-176">In this case, you must use either the <xref:System.ServiceModel.ServiceKnownTypeAttribute> attribute or some alternative mechanism to allow the use of derived types.</span></span> <span data-ttu-id="21285-177">Betrachten Sie den folgenden Vorgang.</span><span class="sxs-lookup"><span data-stu-id="21285-177">Consider the following operation.</span></span>  
  
```csharp  
[OperationContract]  
public bool IsLibraryItemAvailable(LibraryItem item);  
```  
  
```vb
<OperationContract()>  
    Function IsLibraryItemAvailable(item As LibraryItem) As Boolean  
```  
  
 <span data-ttu-id="21285-178">Angenommen, zwei Typen, `Book` und `Magazine`, werden aus `LibraryItem` abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="21285-178">Assume that two types, `Book` and `Magazine`, derive from `LibraryItem`.</span></span> <span data-ttu-id="21285-179">Um diese Typen im `IsLibraryItemAvailable`-Vorgang zu verwenden, können Sie den Vorgang wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="21285-179">To use these types in the `IsLibraryItemAvailable` operation, you can change the operation as follows:</span></span>  
  
 `[OperationContract]`  
  
 `[ServiceKnownType(typeof(Book))]`  
  
 `[ServiceKnownType(typeof(Magazine))]`  
  
 `public bool IsLibraryItemAvailable(LibraryItem item);`  
  
 <span data-ttu-id="21285-180">Alternativ dazu können Sie, wie im folgenden Beispielcode dargestellt, das <xref:System.Runtime.Serialization.KnownTypeAttribute>-Attribut verwenden, wenn das Standard-<xref:System.Runtime.Serialization.DataContractSerializer> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="21285-180">Alternatively, you can use the <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute when the default <xref:System.Runtime.Serialization.DataContractSerializer> is in use, as shown in the following example code.</span></span>  
  
```csharp  
[OperationContract]  
public bool IsLibraryItemAvailable(LibraryItem item);  
  
// code omitted   
  
[DataContract]  
[KnownType(typeof(Book))]  
[KnownType(typeof(Magazine))]  
public class LibraryItem  
{  
    //code omitted  
}  
```  
  
```vb  
<OperationContract()>  
Function IsLibraryItemAvailable(item As LibraryItem) As Boolean  
  
'Code Omitted  
<DataContract()>  
<KnownType(GetType(Book))>  
<KnownType(GetType(Magazine))>  
Public Class LibraryItem  
  'Code Omitted  
End Class  
```  
  
 <span data-ttu-id="21285-181">Sie können das <xref:System.Xml.Serialization.XmlIncludeAttribute>-Attribut verwenden, wenn Sie <xref:System.Xml.Serialization.XmlSerializer> verwenden.</span><span class="sxs-lookup"><span data-stu-id="21285-181">You can use the <xref:System.Xml.Serialization.XmlIncludeAttribute> attribute when using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
 <span data-ttu-id="21285-182">Sie können das <xref:System.ServiceModel.ServiceKnownTypeAttribute>-Attribut auf einen Vorgang oder auf den gesamten Dienst anwenden.</span><span class="sxs-lookup"><span data-stu-id="21285-182">You can apply the <xref:System.ServiceModel.ServiceKnownTypeAttribute> attribute to an operation or to the entire service.</span></span> <span data-ttu-id="21285-183">Es akzeptiert entweder einen Typ oder den Namen der Methode, die aufgerufen werden soll, um eine Liste bekannter Typen zu erzeugen, genau wie das <xref:System.Runtime.Serialization.KnownTypeAttribute>-Attribut.</span><span class="sxs-lookup"><span data-stu-id="21285-183">It accepts either a type or the name of the method to call to get a list of known types, just like the <xref:System.Runtime.Serialization.KnownTypeAttribute> attribute.</span></span> <span data-ttu-id="21285-184">Weitere Informationen finden Sie unter [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="21285-184">For more information, see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span>  
  
## <a name="specifying-the-use-and-style"></a><span data-ttu-id="21285-185">Angeben der Verwendung und des Stils</span><span class="sxs-lookup"><span data-stu-id="21285-185">Specifying the Use and Style</span></span>  
 <span data-ttu-id="21285-186">Bei der Beschreibung von Diensten mithilfe von Web Services Description Language (WSDL) sind die beiden am häufigsten verwendeten Stile der Dokumentstil und der Remoteprozeduraufruf (RPC, remote procedure call).</span><span class="sxs-lookup"><span data-stu-id="21285-186">When describing services using Web Services Description Language (WSDL), the two commonly used styles are Document and remote procedure call (RPC).</span></span> <span data-ttu-id="21285-187">Beim Dokumentstil wird der gesamte Nachrichtentext mithilfe des Schemas beschrieben, und WSDL beschreibt die verschiedenen Nachrichtentextteile durch Verweisen auf Elemente innerhalb dieses Schemas.</span><span class="sxs-lookup"><span data-stu-id="21285-187">In the Document style, the entire message body is described using the schema, and the WSDL describes the various message body parts by referring to elements within that schema.</span></span> <span data-ttu-id="21285-188">Beim RPC-Stil verweist WSDL auf einen Schematyp für jeden Nachrichtenteil statt auf ein Element.</span><span class="sxs-lookup"><span data-stu-id="21285-188">In the RPC style, the WSDL refers to a schema type for each message part rather than an element.</span></span> <span data-ttu-id="21285-189">In einigen Fällen müssen Sie einen dieser Stile manuell auswählen.</span><span class="sxs-lookup"><span data-stu-id="21285-189">In some cases, you have to manually select one of these styles.</span></span> <span data-ttu-id="21285-190">Zu diesem Zweck können Sie das <xref:System.ServiceModel.DataContractFormatAttribute>-Attribut anwenden und die `Style`-Eigenschaft festlegen (wenn das <xref:System.Runtime.Serialization.DataContractSerializer> verwendet wird), oder Sie legen `Style` in dem <xref:System.ServiceModel.XmlSerializerFormatAttribute>-Attribut fest (wenn das <xref:System.Xml.Serialization.XmlSerializer> verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="21285-190">You can do this by applying the <xref:System.ServiceModel.DataContractFormatAttribute> attribute and setting the `Style` property (when the <xref:System.Runtime.Serialization.DataContractSerializer> is in use), or by setting `Style` on the <xref:System.ServiceModel.XmlSerializerFormatAttribute> attribute (when using the <xref:System.Xml.Serialization.XmlSerializer>).</span></span>  
  
 <span data-ttu-id="21285-191">Außerdem unterstützt der <xref:System.Xml.Serialization.XmlSerializer> zwei Formen von serialisiertem XML: `Literal` und `Encoded`.</span><span class="sxs-lookup"><span data-stu-id="21285-191">Additionally, the <xref:System.Xml.Serialization.XmlSerializer> supports two forms of serialized XML: `Literal` and `Encoded`.</span></span> <span data-ttu-id="21285-192">`Literal` ist das am häufigsten akzeptierte Formular und ist die einzige Form, die vom <xref:System.Runtime.Serialization.DataContractSerializer> unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="21285-192">`Literal` is the most commonly accepted form, and is the only form the <xref:System.Runtime.Serialization.DataContractSerializer> supports.</span></span> <span data-ttu-id="21285-193">`Encoded` ist eine Legacy Form, die in Abschnitt 5 der SOAP-Spezifikation beschrieben wird, und wird für neue Dienste nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="21285-193">`Encoded` is a legacy form described in section 5 of the SOAP specification, and is not recommended for new services.</span></span> <span data-ttu-id="21285-194">Um zum `Encoded`-Modus zu wechseln, legen Sie die `Use`-Eigenschaft für das <xref:System.ServiceModel.XmlSerializerFormatAttribute>-Attribut auf `Encoded` fest.</span><span class="sxs-lookup"><span data-stu-id="21285-194">To switch to `Encoded` mode, set the `Use` property on the <xref:System.ServiceModel.XmlSerializerFormatAttribute> attribute to `Encoded`.</span></span>  
  
 <span data-ttu-id="21285-195">In den meisten Fällen sollten Sie die Standardeinstellungen für die `Style`- und die `Use`-Eigenschaft nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="21285-195">In most cases, you should not change the default settings for the `Style` and `Use` properties.</span></span>  
  
## <a name="controlling-the-serialization-process"></a><span data-ttu-id="21285-196">Kontrollieren des Serialisierungsprozesses</span><span class="sxs-lookup"><span data-stu-id="21285-196">Controlling the Serialization Process</span></span>  
 <span data-ttu-id="21285-197">Es gibt eine Reihe von Möglichkeiten, die Art und Weise anzupassen, in der Daten serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="21285-197">You can do a number of things to customize the way data is serialized.</span></span>  
  
### <a name="changing-server-serialization-settings"></a><span data-ttu-id="21285-198">Ändern der Serverserialisierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="21285-198">Changing Server Serialization Settings</span></span>  
 <span data-ttu-id="21285-199">Wenn das Standard-<xref:System.Runtime.Serialization.DataContractSerializer> verwendet wird, können Sie einige Aspekte des Serialisierungsprozesses für den Dienst durch Anwenden des <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attributs auf den Dienst steuern.</span><span class="sxs-lookup"><span data-stu-id="21285-199">When the default <xref:System.Runtime.Serialization.DataContractSerializer> is in use, you can control some aspects of the serialization process on the service by applying the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the service.</span></span> <span data-ttu-id="21285-200">Sie können insbesondere die `MaxItemsInObjectGraph`-Eigenschaft verwenden, um das Kontingent festzulegen, das die maximale Anzahl an Objekten einschränkt, die das <xref:System.Runtime.Serialization.DataContractSerializer> deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="21285-200">Specifically, you may use the `MaxItemsInObjectGraph` property to set the quota that limits the maximum number of objects the <xref:System.Runtime.Serialization.DataContractSerializer> deserializes.</span></span> <span data-ttu-id="21285-201">Sie können die `IgnoreExtensionDataObject`-Eigenschaft verwenden, um die Roundtrip-Versionsverwaltungsfunktion zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="21285-201">You can use the `IgnoreExtensionDataObject` property to turn off the round-tripping versioning feature.</span></span> <span data-ttu-id="21285-202">Weitere Informationen über Kontingenten finden Sie unter [Security Considerations for Data (Sicherheitsüberlegungen zu Daten)](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).</span><span class="sxs-lookup"><span data-stu-id="21285-202">For more information about quotas, see [Security Considerations for Data](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).</span></span> <span data-ttu-id="21285-203">Weitere Informationen zum Roundtrip finden Sie unter [Forward-kompatible Datenverträge](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="21285-203">For more information about round-tripping, see [Forward-Compatible Data Contracts](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).</span></span>  
  
```csharp  
[ServiceBehavior(MaxItemsInObjectGraph=100000)]  
public class MyDataService:IDataService  
{  
    public DataPoint[] GetData()  
    {  
       // Implementation omitted  
    }  
}  
```  
  
```vb  
<ServiceBehavior(MaxItemsInObjectGraph:=100000)>  
Public Class MyDataService Implements IDataService  
  
    Function GetData() As DataPoint()  
         ‘ Implementation omitted  
    End Function  
End Interface  
```  
  
### <a name="serialization-behaviors"></a><span data-ttu-id="21285-204">Serialisierungsverhalten</span><span class="sxs-lookup"><span data-stu-id="21285-204">Serialization Behaviors</span></span>  
 <span data-ttu-id="21285-205">In WCF sind zwei Verhaltensweisen verfügbar, die <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> und die <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior>, die automatisch eingebunden werden, je nachdem, welches Serialisierungsprogramm für einen bestimmten Vorgang verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="21285-205">Two behaviors are available in WCF, the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> and the <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> that are automatically plugged in depending on which serializer is in use for a particular operation.</span></span> <span data-ttu-id="21285-206">Da diese Arten von Verhalten automatisch angewendet werden, müssen Sie sie normalerweise nicht beachten.</span><span class="sxs-lookup"><span data-stu-id="21285-206">Because these behaviors are applied automatically, you normally do not have to be aware of them.</span></span>  
  
 <span data-ttu-id="21285-207">`DataContractSerializerOperationBehavior` weist jedoch die `MaxItemsInObjectGraph`-, die `IgnoreExtensionDataObject`- und die `DataContractSurrogate`-Eigenschaften auf, die Sie zur Anpassung des Serialisierungsprozesses verwenden können.</span><span class="sxs-lookup"><span data-stu-id="21285-207">However, the `DataContractSerializerOperationBehavior` has the `MaxItemsInObjectGraph`, `IgnoreExtensionDataObject`, and `DataContractSurrogate` properties that you may use to customize the serialization process.</span></span> <span data-ttu-id="21285-208">Die ersten beiden Eigenschaften haben die gleiche Bedeutung, wie im vorherigen Abschnitt erläutert.</span><span class="sxs-lookup"><span data-stu-id="21285-208">The first two properties have the same meaning as discussed in the previous section.</span></span> <span data-ttu-id="21285-209">Sie können die `DataContractSurrogate`-Eigenschaft verwenden, um Datenvertrag-Ersatzzeichen zu aktivieren, die ein leistungsfähiges Werkzeug zum Anpassen und Erweitern des Serialisierungsprozesses darstellen.</span><span class="sxs-lookup"><span data-stu-id="21285-209">You can use the `DataContractSurrogate` property to enable data contract surrogates, which are a powerful mechanism for customizing and extending the serialization process.</span></span> <span data-ttu-id="21285-210">Weitere Informationen finden Sie unter [Data Contract Surrogates](../../../../docs/framework/wcf/extending/data-contract-surrogates.md).</span><span class="sxs-lookup"><span data-stu-id="21285-210">For more information, see [Data Contract Surrogates](../../../../docs/framework/wcf/extending/data-contract-surrogates.md).</span></span>  
  
 <span data-ttu-id="21285-211">Sie können das `DataContractSerializerOperationBehavior` verwenden, um sowohl die Client- als auch die Serverserialisierung anzupassen.</span><span class="sxs-lookup"><span data-stu-id="21285-211">You can use the `DataContractSerializerOperationBehavior` to customize both client and server serialization.</span></span> <span data-ttu-id="21285-212">Im folgenden Beispiel wird das Erhöhen des `MaxItemsInObjectGraph`-Kontingents für den Client veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="21285-212">The following example shows how to increase the `MaxItemsInObjectGraph` quota on the client.</span></span>  
  
```csharp  
ChannelFactory<IDataService> factory = new ChannelFactory<IDataService>(binding, address);  
foreach (OperationDescription op in factory.Endpoint.Contract.Operations)  
{  
    DataContractSerializerOperationBehavior dataContractBehavior =  
                op.Behaviors.Find<DataContractSerializerOperationBehavior>()  
                as DataContractSerializerOperationBehavior;  
    if (dataContractBehavior != null)  
    {  
        dataContractBehavior.MaxItemsInObjectGraph = 100000;  
    }  
}  
IDataService client = factory.CreateChannel();  
```  
  
```vb  
Dim factory As ChannelFactory(Of IDataService) = New ChannelFactory(Of IDataService)(binding, address)  
For Each op As OperationDescription In factory.Endpoint.Contract.Operations  
        Dim dataContractBehavior As DataContractSerializerOperationBehavior = op.Behaviors.Find(Of DataContractSerializerOperationBehavior)()  
        If dataContractBehavior IsNot Nothing Then  
            dataContractBehavior.MaxItemsInObjectGraph = 100000  
        End If  
     Next  
    Dim client As IDataService = factory.CreateChannel  
```  
  
<span data-ttu-id="21285-213">Im folgenden finden Sie den entsprechenden Code für den Dienst in der selbstgeh osteten Groß-/Kleinschreibung:</span><span class="sxs-lookup"><span data-stu-id="21285-213">The following is the equivalent code on the service, in the self-hosted case:</span></span>
  
```csharp  
ServiceHost serviceHost = new ServiceHost(typeof(IDataService))  
foreach (ServiceEndpoint ep in serviceHost.Description.Endpoints)  
{  
foreach (OperationDescription op in ep.Contract.Operations)  
{  
        DataContractSerializerOperationBehavior dataContractBehavior =  
           op.Behaviors.Find<DataContractSerializerOperationBehavior>()  
                as DataContractSerializerOperationBehavior;  
        if (dataContractBehavior != null)  
        {  
            dataContractBehavior.MaxItemsInObjectGraph = 100000;  
        }  
}  
}  
serviceHost.Open();  
```  
  
```vb  
Dim serviceHost As ServiceHost = New ServiceHost(GetType(IDataService))  
        For Each ep As ServiceEndpoint In serviceHost.Description.Endpoints  
            For Each op As OperationDescription In ep.Contract.Operations  
                Dim dataContractBehavior As DataContractSerializerOperationBehavior = op.Behaviors.Find(Of DataContractSerializerOperationBehavior)()  
  
                If dataContractBehavior IsNot Nothing Then  
                    dataContractBehavior.MaxItemsInObjectGraph = 100000  
                End If  
            Next  
        Next  
        serviceHost.Open()  
```  
  
 <span data-ttu-id="21285-214">Falls er im Internet gehostet wird, müssen Sie eine neue abgeleitete `ServiceHost`-Klasse erstellen und die Diensthostfactory verwenden, um sie zu laden.</span><span class="sxs-lookup"><span data-stu-id="21285-214">In the Web-hosted case, you must create a new `ServiceHost` derived class and use a service host factory to plug it in.</span></span>  
  
### <a name="controlling-serialization-settings-in-configuration"></a><span data-ttu-id="21285-215">Steuern von Serialisierungseinstellungen in der Konfiguration</span><span class="sxs-lookup"><span data-stu-id="21285-215">Controlling Serialization Settings in Configuration</span></span>  
 <span data-ttu-id="21285-216">`MaxItemsInObjectGraph` und `IgnoreExtensionDataObject` können über die Konfiguration mithilfe des `dataContractSerializer`-Endpunkts oder -Dienstverhaltens gesteuert werden, wie im folgenden Beispiel dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="21285-216">The `MaxItemsInObjectGraph` and `IgnoreExtensionDataObject` can be controlled through configuration by using the `dataContractSerializer` endpoint or service behavior, as shown in the following example.</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="LargeQuotaBehavior">  
                    <dataContractSerializer  
                      maxItemsInObjectGraph="100000" />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <client>  
            <endpoint address="http://example.com/myservice"  
                  behaviorConfiguration="LargeQuotaBehavior"  
                binding="basicHttpBinding" bindingConfiguration=""   
                            contract="IDataService"  
                name="" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
### <a name="shared-type-serialization-object-graph-preservation-and-custom-serializers"></a><span data-ttu-id="21285-217">Serialisierung von gemeinsamen Typen, Objektdiagrammbeibehaltung und benutzerdefinierte Serialisierungsprogramme</span><span class="sxs-lookup"><span data-stu-id="21285-217">Shared Type Serialization, Object Graph Preservation, and Custom Serializers</span></span>  
 <span data-ttu-id="21285-218">Das <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert mithilfe von Datenvertragsnamen und nicht mithilfe von .NET-Typnamen.</span><span class="sxs-lookup"><span data-stu-id="21285-218">The <xref:System.Runtime.Serialization.DataContractSerializer> serializes using data contract names and not .NET type names.</span></span> <span data-ttu-id="21285-219">Dies entspricht dienstorientierten Architekturgrundsätzen und ermöglicht einen hohen Grad an Flexibilität – die .NET-Typen können sich ändern, ohne sich auf den Übertragungsvertrag auszuwirken.</span><span class="sxs-lookup"><span data-stu-id="21285-219">This is consistent with service-oriented architecture tenets and allows for a great degree of flexibility—the .NET types can change without affecting the wire contract.</span></span> <span data-ttu-id="21285-220">In seltenen Fällen kann es notwendig sein, tatsächliche .NET-Typnamen zu serialisieren und dabei eine enge Verknüpfung zwischen dem Client und dem Server vorzunehmen, ähnlich wie bei der .NET-Framework-Remotetechnologie.</span><span class="sxs-lookup"><span data-stu-id="21285-220">In rare cases, you may want to serialize actual .NET type names, thereby introducing a tight coupling between the client and the server, similar to the .NET Framework remoting technology.</span></span> <span data-ttu-id="21285-221">Dies ist keine empfohlene Vorgehensweise, außer in seltenen Fällen, die in der Regel auftreten, wenn von .NET Framework Remoting zu WCF migriert wird.</span><span class="sxs-lookup"><span data-stu-id="21285-221">This is not a recommended practice, except in rare cases that usually occur when migrating to WCF from .NET Framework remoting.</span></span> <span data-ttu-id="21285-222">In diesem Fall müssen Sie die <xref:System.Runtime.Serialization.NetDataContractSerializer>-Klasse statt der <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="21285-222">In this case, you must use the <xref:System.Runtime.Serialization.NetDataContractSerializer> class instead of the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span>  
  
 <span data-ttu-id="21285-223">Das <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert normalerweise Objektdiagramme als Objektstrukturen,</span><span class="sxs-lookup"><span data-stu-id="21285-223">The <xref:System.Runtime.Serialization.DataContractSerializer> normally serializes object graphs as object trees.</span></span> <span data-ttu-id="21285-224">d. h. auf dasselbe Objekt wird mehr als einmal verwiesen, es wird mehr als einmal serialisiert.</span><span class="sxs-lookup"><span data-stu-id="21285-224">That is, if the same object is referred to more than once, it is serialized more than once.</span></span> <span data-ttu-id="21285-225">Betrachten Sie z. B. eine `PurchaseOrder`-Instanz, die über zwei Felder vom Typ Adresse mit den Namen `billTo` und `shipTo` verfügt.</span><span class="sxs-lookup"><span data-stu-id="21285-225">For example, consider a `PurchaseOrder` instance that has two fields of type Address called `billTo` and `shipTo`.</span></span> <span data-ttu-id="21285-226">Wenn beide Felder auf dieselbe Adressinstanz festgelegt werden, gibt es zwei identische Adressinstanzen nach der Serialisierung und der Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="21285-226">If both fields are set to the same Address instance, there are two identical Address instances after serialization and deserialization.</span></span> <span data-ttu-id="21285-227">Dies erfolgt, weil es kein interoperables Standardverfahren zur Darstellung von Objektdiagrammen in XML gibt (außer dem älteren SOAP-Codierungsstandard, der für <xref:System.Xml.Serialization.XmlSerializer> verfügbar ist, wie im vorigen Abschnitt über `Style` und `Use` beschrieben).</span><span class="sxs-lookup"><span data-stu-id="21285-227">This is done because there is no standard interoperable way to represent object graphs in XML (except for the legacy SOAP encoded standard available on the <xref:System.Xml.Serialization.XmlSerializer>, as described in the previous section on `Style` and `Use`).</span></span> <span data-ttu-id="21285-228">Objektdiagramme als Strukturen zu serialisieren, bringt gewisse Nachteile mit sich, z. B. können Diagramme mit Zirkelverweisen nicht serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="21285-228">Serializing object graphs as trees has certain disadvantages, for example, graphs with circular references cannot be serialized.</span></span> <span data-ttu-id="21285-229">Gelegentlich ist es erforderlich, auf echte Objektdiagrammserialisierung umzustellen, obwohl sie nicht interoperabel ist.</span><span class="sxs-lookup"><span data-stu-id="21285-229">Occasionally, it is necessary to switch to true object graph serialization, even though it is not interoperable.</span></span> <span data-ttu-id="21285-230">Dies kann durch Verwendung vom <xref:System.Runtime.Serialization.DataContractSerializer> erfolgen, das mit dem `preserveObjectReferences`-Parameter konstruiert ist, der auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="21285-230">This can be done by using the <xref:System.Runtime.Serialization.DataContractSerializer> constructed with the `preserveObjectReferences` parameter set to `true`.</span></span>  
  
 <span data-ttu-id="21285-231">Gelegentlich reichen die integrierten Serialisierungsprogramme nicht für das Szenario aus.</span><span class="sxs-lookup"><span data-stu-id="21285-231">Occasionally, the built-in serializers are not enough for your scenario.</span></span> <span data-ttu-id="21285-232">In den meisten Fällen können Sie trotzdem die <xref:System.Runtime.Serialization.XmlObjectSerializer>-Abstraktion verwenden, von der sowohl das <xref:System.Runtime.Serialization.DataContractSerializer> als auch das <xref:System.Runtime.Serialization.NetDataContractSerializer> abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="21285-232">In most cases, you can still use the <xref:System.Runtime.Serialization.XmlObjectSerializer> abstraction from which both the <xref:System.Runtime.Serialization.DataContractSerializer> and the <xref:System.Runtime.Serialization.NetDataContractSerializer> derive.</span></span>  
  
 <span data-ttu-id="21285-233">Die drei vorherigen Fälle (.NET-Typbeibehaltung, Objektdiagrammbeibehaltung und die vollkommen benutzerdefinierte `XmlObjectSerializer`-basierte Serialisierung) erfordern alle die Einbindung eines benutzerdefinierten Serialisierungsprogramms.</span><span class="sxs-lookup"><span data-stu-id="21285-233">The previous three cases (.NET type preservation, object graph preservation, and completely custom `XmlObjectSerializer`-based serialization) all require a custom serializer be plugged in.</span></span> <span data-ttu-id="21285-234">Gehen Sie hierzu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="21285-234">To do this, perform the following steps:</span></span>  
  
1. <span data-ttu-id="21285-235">Schreiben Sie ein eigenes Verhalten, das sich vom <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> herleitet.</span><span class="sxs-lookup"><span data-stu-id="21285-235">Write your own behavior deriving from the <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>.</span></span>  
  
2. <span data-ttu-id="21285-236">Überschreiben Sie die beiden `CreateSerializer`-Methoden, um Ihr eigenes Serialisierungsprogramm zurückzugeben (entweder das <xref:System.Runtime.Serialization.NetDataContractSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer> mit `preserveObjectReferences` festgelegt auf `true` oder Ihr eigenes benutzerdefiniertes <xref:System.Runtime.Serialization.XmlObjectSerializer>).</span><span class="sxs-lookup"><span data-stu-id="21285-236">Override the two `CreateSerializer` methods to return your own serializer (either the <xref:System.Runtime.Serialization.NetDataContractSerializer>, the <xref:System.Runtime.Serialization.DataContractSerializer> with `preserveObjectReferences` set to `true`, or your own custom <xref:System.Runtime.Serialization.XmlObjectSerializer>).</span></span>  
  
3. <span data-ttu-id="21285-237">Vor dem Öffnen des Diensthosts oder dem Erstellen eines Clientkanals entfernen Sie das vorhandene <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>-Verhalten und binden die benutzerdefinierte abgeleitete Klasse ein, die Sie in den vorherigen Schritten erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="21285-237">Before opening the service host or creating a client channel, remove the existing <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> behavior and plug in the custom derived class that you created in the previous steps.</span></span>  
  
 <span data-ttu-id="21285-238">Weitere Informationen zu erweiterten Serialisierungskonzepten finden Sie unter [Serialisierung und Deserialisierung](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md).</span><span class="sxs-lookup"><span data-stu-id="21285-238">For more information about advanced serialization concepts, see [Serialization and Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21285-239">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21285-239">See also</span></span>

- [<span data-ttu-id="21285-240">Verwenden der XmlSerializer-Klasse</span><span class="sxs-lookup"><span data-stu-id="21285-240">Using the XmlSerializer Class</span></span>](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)
- [<span data-ttu-id="21285-241">Vorgehensweise: Aktivieren von Streaming</span><span class="sxs-lookup"><span data-stu-id="21285-241">How to: Enable Streaming</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-streaming.md)
- [<span data-ttu-id="21285-242">Vorgehensweise: Erstellen eines grundlegenden Datenvertrags für eine Klasse oder Struktur</span><span class="sxs-lookup"><span data-stu-id="21285-242">How to: Create a Basic Data Contract for a Class or Structure</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-data-contract-for-a-class-or-structure.md)
