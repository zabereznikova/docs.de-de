---
title: 'Vorbereitungen für Windows Communication Foundation: Einfachere Migration in der Zukunft'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: 995bdaaaba96bf8697ea75c1f1a17fa8e51ec2d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185475"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Vorbereitungen für Windows Communication Foundation: Einfachere Migration in der Zukunft
Um eine einfachere zukünftige Migration neuer ASP.NET Anwendungen zu WCF zu gewährleisten, befolgen Sie die vorherigen Empfehlungen sowie die folgenden Empfehlungen.  
  
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
  
 Dies ist ratsam, da WCF Nachrichten benötigt, die verschiedenen Protokollen wie SOAP 1.1 und SOAP 1.2 entsprechen, um verschiedene Endpunkte zu verwenden. Wenn ein ASP.NET 2.0-Webdienst so konfiguriert ist, dass er sowohl SOAP 1.1 als auch SOAP 1.2 unterstützt, was die Standardkonfiguration ist, kann er nicht an einen einzelnen WCF-Endpunkt an der ursprünglichen Adresse migriert werden, die sicherlich mit allen ASP.NET Web kompatibel wäre. bestehende Clients des Service. Auch das Auswählen von SOAP 1.2 anstelle von 1.1 hat eine stärkere Einschränkung der Clients für den Dienst zur Folge.  
  
## <a name="service-development"></a>Dienstentwicklung  
 Mit WCF können Sie Serviceverträge <xref:System.ServiceModel.ServiceContractAttribute> definieren, indem Sie die entweder auf Schnittstellen oder auf Klassen anwenden. Es empfiehlt sich, das Attribut auf eine Schnittstelle (und nicht auf eine Klasse) anzuwenden, da hierdurch die Definition eines Vertrags erstellt wird, der von einer Reihe von Klassen auf unterschiedlichste Weise implementiert werden kann. Von ASP.NET 2.0 wird die Option zum Anwenden des <xref:System.Web.Services.WebService>-Attributs sowohl für Schnittstellen als auch für Klassen unterstützt. Wie jedoch bereits angesprochen: In ASP.NET 2.0 ist ein Fehler vorhanden, durch den der Namespace-Parameter des <xref:System.Web.Services.WebService>-Attributs keine Wirkung zeigt, wenn das Attribut auf eine Schnittstelle (und nicht auf eine Klasse) angewendet wird. Da es im Allgemeinen ratsam ist, den Namespace `http://tempuri.org`eines Dienstes vom Standardwert zu ändern, sollte man mit dem Namespace-Parameter des <xref:System.Web.Services.WebService> Attributs weiterhin ASP.NET Web Dienste definieren, indem sie das <xref:System.ServiceModel.ServiceContractAttribute> Attribut entweder auf Schnittstellen oder auf Klassen anwenden.  
  
- Verwenden Sie in den Methoden zum Definieren dieser Schnittstellen möglichst wenig Code. Konfigurieren Sie sie so, dass deren Aufgaben an andere Klassen delegiert werden. Neue WCF-Diensttypen können dann auch ihre inhaltliche Arbeit an diese Klassen delegieren.  
  
- Geben Sie explizite Namen für die Vorgänge eines Diensts an. Verwenden Sie hierfür den `MessageName`-Parameter des <xref:System.Web.Services.WebMethodAttribute>.  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     Dies ist wichtig, da sich die Standardnamen für Vorgänge in ASP.NET von den von WCF bereitgestellten Standardnamen unterscheiden. Durch Angeben expliziter Namen müssen Sie sich nicht auf die Standardnamen verlassen.  
  
- Implementieren Sie ASP.NET Webdienstvorgänge nicht mit polymorphen Methoden, da WCF die Implementierung von Vorgängen mit polymorphen Methoden nicht unterstützt.  
  
- Verwenden Sie <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>, um explizite Werte für SOAPAction-HTTP-Header anzugeben, durch die HTTP-Anforderungen an Methoden geroutet werden.  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     Bei diesem Ansatz wird umgangen, dass die standardstandardmäßigen SOAPAction-Werte, die von ASP.NET verwendet werden, und WCF identisch sind.  
  
- Verwenden Sie möglichst keine SOAP-Erweiterungen. Wenn SOAP-Erweiterungen erforderlich sind, bestimmen Sie, ob der Zweck, für den sie in Betracht gezogen werden, ein Feature ist, das bereits von WCF bereitgestellt wird. Wenn dies tatsächlich der Fall ist, dann überdenken Sie die Entscheidung, WCF nicht sofort zu übernehmen.  
  
## <a name="state-management"></a>Zustandsverwaltung  
 Verzichten Sie nach Möglichkeit darauf, Zustände in Diensten verwalten zu müssen. Die Aufrechterhaltung des Zustands beeinträchtigt nicht nur die Skalierbarkeit einer Anwendung, sondern auch die Statusverwaltungsmechanismen von ASP.NET und WCF unterscheiden sich sehr, obwohl WCF die ASP.NET Mechanismen im Kompatibilitätsmodus ASP.NET unterstützt.  
  
## <a name="exception-handling"></a>Ausnahmebehandlung  
 Entwerfen Sie beim Ausarbeiten der Strukturen von Datentypen, die von einem Dienst gesendet und empfangen werden sollen, auch Strukturen für die verschiedenen Ausnahmetypen, die in einem an einen Client zu übermittelnden Dienst auftreten können.  
  
```csharp  
[Serializable]  
[XmlRoot(Namespace="ExplicitNamespace", IsNullable=true)]  
public partial class AnticipatedException
{
    private string anticipatedExceptionInformationField;  

    public string AnticipatedExceptionInformation
    {  
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
  
```csharp  
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
  
```csharp  
AnticipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 Diese Ausnahmeklassen können problemlos mit der <xref:System.ServiceModel.FaultException%601> WCF-Klasse wiederverwendet werden, um eine neue`FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>Sicherheit  
 Der folgende Abschnitt enthält einige Sicherheitsempfehlungen:  
  
- Vermeiden Sie die Verwendung ASP.NET 2.0-Profile, da die Verwendung von ihnen die Verwendung ASP.NET Integrationsmodus einschränken würde, wenn der Dienst zu WCF migriert wurde.  
  
- Vermeiden Sie die Verwendung von ACLs zum Steuern des Zugriffs auf Dienste, da ASP.NET Webdienste ACLs mithilfe von Internetinformationsdiensten (Internet Information Services, IIS) unterstützen, WCF dies nicht tut – da ASP.NET Webdienste für das Hosten von IIS abhängig sind und WCF nicht unbedingt in IIS gehostet werden muss.  
  
- Verwenden Sie ASP.NET 2.0-Rollenanbieter zum Autorisieren des Zugriffs auf die Ressource eines Diensts.  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorbereitungen für Windows Communication Foundation: Einfachere Integration in der Zukunft](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
