---
title: Beispiel zur schwach typisierten JSON-Serialisierung
ms.date: 03/30/2017
ms.assetid: 0b30e501-4ef5-474d-9fad-a9d559cf9c52
ms.openlocfilehash: 212a5ea362600e833303711b750d1c7a0f7252b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676054"
---
# <a name="weakly-typed-json-serialization-sample"></a>Beispiel zur schwach typisierten JSON-Serialisierung
Beim Serialisieren eines benutzerdefinierten Typs in ein bestimmtes Übertragungsformat oder beim Deserialisieren eines Übertragungsformats zurück in einen benutzerdefinierten Typ muss der jeweilige benutzerdefinierte Typ für den Dienst und den Client verfügbar sein. Hierzu wird normalerweise das <xref:System.Runtime.Serialization.DataContractAttribute> -Attribut auf diese benutzerdefinierten Typen angewendet, und das <xref:System.Runtime.Serialization.DataMemberAttribute> -Attribut wird auf ihre Member angewendet. Dieser Mechanismus gilt auch beim Arbeiten mit JavaScript Object Notation (JSON)-Objekten, wie beschrieben im Thema [Vorgehensweise: Serialisieren und Deserialisieren von JSON-Daten](../../../../docs/framework/wcf/feature-details/how-to-serialize-and-deserialize-json-data.md).  
  
 In einigen Szenarien muss einen Windows Communication Foundation (WCF)-Dienst oder Client Zugriff auf JSON-Objekte, die von einem Dienst oder Client, der außerhalb der Kontrolle des Entwicklers ist generiert. Da immer mehr Webdienste JSON-APIs öffentlich verfügbar machen, kann es unpraktisch, für den WCF-Entwickler zum Erstellen von lokaler, benutzerdefinierten Typen in dem beliebige JSON-Objekte deserialisiert werden. Dieses Beispiel bietet einen Mechanismus, der WCF-Entwickler mit deserialisierten, beliebigen JSON-Objekten arbeiten, ohne benutzerdefinierte Typen erstellen kann. Dies wird als *schwach typisierte Deserialisierung* von JSON-Objekten bezeichnet, da der Typ, in den ein JSON-Objekt deserialisiert wird, zum Zeitpunkt der Kompilierung nicht bekannt ist.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Beispielsweise gibt eine öffentliche Webdienst-API das folgende JSON-Objekt zurück, das Informationen zu einem Benutzer des Diensts enthält.  
  
```json  
{"personal": {"name": "Paul", "age": 23, "height": 1.7, "isSingle": true, "luckyNumbers": [5,17,21]}, "favoriteBands": ["Band ABC", "Band XYZ"]}  
```  
  
 Um dieses Objekt zu deserialisieren, muss ein WCF-Client die folgenden benutzerdefinierten Typen implementieren.  
  
```  
[DataContract]  
 public class MemberProfile  
 {  
     [DataMember]  
     public PersonalInfo personal;  
  
     [DataMember]  
     public string[] favoriteBands;  
 }  
  
 [DataContract]  
 public class PersonalInfo  
 {  
     [DataMember]  
     public string name;  
  
     [DataMember]  
     public int age;  
  
     [DataMember]  
     public double height;  
  
     [DataMember]  
     public bool isSingle;  
  
     [DataMember]  
     public int[] luckyNumbers;  
 }  
```  
  
 Dies kann aufwändig sein, insbesondere, wenn der Client mehrere Typen von JSON-Objekten behandeln muss.  
  
 Der in diesem Beispiel bereitgestellte `JsonObject` -Typ führt eine schwach typisierte Darstellung des deserialisierten JSON-Objekts ein. `JsonObject` verwendet die natürliche Zuordnung zwischen JSON-Objekten und [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Wörterbüchern und die Zuordnung zwischen JSON-Arrays und [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Arrays. Der folgende Code veranschaulicht den `JsonObject` -Typ:  
  
```  
// Instantiation of JsonObject json omitted  
  
string name = json["root"]["personal"]["name"];  
int age = json["root"]["personal"]["age"];  
double height = json["root"]["personal"]["height"];  
bool isSingle = json["root"]["personal"]["isSingle"];  
int[] luckyNumbers = {  
                                     json["root"]["personal"]["luckyNumbers"][0],  
                                     json["root"]["personal"]["luckyNumbers"][1],  
                                     json["root"]["personal"]["luckyNumbers"][2]   
                                 };  
string[] favoriteBands = {  
                                        json["root"]["favoriteBands"][0],  
                                        json["root"]["favoriteBands"][1]  
                                    };  
```  
  
 Sie können JSON-Objekte und -Arrays "durchsuchen", ohne ihren Typ zum Zeitpunkt der Kompilierung deklarieren zu müssen. Eine Erläuterung der Anforderungen für das `["root"]` -Objekt der obersten Ebene finden Sie im Thema [Mapping Between JSON and XML](../../../../docs/framework/wcf/feature-details/mapping-between-json-and-xml.md)beschrieben.  
  
> [!NOTE]
>  Die `JsonObject` -Klasse wird nur als Beispiel bereitgestellt. Sie wurde nicht gründlich getestet und sollte nicht in Produktionsumgebungen verwendet werden. Eine offensichtliche Implikation der schwach typisierten JSON-Serialisierung ist der Mangel an Typsicherheit beim Arbeiten mit `JsonObject`.  
  
 Damit der `JsonObject` -Typ verwendet werden kann, muss der Clientvorgangsvertrag <xref:System.ServiceModel.Channels.Message> als Rückgabetyp verwenden.  
  
```  
[ServiceContract]  
    interface IClientSideProfileService  
    {  
        // There is no need to write a DataContract for the complex type returned by the service.  
        // The client will use a JsonObject to browse the JSON in the received message.  
  
        [OperationContract]  
        [WebGet(ResponseFormat = WebMessageFormat.Json)]  
        Message GetMemberProfile();  
    }  
```  
  
 `JsonObject` wird dann instanziiert, wie im folgenden Code dargestellt.  
  
```  
// Code to instantiate IClientSideProfileService channel omitted…  
  
// Make a request to the service and obtain the Json response  
XmlDictionaryReader reader = channel.GetMemberProfile().GetReaderAtBodyContents();  
  
// Go through the Json as though it is a dictionary. There is no need to map it to a .NET CLR type.  
JsonObject json = new JsonObject(reader);  
```  
  
 Der `JsonObject` -Konstruktor nimmt einen <xref:System.Xml.XmlDictionaryReader>an, der durch die <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> -Methode abgerufen wird. Der Reader enthält eine XML-Darstellung der vom Client empfangenen JSON-Nachricht. Weitere Informationen finden Sie im Thema [Mapping Between JSON and XML](../../../../docs/framework/wcf/feature-details/mapping-between-json-and-xml.md).  
  
 Das Programm erzeugt die folgende Ausgabe:  
  
```  
Service listening at http://localhost:8000/.  
To view the JSON output from the sample, navigate to http://localhost:8000/GetMemberProfile  
This is Paul's page. I am 23 years old and I am 1.7 meters tall.  
I am single.  
My lucky numbers are 5, 17, and 21.  
My favorite bands are Band ABC and Band XYZ.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Erstellen Sie die Projektmappe "WeaklyTypedJson.sln", wie in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)beschrieben.  
  
3.  Führen Sie die Projektmappe aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Ajax\WeaklyTypedJson`  
  
## <a name="see-also"></a>Siehe auch
