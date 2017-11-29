---
title: "Vorbereitungen für Windows Communication Foundation: Einfachere Migration in der Zukunft"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 375274cd1b67b6dc71d3e66e1c1f063a81db7d8e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Vorbereitungen für Windows Communication Foundation: Einfachere Migration in der Zukunft
Berücksichtigen Sie die vorherigen sowie die folgenden Empfehlungen, um eine einfachere Migration neuer ASP.NET-Anwendungen in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zu gewährleisten.  
  
## <a name="protocols"></a>Protokolle  
 Deaktivieren Sie die SOAP 1.2-Unterstützung von ASP.NET 2.0:  
  
```xml  
<configuration>  
     <system.web>  
      <webServices >  
          <protocols>  
           <remove name="HttpSoap12"/>  
          </protocols>    
      </webServices>  
     </system.web>   
</configuration>  
```  
  
 Dieser Schritt empfiehlt sich, da Nachrichten für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit unterschiedlichen Protokollen (wie SOAP 1.1 und SOAP 1.2) konform sein müssen, damit verschiedene Endpunkte verwendet werden können. Sieht die Konfiguration eines ASP.NET 2.0-Webdiensts sowohl die Unterstützung von SOAP 1.1 als auch von SOAP 1.2 vor (entspricht der Standardkonfiguration), ist keine Vorwärtsmigration an einen einzelnen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunkt an der ursprünglichen Adresse möglich, die mit allen vorhandenen Clients des ASP.NET-Webdiensts kompatibel wäre. Auch das Auswählen von SOAP 1.2 anstelle von 1.1 hat eine stärkere Einschränkung der Clients für den Dienst zur Folge.  
  
## <a name="service-development"></a>Dienstentwicklung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ermöglicht das Definieren von Dienstverträgen durch Anwenden des <xref:System.ServiceModel.ServiceContractAttribute> auf Schnittstellen oder Klassen. Es empfiehlt sich, das Attribut auf eine Schnittstelle (und nicht auf eine Klasse) anzuwenden, da hierdurch die Definition eines Vertrags erstellt wird, der von einer Reihe von Klassen auf unterschiedlichste Weise implementiert werden kann. Von ASP.NET 2.0 wird die Option zum Anwenden des <xref:System.Web.Services.WebService>-Attributs sowohl für Schnittstellen als auch für Klassen unterstützt. Wie jedoch bereits angesprochen: In ASP.NET 2.0 ist ein Fehler vorhanden, durch den der Namespace-Parameter des <xref:System.Web.Services.WebService>-Attributs keine Wirkung zeigt, wenn das Attribut auf eine Schnittstelle (und nicht auf eine Klasse) angewendet wird. Es empfiehlt sich im Allgemeinen, den Standardwert des Namespace eines Diensts (http://tempuri.org) mithilfe des Namespace-Parameters des <xref:System.Web.Services.WebService>-Attributs zu ändern. Dabei sollten ASP.NET-Webdienste auch weiterhin durch Anwenden des <xref:System.ServiceModel.ServiceContractAttribute>-Attributs auf Schnittstellen ODER Klassen definiert werden.  
  
-   Verwenden Sie in den Methoden zum Definieren dieser Schnittstellen möglichst wenig Code. Konfigurieren Sie sie so, dass deren Aufgaben an andere Klassen delegiert werden. Umfangreiche Aufgaben neuer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensttypen können dann ebenfalls an diese Klassen delegiert werden.  
  
-   Geben Sie explizite Namen für die Vorgänge eines Diensts an. Verwenden Sie hierfür den `MessageName`-Parameter des <xref:System.Web.Services.WebMethodAttribute>.  
  
    ```  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     Dieser Schritt ist wichtig, da sich die Standardnamen für Vorgänge in ASP.NET von den Standardnamen aus [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterscheiden. Durch Angeben expliziter Namen müssen Sie sich nicht auf die Standardnamen verlassen.  
  
-   Implementieren Sie keine ASP.NET-Webdienstvorgänge mit polymorphen Methoden, da dies von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nicht unterstützt wird.  
  
-   Verwenden Sie <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>, um explizite Werte für SOAPAction-HTTP-Header anzugeben, durch die HTTP-Anforderungen an Methoden geroutet werden.  
  
    ```  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     Mit dieser Vorgehensweise müssen Sie sich nicht darauf verlassen, dass die standardmäßig von ASP.NET und [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendeten SOAPAction-Werte übereinstimmen.  
  
-   Verwenden Sie möglichst keine SOAP-Erweiterungen. Ist die Verwendung von SOAP-Erweiterungen erforderlich, überprüfen Sie, ob es sich beim geplanten Einsatzzweck möglicherweise um eine Funktion handelt, die bereits von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellt wird. Ist dies der Fall, sollten Sie die Entscheidung, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nicht anzuwenden, nochmals überdenken.  
  
## <a name="state-management"></a>Zustandsverwaltung  
 Verzichten Sie nach Möglichkeit darauf, Zustände in Diensten verwalten zu müssen. Die Zustandsverwaltung neigt dazu, die Skalierbarkeit einer Anwendung zu beeinträchtigen. Darüber hinaus unterscheiden sich die Zustandsverwaltungsmechanismen von ASP.NET und [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] deutlich, obgleich die ASP.NET-Mechanismen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] im ASP.NET-Kompatibilitätsmodus unterstützt werden.  
  
## <a name="exception-handling"></a>Ausnahmebehandlung  
 Entwerfen Sie beim Ausarbeiten der Strukturen von Datentypen, die von einem Dienst gesendet und empfangen werden sollen, auch Strukturen für die verschiedenen Ausnahmetypen, die in einem an einen Client zu übermittelnden Dienst auftreten können.  
  
```  
[Serializable]  
[XmlRoot(  
     Namespace="ExplicitNamespace", IsNullable=true)]  
    public partial class AnticipatedException {  
  
     private string anticipatedExceptionInformationField;  
  
     public string AnticipatedExceptionInformation {  
      get {  
          return this.anticipatedExceptionInformationField;  
          }  
      set {  
          this.anticipatedExceptionInformationField = value;  
          }  
     }  
}  
```  
  
 Konfigurieren Sie Klassen dieser Art so, dass sie eigenständig zu XML serialisiert werden können:  
  
```  
public XmlNode ToXML()  
{  
     XmlSerializer serializer = new XmlSerializer(  
      typeof(AnticipatedException));  
     MemoryStream memoryStream = new MemoryStream();  
     XmlTextWriter writer = new XmlTextWriter(  
     memoryStream, UnicodeEncoding.UTF8);  
     serializer.Serialize(writer, this);  
     XmlDocument document = new XmlDocument();  
     document.LoadXml(new string(  
     UnicodeEncoding.UTF8.GetChars(  
     memoryStream.GetBuffer())).Trim());  
    return document.DocumentElement;  
}  
```  
  
 Die Klassen können anschließend zum Angeben der Details für explizit ausgelöste <xref:System.Web.Services.Protocols.SoapException>-Instanzen verwendet werden:  
  
```  
AnctipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 Diese Ausnahmeklassen können problemlos mit der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.ServiceModel.FaultException%601>-Klasse wiederverwendet werden, um eine neue `FaultException<AnticipatedException>(anticipatedException);` auszulösen.  
  
## <a name="security"></a>Sicherheit  
 Der folgende Abschnitt enthält einige Sicherheitsempfehlungen:  
  
-   Verwenden Sie nach Möglichkeit keine ASP.NET 2.0-Profile, da durch deren Verwendung die Verwendung des ASP.NET-Integrationsmodus eingeschränkt wird, nachdem der Dienst zu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] migriert wurde.  
  
-   Verwenden Sie möglichst keine ACLs zum Steuern des Dienstzugriffs, da von ASP.NET-Webdiensten ACLs unter Verwendung von Internetinformationsdienste (IIS) unterstützt werden, von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dagegen nicht. Der Grund: IIS ist für das Hosten von ASP.NET-Webdiensten erforderlich, wohingegen WCF nicht unbedingt in IIS gehostet werden muss.  
  
-   Verwenden Sie ASP.NET 2.0-Rollenanbieter zum Autorisieren des Zugriffs auf die Ressource eines Diensts.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorbereitungen für Windows Communication Foundation: einfachere Integration in der Zukunft](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
