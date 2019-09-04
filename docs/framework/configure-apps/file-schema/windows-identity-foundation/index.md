---
title: Windows Identity Foundation-Konfigurationsschema
ms.date: 03/30/2017
ms.assetid: 4d4f6d76-49a5-4bad-b345-097b2e2844e9
author: BrucePerlerMS
ms.openlocfilehash: 8dc58f3dc68ee226228056e457914c9dfa53cca5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251975"
---
# <a name="windows-identity-foundation-configuration-schema"></a><span data-ttu-id="7a675-102">Windows Identity Foundation-Konfigurationsschema</span><span class="sxs-lookup"><span data-stu-id="7a675-102">Windows Identity Foundation Configuration Schema</span></span>

<span data-ttu-id="7a675-103">Die Themen in diesem Abschnitt enthalten Informationen über das Konfigurationsschema von Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="7a675-103">The topics in this section provide information about the Windows Identity Foundation (WIF) configuration schema.</span></span> <span data-ttu-id="7a675-104">Sie können eine Anwendung auch so konfigurieren, dass Sie WIF über Klassen verwendet, die vom Framework verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="7a675-104">You can also configure an application to use WIF through classes exposed by the framework.</span></span> <span data-ttu-id="7a675-105">Diese Klassen sind in den Abschnitten aufgeführt, die die für das Schema relevanten Elemente behandeln.</span><span class="sxs-lookup"><span data-stu-id="7a675-105">These classes are noted in the sections that treat relevant elements in the schema.</span></span> <span data-ttu-id="7a675-106">Im Folgenden wird die grundlegende Struktur von XML-Tags dargestellt, die vom WIF-Konfigurationsschema verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="7a675-106">The following shows the basic XML tag structure exposed by the WIF configuration schema.</span></span> <span data-ttu-id="7a675-107">Attribute werden ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="7a675-107">Attributes are omitted.</span></span> <span data-ttu-id="7a675-108">Hervorgehobene Kommentare zeigen die Hauptkomponenten des Schemas an.</span><span class="sxs-lookup"><span data-stu-id="7a675-108">Highlighted comments indicate major components of the schema.</span></span>  
  
```xml  
<configuration>  
    <system.identityModel>  
        <!-- Service Configuration -->  
        <identityConfiguration>  
            <caches>  
                <sessionSecurityTokenCache />  
                <tokenReplayCache />  
            </caches>  
      
            <certificateValidation>  
                <certificateValidator />   
            </certificateValidation>  
      
            <claimsAuthenticationManager />  
      
            <claimsAuthorizationManager>  
                <optionalConfigurationElement>  
            </claimsAuthorizationManager>  
      
            <claimTypeRequired>  
                <claimType />   
            </claimTypeRequired>  
      
            <tokenReplayDetection />  
      
            <!-- Security Token Handler Collection Configuration -->  
            <securityTokenHandlers>  
                <add>  
                    <!-- Can take an optional configuration element which can be one of  
                         the following or a custom element -->  
                    <samlSecurityTokenHandlerRequirement>  
                        <nameClaimType>  
                        <roleClaimType>   
                    </samlSecurityTokenHandlerRequirement>  
      
                    <sessionSecurityTokenHandlerRequirement />  
                    <x509SecurityTokenHandlerRequirement />  
                    <userNameSecurityTokenHandlerRequirement />  
                </add>  
                <clear />  
                <remove />  
                <securityTokenHandlerConfiguration>  
                    <audienceUris>  
                        <add>  
                        <clear>  
                        <remove>  
                    </audienceUris>  
      
                    <caches>  
                        <sessionSecurityTokenCache />  
                        <tokenReplayCache />  
                    </caches>  
      
                    <certificateValidation>  
                        <certificateValidator>   
                    </certificateValidation>  
      
                    <issuerNameRegistry>  
                        <!-- Can take an optional configuration element which can be   
                             the <trustedIssuers> element to configure a configuration-based  
                             issuer name registry or can be a custom element -->  
                        <trustedIssuers>  
                            <add>  
                            <clear>  
                            <remove>  
                        </trustedIssuers>  
                    </issuerNameRegistry>  
      
                    <issuerTokenResolver />  
                    <serviceTokenResolver />  
                    <tokenReplayDetection />  
                </securityTokenHandlerConfiguration>  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  
      
    <system.identityModel.services>  
        <!-- Federation Authentication Configuration -->  
        <federatedAuthentication>  
            <cookieHandler>  
                <chunkedCookieHandler />  
                <customCookieHandler />  
            </cookieHandler>  
      
            <serviceCertificate>  
                <certificateReference>  
            </serviceCertificate>  
      
            <wsFederation />  
        </federatedAuthentication>  
    </system.identityModel.services>  
</configuration>  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="7a675-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7a675-109">In This Section</span></span>  

<span data-ttu-id="7a675-110">[\<system.identityModel>](system-identitymodel.md) Stellt Konfigurationen für das Aktivieren von WIF-Optionen in Anwendungen bereit.</span><span class="sxs-lookup"><span data-stu-id="7a675-110">[\<system.identityModel>](system-identitymodel.md) Provides configuration for enabling WIF options in applications.</span></span>  
  
<span data-ttu-id="7a675-111">[\<system.identityModel.services>](system-identitymodel-services.md) Stellt Konfigurationen für den passiven Verbund mit WIF bereit.</span><span class="sxs-lookup"><span data-stu-id="7a675-111">[\<system.identityModel.services>](system-identitymodel-services.md) Provides configuration for passive federation using WIF.</span></span> <span data-ttu-id="7a675-112">Konfiguriert das Sitzungsauthentifizierungsmodul (SAM) und das Verbundsauthentifizierungsmodul (WSFAM).</span><span class="sxs-lookup"><span data-stu-id="7a675-112">Configures the Session Authentication Module (SAM) and the Federated Authentication Module (WSFAM).</span></span>
