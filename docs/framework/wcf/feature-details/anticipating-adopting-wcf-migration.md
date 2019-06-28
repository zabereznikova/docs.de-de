---
title: 'Vorbereitungen für Windows Communication Foundation: einfachere Integration in der Zukunft'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: 09bbb11c58992f0fabcb822f5f3d88fef273bea9
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425285"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Vorbereitungen für Windows Communication Foundation: einfachere Integration in der Zukunft
Führen Sie die vorherigen Empfehlungen als auch die folgenden Empfehlungen, um sicherzustellen, dass eine einfachere Migration neuer ASP.NET-Anwendungen zu WCF.  
  
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
  
 Auf diese Weise ist ratsam, da WCF Nachrichten an verschiedene Protokolle, wie SOAP 1.1 und SOAP 1.2 entsprechen verschiedene Endpunkte erforderlich ist. Wenn eine ASP.NET 2.0 Web-Dienst für die Unterstützung sowohl SOAP 1.1- und SOAP 1.2, die in der Standardkonfiguration ist er kann nicht konfiguriert ist Weiterleitung mit einem einzigen WCF-Endpunkt, an der ursprünglichen Adresse migriert, das wäre mit aller der ASP.NET Web kompatibel sein vorhandene Clients des Diensts. Auch das Auswählen von SOAP 1.2 anstelle von 1.1 hat eine stärkere Einschränkung der Clients für den Dienst zur Folge.  
  
## <a name="service-development"></a>Dienstentwicklung  
 WCF ermöglicht es Ihnen, Definieren von Dienstverträgen durch Anwenden der <xref:System.ServiceModel.ServiceContractAttribute> auf Schnittstellen oder Klassen. Es empfiehlt sich, das Attribut auf eine Schnittstelle (und nicht auf eine Klasse) anzuwenden, da hierdurch die Definition eines Vertrags erstellt wird, der von einer Reihe von Klassen auf unterschiedlichste Weise implementiert werden kann. Von ASP.NET 2.0 wird die Option zum Anwenden des <xref:System.Web.Services.WebService>-Attributs sowohl für Schnittstellen als auch für Klassen unterstützt. Wie jedoch bereits angesprochen: In ASP.NET 2.0 ist ein Fehler vorhanden, durch den der Namespace-Parameter des <xref:System.Web.Services.WebService>-Attributs keine Wirkung zeigt, wenn das Attribut auf eine Schnittstelle (und nicht auf eine Klasse) angewendet wird. Da es im Allgemeinen ratsam, so ändern Sie den Namespace eines Diensts aus der Standardwert ist `http://tempuri.org`, mit dem Namespace-Parameter von der <xref:System.Web.Services.WebService> -Attribut, eine sollten weiterhin Definieren von ASP.NET Web Services durch Anwenden der <xref:System.ServiceModel.ServiceContractAttribute> Attribut entweder auf Schnittstellen oder Klassen.  
  
- Verwenden Sie in den Methoden zum Definieren dieser Schnittstellen möglichst wenig Code. Konfigurieren Sie sie so, dass deren Aufgaben an andere Klassen delegiert werden. Neue Typen von WCF-Dienst können dann auch substanziellen Arbeit an diese Klassen delegieren.  
  
- Geben Sie explizite Namen für die Vorgänge eines Diensts an. Verwenden Sie hierfür den `MessageName`-Parameter des <xref:System.Web.Services.WebMethodAttribute>.  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     Auf diese Weise ist wichtig, da die Standardnamen für Vorgänge in ASP.NET den Standardnamen, die von WCF unterscheiden. Durch Angeben expliziter Namen müssen Sie sich nicht auf die Standardnamen verlassen.  
  
- Implementieren Sie Webdienstvorgänge auf ASP.NET nicht mit polymorphen Methoden, da WCF keine ASP.NET-Webdienstvorgänge mit polymorphen Methoden unterstützt.  
  
- Verwenden Sie <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>, um explizite Werte für SOAPAction-HTTP-Header anzugeben, durch die HTTP-Anforderungen an Methoden geroutet werden.  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     Bei diesem Ansatz wird umgehen SOAPAction-Werte, die von ASP.NET und WCF nicht identisch, verwendet die Standardeinstellung verwenden müssen.  
  
- Verwenden Sie möglichst keine SOAP-Erweiterungen. Wenn SOAP-Erweiterungen erforderlich sind, klicken Sie dann bestimmen Sie, ob es sich bei der Zweck, die für den sie in Betracht gezogen werden, ein Feature ist, die bereits von WCF bereitgestellt wird. Überdenken Sie, wenn dies tatsächlich der Fall ist, klicken Sie dann die Möglichkeit, WCF nicht sofort zu übernehmen.  
  
## <a name="state-management"></a>Zustandsverwaltung  
 Verzichten Sie nach Möglichkeit darauf, Zustände in Diensten verwalten zu müssen. Nicht nur Zustandsverwaltung neigt dazu, die Skalierbarkeit einer Anwendung beeinträchtigen, sondern die zustandsverwaltungsmechanismen von ASP.NET und WCF sind sehr verschieden, obwohl WCF die Mechanismen ASP.NET im ASP.NET-Kompatibilitätsmodus unterstützt wird.  
  
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
  
 Diese Ausnahmeklassen werden sofort wieder verwendbare, mit den WCF <xref:System.ServiceModel.FaultException%601> Klasse, um ein neues auslösen `FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>Sicherheit  
 Der folgende Abschnitt enthält einige Sicherheitsempfehlungen:  
  
- Vermeiden Sie mithilfe von ASP.NET 2.0-Profile, da durch deren Verwendung die Verwendung des ASP.NET-Integrationsmodus eingeschränkt wird, wenn der Dienst WCF migriert wurde.  
  
- Verwenden Sie Zugriffssteuerungslisten zum Steuern des Zugriffs auf Dienste, wie ASP.NET Web Services unterstützt die Zugriffssteuerungslisten (Internet Information Services, IIS), WCF, jedoch nicht, da ASP.NET Web Services IIS zum Hosten von abhängig und WCF nicht unbedingt in IIS gehostet werden.  
  
- Verwenden Sie ASP.NET 2.0-Rollenanbieter zum Autorisieren des Zugriffs auf die Ressource eines Diensts.  
  
## <a name="see-also"></a>Siehe auch

- [Vorbereitungen für Windows Communication Foundation: Einfachere Integration in der Zukunft](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
