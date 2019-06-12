---
title: Interoperabilität mit ASP.NET-Webdiensten
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: f2f1a8fd2bf34ff61784f2dcb88c0669585da573
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "67026017"
---
# <a name="interoperability-with-aspnet-web-services"></a>Interoperabilität mit ASP.NET-Webdiensten
Interoperabilität zwischen ASP.NET Web Services und Windows Communication Foundation (WCF)-Webdiensten erzielt werden, indem Sie sicherstellen, dass implementierte Dienste, beide Technologien entspricht-I Basic Profile 1.1-Spezifikation. ASP.NET Web Services, die mit WS-I Basic Profile 1.1 sind mit WCF-Clients interoperabel, mithilfe von WCF vom System bereitgestellte Bindung, <xref:System.ServiceModel.BasicHttpBinding>.  
  
 Verwenden Sie ASP.NET 2.0-Option hinzufügen, die <xref:System.Web.Services.WebService> und <xref:System.Web.Services.WebMethodAttribute> Attribute zu einer Schnittstelle anstatt zu einer Klasse, und schreiben eine Klasse zum Implementieren der Schnittstelle, wie im folgenden Beispielcode gezeigt.  
  
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
  
 Die Verwendung dieser Option wird empfohlen, da die Schnittstelle mit dem <xref:System.Web.Services.WebService>-Attribut einen Vertrag für die vom Dienst ausgeführten Vorgänge darstellt. Dieser Vertrag kann wiederholt für verschiedene Klassen verwendet werden, die den gleichen Vertrag möglicherweise auf unterschiedliche Art und Weise implementieren.  
  
 Verwenden Sie das <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute>-Attribut nicht, um Nachrichten basierend auf dem voll qualifizierten Namen des Textelements der SOAP-Nachricht anstatt des `SOAPAction`-HTTP-Headers an Methoden weiterzuleiten. WCF verwendet die `SOAPAction` HTTP-Header zum Weiterleiten von Nachrichten.  
  
 Die XML, in die <xref:System.Xml.Serialization.XmlSerializer> standardmäßig einen Typ serialisiert, ist semantisch identisch mit der XML, in die <xref:System.Runtime.Serialization.DataContractSerializer> einen Typ serialisiert, vorausgesetzt, der Namespace ist für die XML explizit definiert. Wenn Sie einen Datentyp für die Verwendung mit ASP.NETWeb Dienste in der Erwartung einführen WCF definieren, führen Sie folgende Schritte aus:  
  
- Definieren Sie den Typ mit .NET Framework-Klassen und nicht mit dem XML-Schema.  
  
- Fügen Sie der Klasse lediglich <xref:System.SerializableAttribute> und <xref:System.Xml.Serialization.XmlRootAttribute> hinzu, wobei Sie mit dem zweiten Attribut den Namespace für den Typ explizit definieren. Fügen Sie keine zusätzlichen Attribute aus dem <xref:System.Xml.Serialization>-Namespace hinzu, um die Übersetzung der .NET Framework-Klasse in XML zu steuern.  
  
- Wenn Sie diese Vorgehensweise wählen, sollte es später kein Problem darstellen, die .NET-Klassen in Datenverträge umzuwandeln, indem Sie <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> hinzufügen, ohne die XML erheblich zu ändern, in die die Klassen für die Übertragung serialisiert werden. Die von ASP.NET-Webdiensten verwendeten Typen können als Datenverträge von WCF-Anwendungen verarbeitet werden zurückgegeben, neben anderen Vorteilen eine bessere Leistung für WCF-Anwendungen.  
  
 Vermeiden Sie die Verwendung der von den Internetinformationsdiensten (IIS) bereitgestellten Authentifizierungsoptionen. WCF-Clients unterstützen sie nicht. Wenn ein Dienst geschützt werden muss, verwenden Sie die Optionen, WCF, bereitgestellt werden, da diese Optionen robuster sind und auf Standardprotokollen basieren.  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a>Durch das Laden von ServiceModel HttpModule verursachte Leistungsbeeinträchtigungen  
 In .NET Framework&#160;3.0 wurde das WCF-`HttpModule`-Element in der Stammdatei Web.config installiert, sodass jede ASP.NET-Anwendung WCF unterstützte. Dies kann die Leistung beeinträchtigen. Sie können daher `ServiceModel` für die Datei Web.config entfernen, wie im folgenden Bespiel gezeigt.  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
<httpModules/>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Konfigurieren von WCF-Dienst für die Zusammenarbeit mit ASP.NET-Webdienstclients](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
