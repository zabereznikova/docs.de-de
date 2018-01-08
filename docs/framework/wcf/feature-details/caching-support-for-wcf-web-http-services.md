---
title: "Cacheunterstützung für WCF-Web-HTTP-Dienste"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f8078e0-00d9-415c-b8ba-c1b6d5c31799
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 723f485ab45cbe127bfd337c2d428d38d5f27232
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2018
---
# <a name="caching-support-for-wcf-web-http-services"></a>Cacheunterstützung für WCF-Web-HTTP-Dienste
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]ermöglicht es Ihnen, verwenden Sie deklarative Zwischenspeichermechanismus in ASP.NET in Ihre WCF-Web-HTTP-Dienste bereits verfügbar. Auf diese Weise können Sie Antworten der WCF-Web-HTTP-Dienstvorgänge zwischenspeichern. Wenn ein Benutzer HTTP GET an den Dienst sendet, der zum Zwischenspeichern konfiguriert ist, sendet ASP.NET die zwischengespeicherte Antwort zurück, und die Dienstmethode wird nicht aufgerufen. Wenn der Cache abgelaufen ist, wird beim nächsten Senden eines HTTP GET durch einen Benutzer die Dienstmethode aufgerufen und die Antwort erneut zwischengespeichert. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Das Zwischenspeichern, in ASP.NET finden Sie unter [Übersicht über das Zwischenspeichern von ASP.NET](http://go.microsoft.com/fwlink/?LinkId=152534)  
  
## <a name="basic-web-http-service-caching"></a>Grundlegendes Zwischenspeichern von Web-HTTP-Diensten  
 Zum Aktivieren des Zwischenspeicherns von WEB-HTTP-Diensten müssen Sie zuerst die ASP.NET-Kompatibilität aktivieren, indem Sie <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> auf die Diensteinstellung <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute.RequirementsMode%2A> und <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> oder <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required> anwenden.  
  
 Mit [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] wird ein neues Attribut mit dem Namen <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> eingeführt, das Ihnen das Angeben eines Cacheprofilnamens ermöglicht. Dieses Attribut wird auf einen Dienstvorgang angewendet. Im folgenden Beispiel wird <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> auf einen Dienst angewendet, um ASP.NET-Kompatibilität zu erzielen, und der `GetCustomer`-Vorgang wird für die Zwischenspeicherung konfiguriert. Die <!--zz<xref:System.ServiceModel.Activation.AspNetCacheProfileAttribute>--> `System.ServiceModel.Activation.AspNetCacheProfileAttribute` Attribut gibt ein Cacheprofil, das die Einstellungen zum Zwischenspeichern zu verwendende enthält.  
  
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
  
 Sie müssen auch den ASP.NET-Kompatibilitätsmodus in der Datei "Web.config" aktivieren, wie im folgenden Beispiel gezeigt.  
  
```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```
  
> [!WARNING]
>  Wenn der ASP.NET-Kompatibilitätsmodus nicht aktiviert ist und <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> verwendet wird, wird eine Ausnahme ausgelöst.  
  
 Der von <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> angegebene Cacheprofilname identifiziert ein Cacheprofil, das der Konfigurationsdatei "Web.config" hinzugefügt wird. Das Cacheprofil mit definiert ist, einem <`outputCacheSetting`>-Element wie im folgenden Konfigurationsbeispiel gezeigt.  
  
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
  
 Dies ist das gleiche Konfigurationselement, das für ASP.NET-Anwendungen verfügbar ist. [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu ASP.NET-Cacheprofilen finden Sie unter <xref:System.Web.Configuration.OutputCacheProfile>. Die wichtigsten Attribute im Cacheprofil für Web-HTTP-Dienste sind `cacheDuration` und `varyByParam`. Beide Attribute sind erforderlich. `cacheDuration` legt den Zeitraum in Sekunden fest, für den eine Antwort zwischengespeichert werden soll. Mit `varyByParam` können Sie einen Abfragezeichenfolgenparameter angeben, der zum Zwischenspeichern von Antworten verwendet wird. Alle Anforderungen, die mit unterschiedlichen Abfragezeichenfolgenparameter-Werten gestellt werden, werden separat zwischengespeichert. Nachdem zum Beispiel eine ursprüngliche Anforderung an "http://MyServer/MyHttpService/MyOperation?param=10" gestellt wird, wird für alle nachfolgenden Anforderungen mit dem gleichen URI die zwischengespeicherte Antwort zurückgegeben (sofern die Cachedauer nicht verstrichen ist). Antworten für eine ähnliche Anforderung, die gleich ist, jedoch über einen anderen Wert als Abfragezeichenfolgenparameter verfügt, werden getrennt zwischengespeichert. Falls Sie dieses separate Zwischenspeicherverhalten nicht wünschen, legen Sie `varyByParam` auf "none" fest.  
  
## <a name="sql-cache-dependency"></a>SQL-Cacheabhängigkeit  
 Antworten auf Web-HTTP-Dienste können auch mit einer SQL-Cacheabhängigkeit zwischengespeichert werden. Wenn der WCF-Web-HTTP-Dienst von in einer SQL-Datenbank gespeicherten Daten abhängig ist, sollten Sie die Antwort des Diensts zwischenspeichern und die zwischengespeicherte Antwort für ungültig erklären, wenn sich die Daten in der SQL-Datenbanktabelle ändern. Dieses Verhalten wird vollständig in der Datei "Web.config" konfiguriert. Definieren Sie zunächst eine Verbindungszeichenfolge in der <`connectionStrings`> Element.  
  
```xml
<connectionStrings>
  <add name="connectString"
       connectionString="Data Source=MyService;Initial Catalog=MyTestDatabase;Integrated Security=True"
       providerName="System.Data.SqlClient" />
</connectionStrings>
```  
  
 Dann müssen Sie die SQL-Cacheabhängigkeit innerhalb Aktivieren einer <`caching`> Element innerhalb der <`system.web`> Element wie im folgenden Beispiel Config dargestellt.  
  
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
  
 Hier wird die SQL-Cacheabhängigkeit aktiviert und ein Abrufzeitraum von 1000 Millisekunden festgelegt. Wenn der Abrufzeitraum verstrichen ist, wird die Datenbanktabelle jeweils auf Updates geprüft. Wenn Änderungen erkannt werden, wird der Inhalt des Caches entfernt, und beim nächsten Aufrufen des Dienstvorgangs wird eine neue Antwort zwischengespeichert. In der <`sqlCacheDependency`> Element Datenbanken hinzuzufügen, und verweisen Sie die Verbindungszeichenfolgen in der <`databases`>-Element wie im folgenden Beispiel gezeigt.  
  
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
  
 Als Nächstes müssen Sie konfigurieren die ausgabechacheinstellungen innerhalb der <`caching`>-Element wie im folgenden Beispiel gezeigt.  
  
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
  
 Hier wird die Cachedauer auf 60 Sekunden festgelegt, `varyByParam` wird auf "none" festgelegt, und `sqlDependency` wird auf eine durch Semikolons getrennte Liste mit Datenbankname/Tabelle-Paaren festgelegt, die jeweils durch Doppelpunkte getrennt sind. Falls Daten in `MyTable` geändert werden, wird die zwischengespeicherte Antwort für den Dienstvorgang entfernt. Wenn der Vorgang dann aufgerufen wird, wird eine neue Antwort generiert (durch das Aufrufen des Dienstvorgangs), zwischengespeichert und für den Client zurückgegeben.  
  
> [!IMPORTANT]
>  Verwenden Sie für ASP.NET für den Zugriff auf eine SQL­Datenbank, die [ASP.NET SQL Server-Registrierungstool](http://go.microsoft.com/fwlink/?LinkId=152536). Außerdem müssen Sie für das entsprechende Benutzerkonto den Zugriff auf die Datenbank und die Tabelle zulassen. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Zugriff auf SQLServer aus einer Webanwendung](http://go.microsoft.com/fwlink/?LinkId=178988).  
  
## <a name="conditional-http-get-based-caching"></a>Bedingtes HTTP GET-basiertes Zwischenspeichern  
 In Web-HTTP-Szenarien eine bedingte HTTP GET wird häufig von Diensten intelligent HTTP-caching implementieren, wie beschrieben in der [HTTP-Spezifikation](http://go.microsoft.com/fwlink/?LinkId=165800). Dazu muss der Dienst den Wert des ETag-Headers in der HTTP-Antwort festlegen. Außerdem muss er den If-None-Match-Header in der HTTP-Anforderung überprüfen, um zu ermitteln, ob ein angegebener ETag mit dem aktuellen ETag übereinstimmt.  
  
 Für GET- und HEAD-Anforderungen verwendet <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> einen ETag-Wert und überprüft diesen anhand des If-None-Match-Headers der Anforderung. Wenn der Header vorhanden ist und eine Übereinstimmung vorliegt, wird eine <xref:System.ServiceModel.Web.WebFaultException> mit dem HTTP-Statuscode 304 (Nicht geändert) ausgelöst, und der Antwort mit dem übereinstimmenden ETag wird ein ETag-Header hinzugefügt.  
  
 Eine Überladung der <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>-Methode verwendet ein Datum der letzten Änderung und vergleicht es mit dem If-Modified-Since-Header der Anforderung. Wenn der Header vorhanden ist und die Ressource seitdem nicht geändert wurde, wird eine <xref:System.ServiceModel.Web.WebFaultException> mit einem HTTP-Statuscode 304 (Nicht geändert) ausgelöst.  
  
 Für PUT-, POST- und DELETE-Anforderungen verwendet <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> den aktuellen ETag-Wert einer Ressource. Wenn der aktuelle ETag-Wert null ist, die Methode überprüft, ob der If-None-Match-Header den Wert hat "*".  Falls der aktuelle ETag-Wert kein Standardwert ist, vergleicht die Methode den aktuellen ETag-Wert mit dem If-Match-Header der Anforderung. In beiden Fällen löst die Methode eine <xref:System.ServiceModel.Web.WebFaultException> mit dem HTTP-Statuscode 412 (Vorbedingungsfehler) aus, wenn der erwartete Header in der Anforderung nicht vorhanden ist oder der Wert die Bedingungsprüfung nicht besteht, und legt den ETag-Header der Antwort auf den aktuellen ETag-Wert fest.  
  
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
