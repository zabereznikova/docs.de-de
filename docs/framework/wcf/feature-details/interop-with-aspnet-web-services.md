---
title: Interoperabilität mit ASP.NET-Webdiensten
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: 8a0737a36989dd8bc6f5d5670555c7b2218798bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33494295"
---
# <a name="interoperability-with-aspnet-web-services"></a>Interoperabilität mit ASP.NET-Webdiensten
Interoperabilität zwischen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Webdienste und Windows Communication Foundation (WCF)-Webdienste erreichen, indem sichergestellt wird, dass mithilfe beider Technologien implementierte Dienste, die mit WS entsprechen-I Basic Profile 1.1-Spezifikation. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Webdienste, die mit WS-I Basic Profile 1.1 werden mithilfe der vom System bereitgestellte Bindung WCF mit WCF-Clients interoperabel <xref:System.ServiceModel.BasicHttpBinding>.  
  
 Verwenden Sie wie im folgenden Beispielcode gezeigt die in [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] gebotene Möglichkeit, das <xref:System.Web.Services.WebService>-Attribut und das <xref:System.Web.Services.WebMethodAttribute>-Attribut zu einer Schnittstelle anstatt zu einer Klasse hinzuzufügen und zum Implementieren der Schnittstelle eine Klasse zu schreiben.  
  
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
  
 Die XML, in die <xref:System.Xml.Serialization.XmlSerializer> standardmäßig einen Typ serialisiert, ist semantisch identisch mit der XML, in die <xref:System.Runtime.Serialization.DataContractSerializer> einen Typ serialisiert, vorausgesetzt, der Namespace ist für die XML explizit definiert. Wenn Sie einen Datentyp für die Verwendung mit definieren [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Webdienste in antizipation einer WCF, gehen Sie folgendermaßen vor:  
  
-   Definieren Sie den Typ mit .NET Framework-Klassen und nicht mit dem XML-Schema.  
  
-   Fügen Sie der Klasse lediglich <xref:System.SerializableAttribute> und <xref:System.Xml.Serialization.XmlRootAttribute> hinzu, wobei Sie mit dem zweiten Attribut den Namespace für den Typ explizit definieren. Fügen Sie keine zusätzlichen Attribute aus dem <xref:System.Xml.Serialization>-Namespace hinzu, um die Übersetzung der .NET Framework-Klasse in XML zu steuern.  
  
-   Wenn Sie diese Vorgehensweise wählen, sollte es später kein Problem darstellen, die .NET-Klassen in Datenverträge umzuwandeln, indem Sie <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> hinzufügen, ohne die XML erheblich zu ändern, in die die Klassen für die Übertragung serialisiert werden. Die Nachrichten vom verwendeten Typen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Webdienste können von WCF-Clientanwendungen, was u. a. andere Vorteile, eine bessere Leistung in WCF-Anwendungen als Datenverträge verarbeitet werden.  
  
 Vermeiden Sie die Verwendung der von den Internetinformationsdiensten (IIS) bereitgestellten Authentifizierungsoptionen. WCF-Clients werden nicht unterstützt. Wenn ein Dienst geschützt werden muss, verwenden Sie die Optionen, die von WCF bereitgestellt werden, da diese Optionen robuster sind und auf Standardprotokollen basieren.  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a>Durch das Laden von ServiceModel HttpModule verursachte Leistungsbeeinträchtigungen  
 In .NET Framework&#160;3.0 wurde das WCF-`HttpModule`-Element in der Stammdatei Web.config installiert, sodass jede ASP.NET-Anwendung WCF unterstützte. Dies kann die Leistung beeinträchtigen. Sie können daher `ServiceModel` für die Datei Web.config entfernen, wie im folgenden Bespiel gezeigt.  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
<httpModules/>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Konfigurieren eines WCF-Diensts für die Zusammenarbeit mit ASP.NET-Webdienstclients](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
