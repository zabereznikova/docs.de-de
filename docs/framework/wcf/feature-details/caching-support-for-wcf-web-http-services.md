---
title: Cacheunterstützung für WCF-Web-HTTP-Dienste
ms.date: 03/30/2017
ms.assetid: 7f8078e0-00d9-415c-b8ba-c1b6d5c31799
ms.openlocfilehash: b6247dd6c178b355fa4de271415b7cac12f6c629
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116678"
---
# <a name="caching-support-for-wcf-web-http-services"></a>Cacheunterstützung für WCF-Web-HTTP-Dienste

[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] ermöglicht Ihnen die Verwendung des deklarativen zwischen Speicherungs Mechanismus, der in ASP.net in den WCF-Web-http-Diensten bereits verfügbar ist. Auf diese Weise können Sie Antworten der WCF-Web-HTTP-Dienstvorgänge zwischenspeichern. Wenn ein Benutzer HTTP GET an den Dienst sendet, der zum Zwischenspeichern konfiguriert ist, sendet ASP.NET die zwischengespeicherte Antwort zurück, und die Dienstmethode wird nicht aufgerufen. Wenn der Cache abgelaufen ist, wird beim nächsten Senden eines HTTP GET durch einen Benutzer die Dienstmethode aufgerufen und die Antwort erneut zwischengespeichert. Weitere Informationen zum Zwischenspeichern von ASP.net finden Sie unter [ASP.NET Caching Overview](https://docs.microsoft.com/previous-versions/aspnet/ms178597(v=vs.100)).  
  
## <a name="basic-web-http-service-caching"></a>Grundlegendes Zwischenspeichern von Web-HTTP-Diensten  

  Um das Zwischenspeichern von Web-http-Diensten zu aktivieren, müssen Sie zunächst die ASP.NET-Kompatibilität aktivieren, indem Sie die <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> auf die Dienst <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute.RequirementsMode%2A> Einstellung anwenden, um <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> oder <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>  
  
 .NET Framework 4 führt ein neues Attribut mit dem Namen <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> ein, mit dem Sie einen Cache Profilnamen angeben können. Dieses Attribut wird auf einen Dienstvorgang angewendet. Im folgenden Beispiel wird <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> auf einen Dienst angewendet, um ASP.NET-Kompatibilität zu erzielen, und der `GetCustomer`-Vorgang wird für die Zwischenspeicherung konfiguriert. Das <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>-Attribut gibt ein Cacheprofil an, das die zu verwendenden Cacheeinstellungen enthält.  
  
```csharp
[ServiceContract] 
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]
public class Service
{
    [WebGet(UriTemplate = "{id}")]
    [AspNetCacheProfile("CacheFor60Seconds")]
    public Customer GetCustomer(string id)
    {
        // ...
    }
}
```  
  
Aktivieren Sie auch den ASP.NET-Kompatibilitätsmodus in der Datei "Web. config", wie im folgenden Beispiel gezeigt.  
  
```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```
  
> [!WARNING]
> Wenn der ASP.NET-Kompatibilitätsmodus nicht aktiviert ist und <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> verwendet wird, wird eine Ausnahme ausgelöst.  
  
 Der von <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> angegebene Cacheprofilname identifiziert ein Cacheprofil, das der Konfigurationsdatei "Web.config" hinzugefügt wird. Das Cache Profil wird in einem <`outputCacheSetting`>-Element definiert, wie im folgenden Konfigurationsbeispiel gezeigt.  
  
```xml
<!-- ...  -->
<system.web>  
   <caching>  
      <outputCacheSettings>  
         <outputCacheProfiles>  
            <add name="CacheFor60Seconds" duration="60" varyByParam="none" sqlDependency="MyTestDatabase:MyTable"/>  
         </outputCacheProfiles>  
      </outputCacheSettings>  
   </caching>  
   <!-- ... -->  
</system.web>  
```  
  
 Dies ist das gleiche Konfigurationselement, das für ASP.NET-Anwendungen verfügbar ist. Weitere Informationen zu ASP.NET-Cache Profilen finden Sie unter <xref:System.Web.Configuration.OutputCacheProfile>. Die wichtigsten Attribute im Cacheprofil für Web-HTTP-Dienste sind `cacheDuration` und `varyByParam`. Beide Attribute sind erforderlich. `cacheDuration` legt den Zeitraum in Sekunden fest, für den eine Antwort zwischengespeichert werden soll. Mit `varyByParam` können Sie einen Abfragezeichenfolgenparameter angeben, der zum Zwischenspeichern von Antworten verwendet wird. Alle Anforderungen, die mit unterschiedlichen Abfragezeichenfolgenparameter-Werten gestellt werden, werden separat zwischengespeichert. Wenn z. b. eine anfängliche Anforderung an `http://MyServer/MyHttpService/MyOperation?param=10`erfolgt, würden alle nachfolgenden Anforderungen, die mit demselben URI erfolgen, die zwischengespeicherte Antwort zurückgeben (solange die Cache Dauer nicht verstrichen ist). Antworten für eine ähnliche Anforderung, die gleich ist, jedoch über einen anderen Wert als Abfragezeichenfolgenparameter verfügt, werden getrennt zwischengespeichert. Falls Sie dieses separate Zwischenspeicherverhalten nicht wünschen, legen Sie `varyByParam` auf "none" fest.  
  
## <a name="sql-cache-dependency"></a>SQL-Cacheabhängigkeit  

  Antworten auf Web-HTTP-Dienste können auch mit einer SQL-Cacheabhängigkeit zwischengespeichert werden. Wenn der WCF-Web-HTTP-Dienst von in einer SQL-Datenbank gespeicherten Daten abhängig ist, sollten Sie die Antwort des Diensts zwischenspeichern und die zwischengespeicherte Antwort für ungültig erklären, wenn sich die Daten in der SQL-Datenbanktabelle ändern. Dieses Verhalten wird vollständig in der Datei "Web.config" konfiguriert. Definieren Sie zunächst eine Verbindungs Zeichenfolge im <`connectionStrings`>-Element.  
  
```xml
<connectionStrings>
  <add name="connectString"
       connectionString="Data Source=MyService;Initial Catalog=MyTestDatabase;Integrated Security=True"
       providerName="System.Data.SqlClient" />
</connectionStrings>
```  
  
 Anschließend müssen Sie die SQL-Cache Abhängigkeit in einem <`caching`>-Element innerhalb des <`system.web`>-Elements aktivieren, wie im folgenden Konfigurationsbeispiel gezeigt.  
  
```xml  
<system.web>
  <caching>
    <sqlCacheDependency enabled="true" pollTime="1000">
      <databases>
        <add name="MyTestDatabase" connectionStringName="connectString" />
      </databases>
    </sqlCacheDependency>
    <!-- ... -->
  </caching>
  <!-- ... -->
</system.web>
```  
  
 Hier wird die SQL-Cacheabhängigkeit aktiviert und ein Abrufzeitraum von 1000 Millisekunden festgelegt. Wenn der Abrufzeitraum verstrichen ist, wird die Datenbanktabelle jeweils auf Updates geprüft. Wenn Änderungen erkannt werden, wird der Inhalt des Caches entfernt, und beim nächsten Aufrufen des Dienstvorgangs wird eine neue Antwort zwischengespeichert. Fügen Sie im <`sqlCacheDependency`>-Element die Datenbanken hinzu, und verweisen Sie auf die Verbindungs Zeichenfolgen innerhalb des <`databases`>-Elements, wie im folgenden Beispiel gezeigt.  
  
```xml  
<system.web>
  <caching>
    <sqlCacheDependency enabled="true" pollTime="1000">
      <databases>
        <add name="MyTestDatabase" connectionStringName="connectString" />
      </databases>  
    </sqlCacheDependency>  
    <!-- ... -->  
  </caching>  
  <!-- ... -->  
</system.web>  
```  
  
 Im nächsten Schritt müssen Sie die Ausgabe Cache Einstellungen innerhalb des <`caching`>-Elements konfigurieren, wie im folgenden Beispiel gezeigt.  
  
```xml
<system.web>
  <caching>  
    <!-- ...  -->
    <outputCacheSettings>
      <outputCacheProfiles>
        <add name="CacheFor60Seconds" duration="60" varyByParam="none" sqlDependency="MyTestDatabase:MyTable" />
      </outputCacheProfiles>
    </outputCacheSettings>
  </caching>
  <!-- ... -->
</system.web>
```  
  
 Hier ist die Cache Dauer auf 60 Sekunden, `varyByParam` auf None festgelegt, und `sqlDependency` wird auf eine durch Semikolons getrennte Liste von Datenbanknamen/Tabellen Paaren festgelegt, die durch Doppelpunkte getrennt sind. Falls Daten in `MyTable` geändert werden, wird die zwischengespeicherte Antwort für den Dienstvorgang entfernt. Wenn der Vorgang dann aufgerufen wird, wird eine neue Antwort generiert (durch das Aufrufen des Dienstvorgangs), zwischengespeichert und für den Client zurückgegeben.  
  
> [!IMPORTANT]
> Damit ASP.net auf eine SQL-Datenbank zugreifen kann, müssen Sie das [Registrierungs Tool ASP.NET SQL Server](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms229862(v=vs.90))verwenden. Außerdem müssen Sie für das entsprechende Benutzerkonto den Zugriff auf die Datenbank und die Tabelle zulassen. Weitere Informationen finden Sie unter [zugreifen auf SQL Server aus einer Webanwendung](https://docs.microsoft.com/previous-versions/aspnet/ht43wsex(v=vs.100)).  
  
## <a name="conditional-http-get-based-caching"></a>Bedingtes HTTP GET-basiertes Zwischenspeichern  

  In Web-HTTP-Szenarien wird ein bedingtes HTTP Get häufig von Diensten verwendet, um intelligentes http-Caching wie in der [http-Spezifikation](https://www.w3.org/Protocols/rfc2616/rfc2616.html)beschrieben zu implementieren. Zu diesem Zweck muss der Dienst den Wert des ETag-Headers in der HTTP-Antwort festlegen. Außerdem muss er den If-None-Match-Header in der HTTP-Anforderung überprüfen, um zu ermitteln, ob ein angegebener ETag mit dem aktuellen ETag übereinstimmt.  
  
 Für GET- und HEAD-Anforderungen verwendet <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> einen ETag-Wert und überprüft diesen anhand des If-None-Match-Headers der Anforderung. Wenn der Header vorhanden ist und eine Übereinstimmung vorliegt, wird eine <xref:System.ServiceModel.Web.WebFaultException> mit einem HTTP-Statuscode 304 (nicht geändert) ausgelöst, und der Antwort wird ein ETag-Header mit dem passenden ETag hinzugefügt.  
  
 Eine Überladung der <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>-Methode verwendet ein Datum der letzten Änderung und vergleicht es mit dem If-Modified-Since-Header der Anforderung. Wenn der Header vorhanden ist und die Ressource seitdem nicht geändert wurde, wird eine <xref:System.ServiceModel.Web.WebFaultException> mit einem HTTP-Statuscode 304 (Nicht geändert) ausgelöst.  
  
 Für PUT-, POST- und DELETE-Anforderungen verwendet <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> den aktuellen ETag-Wert einer Ressource. Wenn der aktuelle ETag-Wert NULL ist, überprüft die Methode, ob der If-None-Match-Header den Wert "*" hat.  Falls der aktuelle ETag-Wert kein Standardwert ist, vergleicht die Methode den aktuellen ETag-Wert mit dem If-Match-Header der Anforderung. In beiden Fällen löst die Methode eine <xref:System.ServiceModel.Web.WebFaultException> mit dem HTTP-Statuscode 412 (Vorbedingungsfehler) aus, wenn der erwartete Header in der Anforderung nicht vorhanden ist oder der Wert die Bedingungsprüfung nicht besteht, und legt den ETag-Header der Antwort auf den aktuellen ETag-Wert fest.  
  
 Sowohl die `CheckConditional`-Methode als auch die <xref:System.ServiceModel.Web.OutgoingWebResponseContext.SetETag%2A>-Methode stellt sicher, dass der für den Antwortheader festgelegte ETag-Wert ein gültiges ETag gemäß HTTP-Spezifikation ist. Dies schließt das Setzen des ETag-Werts in doppelte Anführungszeichen ein, falls diese nicht bereits vorhanden sind, sowie das ordnungsgemäße Versehen von internen doppelten Anführungszeichen mit Escapezeichen. Der Vergleich von schwachen ETags wird nicht unterstützt.  
  
 Das folgende Beispiel veranschaulicht die Verwendung dieser Methoden.  
  
```csharp
[WebGet(UriTemplate = "{id}"), Description("Returns the specified customer from customers collection. Returns NotFound if there is no such customer. Supports conditional GET.")]
public Customer GetCustomer(string id)
{
    lock (writeLock)
    {
        // return NotFound if there is no item with the specified id.
        object itemEtag = customerEtags[id];
        if (itemEtag == null)
        {
            throw new WebFaultException(HttpStatusCode.NotFound);
        }
  
        // return NotModified if the client did a conditional GET and the customer item has not changed
        // since when the client last retrieved it
        WebOperationContext.Current.IncomingRequest.CheckConditionalRetrieve((long)itemEtag);
        Customer result = this.customers[id] as Customer;
        
        // set the customer etag before returning the result
        WebOperationContext.Current.OutgoingResponse.SetETag((long)itemEtag);
        return result;
    }
}
```  
  
## <a name="security-considerations"></a>Sicherheitsüberlegungen  
 Für Anforderungen, die eine Autorisierung erfordern, sollten die Antworten nicht zwischengespeichert werden, da die Autorisierung nicht ausgeführt wird, wenn die Antwort aus dem Cache bereitgestellt wird.  Die Zwischenspeicherung dieser Antworten würde eine ernste Sicherheitslücke darstellen.  Anforderungen, die eine Autorisierung erfordern, stellen gewöhnlich benutzerspezifische Daten bereit. Aus diesem Grund bietet serverseitiges Zwischenspeichern auch keine Vorteile.  In solchen Situationen ist clientseitiges Zwischenspeichern oder der Verzicht auf Zwischenspeichern besser geeignet.
