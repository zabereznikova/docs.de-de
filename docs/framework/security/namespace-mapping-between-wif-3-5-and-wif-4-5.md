---
title: Namespacezuordnung zwischen WIF 3.5 und WIF 4.5
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a092d98c-444d-4336-a644-63c2e11e96c8
caps.latest.revision: 4
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9c3d726ee5b6da733ddaa79ec23943bb6faa43e5
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="namespace-mapping-between-wif-35-and-wif-45"></a>Namespacezuordnung zwischen WIF 3.5 und WIF 4.5
Ab .NET 4.5 wurde Windows Identity Foundation (WIF) vollständig in das .NET Framework integriert. Durch diese Integration sind Namensänderungen und einige Konsolidierungen der WIF-Namespaces und der API-Oberfläche entstanden. Diese Thema enthält Empfehlungen und eine allgemeine Zuordnung zwischen den WIF 3.5-Namespaces und den WIF 4.5-Namespaces. Es hat keinen Anspruch auf Vollständigkeit, sondern stellt einige allgemeine Informationen darüber bereit, wo bekannte WIF 3.5-Klassen in WIF 4.5 zu finden sind. Ausführliche Informationen zu den Unterschieden zwischen WIF 3.5 und WIF 4.5 finden Sie unter [What's New in Windows Identity Foundation 4.5 (Neuerungen in Windows Identity Foundation 4.5)](../../../docs/framework/security/whats-new-in-wif.md). Empfehlungen zum Migrieren einer mithilfe von WIF 3.5 erstellten Anwendung zu WIF 4.5 finden Sie unter [Guidelines for Migrating an Application Built Using WIF 3.5 to WIF 4.5 (Richtlinien zum Migrieren einer mithilfe von WIF 3.5 erstellten Anwendung zu WIF 4.5)](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md).  
  
## <a name="wif-35-to-wif-45-namespace-map"></a>Namespace-Zuordnung WIF 3.5 zu WIF 4.5  
 Die WIF-Klassen, die unter den `Microsoft.IdentityModel`-Namespaces in WIF 3.5 gesammelt wurden, werden nun auf die folgenden Namespaces aufgeteilt: `System.Security.Claims`, `System.ServiceModel.Security` und die `System.IdentityModel`-Namespaces in WIF 4.5. Darüber hinaus wurden einige WIF 3.5-Namespaces in WIF 4.5 konsolidiert oder ganz verworfen.  
  
> [!IMPORTANT]
>  In den folgenden `System.IdentityModel`-Namespaces sind Klassen enthalten, die das anspruchsbasierte WCF-Identitätsmodell implementieren: <xref:System.IdentityModel.Claims?displayProperty=fullName>, <xref:System.IdentityModel.Policy?displayProperty=fullName> und <xref:System.IdentityModel.Selectors?displayProperty=fullName>. Das anspruchsbasierte WCF-Identitätsmodell wird von WIF abgelöst. Sie sollten beim Erstellen von Projektmappen auf Grundlage von WIF in diesen drei Namespaces keine Klassen verwenden.  
  
 Die folgende Tabelle enthält Informationen dazu, wo WIF 3.5-Klassen in WIF 4.5 gefunden werden können.  
  
|**WIF 3.5-Namespace**|**WIF 4.5-Namespace**|**Kommentare**|  
|-|-|-|  
|`Microsoft.IdentityModel`|<xref:System.IdentityModel?displayProperty=fullName>|– Die meisten Klassen, die Konstanten darstellen, werden nicht implementiert.<br />– Die Klassen, die zum Erstellen eines Sicherheitstokendiensts verwendet werden, wurden von `Microsoft.IdentityModel.SecurityTokenService` nach <xref:System.IdentityModel?displayProperty=fullName> verschoben.<br />– Die Klassen in `Microsoft.IdentityModel.Threading` wurden nach <xref:System.IdentityModel?displayProperty=fullName> verschoben.<br />– Die Klassen `ExceptionMapper` und `MruSecurityTokenCache` werden nicht implementiert.|  
|`Microsoft.IdentityModel.Claims`|<xref:System.Security.Claims?displayProperty=fullName>|– Die Schnittstellen `IClaimsPrincipal` und `IClaimsIdentity` werden in WIF 4.5 nicht implementiert. Stattdessen sind <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> und <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> nun die Basisklassen, aus denen die meisten .NET-Prinzipal- und -Identitätsklassen abgeleitet werden. Daher werden keine speziellen Anspruchsprinzipal- und Identitätsklassen wie `Microsoft.IdentityModel.Claims.WindowsClaimsPrincipal` und `Microsoft.IdentityModel.Claims.WindowsClaimsIdentity` mehr in WIF 4.5 benötigt; verwenden Sie stattdessen <xref:System.Security.Principal.WindowsPrincipal?displayProperty=fullName> und <xref:System.Security.Principal.WindowsIdentity?displayProperty=fullName>. Dasselbe gilt auch für die anderen speziellen Anspruchsprinzipal- und Identitätsklassen, die in WIF 3.5 vorhanden waren.<br />– Die `Microsoft.IdentityModel.Claims.ClaimsCollection`-Klasse wird in WIF 4.5 nicht implementiert. Stattdessen werden Auflistungen von Ansprüchen als aufzählbare Auflistung des Typs <xref:System.Security.Claims.Claim?displayProperty=fullName> offen gelegt.<br />-   <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> und <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> bieten Methoden, die LINQ jetzt vollständig unterstützen.|  
|`Microsoft.IdentityModel.Configuration`|<xref:System.IdentityModel.Configuration?displayProperty=fullName>|Einige Elemente und Klassen wurden einigen Änderungen unterzogen und einige wurden komplett aus WIF 4.5 entfernt. `Microsoft.IdentityModel.Configuraiton.ServiceConfiguration` ist jetzt z.B <xref:System.IdentityModel.Configuration.IdentityConfiguration?displayProperty=fullName>.|  
|`Microsoft.IdentityModel.Protocols`|<xref:System.IdentityModel.Services?displayProperty=fullName>|-|  
|`Microsoft.IdentityModel.Protocols.WSFederation`|<xref:System.IdentityModel.Services?displayProperty=fullName>|-|  
|`Microsoft.IdentityModel.Protocols.WSFederation.Metadata`|<xref:System.IdentityModel.Metadata?displayProperty=fullName>|-|  
|`Microsoft.IdentityModel.Protocols.WSIdentity`|In WIF 4.5 nicht implementiert.|In WIF 3.5 enthaltene Klassen zur Unterstützung von CardSpace, in WIF 4.5 nicht implementiert.|  
|`Microsoft.IdentityModel.Protocols.WSTrust`|Aufgeteilt auf die <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName>- und <xref:System.ServiceModel.Security?displayProperty=fullName>-Namespaces.|Klassen, die WS-Trust-Artefakte darstellen, sind im Namespace <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName>, z.B. die <xref:System.IdentityModel.Protocols.WSTrust.RequestSecurityToken>-Klasse. Klassen, die WCF-Dienstverträge, -Diensthosts und Kanäle darstellen, die einem WCF-Dienst ermöglichen, mithilfe des WS-Trust-Protokolls zu kommunizieren, sind im Namespace <xref:System.ServiceModel.Security?displayProperty=fullName>, z.B. die <xref:System.ServiceModel.Security.WSTrustServiceHost>-Klasse.|  
|`Microsoft.IdentityModel.Protocols.WSTrust.Bindings`|In WIF 4.5 nicht implementiert.|-|  
|`Microsoft.IdentityModel.Protocols.XmlEncryption`|In WIF 4.5 nicht implementiert.|Enthielt Klassen, die XML-Verschlüsselungskonstanten in WIF 3.5 darstellen. Diese Konstanten sind in WIF 4.5 nicht implementiert.|  
|`Microsoft.IdentityModel.Protocols.XmlSignature`|<xref:System.IdentityModel?displayProperty=fullName>|Die `EnvelopingSignature`-Klasse und Klassen, die Konstanten darstellen, werden nicht implementiert.|  
|`Microsoft.IdentityModel.SecurityTokenService`|Aufgeteilt auf die <xref:System.IdentityModel?displayProperty=fullName>-, <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName>- und <xref:System.IdentityModel.Tokens?displayProperty=fullName>-Namespaces.|-|  
|`Microsoft.IdentityModel.Threading`|<xref:System.IdentityModel?displayProperty=fullName>|-|  
|`Microsoft.IdentityModel.Tokens`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|-|  
|`Microsoft.IdentityModel.Tokens.Saml11`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|-|  
|`Microsoft.IdentityModel.Tokens.Saml2`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|-|  
|`Microsoft.IdentityModel.Web`|<xref:System.IdentityModel.Services?displayProperty=fullName>|-|  
|`Microsoft.IdentityModel.Web.Configuration`|<xref:System.IdentityModel.Services.Configuration?displayProperty=fullName>|Klassen, die die Konfiguration für passive (WS-Verbund-)Szenarios bereitstellen, wurden überwiegend in <xref:System.IdentityModel.Services.Configuration?displayProperty=fullName> verschoben; jedoch sind einige dieser Klassen in <xref:System.IdentityModel.Services?displayProperty=fullName>.|  
|`Microsoft.IdentityModel.Web.Controls`|In WIF 4.5 nicht implementiert.|Die Klassen in `Microsoft.IdentityModel.Web.Controls` haben das Steuerelement FederatedPassiveSignIn implementiert, das in WIF 4.5 nicht existiert.|  
|`Microsoft.IdentityModel.WindowsTokenService`|In WIF 4.5 nicht implementiert.|-|  
  
## <a name="see-also"></a>Siehe auch  
 [What's New in Windows Identity Foundation 4.5 (Neuerungen in Windows Identity Foundation 4.5)](../../../docs/framework/security/whats-new-in-wif.md)   
 [Richtlinien für die Migration einer mit WIF 3.5 bis WIF 4.5 erstellten Anwendung](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md)

