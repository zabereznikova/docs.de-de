---
title: WIF und Webfarmen
ms.date: 03/30/2017
ms.assetid: fc3cd7fa-2b45-4614-a44f-8fa9b9d15284
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: ed6a7fbe550dad85cf505eaf20a446803b84c96f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33410415"
---
# <a name="wif-and-web-farms"></a>WIF und Webfarmen
Wenn Sie Windows Identity Foundation (WIF) verwenden, um die Ressourcen von einer Anwendung der vertrauenden Seite zu sichern, die in einer Webfarm bereitgestellt wird, müssen Sie bestimmte Schritte durchführen, um sicherzustellen, dass WIF Token von Instanzen der Anwendung der vertrauenden Seite verarbeiten kann. Diese Anwendung wird auf verschiedenen Computern in der Farm ausgeführt. Diese Verarbeitung beinhaltet die Überprüfung von Signaturen der Sitzungstokens, die Verschlüsselung, Entschlüsselung und Zwischenspeicherung der Sitzungstoken, und die Erkennung von wiedergegebenen Sicherheitstoken.  
  
 Wenn WIF zur Absicherung von Ressourcen von Anwendungen der vertrauenden Seite verwendet wird (unabhängig davon, ob die vertrauende Seite auf einem einzelnen Computer oder in einer Webfarm ausgeführt wird), wird im Normalfall eine Sitzung mit dem Client erstellt, die auf dem Sicherheitstoken basiert, das vom Sicherheitstokendienst (STS) abgerufen wurde. Dadurch wird vermieden, dass der Client jede mithilfe von WIF gesicherte Anwendungsressource gegenüber des STS authentifizieren muss. Weitere Informationen zur Behandlung von Sitzungen in WIF finden Sie unter [WIF-Sitzungsverwaltung](../../../docs/framework/security/wif-session-management.md).  
  
 Wenn die Standardeinstellungen verwendet werden, führt WIF Folgendes aus:  
  
-   Es wird eine Instanz der <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>-Klasse zum Lesen und Schreiben eines Sitzungstokens (eine Instanz der <xref:System.IdentityModel.Tokens.SessionSecurityToken>-Klasse) verwendet, die Ansprüche und andere Informationen über das Sicherheitstoken überträgt, die für die Authentifizierung verwendet wurden sowie Informationen über die Sitzung selbst. Das Sitzungstoken wird verpackt und in ein Sitzungscookie gespeichert. Standardmäßig verwendet <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> die <xref:System.IdentityModel.ProtectedDataCookieTransform>-Klasse, welche Sitzungstoken mit der Data Protection API (DPAPI) schützt. Die DPAPI bietet Schutz mithilfe der Anmeldeinformationen für Benutzer oder Computer und speichert die Schlüsseldaten im Benutzerprofil.  
  
-   Sie verwendet eine standardmäßige, speicherinterne Implementierung der <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>-Klasse zur Speicherung und Verarbeitung des Sitzungstokens.  
  
 Diese Standardeinstellungen eignen sich für Szenarios, in denen die Anwendung der vertrauenden Seite auf einem Einzelcomputer bereitgestellt wird. Bei der Bereitstellung in einer Webfarm kann jede HTTP-Anforderung möglicherweise an eine andere Instanz dieser Anwendung, die auf einem anderen Computer ausgeführt wird, gesendet und von ihr verarbeitet werden. In diesem Szenario funktionieren die oben beschriebenen WIF-Standardeinstellungen nicht, da sowohl der Schutz und die Zwischenspeicherung des Tokens von einem bestimmten Computer abhängig sind.  
  
 Um eine Anwendung der vertrauenden Seite in einer Webfarm bereitstellen zu können, müssen Sie sicherstellen, dass die Verarbeitung der Sitzungstoken (sowie der wiedergegebenen Token) nicht davon abhängt, dass die Anwendung auf einem bestimmten Computer ausgeführt wird. Eine Möglichkeit hierfür ist die Implementierung Ihrer Anwendung der vertrauenden Seite, sodass sie die vom `<machineKey>`-Konfigurationselement von ASP.NET bereitgestellten Funktionen verwendet, und verteilte Zwischenspeicherung für die Verarbeitung von Sitzungstoken und wiedergegebenen Token bereitstellt. Das `<machineKey>`-Element ermöglicht Ihnen das Festlegen der Schlüssel, die zur Überprüfung, Ver- und Entschlüsselung von Token in einer Konfigurationsdatei nötig sind. Sie können somit die gleichen Schlüssel auf verschiedenen Computern in der Webfarm festlegen. WIF stellt einen speziellen Sitzungstokenhandler <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> zur Verfügung, der Token mit den im `<machineKey>`-Element angegebenen Schlüsseln schützt. Um diese Strategie zu implementieren, können Sie die folgenden Richtlinien beachten:  
  
-   Verwenden Sie das `<machineKey>`-Element von ASP.NET in der Konfiguration, um die Schlüssel zur Signierung und Verschlüsselung explizit anzugeben, die auf Computern in der Farm verwendet werden können. Das folgende XML zeigt die Spezifikation des `<machineKey>`-Elements unter dem `<system.web>`-Element in einer Konfigurationsdatei.  
  
    ```xml  
    <machineKey compatibilityMode="Framework45" decryptionKey="CC510D … 8925E6" validationKey="BEAC8 … 6A4B1DE" />  
    ```  
  
-   Konfigurieren Sie die Anwendung für die Verwendung der <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, indem Sie sie zur Auflistung der Tokenhandler hinzufügen. Entfernen Sie zuerst die <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> (oder alle aus der <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>-Klasse abgeleiteten Handler) aus der Auflistung der Tokenhandler, wenn ein solcher Handler vorhanden ist. Die <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> verwendet die <xref:System.IdentityModel.Services.MachineKeyTransform>-Klasse, die die Cookiedaten der Sitzung mit kryptografischem Material schützt, das im `<machineKey>`-Element angegeben ist. Das folgende XML zeigt das Hinzufügen der <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> zu einer Auflistung von Tokenhandler.  
  
    ```xml  
    <securityTokenHandlers>  
      <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
      <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </securityTokenHandlers>  
    ```  
  
-   Von <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> ableiten und verteilte Zwischenspeicherung implementieren, d.h., einen Zwischenspeicher, auf den von allen Computern in der Farm, auf denen die vertrauende Seite ausgeführt werden könnte, zugegriffen werden kann. Konfigurieren Sie die vertrauende Seite für die Verwendung Ihres verteilten Zwischenspeichers durch Angabe des [\<SessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)-Elements in der Konfigurationsdatei. Sie können die <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=nameWithType>-Methode in der abgeleiteten Klasse überschreiben, sodass sie untergeordnete Elemente des `<sessionSecurityTokenCache>`-Elements überschreibt, sofern diese erforderlich sind.  
  
    ```xml  
    <caches>  
      <sessionSecurityTokenCache type="MyCacheLibrary.MySharedSessionSecurityTokenCache, MyCacheLibrary">  
        <!—optional child configuration elements, if implemented by the derived class -->  
      </sessionSecurityTokenCache>  
    </caches>  
    ```  
  
     Eine Möglichkeit zur Implementierung des verteilten Zwischenspeichers ist die Bereitstellung des WCF-Front-Ends für Ihren benutzerdefinierten Zwischenspeicher. Weitere Informationen zum Implementieren eines WCFS-Caching-Diensts finden Sie unter [Der WCF-Cache-Dienst](#BKMK_TheWCFCachingService). Weitere Informationen zum Implementieren eines WCF-Clients, den die Anwendung der vertrauenden Seite zum Aufrufen des Cache-Diensts verwenden kann, finden Sie unter [Der WCF-Caching-Client](#BKMK_TheWCFClient).  
  
-   Wenn Ihre Anwendung wiedergegebene Token erkennt, müssen Sie einer ähnlichen Strategie für verteilte Zwischenspeicher für den Zwischenspeicher der wiedergegebene Token folgen. Leiten Sie von <xref:System.IdentityModel.Tokens.TokenReplayCache> ab, und verweisen Sie auf den Caching-Dienst für wiedergegebene Token im Konfigurationselement [\<TokenReplayCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md).  
  
> [!IMPORTANT]
>  Alle XML-Beispiel und Code in diesem Thema stammt aus dem [ClaimsAwareWebFarm](http://go.microsoft.com/fwlink/?LinkID=248408) (http://go.microsoft.com/fwlink/?LinkID=248408) Beispiel.  
  
> [!IMPORTANT]
>  Die Beispiele in diesem Thema werden unverändert bereitgestellt, und sollen nicht ohne Änderungen im Produktionscode verwendet werden.  
  
<a name="BKMK_TheWCFCachingService"></a>   
## <a name="the-wcf-caching-service"></a>Der WCF-Caching-Dienst  
 Die folgende Schnittstelle definiert den Vertrag zwischen dem WCF-Cache-Dienst und dem WCF-Client, die von der Anwendung der vertrauenden Seite für die Kommunikation verwendet werden. Im Wesentlichen werden die Methoden der <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>-Klasse als Dienstvorgänge verfügbar gemacht.  
  
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
  
 Im folgenden Codebeispiel wird die Implementierung des WCF-Cache-Diensts veranschaulicht. In diesem Beispiel wird der von WIF implementierte speicherinterne, standardmäßige Zwischenspeicher für Sitzungstoken verwendet. Alternativ könnten Sie einen permanenten Zwischenspeicher implementieren, der von einer Datenbank ergänzt wird. `ISessionSecurityTokenCacheService` definiert die oben gezeigte Schnittstelle. In diesem Beispiel werden aus Gründen der Übersichtlichkeit nicht alle Methoden gezeigt, die zur Implementierung der Schnittstelle erforderlich sind.  
  
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
## <a name="the-wcf-caching-client"></a>Der WCF-Cachingclient  
 Dieser Abschnitt zeigt die Implementierung einer Klasse, die von <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> abgeleitet ist, und Aufrufe an den Cachedienst weiterleitet. Sie konfigurieren die Anwendung der vertrauenden Seite zur Verwendung dieser Klasse, indem Sie das [\<SessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)-Element wie im folgenden XML-Code verwenden.  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
 Die Klasse überschreibt die <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A>-Methode zum Abrufen des Dienstendpunkts aus dem benutzerdefinierten, untergeordneten `<cacheServiceAddress>`-Element des `<sessionSecurityTokenCache>`-Elements. Sie verwendet diesen Endpunkt zum Initialisieren eines `ISessionSecurityTokenCacheService`-Kanals, über den sie mit dem Dienst kommunizieren kann.  In diesem Beispiel werden aus Gründen der Übersichtlichkeit nicht alle Methoden gezeigt, die zur Implementierung der <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>-Klasse erforderlich sind.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>  
 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>  
 [WIF-Sitzungsverwaltung](../../../docs/framework/security/wif-session-management.md)
