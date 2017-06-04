---
title: "Namespacezuordnung zwischen WIF 3.5 und WIF 4.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a092d98c-444d-4336-a644-63c2e11e96c8
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# Namespacezuordnung zwischen WIF 3.5 und WIF 4.5
Ab .NET 4.5, ist Windows Identity Foundation \(WIF\) vollständig in .NET Framework integriert wurde.  Änderungen dieses taucht Integration generierte Namen und einige Konsolidierung der WIF\-Namespaces und APIs auf.  Dieses Thema stellt einige Anweisungen und eine allgemeine Zuordnung zwischen den Namespaces WIF 3.5 und den Namespaces WIF 4.5.  Es ist nicht vorgesehen, um vollständig zu sein, sondern einige allgemeine Informationen bietet darüber, wo Sie vertrauten Klassen WIF 3.5 in WIF 4.5 gefunden.  Ausführlichere Informationen über die Unterschiede zwischen WIF WIF 3.5 und 4.5, finden Sie unter [Neuerungen Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md).  Anleitungen dazu, wie Sie die Anwendungen migriert, die mit WIF WIF 3.5 bis 4.5 erstellt werden, finden Sie unter [Richtlinien für die Migration einer mit WIF 3.5 bis WIF 4.5 erstellten Anwendung](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md).  
  
## Namespace\-Zuordnung WIF WIF 3.5 bis 4.5  
 Die WIF\-Klassen, die den `Microsoft.IdentityModel`\-Namespaces in WIF 3.5 gesammelt wurden, werden jetzt unter den folgenden Namespaces verteilt: `System.Security.Claims`, `System.ServiceModel.Security` und die `System.IdentityModel`\-Namespaces in WIF 4.5.  Außerdem wurden einige Namespaces WIF 3.5 vollständig in WIF 4.5 konsolidiert oder verworfen.  
  
> [!IMPORTANT]
>  Die folgenden `System.IdentityModel`\-Namespaces enthalten Klassen, die das anspruchsbasierte Identitätsmodell WCF implementieren: <xref:System.IdentityModel.Claims?displayProperty=fullName>, <xref:System.IdentityModel.Policy?displayProperty=fullName> und <xref:System.IdentityModel.Selectors?displayProperty=fullName>.  Das anspruchsbasierte Identitätsmodell WCF wird durch WIF ersetzt.  Sie sollten Klassen in diesen drei Namespaces nicht verwenden, wenn Sie Projektmappen auf Grundlage WIF erstellen.  
  
 Die folgende Tabelle enthält Informationen zu, wenn Klassen WIF 3.5 in WIF 4.5 gefunden werden können.  
  
||||  
|-|-|-|  
|**Namespace WIF 3.5**|**Namespace WIF 4.5**|**Kommentare**|  
|`Microsoft.IdentityModel`|<xref:System.IdentityModel?displayProperty=fullName>|-   Die meisten Klassen, die Konstanten darstellen, werden nicht implementiert.<br />-   Die Klassen, die verwendet werden, um Sicherheitstokendienste erstellen, sind von `Microsoft.IdentityModel.SecurityTokenService` zu <xref:System.IdentityModel?displayProperty=fullName> verschoben.<br />-   Die Klassen in `Microsoft.IdentityModel.Threading` sind auf <xref:System.IdentityModel?displayProperty=fullName> verschoben.<br />-   Die `ExceptionMapper` und `MruSecurityTokenCache`\-Klassen werden nicht implementiert.|  
|`Microsoft.IdentityModel.Claims`|<xref:System.Security.Claims?displayProperty=fullName>|-   Die `IClaimsPrincipal` und `IClaimsIdentity`\-Schnittstellen sind in WIF 4.5 implementiert.  Stattdessen <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> und <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> ist nun die Basisklassen, von denen die meisten .NET\-Prinzipal\- und \-Identitätsklassen berechnen.  Dies bedeutet, dass keine Anforderung für spezielle Ansprüche Principal\- und Identitätsklassen wie `Microsoft.IdentityModel.Claims.WindowsClaimsPrincipal` und `Microsoft.IdentityModel.Claims.WindowsClaimsIdentity` in WIF 4.5, in der Verwendung <xref:System.Security.Principal.WindowsPrincipal?displayProperty=fullName> und in <xref:System.Security.Principal.WindowsIdentity?displayProperty=fullName> stattdessen gibt.  Das gilt auch für andere für die anderen spezialisierten Ansprüche Principal\- und die Identitätsklassen erfüllt, die in WIF 3.5 vorhanden waren.<br />-   Die `Microsoft.IdentityModel.Claims.ClaimsCollection`\-Klasse wird nicht in WIF 4.5 implementiert.  Stattdessen werden Auflistungen Ansprüche als aufzählbare Auflistungen Typ <xref:System.Security.Claims.Claim?displayProperty=fullName> verfügbar gemacht.<br />-   <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> und <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> stellen Methoden, die LINQ unterstützen jetzt vollständig.|  
|`Microsoft.IdentityModel.Configuration`|<xref:System.IdentityModel.Configuration?displayProperty=fullName>|Einige Elemente und Klassen verfügen Namensänderungen unterzogen und einige sind in WIF 4.5 abgelegt wurde; beispielsweise `Microsoft.IdentityModel.Configuraiton.ServiceConfiguration` ist jetzt <xref:System.IdentityModel.Configuration.IdentityConfiguration?displayProperty=fullName>.|  
|`Microsoft.IdentityModel.Protocols`|<xref:System.IdentityModel.Services?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Protocols.WSFederation`|<xref:System.IdentityModel.Services?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Protocols.WSFederation.Metadata`|<xref:System.IdentityModel.Metadata?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Protocols.WSIdentity`|Implementiert nicht in WIF 4.5|In WIF 3.5 enthält Klassen, um CardSpace zu unterstützen, implementiert nicht in WIF 4.5.|  
|`Microsoft.IdentityModel.Protocols.WSTrust`|Unterteilung zwischen <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName> und den <xref:System.ServiceModel.Security?displayProperty=fullName>\-Namespaces.|Klassen, das WS\-Trust\-Artefakte darstellt, sind im \- Namespace; <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName> beispielsweise die <xref:System.IdentityModel.Protocols.WSTrust.RequestSecurityToken>\-Klasse.  Klassen, die WCF\-Dienstverträge, \-Diensthosts und \-Channel darstellen, die einen WCF\-Dienst aktivieren, um mithilfe des WS\-Trust\-Protokolls zu kommunizieren, sind im \- Namespace; <xref:System.ServiceModel.Security?displayProperty=fullName> beispielsweise die <xref:System.ServiceModel.Security.WSTrustServiceHost>\-Klasse.|  
|`Microsoft.IdentityModel.Protocols.WSTrust.Bindings`|Implementiert nicht in WIF 4.5|\-|  
|`Microsoft.IdentityModel.Protocols.XmlEncryption`|Implementiert nicht in WIF 4.5|Eingeschlossene Klassen, die XML\-Verschlüsselungskonstanten in WIF 3.5 darstellen.  Diese Konstanten werden nicht in WIF 4.5 implementiert.|  
|`Microsoft.IdentityModel.Protocols.XmlSignature`|<xref:System.IdentityModel?displayProperty=fullName>|Die `EnvelopingSignature`\-Klasse und Klassen, die Konstanten darstellen, werden nicht implementiert.|  
|`Microsoft.IdentityModel.SecurityTokenService`|Unterteilung zwischen <xref:System.IdentityModel?displayProperty=fullName>, <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName> und <xref:System.IdentityModel.Tokens?displayProperty=fullName>\-Namespaces.|\-|  
|`Microsoft.IdentityModel.Threading`|<xref:System.IdentityModel?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Tokens`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Tokens.Saml11`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Tokens.Saml2`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Web`|<xref:System.IdentityModel.Services?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Web.Configuration`|<xref:System.IdentityModel.Services.Configuration?displayProperty=fullName>|Klassen, die Konfiguration für passive \(WS\-Verbund\-\) Szenarien bereitstellen, sind hauptsächlich auf <xref:System.IdentityModel.Services.Configuration?displayProperty=fullName> verschoben wurde; sind jedoch einige dieser Klassen in <xref:System.IdentityModel.Services?displayProperty=fullName>.|  
|`Microsoft.IdentityModel.Web.Controls`|Implementiert nicht in WIF 4.5|Die Klassen in `Microsoft.IdentityModel.Web.Controls` implementierten das Verbunde passive Anmeldungs\-Steuerelement, das nicht in WIF 4.5 vorhanden ist.|  
|`Microsoft.IdentityModel.WindowsTokenService`|Implementiert nicht in WIF 4.5|\-|  
  
## Siehe auch  
 [Neuerungen Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md)   
 [Richtlinien für die Migration einer mit WIF 3.5 bis WIF 4.5 erstellten Anwendung](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md)