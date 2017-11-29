---
title: "Interoperabilität mit ASP.NET-Webdiensten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 933d1bdac8f6e3a9e2bec5278fe398696131678a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="interoperability-with-aspnet-web-services"></a>Interoperabilität mit ASP.NET-Webdiensten
Eine Interoperabilität zwischen [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Webdiensten und den Webdiensten von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] kann erreicht werden, indem Sie sicherstellen, dass implementierte Dienste, die beide Technologien verwenden, der Spezifikation für WS-I Basic Profile 1.1 entsprechen. [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Webdienste, die die WS-I Basic Profile 1.1-Spezifikation erfüllen, können mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients über die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellte Bindung (<xref:System.ServiceModel.BasicHttpBinding>) interagieren.  
  
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
  
 Verwenden Sie das <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute>-Attribut nicht, um Nachrichten basierend auf dem voll qualifizierten Namen des Textelements der SOAP-Nachricht anstatt des `SOAPAction`-HTTP-Headers an Methoden weiterzuleiten. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet den `SOAPAction`-HTTP-Header zum Weiterleiten von Nachrichten.  
  
 Die XML, in die <xref:System.Xml.Serialization.XmlSerializer> standardmäßig einen Typ serialisiert, ist semantisch identisch mit der XML, in die <xref:System.Runtime.Serialization.DataContractSerializer> einen Typ serialisiert, vorausgesetzt, der Namespace ist für die XML explizit definiert. Wenn Sie einen Datentyp für die Verwendung mit definieren [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Webdienste in antizipation einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], gehen Sie folgendermaßen vor:  
  
-   Definieren Sie den Typ mit .NET Framework-Klassen und nicht mit dem XML-Schema.  
  
-   Fügen Sie der Klasse lediglich <xref:System.SerializableAttribute> und <xref:System.Xml.Serialization.XmlRootAttribute> hinzu, wobei Sie mit dem zweiten Attribut den Namespace für den Typ explizit definieren. Fügen Sie keine zusätzlichen Attribute aus dem <xref:System.Xml.Serialization>-Namespace hinzu, um die Übersetzung der .NET Framework-Klasse in XML zu steuern.  
  
-   Wenn Sie diese Vorgehensweise wählen, sollte es später kein Problem darstellen, die .NET-Klassen in Datenverträge umzuwandeln, indem Sie <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> hinzufügen, ohne die XML erheblich zu ändern, in die die Klassen für die Übertragung serialisiert werden. Die von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Webdiensten verwendeten Typen können von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] als Datenverträge verarbeitet werden, was u.&#160;a. zu einer besseren Leistung bei [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen führt.  
  
 Vermeiden Sie die Verwendung der von den Internetinformationsdiensten (IIS) bereitgestellten Authentifizierungsoptionen. Diese werden von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients nicht unterstützt. Falls ein Dienst geschützt werden muss, verwenden Sie die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellten Funktionen, da diese Optionen robuster sind und auf Standardprotokollen basieren.  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a>Durch das Laden von ServiceModel HttpModule verursachte Leistungsbeeinträchtigungen  
 In .NET Framework&#160;3.0 wurde das WCF-`HttpModule`-Element in der Stammdatei Web.config installiert, sodass jede ASP.NET-Anwendung WCF unterstützte. Dies kann die Leistung beeinträchtigen. Sie können daher `ServiceModel` für die Datei Web.config entfernen, wie im folgenden Bespiel gezeigt.  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
<httpModules/>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Konfigurieren von WCF-Dienst für die Zusammenarbeit mit ASP.NET Webdienstclients](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
