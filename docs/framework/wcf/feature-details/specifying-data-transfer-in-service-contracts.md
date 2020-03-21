---
title: Angeben von Datenübertragung in Dienstverträgen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], data transfer
ms.assetid: 7c5a26c8-89c9-4bcb-a4bc-7131e6d01f0c
ms.openlocfilehash: e68ca46f9d2c562491063ae66754c469dbe0898e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184429"
---
# <a name="specifying-data-transfer-in-service-contracts"></a>Angeben von Datenübertragung in Dienstverträgen
Die Windows Communication Foundation (WCF) kann als Messaginginfrastruktur betrachtet werden. Dienstvorgänge können Nachrichten empfangen, sie verarbeiten und ihnen Nachrichten schicken. Nachrichten werden mit Vorgangsverträgen beschrieben. Beispiel:  
  
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
  
 Hier akzeptiert der `GetAirfare`-Vorgang eine Nachricht mit Informationen über `fromCity` und `toCity` und gibt dann eine Nachricht zurück, die eine Zahl enthält.  
  
 In diesem Thema werden die verschiedenen Möglichkeiten erläutert, wie ein Vorgangsvertrag Nachrichten beschreiben kann.  
  
## <a name="describing-messages-by-using-parameters"></a>Beschreiben von Nachrichten mithilfe von Parametern  
 Die einfachste Art zur Beschreibung einer Nachricht ist die Verwendung einer Parameterliste und des Rückgabewerts. Im vorherigen Beispiel wurden der `fromCity`- und der `toCity`-Zeichenfolgenparameter zur Beschreibung der Anforderungsnachricht verwendet, und der Gleitkommarückgabewert wurde zur Beschreibung der Antwortnachricht verwendet. Wenn der Rückgabewert allein zur Beschreibung einer Antwortnachricht nicht ausreicht, können out-Parameter verwendet werden. Der folgende Vorgang enthält z. B. `fromCity` und `toCity` in der Anforderungsnachricht und eine Zahl zusammen mit einer Währung in der Antwortnachricht:  
  
```csharp  
[OperationContract]  
float GetAirfare(string fromCity, string toCity, out string currency);  
```  
  
```vb  
<OperationContract()>  
    Function GetAirfare(fromCity As String, toCity As String) As Double  
```  
  
 Sie können zusätzlich Verweisparameter verwenden, um einen Parameter sowohl zu einem Teil der Anforderungs- als auch der Antwortnachricht zu machen. Die Parameter müssen Typen angehören, die serialisiert (zu XML konvertiert) werden können. Standardmäßig verwendet WCF eine Komponente <xref:System.Runtime.Serialization.DataContractSerializer> namens Klasse, um diese Konvertierung durchzuführen. Die meisten primitiven Typen (z. B. `int`, `string`, `float` und `DateTime`) werden unterstützt. Benutzerdefinierte Typen müssen normalerweise einen Datenvertrag aufweisen. Weitere Informationen finden Sie unter [Verwenden von Datenverträgen](../../../../docs/framework/wcf/feature-details/using-data-contracts.md).  
  
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
  
 Gelegentlich ist der `DataContractSerializer` nicht zur Serialisierung der Typen geeignet. WCF unterstützt ein alternatives Serialisierungsmodul, die <xref:System.Xml.Serialization.XmlSerializer>, die Sie auch zum Serialisieren von Parametern verwenden können. Das <xref:System.Xml.Serialization.XmlSerializer> bietet mehr Kontrolle über den resultierenden XML-Code durch Verwendung von Attributen, wie z. B. `XmlAttributeAttribute`. Um zur Verwendung von <xref:System.Xml.Serialization.XmlSerializer> für einen bestimmten Vorgang oder den gesamten Dienst überzugehen, wenden Sie das <xref:System.ServiceModel.XmlSerializerFormatAttribute>-Attribut auf einen Vorgang oder einen Dienst an. Beispiel:  
  
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
  
 Weitere Informationen finden Sie unter [Verwenden der XmlSerializer-Klasse](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md). Vergessen Sie nicht, dass ein manueller Wechsel zum <xref:System.Xml.Serialization.XmlSerializer>, wie hier dargestellt, nicht empfohlen wird, wenn nicht triftige Gründe dafür vorliegen, wie sie in diesem Thema ausführlich beschrieben werden.  
  
 Zur Isolierung von .NET-Parameternamen von Vertragsnamen können Sie das <xref:System.ServiceModel.MessageParameterAttribute>-Attribut verwenden. Verwenden Sie die `Name`-Eigenschaft zur Festlegung des Vertragsnamens. Der folgende Vorgangsvertrag entspricht z. B. dem ersten Beispiel in diesem Thema.  
  
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
  
## <a name="describing-empty-messages"></a>Beschreiben von leeren Nachrichten  
 Eine leere Anforderungsnachricht kann dadurch beschrieben werden, dass sie keine Eingabe- oder Verweisparameter aufweist. Zum Beispiel in C-Code:  
  
 `[OperationContract]`  
  
 `public int GetCurrentTemperature();`  
  
 For example, in Visual Basic:  
  
 `<OperationContract()>`  
  
 `Function GetCurrentTemperature() as Integer`  
  
 Eine leere Antwortnachricht kann dadurch beschrieben werden, dass sie einen `void`-Rückgabetyp und keine Ausgabe- oder Verweisparameter aufweist. Beispiel:  
  
```csharp  
[OperationContract]  
public void SetTemperature(int temperature);  
```  
  
```vb  
<OperationContract()>  
Sub SetTemperature(temperature As Integer)  
```  
  
 Dies unterscheidet sich von einem unidirektionalen Vorgang wie z. B.:  
  
```csharp  
[OperationContract(IsOneWay=true)]  
public void SetLightbulbStatus(bool isOn);  
```  
  
```vb  
<OperationContract(IsOneWay:=True)>  
Sub SetLightbulbStatus(isOne As Boolean)  
```  
  
 Der `SetTemperatureStatus`-Vorgang gibt eine leere Nachricht zurück. Er gibt stattdessen möglicherweise einen Fehler zurück, wenn es ein Problem beim Verarbeiten der Eingabenachricht gibt. Der `SetLightbulbStatus`-Vorgang gibt keinen Wert zurück. Es gibt keine Möglichkeit, eine Fehlerbedingung dieses Vorgangs zu übermitteln.  
  
## <a name="describing-messages-by-using-message-contracts"></a>Beschreiben von Nachrichten mithilfe von Nachrichtenverträgen  
 Sie können einen einzelnen Typ verwenden, um die ganze Nachricht darzustellen. Es ist zwar möglich, für diesen Zweck einen Datenvertrag zu verwenden, empfohlen wird jedoch die Verwendung eines Nachrichtenvertrags – dadurch werden unnötige Wrappingebenen im resultierenden XML-Code vermieden. Darüber hinaus ermöglichen Nachrichtenverträge eine bessere Kontrolle über die resultierenden Nachrichten. Sie können z. B. entscheiden, welche Informationen im Nachrichtentext und welche in den Nachrichtenheadern enthalten sein sollen. Im folgenden Beispiel wird die Verwendung von Nachrichtenverträgen veranschaulicht.  
  
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
  
 Weitere Informationen finden Sie unter [Verwenden von Nachrichtenverträgen](../../../../docs/framework/wcf/feature-details/using-message-contracts.md).  
  
 Im vorigen Beispiel wird die <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse noch standardmäßig verwendet. Die <xref:System.Xml.Serialization.XmlSerializer>-Klasse kann auch in Verbindung mit Nachrichtenverträgen verwendet werden. Zu diesem Zweck wenden Sie das <xref:System.ServiceModel.XmlSerializerFormatAttribute>-Attribut entweder auf den Vorgang oder auf den Vertrag an, und verwenden Sie Typen, die mit der <xref:System.Xml.Serialization.XmlSerializer>-Klasse in den Nachrichtenheadern und Textmembern kompatibel sind.  
  
## <a name="describing-messages-by-using-streams"></a>Beschreiben von Nachrichten mithilfe von Streams  
 Eine andere Möglichkeit zur Beschreibung von Nachrichten in Vorgängen ist die Verwendung der <xref:System.IO.Stream>-Klasse oder einer der von ihr abgeleiteten Klasse in einem Vorgangsvertrag oder als Textmember eines Nachrichtenvertrags (es muss sich in diesem Fall um den einzigen Member handeln). Für eingehende Nachrichten muss der Typ `Stream` sein – es können keine abgeleiteten Klassen verwendet werden.  
  
 Anstatt den Serialisierungsaufruf aufzurufen, ruft WCF Daten aus einem Stream ab und legt sie direkt in eine ausgehende Nachricht ab, oder ruft Daten aus einer eingehenden Nachricht ab und legt sie direkt in einen Stream ab. Im folgenden Beispiel wird die Verwendung von Streams veranschaulicht.  
  
```csharp  
[OperationContract]  
public Stream DownloadFile(string fileName);  
```  
  
```vb  
<OperationContract()>  
Function DownloadFile(fileName As String) As String  
```  
  
 Sie können `Stream`- und Nicht-Stream-Daten in einem einzelnen Nachrichtentext nicht kombinieren. Verwenden Sie einen Nachrichtenvertrag, um die zusätzlichen Daten in Nachrichtenheader einzusetzen. Im folgenden Beispiel wird die falsche Verwendung von Streams bei der Definition des Vorgangsvertrags veranschaulicht.  
  
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
  
 Im folgenden Beispiel wird die korrekte Verwendung von Streams bei der Definition eines Vorgangsvertrags veranschaulicht.  
  
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
  
 Weitere Informationen finden Sie unter [Große Daten und Streaming](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md).  
  
## <a name="using-the-message-class"></a>Verwenden der Message-Klasse  
 Um umfassende programmgesteuerte Kontrolle über gesendete oder empfangene Nachrichten zu haben, können Sie die <xref:System.ServiceModel.Channels.Message>-Klasse direkt verwenden, wie im folgenden Beispielcode dargestellt wird.  
  
```csharp  
[OperationContract]  
public void LogMessage(Message m);  
```  
  
```vb  
<OperationContract()>  
Sub LogMessage(m As Message)  
```  
  
 Dies ist ein erweitertes Szenario, das unter [Verwenden der Nachrichtenklasse](../../../../docs/framework/wcf/feature-details/using-the-message-class.md)ausführlich beschrieben wird.  
  
## <a name="describing-fault-messages"></a>Beschreiben von Fehlernachrichten  
 Zusätzlich zu den Nachrichten, die durch den Rückgabewert und Ausgabe- oder Verweisparameter beschrieben werden, kann jeder nicht unidirektionale Vorgang mindestes zwei mögliche Nachrichten zurückgeben: die normale Antwortnachricht und eine Fehlernachricht. Betrachten Sie den folgenden Vorgangsvertrag.  
  
```csharp  
[OperationContract]  
float GetAirfare(string fromCity, string toCity, DateTime date);  
```  
  
```vb  
<OperationContract()>  
Function GetAirfare(fromCity As String, toCity As String, date as DateTime)  
```  
  
 Dieser Vorgang kann entweder eine normale Nachricht zurückgeben, die eine `float`-Zahl enthält, oder eine Fehlernachricht, die einen Fehlercode und eine Beschreibung enthält. Dies kann durch Auslösen einer <xref:System.ServiceModel.FaultException> in der Dienstimplementierung erreicht werden.  
  
 Sie können weitere mögliche Fehlermeldungen angeben, indem Sie das <xref:System.ServiceModel.FaultContractAttribute>-Attribut verwenden. Die zusätzlichen Fehler müssen mit dem <xref:System.Runtime.Serialization.DataContractSerializer> serialisierbar sein, wie im folgenden Beispielcode gezeigt.  
  
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
  
 Diese zusätzlichen Fehler können durch Auslösen einer <xref:System.ServiceModel.FaultException%601> des geeigneten Datenvertragstyps generiert werden. Weitere Informationen finden Sie [unter Behandeln von Ausnahmen und Fehlern](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).  
  
 Sie können die <xref:System.Xml.Serialization.XmlSerializer>-Klasse nicht verwenden, um Fehler zu beschreiben. Das <xref:System.ServiceModel.XmlSerializerFormatAttribute> hat keine Auswirkungen auf Fehlerverträge.  
  
## <a name="using-derived-types"></a>Verwenden von abgeleiteten Typen  
 Sie können einen Basistyp für einen Vorgangs- oder Nachrichtenvertrag verwenden und dann einen abgeleiteten Typ verwenden, wenn Sie den Vorgang tatsächlich aufrufen. In diesem Fall müssen Sie entweder das <xref:System.ServiceModel.ServiceKnownTypeAttribute>-Attribut oder einen alternativen Mechanismus verwenden, um die Verwendung von abgeleiteten Typen zu ermöglichen. Betrachten Sie den folgenden Vorgang.  
  
```csharp  
[OperationContract]  
public bool IsLibraryItemAvailable(LibraryItem item);  
```  
  
```vb
<OperationContract()>  
    Function IsLibraryItemAvailable(item As LibraryItem) As Boolean  
```  
  
 Angenommen, zwei Typen, `Book` und `Magazine`, werden aus `LibraryItem` abgeleitet. Um diese Typen im `IsLibraryItemAvailable`-Vorgang zu verwenden, können Sie den Vorgang wie folgt ändern:  
  
 `[OperationContract]`  
  
 `[ServiceKnownType(typeof(Book))]`  
  
 `[ServiceKnownType(typeof(Magazine))]`  
  
 `public bool IsLibraryItemAvailable(LibraryItem item);`  
  
 Alternativ dazu können Sie, wie im folgenden Beispielcode dargestellt, das <xref:System.Runtime.Serialization.KnownTypeAttribute>-Attribut verwenden, wenn das Standard-<xref:System.Runtime.Serialization.DataContractSerializer> verwendet wird.  
  
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
  
 Sie können das <xref:System.Xml.Serialization.XmlIncludeAttribute>-Attribut verwenden, wenn Sie <xref:System.Xml.Serialization.XmlSerializer> verwenden.  
  
 Sie können das <xref:System.ServiceModel.ServiceKnownTypeAttribute>-Attribut auf einen Vorgang oder auf den gesamten Dienst anwenden. Es akzeptiert entweder einen Typ oder den Namen der Methode, die aufgerufen werden soll, um eine Liste bekannter Typen zu erzeugen, genau wie das <xref:System.Runtime.Serialization.KnownTypeAttribute>-Attribut. Weitere Informationen finden Sie unter [Bekannte Datenvertragstypen](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
## <a name="specifying-the-use-and-style"></a>Angeben der Verwendung und des Stils  
 Bei der Beschreibung von Diensten mithilfe von Web Services Description Language (WSDL) sind die beiden am häufigsten verwendeten Stile der Dokumentstil und der Remoteprozeduraufruf (RPC, remote procedure call). Beim Dokumentstil wird der gesamte Nachrichtentext mithilfe des Schemas beschrieben, und WSDL beschreibt die verschiedenen Nachrichtentextteile durch Verweisen auf Elemente innerhalb dieses Schemas. Beim RPC-Stil verweist WSDL auf einen Schematyp für jeden Nachrichtenteil statt auf ein Element. In einigen Fällen müssen Sie einen dieser Stile manuell auswählen. Zu diesem Zweck können Sie das <xref:System.ServiceModel.DataContractFormatAttribute>-Attribut anwenden und die `Style`-Eigenschaft festlegen (wenn das <xref:System.Runtime.Serialization.DataContractSerializer> verwendet wird), oder Sie legen `Style` in dem <xref:System.ServiceModel.XmlSerializerFormatAttribute>-Attribut fest (wenn das <xref:System.Xml.Serialization.XmlSerializer> verwendet wird).  
  
 Außerdem unterstützt der <xref:System.Xml.Serialization.XmlSerializer> zwei Formen von serialisiertem XML: `Literal` und `Encoded`. `Literal` ist die am häufigsten akzeptierte Form und die einzige Form, die vom <xref:System.Runtime.Serialization.DataContractSerializer> unterstützt wird. `Encoded` ist eine Legacyform, die in Abschnitt 5 der SOAP-Spezifikation beschrieben wird. Sie wird für neue Dienste nicht empfohlen. Um zum `Encoded`-Modus zu wechseln, legen Sie die `Use`-Eigenschaft für das <xref:System.ServiceModel.XmlSerializerFormatAttribute>-Attribut auf `Encoded` fest.  
  
 In den meisten Fällen sollten Sie die Standardeinstellungen für die `Style`- und die `Use`-Eigenschaft nicht ändern.  
  
## <a name="controlling-the-serialization-process"></a>Kontrollieren des Serialisierungsprozesses  
 Es gibt eine Reihe von Möglichkeiten, die Art und Weise anzupassen, in der Daten serialisiert werden.  
  
### <a name="changing-server-serialization-settings"></a>Ändern der Serverserialisierungseinstellungen  
 Wenn das Standard-<xref:System.Runtime.Serialization.DataContractSerializer> verwendet wird, können Sie einige Aspekte des Serialisierungsprozesses für den Dienst durch Anwenden des <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attributs auf den Dienst steuern. Sie können insbesondere die `MaxItemsInObjectGraph`-Eigenschaft verwenden, um das Kontingent festzulegen, das die maximale Anzahl an Objekten einschränkt, die das <xref:System.Runtime.Serialization.DataContractSerializer> deserialisiert. Sie können die `IgnoreExtensionDataObject`-Eigenschaft verwenden, um die Roundtrip-Versionsverwaltungsfunktion zu deaktivieren. Weitere Informationen über Kontingenten finden Sie unter [Security Considerations for Data (Sicherheitsüberlegungen zu Daten)](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md). Weitere Informationen zum Round-Tripping finden Sie unter [Forward-Compatible Data Contracts](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).  
  
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
  
### <a name="serialization-behaviors"></a>Serialisierungsverhalten  
 In WCF stehen zwei Verhaltensweisen <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> zur <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> Verfügung, die und die automatisch eingesteckt werden, je nachdem, welcher Serialisierungsvorgang für einen bestimmten Vorgang verwendet wird. Da diese Arten von Verhalten automatisch angewendet werden, müssen Sie sie normalerweise nicht beachten.  
  
 `DataContractSerializerOperationBehavior` weist jedoch die `MaxItemsInObjectGraph`-, die `IgnoreExtensionDataObject`- und die `DataContractSurrogate`-Eigenschaften auf, die Sie zur Anpassung des Serialisierungsprozesses verwenden können. Die ersten beiden Eigenschaften haben die gleiche Bedeutung, wie im vorherigen Abschnitt erläutert. Sie können die `DataContractSurrogate`-Eigenschaft verwenden, um Datenvertrag-Ersatzzeichen zu aktivieren, die ein leistungsfähiges Werkzeug zum Anpassen und Erweitern des Serialisierungsprozesses darstellen. Weitere Informationen finden Sie unter [Datenvertrags-Surrogate .](../../../../docs/framework/wcf/extending/data-contract-surrogates.md)  
  
 Sie können das `DataContractSerializerOperationBehavior` verwenden, um sowohl die Client- als auch die Serverserialisierung anzupassen. Im folgenden Beispiel wird das Erhöhen des `MaxItemsInObjectGraph`-Kontingents für den Client veranschaulicht.  
  
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
  
Im folgenden Fall ist der entsprechende Code für den Dienst im selbst gehosteten Fall:
  
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
  
 Falls er im Internet gehostet wird, müssen Sie eine neue abgeleitete `ServiceHost`-Klasse erstellen und die Diensthostfactory verwenden, um sie zu laden.  
  
### <a name="controlling-serialization-settings-in-configuration"></a>Steuern von Serialisierungseinstellungen in der Konfiguration  
 `MaxItemsInObjectGraph` und `IgnoreExtensionDataObject` können über die Konfiguration mithilfe des `dataContractSerializer`-Endpunkts oder -Dienstverhaltens gesteuert werden, wie im folgenden Beispiel dargestellt wird.  
  
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
  
### <a name="shared-type-serialization-object-graph-preservation-and-custom-serializers"></a>Serialisierung von gemeinsamen Typen, Objektdiagrammbeibehaltung und benutzerdefinierte Serialisierungsprogramme  
 Das <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert mithilfe von Datenvertragsnamen und nicht mithilfe von .NET-Typnamen. Dies entspricht dienstorientierten Architekturgrundsätzen und ermöglicht einen hohen Grad an Flexibilität – die .NET-Typen können sich ändern, ohne sich auf den Übertragungsvertrag auszuwirken. In seltenen Fällen kann es notwendig sein, tatsächliche .NET-Typnamen zu serialisieren und dabei eine enge Verknüpfung zwischen dem Client und dem Server vorzunehmen, ähnlich wie bei der .NET-Framework-Remotetechnologie. Dies ist keine empfohlene Vorgehensweise, außer in seltenen Fällen, die normalerweise bei der Migration von .NET Framework-Remoting zu WCF auftreten. In diesem Fall müssen Sie die <xref:System.Runtime.Serialization.NetDataContractSerializer>-Klasse statt der <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse verwenden.  
  
 Das <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert normalerweise Objektdiagramme als Objektstrukturen, d. h. auf dasselbe Objekt wird mehr als einmal verwiesen, es wird mehr als einmal serialisiert. Betrachten Sie z. B. eine `PurchaseOrder`-Instanz, die über zwei Felder vom Typ Adresse mit den Namen `billTo` und `shipTo` verfügt. Wenn beide Felder auf dieselbe Adressinstanz festgelegt werden, gibt es zwei identische Adressinstanzen nach der Serialisierung und der Deserialisierung. Dies erfolgt, weil es kein interoperables Standardverfahren zur Darstellung von Objektdiagrammen in XML gibt (außer dem älteren SOAP-Codierungsstandard, der für <xref:System.Xml.Serialization.XmlSerializer> verfügbar ist, wie im vorigen Abschnitt über `Style` und `Use` beschrieben). Objektdiagramme als Strukturen zu serialisieren, bringt gewisse Nachteile mit sich, z. B. können Diagramme mit Zirkelverweisen nicht serialisiert werden. Gelegentlich ist es erforderlich, auf echte Objektdiagrammserialisierung umzustellen, obwohl sie nicht interoperabel ist. Dies kann durch Verwendung vom <xref:System.Runtime.Serialization.DataContractSerializer> erfolgen, das mit dem `preserveObjectReferences`-Parameter konstruiert ist, der auf `true` festgelegt ist.  
  
 Gelegentlich reichen die integrierten Serialisierungsprogramme nicht für das Szenario aus. In den meisten Fällen können Sie trotzdem die <xref:System.Runtime.Serialization.XmlObjectSerializer>-Abstraktion verwenden, von der sowohl das <xref:System.Runtime.Serialization.DataContractSerializer> als auch das <xref:System.Runtime.Serialization.NetDataContractSerializer> abgeleitet werden.  
  
 Die drei vorherigen Fälle (.NET-Typbeibehaltung, Objektdiagrammbeibehaltung und die vollkommen benutzerdefinierte `XmlObjectSerializer`-basierte Serialisierung) erfordern alle die Einbindung eines benutzerdefinierten Serialisierungsprogramms. Gehen Sie hierzu folgendermaßen vor:  
  
1. Schreiben Sie ein eigenes Verhalten, das sich vom <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> herleitet.  
  
2. Überschreiben Sie die beiden `CreateSerializer`-Methoden, um Ihr eigenes Serialisierungsprogramm zurückzugeben (entweder das <xref:System.Runtime.Serialization.NetDataContractSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer> mit `preserveObjectReferences` festgelegt auf `true` oder Ihr eigenes benutzerdefiniertes <xref:System.Runtime.Serialization.XmlObjectSerializer>).  
  
3. Vor dem Öffnen des Diensthosts oder dem Erstellen eines Clientkanals entfernen Sie das vorhandene <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>-Verhalten und binden die benutzerdefinierte abgeleitete Klasse ein, die Sie in den vorherigen Schritten erstellt haben.  
  
 Weitere Informationen zu erweiterten Serialisierungskonzepten finden Sie unter [Serialisierung und Deserialisierung](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden der XmlSerializer-Klasse](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md)
- [Vorgehensweise: Aktivieren des Streamingmodus](../../../../docs/framework/wcf/feature-details/how-to-enable-streaming.md)
- [Vorgehensweise: Erstellen eines grundlegenden Datenvertrags für eine Klasse oder Struktur](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-data-contract-for-a-class-or-structure.md)
