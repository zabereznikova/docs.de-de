---
title: Interoperabilität mit ASP.NET-Webdiensten
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: cca4e1b3da26d8026d41d0a7107432cdd2960545
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276632"
---
# <a name="interoperability-with-aspnet-web-services"></a>Interoperabilität mit ASP.NET-Webdiensten

Die Interoperabilität zwischen ASP.NET-Webdiensten und-Windows Communication Foundation (WCF)-Webdiensten kann erreicht werden, indem sichergestellt wird, dass die mithilfe beider Technologien implementierten Dienste der Spezifikation WS-I Basic Profile 1,1 entsprechen. ASP.NET-Webdienste, die WS-I Basic Profile 1,1 entsprechen, sind mithilfe der vom System bereitgestellten WCF-Bindung mit WCF-Clients interoperabel <xref:System.ServiceModel.BasicHttpBinding> .  
  
 Verwenden Sie die Option ASP.NET 2,0, <xref:System.Web.Services.WebService> um das-Attribut und das- <xref:System.Web.Services.WebMethodAttribute> Attribut zu einer Schnittstelle anstatt zu einer Klasse hinzuzufügen, und schreiben Sie eine Klasse, um die Schnittstelle zu implementieren, wie im folgenden Beispielcode gezeigt.  
  
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
  
 Die Verwendung dieser Option wird empfohlen, da die Schnittstelle mit dem <xref:System.Web.Services.WebService>-Attribut einen Vertrag für die vom Dienst ausgeführten Vorgänge darstellt. Dieser Vertrag kann wiederholt für verschiedene Klassen verwendet werden, die den gleichen Vertrag möglicherweise auf unterschiedliche Art und Weise implementieren.  
  
 Verwenden Sie das <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute>-Attribut nicht, um Nachrichten basierend auf dem voll qualifizierten Namen des Textelements der SOAP-Nachricht anstatt des `SOAPAction`-HTTP-Headers an Methoden weiterzuleiten. WCF verwendet den- `SOAPAction` http-Header zum Weiterleiten von Nachrichten.  
  
 Die XML, in die <xref:System.Xml.Serialization.XmlSerializer> standardmäßig einen Typ serialisiert, ist semantisch identisch mit der XML, in die <xref:System.Runtime.Serialization.DataContractSerializer> einen Typ serialisiert, vorausgesetzt, der Namespace ist für die XML explizit definiert. Gehen Sie wie folgt vor, wenn Sie einen Datentyp für die Verwendung mit ASP. NETWeb-Diensten in Erwartung der Einführung von WCF definieren:  
  
- Definieren Sie den Typ mit .NET Framework-Klassen und nicht mit dem XML-Schema.  
  
- Fügen Sie der Klasse lediglich <xref:System.SerializableAttribute> und <xref:System.Xml.Serialization.XmlRootAttribute> hinzu, wobei Sie mit dem zweiten Attribut den Namespace für den Typ explizit definieren. Fügen Sie keine zusätzlichen Attribute aus dem <xref:System.Xml.Serialization>-Namespace hinzu, um die Übersetzung der .NET Framework-Klasse in XML zu steuern.  
  
- Wenn Sie diese Vorgehensweise wählen, sollte es später kein Problem darstellen, die .NET-Klassen in Datenverträge umzuwandeln, indem Sie <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> hinzufügen, ohne die XML erheblich zu ändern, in die die Klassen für die Übertragung serialisiert werden. Die in Nachrichten von ASP.NET-Webdiensten verwendeten Typen können von WCF-Anwendungen als Datenverträge verarbeitet werden, was zu anderen Vorteilen eine bessere Leistung in WCF-Anwendungen bietet.  
  
 Vermeiden Sie die Verwendung der von den Internetinformationsdiensten (IIS) bereitgestellten Authentifizierungsoptionen. WCF-Clients unterstützen diese nicht. Wenn ein Dienst geschützt werden muss, verwenden Sie die von WCF bereitgestellten Optionen, da diese Optionen robust sind und auf Standardprotokollen basieren.  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a>Durch das Laden von ServiceModel HttpModule verursachte Leistungsbeeinträchtigungen  

 In .NET Framework&#160;3.0 wurde das WCF-`HttpModule`-Element in der Stammdatei Web.config installiert, sodass jede ASP.NET-Anwendung WCF unterstützte. Dies kann die Leistung beeinträchtigen. Sie können daher `ServiceModel` für die Datei Web.config entfernen, wie im folgenden Bespiel gezeigt.  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
</httpModules>
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Konfigurieren eines WCF-Diensts für die Zusammenarbeit mit ASP.NET-Webdienstclients](config-wcf-service-with-aspnet-web-service.md)
