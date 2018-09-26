---
title: Windows Identity Foundation-Konfigurationsschema
ms.date: 03/30/2017
ms.assetid: 4d4f6d76-49a5-4bad-b345-097b2e2844e9
author: BrucePerlerMS
ms.openlocfilehash: c081e582f4c509843c04c292ecf13b2bff2fef06
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47173134"
---
# <a name="windows-identity-foundation-configuration-schema"></a><span data-ttu-id="f364a-102">Windows Identity Foundation-Konfigurationsschema</span><span class="sxs-lookup"><span data-stu-id="f364a-102">Windows Identity Foundation Configuration Schema</span></span>
<span data-ttu-id="f364a-103">Die Themen in diesem Abschnitt enthalten Informationen über das Konfigurationsschema von Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="f364a-103">The topics in this section provide information about the Windows Identity Foundation (WIF) configuration schema.</span></span> <span data-ttu-id="f364a-104">Sie können eine Anwendung auch für die Verwendung von WIF konfigurieren, indem Sie die Klassen verwenden, die durch das Framework verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="f364a-104">You can also configure an application to use WIF through classes exposed by the framework,.</span></span> <span data-ttu-id="f364a-105">Diese Klassen sind in den Abschnitten aufgeführt, die die für das Schema relevanten Elemente behandeln.</span><span class="sxs-lookup"><span data-stu-id="f364a-105">These classes are noted in the sections that treat relevant elements in the schema.</span></span> <span data-ttu-id="f364a-106">Im Folgenden wird die grundlegende Struktur von XML-Tags dargestellt, die vom WIF-Konfigurationsschema verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="f364a-106">The following shows the basic XML tag structure exposed by the WIF configuration schema.</span></span> <span data-ttu-id="f364a-107">Attribute werden ausgelassen.</span><span class="sxs-lookup"><span data-stu-id="f364a-107">Attributes are omitted.</span></span> <span data-ttu-id="f364a-108">Hervorgehobene Kommentare zeigen die Hauptkomponenten des Schemas an.</span><span class="sxs-lookup"><span data-stu-id="f364a-108">Highlighted comments indicate major components of the schema.</span></span>  
  
```xml  
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
```  
  
## <a name="in-this-section"></a><span data-ttu-id="f364a-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f364a-109">In This Section</span></span>  
 <span data-ttu-id="f364a-110">[\<system.identityModel>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) Stellt Konfigurationen für das Aktivieren von WIF-Optionen in Anwendungen bereit.</span><span class="sxs-lookup"><span data-stu-id="f364a-110">[\<system.identityModel>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) Provides configuration for enabling WIF options in applications.</span></span>  
  
 <span data-ttu-id="f364a-111">[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) Stellt Konfigurationen für den passiven Verbund mit WIF bereit.</span><span class="sxs-lookup"><span data-stu-id="f364a-111">[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) Provides configuration for passive federation using WIF.</span></span> <span data-ttu-id="f364a-112">Konfiguriert das Sitzungsauthentifizierungsmodul (SAM) und das Verbundsauthentifizierungsmodul (WSFAM).</span><span class="sxs-lookup"><span data-stu-id="f364a-112">Configures the Session Authentication Module (SAM) and the Federated Authentication Module (WSFAM).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f364a-113">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="f364a-113">Related Sections</span></span>  
 <span data-ttu-id="f364a-114">[Configuration, Administration, And Management (Konfiguration, Administration und Verwaltung)](https://msdn.microsoft.com/library/1e03c389-de2c-4096-aaff-86b087e1bea0) Beschreibt die Konfiguration und Verwaltung von WIF-Anwendungen und -Diensten.</span><span class="sxs-lookup"><span data-stu-id="f364a-114">[Configuration, Administration, And Management](https://msdn.microsoft.com/library/1e03c389-de2c-4096-aaff-86b087e1bea0) Describes how to configure and manage WIF applications and services.</span></span>
