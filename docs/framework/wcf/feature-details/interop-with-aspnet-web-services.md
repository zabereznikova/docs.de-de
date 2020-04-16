---
title: Interoperabilität mit ASP.NET-Webdiensten
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: 41810d8044e4b7ff3193950a914edbf1e61cffb1
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464093"
---
# <a name="interoperability-with-aspnet-web-services"></a>Interoperabilität mit ASP.NET-Webdiensten
Die Interoperabilität zwischen ASP.NET Webdiensten und WCF-Webdiensten (Windows Communication Foundation) kann erreicht werden, indem sichergestellt wird, dass Dienste, die mit beiden Technologien implementiert werden, der WS-I Basic Profile 1.1-Spezifikation entsprechen. ASP.NET Webdienste, die WS-I Basic Profile 1.1 entsprechen, mit WCF-Clients mithilfe <xref:System.ServiceModel.BasicHttpBinding>der vom WCF bereitgestellten Bindung interoperabel sind.  
  
 Verwenden Sie ASP.NET 2.0-Option, um die <xref:System.Web.Services.WebService> und-Attribute <xref:System.Web.Services.WebMethodAttribute> zu einer Schnittstelle anstatt zu einer Klasse hinzuzufügen und eine Klasse zum Implementieren der Schnittstelle zu schreiben, wie im folgenden Beispielcode gezeigt.  
  
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
  
 Verwenden Sie das <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute>-Attribut nicht, um Nachrichten basierend auf dem voll qualifizierten Namen des Textelements der SOAP-Nachricht anstatt des `SOAPAction`-HTTP-Headers an Methoden weiterzuleiten. WCF verwendet `SOAPAction` den HTTP-Header zum Weiterleiten von Nachrichten.  
  
 Die XML, in die <xref:System.Xml.Serialization.XmlSerializer> standardmäßig einen Typ serialisiert, ist semantisch identisch mit der XML, in die <xref:System.Runtime.Serialization.DataContractSerializer> einen Typ serialisiert, vorausgesetzt, der Namespace ist für die XML explizit definiert. Gehen Sie beim Definieren eines Datentyps für die Verwendung mit ASP.NETWeb-Diensten im Vorgriff auf die Einführung von WCF wie folgt vor:  
  
- Definieren Sie den Typ mit .NET Framework-Klassen und nicht mit dem XML-Schema.  
  
- Fügen Sie der Klasse lediglich <xref:System.SerializableAttribute> und <xref:System.Xml.Serialization.XmlRootAttribute> hinzu, wobei Sie mit dem zweiten Attribut den Namespace für den Typ explizit definieren. Fügen Sie keine zusätzlichen Attribute aus dem <xref:System.Xml.Serialization>-Namespace hinzu, um die Übersetzung der .NET Framework-Klasse in XML zu steuern.  
  
- Wenn Sie diese Vorgehensweise wählen, sollte es später kein Problem darstellen, die .NET-Klassen in Datenverträge umzuwandeln, indem Sie <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> hinzufügen, ohne die XML erheblich zu ändern, in die die Klassen für die Übertragung serialisiert werden. Die typen, die in Nachrichten von ASP.NET Webdiensten verwendet werden, können von WCF-Anwendungen als Datenverträge verarbeitet werden, was unter anderem zu einer besseren Leistung in WCF-Anwendungen führt.  
  
 Vermeiden Sie die Verwendung der von den Internetinformationsdiensten (IIS) bereitgestellten Authentifizierungsoptionen. WCF-Clients unterstützen sie nicht. Wenn ein Dienst gesichert werden muss, verwenden Sie die von WCF bereitgestellten Optionen, da diese Optionen robust sind und auf Standardprotokollen basieren.  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a>Durch das Laden von ServiceModel HttpModule verursachte Leistungsbeeinträchtigungen  
 In .NET Framework&#160;3.0 wurde das WCF-`HttpModule`-Element in der Stammdatei Web.config installiert, sodass jede ASP.NET-Anwendung WCF unterstützte. Dies kann die Leistung beeinträchtigen. Sie können daher `ServiceModel` für die Datei Web.config entfernen, wie im folgenden Bespiel gezeigt.  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
</httpModules>
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Konfigurieren eines WCF-Diensts für die Zusammenarbeit mit ASP.NET-Webdienstclients](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
