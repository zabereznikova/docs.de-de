---
title: 'Vorbereitungen für Windows Communication Foundation: einfachere Integration in der Zukunft'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: bf3155f19e42787746d59ce7b593273522e2840a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245054"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Vorbereitungen für Windows Communication Foundation: einfachere Integration in der Zukunft

Um eine einfachere Migration neuer ASP.NET-Anwendungen zu WCF zu gewährleisten, befolgen Sie die vorangehenden Empfehlungen sowie die folgenden Empfehlungen.  
  
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
  
 Dies ist empfehlenswert, da für WCF Nachrichten erforderlich sind, die mit verschiedenen Protokollen wie SOAP 1,1 und SOAP 1,2 konform sind, um unterschiedliche Endpunkte zu verwenden. Wenn ein ASP.NET 2,0-Webdienst für die Unterstützung von SOAP 1,1 und SOAP 1,2 (der Standardkonfiguration) konfiguriert ist, kann er nicht zu einem einzelnen WCF-Endpunkt an der ursprünglichen Adresse migriert werden, der sicherlich mit allen vorhandenen Clients des ASP.NET-Webdiensts kompatibel wäre. Auch das Auswählen von SOAP 1.2 anstelle von 1.1 hat eine stärkere Einschränkung der Clients für den Dienst zur Folge.  
  
## <a name="service-development"></a>Dienstentwicklung  

 WCF ermöglicht es Ihnen, Dienstverträge zu definieren, indem Sie <xref:System.ServiceModel.ServiceContractAttribute> entweder auf Schnittstellen oder Klassen anwenden. Es empfiehlt sich, das Attribut auf eine Schnittstelle (und nicht auf eine Klasse) anzuwenden, da hierdurch die Definition eines Vertrags erstellt wird, der von einer Reihe von Klassen auf unterschiedlichste Weise implementiert werden kann. Von ASP.NET 2.0 wird die Option zum Anwenden des <xref:System.Web.Services.WebService>-Attributs sowohl für Schnittstellen als auch für Klassen unterstützt. Wie jedoch bereits angesprochen: In ASP.NET 2.0 ist ein Fehler vorhanden, durch den der Namespace-Parameter des <xref:System.Web.Services.WebService>-Attributs keine Wirkung zeigt, wenn das Attribut auf eine Schnittstelle (und nicht auf eine Klasse) angewendet wird. Da es im Allgemeinen ratsam ist, den Namespace eines Diensts vom Standardwert zu ändern, muss `http://tempuri.org` mithilfe des Namespace-Parameters des- <xref:System.Web.Services.WebService> Attributs weiterhin ASP.NET-Webdienste definiert werden, indem das- <xref:System.ServiceModel.ServiceContractAttribute> Attribut entweder auf Schnittstellen oder Klassen angewendet wird.  
  
- Verwenden Sie in den Methoden zum Definieren dieser Schnittstellen möglichst wenig Code. Konfigurieren Sie sie so, dass deren Aufgaben an andere Klassen delegiert werden. Neue WCF-Dienst Typen können dann auch Ihre inhaltlichen Aufgaben an diese Klassen delegieren.  
  
- Geben Sie explizite Namen für die Vorgänge eines Diensts an. Verwenden Sie hierfür den `MessageName`-Parameter des <xref:System.Web.Services.WebMethodAttribute>.  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     Dies ist wichtig, da sich die Standardnamen für Vorgänge in ASP.net von den Standardnamen unterscheiden, die von WCF bereitgestellt werden. Durch Angeben expliziter Namen müssen Sie sich nicht auf die Standardnamen verlassen.  
  
- Implementieren Sie keine ASP.NET-Webdienst Vorgänge mit polymorphen Methoden, da WCF das Implementieren von Vorgängen mit polymorphen Methoden nicht unterstützt.  
  
- Verwenden Sie <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>, um explizite Werte für SOAPAction-HTTP-Header anzugeben, durch die HTTP-Anforderungen an Methoden geroutet werden.  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     Wenn Sie diesen Ansatz verwenden, müssen Sie sich nicht auf die standardmäßigen SOAPAction-Werte verlassen, die von ASP.net und WCF verwendet werden.  
  
- Verwenden Sie möglichst keine SOAP-Erweiterungen. Wenn SOAP-Erweiterungen erforderlich sind, stellen Sie fest, ob der Zweck, für den Sie gelten, eine Funktion ist, die bereits von WCF bereitgestellt wird. Wenn dies tatsächlich der Fall ist, sollten Sie die Auswahl überdenken, um WCF nicht sofort zu übernehmen.  
  
## <a name="state-management"></a>Zustandsverwaltung  

 Verzichten Sie nach Möglichkeit darauf, Zustände in Diensten verwalten zu müssen. Nicht nur die Zustands Verwaltung beeinträchtigt tendenziell die Skalierbarkeit einer Anwendung, aber die Zustands Verwaltungsmechanismen von ASP.net und WCF unterscheiden sich stark, obwohl WCF die ASP.net-Mechanismen im ASP.NET-Kompatibilitätsmodus unterstützt.  
  
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
  
 Diese Ausnahme Klassen können problemlos mit der WCF-Klasse wieder verwendet werden <xref:System.ServiceModel.FaultException%601> , um eine neue `FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>Sicherheit  

 Der folgende Abschnitt enthält einige Sicherheitsempfehlungen:  
  
- Vermeiden Sie die Verwendung von ASP.NET 2,0-Profilen, da die Verwendung des ASP.net-Integrationsmodus eingeschränkt wäre, wenn der Dienst zu WCF migriert wurde.  
  
- Vermeiden Sie die Verwendung von ACLs, um den Zugriff auf Dienste zu steuern, da ASP.NET-Webdienste ACLs mithilfe von Internetinformationsdienste (IIS) unterstützen, WCF nicht –, weil ASP.NET-Webdienste von IIS zum Hosten abhängen und WCF nicht unbedingt in IIS gehostet werden muss.  
  
- Verwenden Sie ASP.NET 2.0-Rollenanbieter zum Autorisieren des Zugriffs auf die Ressource eines Diensts.  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorbereitungen für Windows Communication Foundation: einfachere Migration in der Zukunft](anticipating-adopting-the-wcf-easing-future-integration.md)
