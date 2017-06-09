---
title: "WIF und Webfarmen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc3cd7fa-2b45-4614-a44f-8fa9b9d15284
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# WIF und Webfarmen
Wenn Sie Windows Identity Foundation \(WIF\) verwenden, um die Ressourcen einer Anwendung für relying Party \(RP\) zu sichern, die in einer Webfarm bereitgestellt wird, müssen Sie Schritte spezifische um sicherzustellen, dass WIF Token von Instanzen auf verschiedenen Computern in der Farm laufenden RP\-Anwendung verarbeitet werden kann.  Diese Verarbeitung umfasst überprüfen Session\-token\-Signaturen, verschlüsseln und Entschlüsseln Sitzungstoken, Zwischenspeichern Sitzungstoken und Erkennen von Sicherheitstoken wiedergegeben.  
  
 In diesem typischen Fall Wenn WIF zum Sichern von Ressourcen einer Anwendung RP – verwendet wird, ob die RP auf einem einzelnen Computer oder in einer Webfarm läuft\-\-wird eine Sitzung eingerichtet mit dem Kunden basierend auf dem Sicherheitstoken, das von der Sicherheitstokendienst \(STS\) erreicht wurde.  Dies ist zu vermeiden, zwingt den Client sich am STS für jede Anwendungsressource der zu identifizieren, die mit WIF gesichert ist.  Weitere Informationen dazu, wie WIF Sitzungen verarbeitet, finden Sie unter [WIF\-Sitzungsverwaltung](../../../docs/framework/security/wif-session-management.md).  
  
 Wenn die Standardeinstellungen verwendet werden, führt WIF Folgendes aus:  
  
-   Es verwendet eine Instanz der <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> Klasse zum Lesen und Schreiben einen Sitzungstoken \(eine Instanz von der <xref:System.IdentityModel.Tokens.SessionSecurityToken> Klasse\) die Ansprüche und andere Informationen über das Sicherheitstoken, die für die Authentifizierung verwendet wurde, sowie Informationen über die Sitzung selbst ausführt.  Das Sitzungstoken wird verpackt und in einem Sitzungscookie gespeichert.  In der Standardeinstellung <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> verwendet die <xref:System.IdentityModel.ProtectedDataCookieTransform> \-Klasse, die die Data Protection API \(DPAPI\) verwendet, um das Sitzungstoken zu schützen.  Die DPAPI schützt mithilfe der Anmeldeinformationen für Benutzer oder Computer und die wichtigsten Daten im Benutzerprofil gespeichert.  
  
-   Es verwendet ein Standard, der in\-Memory\-Implementierung von der <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> Klasse zum Speichern und verarbeiten das Sitzungstoken.  
  
 Diese Standardeinstellungen arbeiten in Szenarien, in denen die RP\-Anwendung auf einem einzelnen Computer bereitgestellt wird; jedoch, wenn in einer Webfarm bereitgestellt wird, jede HTTP\-Anforderung möglicherweise an gesendet und verarbeitet, die von einer anderen Instanz der RP\-Anwendung auf einem anderen Computer ausgeführt.  In diesem Szenario funktioniert die oben beschriebenen WIF Standardeinstellungen nicht da Sicherheitstoken und Zwischenspeichern von Tokens auf einem bestimmten Computer angewiesen sind.  
  
 Eine RP\-Anwendung in einer Webfarm bereitstellen, müssen Sie sicherstellen, dass die Verarbeitung der Sitzungstoken \(sowie der wiedergegebenen Token\) nicht auf einem bestimmten Computer ausgeführte Anwendung abhängig ist.  Eine Möglichkeit hierzu ist die RP\-Anwendung implementieren, so dass diese die Funktionalität von ASP verwendet.NET `<machineKey>` \-Konfigurationselement und verteilte Zwischenspeicherung für die Verarbeitung von Sitzungstoken und Tokens wiedergegeben.  Die `<machineKey>` Element können Sie geben Sie die Schlüssel erforderlich, um zu überprüfen, verschlüsseln und Entschlüsseln von Token in einer Konfigurationsdatei, die Ihnen ermöglicht, auf verschiedenen Computern in der Webfarm dieselben Schlüssel angeben.  WIF stellt eine spezielle Sitzung Tokenhandler der <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, schützt Token mithilfe der Schlüssel angegeben in der `<machineKey>` Element.  Um diese Strategie zu implementieren, können Sie die folgenden Richtlinien beachten:  
  
-   Verwenden Sie das ASP.NET `<machineKey>` Element Konfiguration explizit Signatur\-und Verschlüsselungsschlüssel angeben, die auf mehreren Computern in der Serverfarm verwendet werden können.  Die folgende XML veranschaulicht die Spezifikation der `<machineKey>` Element unter den `<system.web>` Element in einer Konfigurationsdatei.  
  
    ```xml  
    <machineKey compatibilityMode="Framework45" decryptionKey="CC510D … 8925E6" validationKey="BEAC8 … 6A4B1DE" />  
    ```  
  
-   Konfigurieren Sie die Anwendung für die <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> von der Tokenhandler\-Auflistung hinzufügen.  Zuerst müssen Sie die <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> \(oder alle Handler aus der <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> Klasse\) aus der Tokenhandler\-Auflistung, wenn solche Handler vorhanden ist.  Die <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> verwendet die <xref:System.IdentityModel.Services.MachineKeyTransform> \-Klasse, die die Session\-Cookie\-Daten mithilfe des kryptografischen gemäß schützt die `<machineKey>` Element.  Das folgende XML veranschaulicht das Hinzufügen der <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> Tokenhandler\-Auflistung.  
  
    ```xml  
    <securityTokenHandlers>  
      <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
      <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </securityTokenHandlers>  
    ```  
  
-   Leiten Sie von <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> und implementieren verteilte Zwischenspeicherung, d. h. einen Cache, der von allen Computern in der Farm zugänglich ist auf dem die RP ausgeführt werden kann.  Konfigurieren die RP verwenden Ihre verteilten Cache durch Angabe der [\<sessionSecurityTokenCache\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) Element in der Konfigurationsdatei.  Können Sie überschreiben die <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=fullName> Methode in der abgeleiteten Klasse zum Implementieren der untergeordneten Elemente der `<sessionSecurityTokenCache>` \-Element, wenn sie benötigt werden.  
  
    ```xml  
    <caches>  
      <sessionSecurityTokenCache type="MyCacheLibrary.MySharedSessionSecurityTokenCache, MyCacheLibrary">  
        <!—optional child configuration elements, if implemented by the derived class -->  
      </sessionSecurityTokenCache>  
    </caches>  
    ```  
  
     Eine Möglichkeit zum Implementieren verteilte Zwischenspeicherung ist ein WCF\-front\-End für Ihre benutzerdefinierten Cache bereitstellen.  Weitere Informationen über das Implementieren eines WCF\-Dienst Zwischenspeichern finden Sie unter [Der WCF-Dienst Zwischenspeichern](#BKMK_TheWCFCachingService).  Weitere Informationen über das Implementieren eines WCF\-Clients, die die RP\-Anwendung aufrufen, die caching\-Service verwenden können, finden Sie unter [Der WCF-Client zwischenspeichern](#BKMK_TheWCFClient).  
  
-   Erkennt die Anwendung wiedergegebenen Token müssen Sie eine ähnliche verteilte Zwischenspeicherung Strategie für den token Replay\-Cache durch Ableiten von <xref:System.IdentityModel.Tokens.TokenReplayCache> und replay\-caching\-Service in Ihr Token auf die [\<tokenReplayCache\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) \-Konfigurationselement.  
  
> [!IMPORTANT]
>  Alle XML\-Beispiel und den Code in diesem Thema stammt aus der [ClaimsAwareWebFarm](http://go.microsoft.com/fwlink/?LinkID=248408) \(http:\/\/go.microsoft.com\/fwlink\/?LinkID\=248408\) Beispiel.  
  
> [!IMPORTANT]
>  Die Beispiele in diesem Thema sind ohne Gewähr\-ist und nicht in Produktionscode ohne Änderung verwendet werden sollen.  
  
<a name="BKMK_TheWCFCachingService"></a>   
## Der WCF\-Dienst Zwischenspeichern  
 Die folgende Schnittstelle definiert den Vertrag zwischen dem caching WCF\-Dienst und der WCF\-Client von der relying Party\-Anwendung für die Kommunikation verwendet.  Sie stellt im Wesentlichen die Methoden der <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> Klasse als Dienstvorgänge.  
  
```  
[ServiceContract()]  
public interface ISessionSecurityTokenCacheService  
{  
    [OperationContract]  
    void AddOrUpdate(string endpointId, string contextId, string keyGeneration, SessionSecurityToken value, DateTime expiryTime);  
  
    [OperationContract]  
    IEnumerable<SessionSecurityToken> GetAll(string endpointId, string contextId);  
  
    [OperationContract]  
    SessionSecurityToken Get(string endpointId, string contextId, string keyGeneration);  
  
    [OperationContract(Name = "RemoveAll")]  
    void RemoveAll(string endpointId, string contextId);  
  
    [OperationContract(Name = "RemoveAllByEndpointId")]  
    void RemoveAll(string endpointId);  
  
    [OperationContract]  
    void Remove(string endpointId, string contextId, string keyGeneration);  
}  
```  
  
 Der folgende Code zeigt die Implementierung der WCF Service Zwischenspeichern.  In diesem Beispiel wird der Standardwert wird im Speicher befindlichen Sitzungsstatus Tokencache von WIF implementiert verwendet.  Alternativ könnten Sie einen dauerhaften Cache benötigt eine Datenbank implementieren.  `ISessionSecurityTokenCacheService`definiert die Schnittstelle oben gezeigt.  In diesem Beispiel werden nicht alle Methoden, die die Schnittstelle implementieren aus Platzgründen angezeigt.  
  
```  
using System;  
using System.Collections.Generic;  
using System.IdentityModel.Configuration;  
using System.IdentityModel.Tokens;  
using System.ServiceModel;  
using System.Xml;  
  
namespace WcfSessionSecurityTokenCacheService  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    public class SessionSecurityTokenCacheService : ISessionSecurityTokenCacheService  
    {  
        SessionSecurityTokenCache internalCache;  
  
        // sets the internal cache used by the service to the default WIF in-memory cache.  
        public SessionSecurityTokenCacheService()  
        {  
            internalCache = new IdentityModelCaches().SessionSecurityTokenCache;  
        }  
  
        ...  
  
        public SessionSecurityToken Get(string endpointId, string contextId, string keyGeneration)  
        {  
            // Delegates to the default, in-memory MruSessionSecurityTokenCache used by WIF  
            SessionSecurityToken token = internalCache.Get(new SessionSecurityTokenCacheKey(endpointId, GetContextId(contextId), GetKeyGeneration(keyGeneration)));  
            return token;  
        }  
  
        ...  
  
        private static UniqueId GetContextId(string contextIdString)  
        {  
            return contextIdString == null ? null : new UniqueId(contextIdString);  
        }  
  
        private static UniqueId GetKeyGeneration(string keyGenerationString)  
        {  
            return keyGenerationString == null ? null : new UniqueId(keyGenerationString);  
        }  
    }  
}  
```  
  
<a name="BKMK_TheWCFClient"></a>   
## Der WCF\-Client zwischenspeichern  
 Dieser Abschnitt zeigt die Implementierung einer Klasse, die von <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> und, dass Delegaten an den Zwischenspeicherungsdienst aufruft.  Konfigurieren Sie die RP\-Anwendung zum Verwenden dieser Klasse durch die [\<sessionSecurityTokenCache\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) Element, wie in der folgenden XML\-Code  
  
```  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
 Die Klasse überschreibt die <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A> Methode, um den Dienstendpunkt aus dem benutzerdefinierten `<cacheServiceAddress>` untergeordnetes Element von der `<sessionSecurityTokenCache>` Element.  Es verwendet diesen Endpunkt zum Initialisieren einer `ISessionSecurityTokenCacheService` Kanal, über das sie mit dem Dienst kommunizieren kann.  In diesem Beispiel nicht alle Methoden benötigt, um die Implementierung der <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> Klasse aus Platzgründen angezeigt werden.  
  
```  
using System;  
using System.Configuration;  
using System.IdentityModel.Configuration;  
using System.IdentityModel.Tokens;  
using System.ServiceModel;  
using System.Xml;  
  
namespace CacheLibrary  
{  
    /// <summary>  
    /// This class acts as a proxy to the WcfSessionSecurityTokenCacheService.  
    /// </summary>  
    public class SharedSessionSecurityTokenCache : SessionSecurityTokenCache, ICustomIdentityConfiguration  
    {  
        private ISessionSecurityTokenCacheService WcfSessionSecurityTokenCacheServiceClient;  
  
        internal SharedSessionSecurityTokenCache()  
        {  
        }  
  
        /// <summary>  
        /// Creates a client channel to call the service host.  
        /// </summary>  
        protected void Initialize(string cacheServiceAddress)  
        {  
            if (this.WcfSessionSecurityTokenCacheServiceClient != null)  
            {  
                return;  
            }  
  
            ChannelFactory<ISessionSecurityTokenCacheService> cf = new ChannelFactory<ISessionSecurityTokenCacheService>(  
                new WS2007HttpBinding(SecurityMode.None),  
                new EndpointAddress(cacheServiceAddress));  
            this.WcfSessionSecurityTokenCacheServiceClient = cf.CreateChannel();  
        }  
  
        #region SessionSecurityTokenCache Members  
        // Delegates the following operations to the centralized session security token cache service in the web farm.  
  
        ...  
  
        public override SessionSecurityToken Get(SessionSecurityTokenCacheKey key)  
        {  
            return this.WcfSessionSecurityTokenCacheServiceClient.Get(key.EndpointId, GetContextIdString(key), GetKeyGenerationString(key));  
        }  
  
        ...  
  
        #endregion  
  
        #region ICustomIdentityConfiguration Members  
        // Called from configuration infrastructure to load custom elements  
        public void LoadCustomConfiguration(XmlNodeList nodeList)  
        {  
            // Retrieve the endpoint address of the centralized session security token cache service running in the web farm  
            if (nodeList.Count == 0)  
            {  
                throw new ConfigurationException("No child config element found under <sessionSecurityTokenCache>.");  
            }  
  
            XmlElement cacheServiceAddressElement = nodeList.Item(0) as XmlElement;  
            if (cacheServiceAddressElement.LocalName != "cacheServiceAddress")  
            {  
                throw new ConfigurationException("First child config element under <sessionSecurityTokenCache> is expected to be <cacheServiceAddress>.");  
            }  
  
            string cacheServiceAddress = null;  
            if (cacheServiceAddressElement.Attributes["url"] != null)  
            {  
                cacheServiceAddress = cacheServiceAddressElement.Attributes["url"].Value;  
            }  
            else  
            {  
                throw new ConfigurationException("<cacheServiceAddress> is expected to contain a 'url' attribute.");  
            }  
  
            // Initialize the proxy to the WebFarmSessionSecurityTokenCacheService  
            this.Initialize(cacheServiceAddress);  
        }  
        #endregion  
  
        private static string GetKeyGenerationString(SessionSecurityTokenCacheKey key)  
        {  
            return key.KeyGeneration == null ? null : key.KeyGeneration.ToString();  
        }  
  
        private static string GetContextIdString(SessionSecurityTokenCacheKey key)  
        {  
            return GetContextIdString(key.ContextId);  
        }  
  
        private static string GetContextIdString(UniqueId contextId)  
        {  
            return contextId == null ? null : contextId.ToString();  
        }  
    }  
}  
```  
  
## Siehe auch  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>   
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>   
 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>   
 [WIF\-Sitzungsverwaltung](../../../docs/framework/security/wif-session-management.md)