---
title: Cacheunterstützung für WCF-Web-HTTP-Dienste
ms.date: 03/30/2017
ms.assetid: 7f8078e0-00d9-415c-b8ba-c1b6d5c31799
ms.openlocfilehash: 7c60deab635c29785398a1b50f9cf14c0f688420
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141789"
---
# <a name="caching-support-for-wcf-web-http-services"></a><span data-ttu-id="00a3e-102">Cacheunterstützung für WCF-Web-HTTP-Dienste</span><span class="sxs-lookup"><span data-stu-id="00a3e-102">Caching Support for WCF Web HTTP Services</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="00a3e-103">ermöglicht Ihnen die Verwendung des deklarativen zwischen Speicherungs Mechanismus, der in ASP.net in den WCF-Web-http-Diensten bereits verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="00a3e-103">enables you to use the declarative caching mechanism already available in ASP.NET in your WCF Web HTTP services.</span></span> <span data-ttu-id="00a3e-104">Auf diese Weise können Sie Antworten der WCF-Web-HTTP-Dienstvorgänge zwischenspeichern.</span><span class="sxs-lookup"><span data-stu-id="00a3e-104">This allows you to cache responses from your WCF Web HTTP service operations.</span></span> <span data-ttu-id="00a3e-105">Wenn ein Benutzer HTTP GET an den Dienst sendet, der zum Zwischenspeichern konfiguriert ist, sendet ASP.NET die zwischengespeicherte Antwort zurück, und die Dienstmethode wird nicht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="00a3e-105">When a user sends an HTTP GET to your service that is configured for caching, ASP.NET sends back the cached response and the service method is not called.</span></span> <span data-ttu-id="00a3e-106">Wenn der Cache abgelaufen ist, wird beim nächsten Senden eines HTTP GET durch einen Benutzer die Dienstmethode aufgerufen und die Antwort erneut zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="00a3e-106">When the cache expires, the next time a user sends an HTTP GET, your service method is called and the response is once again cached.</span></span> <span data-ttu-id="00a3e-107">Weitere Informationen zum Zwischenspeichern von ASP.net finden Sie unter [ASP.NET Caching Overview](https://go.microsoft.com/fwlink/?LinkId=152534) .</span><span class="sxs-lookup"><span data-stu-id="00a3e-107">For more information about ASP.NET caching, see [ASP.NET Caching Overview](https://go.microsoft.com/fwlink/?LinkId=152534)</span></span>  
  
## <a name="basic-web-http-service-caching"></a><span data-ttu-id="00a3e-108">Grundlegendes Zwischenspeichern von Web-HTTP-Diensten</span><span class="sxs-lookup"><span data-stu-id="00a3e-108">Basic Web HTTP Service Caching</span></span>  
 <span data-ttu-id="00a3e-109">Zum Aktivieren des Zwischenspeicherns von WEB-HTTP-Diensten müssen Sie zuerst die ASP.NET-Kompatibilität aktivieren, indem Sie <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> auf die Diensteinstellung <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute.RequirementsMode%2A> und <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> oder <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required> anwenden.</span><span class="sxs-lookup"><span data-stu-id="00a3e-109">To enable WEB HTTP service caching you must first enable ASP.NET compatibility by applying the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> to the service setting <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute.RequirementsMode%2A> to <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> or <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>.</span></span>  
  
 <span data-ttu-id="00a3e-110">.NET Framework 4 führt ein neues Attribut mit dem Namen <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> ein, mit dem Sie einen Cache Profilnamen angeben können.</span><span class="sxs-lookup"><span data-stu-id="00a3e-110">.NET Framework 4 introduces a new attribute called <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> that allows you to specify a cache profile name.</span></span> <span data-ttu-id="00a3e-111">Dieses Attribut wird auf einen Dienstvorgang angewendet.</span><span class="sxs-lookup"><span data-stu-id="00a3e-111">This attribute is applied to a service operation.</span></span> <span data-ttu-id="00a3e-112">Im folgenden Beispiel wird <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> auf einen Dienst angewendet, um ASP.NET-Kompatibilität zu erzielen, und der `GetCustomer`-Vorgang wird für die Zwischenspeicherung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="00a3e-112">The following example applies the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> to a service to enable ASP.NET compatibility and configures the `GetCustomer` operation for caching.</span></span> <span data-ttu-id="00a3e-113">Das <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>-Attribut gibt ein Cacheprofil an, das die zu verwendenden Cacheeinstellungen enthält.</span><span class="sxs-lookup"><span data-stu-id="00a3e-113">The <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> attribute specifies a cache profile that contains the cache settings to be used.</span></span>  
  
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
  
 <span data-ttu-id="00a3e-114">Sie müssen auch den ASP.NET-Kompatibilitätsmodus in der Datei "Web.config" aktivieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="00a3e-114">You must also turn on ASP.NET compatibility mode in the Web.config file as shown in the following example.</span></span>  
  
```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```
  
> [!WARNING]
> <span data-ttu-id="00a3e-115">Wenn der ASP.NET-Kompatibilitätsmodus nicht aktiviert ist und <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> verwendet wird, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="00a3e-115">If ASP.NET compatibility mode is not turned on and the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> is used an exception is thrown.</span></span>  
  
 <span data-ttu-id="00a3e-116">Der von <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> angegebene Cacheprofilname identifiziert ein Cacheprofil, das der Konfigurationsdatei "Web.config" hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="00a3e-116">The cache profile name specified by the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> identifies a cache profile that is added to your Web.config configuration file.</span></span> <span data-ttu-id="00a3e-117">Das Cache Profil wird in einem <`outputCacheSetting`>-Element definiert, wie im folgenden Konfigurationsbeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="00a3e-117">The cache profile is defined with in a <`outputCacheSetting`> element as shown in the following configuration example.</span></span>  
  
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
  
 <span data-ttu-id="00a3e-118">Dies ist das gleiche Konfigurationselement, das für ASP.NET-Anwendungen verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="00a3e-118">This is the same configuration element that is available to ASP.NET applications.</span></span> <span data-ttu-id="00a3e-119">Weitere Informationen zu ASP.NET-Cache Profilen finden Sie unter <xref:System.Web.Configuration.OutputCacheProfile>.</span><span class="sxs-lookup"><span data-stu-id="00a3e-119">For more information about ASP.NET cache profiles, see <xref:System.Web.Configuration.OutputCacheProfile>.</span></span> <span data-ttu-id="00a3e-120">Die wichtigsten Attribute im Cacheprofil für Web-HTTP-Dienste sind `cacheDuration` und `varyByParam`.</span><span class="sxs-lookup"><span data-stu-id="00a3e-120">For Web HTTP services, the most important attributes in the cache profile are: `cacheDuration` and `varyByParam`.</span></span> <span data-ttu-id="00a3e-121">Beide Attribute sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="00a3e-121">Both of these attributes are required.</span></span> <span data-ttu-id="00a3e-122">`cacheDuration` legt den Zeitraum in Sekunden fest, für den eine Antwort zwischengespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="00a3e-122">`cacheDuration` sets the amount of time a response should be cached in seconds.</span></span> <span data-ttu-id="00a3e-123">Mit `varyByParam` können Sie einen Abfragezeichenfolgenparameter angeben, der zum Zwischenspeichern von Antworten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="00a3e-123">`varyByParam` allows you to specify a query string parameter that is used to cache responses.</span></span> <span data-ttu-id="00a3e-124">Alle Anforderungen, die mit unterschiedlichen Abfragezeichenfolgenparameter-Werten gestellt werden, werden separat zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="00a3e-124">All requests made with different query string parameter values are cached separately.</span></span> <span data-ttu-id="00a3e-125">Wenn z. b. eine anfängliche Anforderung an `http://MyServer/MyHttpService/MyOperation?param=10`erfolgt, würden alle nachfolgenden Anforderungen, die mit demselben URI erfolgen, die zwischengespeicherte Antwort zurückgeben (solange die Cache Dauer nicht verstrichen ist).</span><span class="sxs-lookup"><span data-stu-id="00a3e-125">For example, once an initial request is made to `http://MyServer/MyHttpService/MyOperation?param=10`, all subsequent requests made with the same URI would be returned the cached response (so long as the cache duration has not elapsed).</span></span> <span data-ttu-id="00a3e-126">Antworten für eine ähnliche Anforderung, die gleich ist, jedoch über einen anderen Wert als Abfragezeichenfolgenparameter verfügt, werden getrennt zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="00a3e-126">Responses for a similar request that is the same but has a different value for the parameter query string parameter are cached separately.</span></span> <span data-ttu-id="00a3e-127">Falls Sie dieses separate Zwischenspeicherverhalten nicht wünschen, legen Sie `varyByParam` auf "none" fest.</span><span class="sxs-lookup"><span data-stu-id="00a3e-127">If you do not want this separate caching behavior, set `varyByParam` to "none".</span></span>  
  
## <a name="sql-cache-dependency"></a><span data-ttu-id="00a3e-128">SQL-Cacheabhängigkeit</span><span class="sxs-lookup"><span data-stu-id="00a3e-128">SQL Cache Dependency</span></span>  
 <span data-ttu-id="00a3e-129">Antworten auf Web-HTTP-Dienste können auch mit einer SQL-Cacheabhängigkeit zwischengespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="00a3e-129">Web HTTP service responses can also be cached with a SQL cache dependency.</span></span> <span data-ttu-id="00a3e-130">Wenn der WCF-Web-HTTP-Dienst von in einer SQL-Datenbank gespeicherten Daten abhängig ist, sollten Sie die Antwort des Diensts zwischenspeichern und die zwischengespeicherte Antwort für ungültig erklären, wenn sich die Daten in der SQL-Datenbanktabelle ändern.</span><span class="sxs-lookup"><span data-stu-id="00a3e-130">If your WCF Web HTTP service depends on data stored in a SQL database, you may want to cache the service's response and invalidate the cached response when data in the SQL database table changes.</span></span> <span data-ttu-id="00a3e-131">Dieses Verhalten wird vollständig in der Datei "Web.config" konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="00a3e-131">This behavior is configured completely within the Web.config file.</span></span> <span data-ttu-id="00a3e-132">Sie müssen zunächst eine Verbindungs Zeichenfolge im <`connectionStrings`>-Element definieren.</span><span class="sxs-lookup"><span data-stu-id="00a3e-132">You must first define a connection string in the <`connectionStrings`> element.</span></span>  
  
```xml
<connectionStrings>
  <add name="connectString"
       connectionString="Data Source=MyService;Initial Catalog=MyTestDatabase;Integrated Security=True"
       providerName="System.Data.SqlClient" />
</connectionStrings>
```  
  
 <span data-ttu-id="00a3e-133">Anschließend müssen Sie die SQL-Cache Abhängigkeit in einem <`caching`>-Element innerhalb des <`system.web`>-Elements aktivieren, wie im folgenden Konfigurationsbeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="00a3e-133">Then you must enable SQL cache dependency within a <`caching`> element within the <`system.web`> element as shown in the following config example.</span></span>  
  
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
  
 <span data-ttu-id="00a3e-134">Hier wird die SQL-Cacheabhängigkeit aktiviert und ein Abrufzeitraum von 1000 Millisekunden festgelegt.</span><span class="sxs-lookup"><span data-stu-id="00a3e-134">Here SQL cache dependency is enabled and a polling time of 1000 milliseconds is set.</span></span> <span data-ttu-id="00a3e-135">Wenn der Abrufzeitraum verstrichen ist, wird die Datenbanktabelle jeweils auf Updates geprüft.</span><span class="sxs-lookup"><span data-stu-id="00a3e-135">Each time the polling time elapses the database table is checked for updates.</span></span> <span data-ttu-id="00a3e-136">Wenn Änderungen erkannt werden, wird der Inhalt des Caches entfernt, und beim nächsten Aufrufen des Dienstvorgangs wird eine neue Antwort zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="00a3e-136">If changes are detected the contents of the cache are removed and the next time the service operation is invoked a new response is cached.</span></span> <span data-ttu-id="00a3e-137">Fügen Sie im <`sqlCacheDependency`>-Element die Datenbanken hinzu, und verweisen Sie auf die Verbindungs Zeichenfolgen innerhalb des <`databases`>-Elements, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="00a3e-137">Within the <`sqlCacheDependency`> element add the databases and reference the connection strings within the <`databases`> element as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="00a3e-138">Im nächsten Schritt müssen Sie die Ausgabe Cache Einstellungen innerhalb des <`caching`>-Elements konfigurieren, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="00a3e-138">Next you must configure the output cache settings within the <`caching`> element as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="00a3e-139">Hier wird die Cachedauer auf 60 Sekunden festgelegt, `varyByParam` wird auf "none" festgelegt, und `sqlDependency` wird auf eine durch Semikolons getrennte Liste mit Datenbankname/Tabelle-Paaren festgelegt, die jeweils durch Doppelpunkte getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="00a3e-139">Here the cache duration is set to 60 seconds, `varyByParam` is set to none and `sqlDependency` is set to a semicolon delimited list of database name/table pairs separated by colons.</span></span> <span data-ttu-id="00a3e-140">Falls Daten in `MyTable` geändert werden, wird die zwischengespeicherte Antwort für den Dienstvorgang entfernt. Wenn der Vorgang dann aufgerufen wird, wird eine neue Antwort generiert (durch das Aufrufen des Dienstvorgangs), zwischengespeichert und für den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="00a3e-140">When data in `MyTable` is changed the cached response for the service operation is removed and when the operation is invoked a new response is generated (by calling the service operation), cached, and returned to the client.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="00a3e-141">Damit ASP.net auf eine SQL-Datenbank zugreifen kann, müssen Sie das [Registrierungs Tool ASP.NET SQL Server](https://go.microsoft.com/fwlink/?LinkId=152536)verwenden.</span><span class="sxs-lookup"><span data-stu-id="00a3e-141">For ASP.NET to access a SQL database, you must use the [ASP.NET SQL Server Registration Tool](https://go.microsoft.com/fwlink/?LinkId=152536).</span></span> <span data-ttu-id="00a3e-142">Außerdem müssen Sie für das entsprechende Benutzerkonto den Zugriff auf die Datenbank und die Tabelle zulassen.</span><span class="sxs-lookup"><span data-stu-id="00a3e-142">In addition you must allow the appropriate user account access to the database and table.</span></span> <span data-ttu-id="00a3e-143">Weitere Informationen finden Sie unter [zugreifen auf SQL Server aus einer Webanwendung](https://go.microsoft.com/fwlink/?LinkId=178988).</span><span class="sxs-lookup"><span data-stu-id="00a3e-143">For more information, see [Accessing SQL Server from a Web Application](https://go.microsoft.com/fwlink/?LinkId=178988).</span></span>  
  
## <a name="conditional-http-get-based-caching"></a><span data-ttu-id="00a3e-144">Bedingtes HTTP GET-basiertes Zwischenspeichern</span><span class="sxs-lookup"><span data-stu-id="00a3e-144">Conditional HTTP GET Based Caching</span></span>  
 <span data-ttu-id="00a3e-145">In Web-HTTP-Szenarien wird ein bedingtes HTTP Get häufig von Diensten verwendet, um intelligentes http-Caching wie in der [http-Spezifikation](https://go.microsoft.com/fwlink/?LinkId=165800)beschrieben zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="00a3e-145">In Web HTTP scenarios a conditional HTTP GET is often used by services to implement intelligent HTTP caching as described in the [HTTP Specification](https://go.microsoft.com/fwlink/?LinkId=165800).</span></span> <span data-ttu-id="00a3e-146">Dazu muss der Dienst den Wert des ETag-Headers in der HTTP-Antwort festlegen.</span><span class="sxs-lookup"><span data-stu-id="00a3e-146">To do this the service must set the value of the ETag header in the HTTP response.</span></span> <span data-ttu-id="00a3e-147">Außerdem muss er den If-None-Match-Header in der HTTP-Anforderung überprüfen, um zu ermitteln, ob ein angegebener ETag mit dem aktuellen ETag übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="00a3e-147">It also must check the If-None-Match header in the HTTP request to see whether any of the ETag specified matches the current ETag.</span></span>  
  
 <span data-ttu-id="00a3e-148">Für GET- und HEAD-Anforderungen verwendet <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> einen ETag-Wert und überprüft diesen anhand des If-None-Match-Headers der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="00a3e-148">For GET and HEAD requests, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> takes an ETag value and checks it against the If-None-Match header of the request.</span></span> <span data-ttu-id="00a3e-149">Wenn der Header vorhanden ist und eine Übereinstimmung vorliegt, wird eine <xref:System.ServiceModel.Web.WebFaultException> mit dem HTTP-Statuscode 304 (Nicht geändert) ausgelöst, und der Antwort mit dem übereinstimmenden ETag wird ein ETag-Header hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="00a3e-149">If the header is present and there is a match, a <xref:System.ServiceModel.Web.WebFaultException> with a HTTP status code 304 (Not Modified) is thrown and an ETag header is added to the response with the matching ETag.</span></span>  
  
 <span data-ttu-id="00a3e-150">Eine Überladung der <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>-Methode verwendet ein Datum der letzten Änderung und vergleicht es mit dem If-Modified-Since-Header der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="00a3e-150">One overload of the <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> method takes a last modified date and checks it against the If-Modified-Since header of the request.</span></span> <span data-ttu-id="00a3e-151">Wenn der Header vorhanden ist und die Ressource seitdem nicht geändert wurde, wird eine <xref:System.ServiceModel.Web.WebFaultException> mit einem HTTP-Statuscode 304 (Nicht geändert) ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="00a3e-151">If the header is present and the resource has not been modified since, a <xref:System.ServiceModel.Web.WebFaultException> with an HTTP status code 304 (Not Modified) is thrown.</span></span>  
  
 <span data-ttu-id="00a3e-152">Für PUT-, POST- und DELETE-Anforderungen verwendet <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> den aktuellen ETag-Wert einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="00a3e-152">For PUT, POST, and DELETE requests, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> takes the current ETag value of a resource.</span></span> <span data-ttu-id="00a3e-153">Wenn der aktuelle ETag-Wert NULL ist, überprüft die Methode, ob der If-None-Match-Header den Wert "\*" hat.</span><span class="sxs-lookup"><span data-stu-id="00a3e-153">If the current ETag value is null, the method checks that the If-None- Match header has a value of "\*".</span></span>  <span data-ttu-id="00a3e-154">Falls der aktuelle ETag-Wert kein Standardwert ist, vergleicht die Methode den aktuellen ETag-Wert mit dem If-Match-Header der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="00a3e-154">If the current ETag value is not a default value, then the method checks the current ETag value against the If- Match header of the request.</span></span> <span data-ttu-id="00a3e-155">In beiden Fällen löst die Methode eine <xref:System.ServiceModel.Web.WebFaultException> mit dem HTTP-Statuscode 412 (Vorbedingungsfehler) aus, wenn der erwartete Header in der Anforderung nicht vorhanden ist oder der Wert die Bedingungsprüfung nicht besteht, und legt den ETag-Header der Antwort auf den aktuellen ETag-Wert fest.</span><span class="sxs-lookup"><span data-stu-id="00a3e-155">In either case, the method throws a <xref:System.ServiceModel.Web.WebFaultException> with an HTTP status code 412 (Precondition Failed) if the expected header is not present in the request or its value does not satisfy the conditional check and sets the ETag header of the response to the current ETag value.</span></span>  
  
 <span data-ttu-id="00a3e-156">Sowohl die `CheckConditional`-Methode als auch die <xref:System.ServiceModel.Web.OutgoingWebResponseContext.SetETag%2A>-Methode stellt sicher, dass der für den Antwortheader festgelegte ETag-Wert ein gültiges ETag gemäß HTTP-Spezifikation ist.</span><span class="sxs-lookup"><span data-stu-id="00a3e-156">Both the `CheckConditional` methods and the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.SetETag%2A> method ensures that the ETag value set on the response header is a valid ETag according to the HTTP specification.</span></span> <span data-ttu-id="00a3e-157">Dies schließt das Setzen des ETag-Werts in doppelte Anführungszeichen ein, falls diese nicht bereits vorhanden sind, sowie das ordnungsgemäße Versehen von internen doppelten Anführungszeichen mit Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="00a3e-157">This includes surrounding the ETag value in double quotes if they are not already present and properly escaping any internal double quote characters.</span></span> <span data-ttu-id="00a3e-158">Der Vergleich von schwachen ETags wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="00a3e-158">Weak ETag comparison is not supported.</span></span>  
  
 <span data-ttu-id="00a3e-159">Das folgende Beispiel veranschaulicht die Verwendung dieser Methoden.</span><span class="sxs-lookup"><span data-stu-id="00a3e-159">The following example shows how to use these methods.</span></span>  
  
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
  
## <a name="security-considerations"></a><span data-ttu-id="00a3e-160">Sicherheitsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="00a3e-160">Security Considerations</span></span>  
 <span data-ttu-id="00a3e-161">Für Anforderungen, die eine Autorisierung erfordern, sollten die Antworten nicht zwischengespeichert werden, da die Autorisierung nicht ausgeführt wird, wenn die Antwort aus dem Cache bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="00a3e-161">Requests that require authorization should not have their responses cached, because the authorization is not performed when the response is served from the cache.</span></span>  <span data-ttu-id="00a3e-162">Die Zwischenspeicherung dieser Antworten würde eine ernste Sicherheitslücke darstellen.</span><span class="sxs-lookup"><span data-stu-id="00a3e-162">Caching such responses would introduce a serious security vulnerability.</span></span>  <span data-ttu-id="00a3e-163">Anforderungen, die eine Autorisierung erfordern, stellen gewöhnlich benutzerspezifische Daten bereit. Aus diesem Grund bietet serverseitiges Zwischenspeichern auch keine Vorteile.</span><span class="sxs-lookup"><span data-stu-id="00a3e-163">Usually, requests that require authorization provide user-specific data and therefore server-side caching is not even beneficial.</span></span>  <span data-ttu-id="00a3e-164">In solchen Situationen ist clientseitiges Zwischenspeichern oder der Verzicht auf Zwischenspeichern besser geeignet.</span><span class="sxs-lookup"><span data-stu-id="00a3e-164">In such situations, client-side caching or simply not caching at all will be more appropriate.</span></span>
