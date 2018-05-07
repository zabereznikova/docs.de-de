---
title: 'Vorbereitungen für Windows Communication Foundation: Einfachere Migration in der Zukunft'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: aeafc164d16d9dc60ad0b3012da292e9b0bb38b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Vorbereitungen für Windows Communication Foundation: Einfachere Migration in der Zukunft
Um eine einfachere Migration neuer ASP.NET-Anwendungen in WCF, führen Sie die vorherigen Empfehlungen als auch die folgenden Empfehlungen beachten.  
  
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
  
 Auf diese Weise ist ratsam, da WCF Nachrichten, die verschiedene Protokolle wie SOAP 1.1 und SOAP 1.2 entsprechen, fahren Sie mit verschiedenen Endpunkten erforderlich sind. Wenn eine ASP.NET 2.0 Web-Dienst für die Unterstützung von SOAP 1.1 und SOAP 1.2 mit der Standardkonfiguration ist er kann nicht konfiguriert ist vorwärts zu einem einzelnen WCF-Endpunkt an der ursprünglichen Adresse migriert wäre mit der ASP.NET Web kompatibel sein der Dienst vorhandenen Clients. Auch das Auswählen von SOAP 1.2 anstelle von 1.1 hat eine stärkere Einschränkung der Clients für den Dienst zur Folge.  
  
## <a name="service-development"></a>Dienstentwicklung  
 WCF bietet die Möglichkeit zum Definieren von Dienstverträgen durch Anwenden der <xref:System.ServiceModel.ServiceContractAttribute> auf Schnittstellen oder Klassen. Es empfiehlt sich, das Attribut auf eine Schnittstelle (und nicht auf eine Klasse) anzuwenden, da hierdurch die Definition eines Vertrags erstellt wird, der von einer Reihe von Klassen auf unterschiedlichste Weise implementiert werden kann. Von ASP.NET 2.0 wird die Option zum Anwenden des <xref:System.Web.Services.WebService>-Attributs sowohl für Schnittstellen als auch für Klassen unterstützt. Wie jedoch bereits angesprochen: In ASP.NET 2.0 ist ein Fehler vorhanden, durch den der Namespace-Parameter des <xref:System.Web.Services.WebService>-Attributs keine Wirkung zeigt, wenn das Attribut auf eine Schnittstelle (und nicht auf eine Klasse) angewendet wird. Da es in der Regel empfehlenswert, so ändern Sie den Namespace eines Diensts aus der Standardwert ist http://tempuri.org, mit dem Namespace-Parameter von der <xref:System.Web.Services.WebService> -Attribut, eine sollten weiterhin definieren ASP.NET-Webdienste durch Anwenden der <xref:System.ServiceModel.ServiceContractAttribute> Attribut entweder auf Schnittstellen oder Klassen.  
  
-   Verwenden Sie in den Methoden zum Definieren dieser Schnittstellen möglichst wenig Code. Konfigurieren Sie sie so, dass deren Aufgaben an andere Klassen delegiert werden. Neue Typen von WCF-Dienste konnten substanziellen Arbeit an diese Klassen dann auch delegieren.  
  
-   Geben Sie explizite Namen für die Vorgänge eines Diensts an. Verwenden Sie hierfür den `MessageName`-Parameter des <xref:System.Web.Services.WebMethodAttribute>.  
  
    ```  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     Auf diese Weise ist wichtig, da die Standardnamen für Vorgänge in ASP.NET von den Standardnamen durch WCF unterschiedlich sind. Durch Angeben expliziter Namen müssen Sie sich nicht auf die Standardnamen verlassen.  
  
-   Da WCF keine implementierende Vorgänge mit polymorphen Methoden unterstützt ASP.NET Web-Dienstvorgängen nicht mit polymorphen Methoden implementiert werden.  
  
-   Verwenden Sie <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>, um explizite Werte für SOAPAction-HTTP-Header anzugeben, durch die HTTP-Anforderungen an Methoden geroutet werden.  
  
    ```  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     Bei diesem Ansatz wird umgehen, müssen die Standardeinstellung von ASP.NET und WCF übereinstimmen verwendeten SOAPAction-Werte abhängig.  
  
-   Verwenden Sie möglichst keine SOAP-Erweiterungen. Überprüfen Sie SOAP-Erweiterungen erforderlich sind, ob für die sie in Betracht gezogen werden eine Funktion dient, die bereits von WCF bereitgestellt wird. Wenn dies tatsächlich der Fall ist, überprüfen Sie die Wahl, WCF nicht sofort zu verwenden.  
  
## <a name="state-management"></a>Zustandsverwaltung  
 Verzichten Sie nach Möglichkeit darauf, Zustände in Diensten verwalten zu müssen. Nicht nur ist Zustandsverwaltung tendenziell die Skalierbarkeit einer Anwendung beeinträchtigen, sondern der Zustand schlüsselverwaltungsmechanismen von ASP.NET und WCF sehr unterschiedlich sind, obwohl WCF das ASP.NET Mechanismen im ASP.NET-Kompatibilitätsmodus unterstützt wird.  
  
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
  
 Diese Ausnahmeklassen werden mit den WCF sofort verwendbare<xref:System.ServiceModel.FaultException%601> Klasse eine neue ausgelöst werden soll `FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>Sicherheit  
 Der folgende Abschnitt enthält einige Sicherheitsempfehlungen:  
  
-   Vermeiden Sie mithilfe von ASP.NET 2.0-Profile, da durch deren Verwendung die Verwendung des ASP.NET-Integrationsmodus eingeschränkt wird, wenn der Dienst in WCF migriert wurde.  
  
-   Vermeiden Sie die Verwendung von ACLs zum Steuern des Zugriffs auf Dienste, als ASP.NET Web Services unterstützt ACLs unter Verwendung von Internet Information Services (IIS), WCF nicht der Fall, da ASP.NET-Webdienste hängen IIS zum Hosten von WCF nicht unbedingt in IIS gehostet werden.  
  
-   Verwenden Sie ASP.NET 2.0-Rollenanbieter zum Autorisieren des Zugriffs auf die Ressource eines Diensts.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorbereitungen für Windows Communication Foundation: Einfachere Integration in der Zukunft](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
