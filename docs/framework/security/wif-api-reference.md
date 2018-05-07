---
title: WIF-API-Verweis
ms.date: 03/30/2017
ms.assetid: a027d902-9314-4bfd-b172-4e81847b1d68
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: f5a38420cf5ddb0a76946d5e44e98e1f39118236
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="wif-api-reference"></a>WIF-API-Verweis
Windows Identity Foundation-Klassen (WIF) werden in folgende Assemblys unterteilt: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll) und `System.ServiceModel` (System.ServiceModel.dll). Dieses Thema enthält Links zu den WIF-Namespaces und kurze Erläuterungen zu den Klassen, die jeder Namespace enthält.  
  
> [!IMPORTANT]
>  In den folgenden `System.IdentityModel`-Namespaces sind Klassen enthalten, die das anspruchsbasierte WCF-Identitätsmodell implementieren: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType> und <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>. Beginnend mit .NET Framework 4.5: Das anspruchsbasierte WCF-Identitätsmodell wird von WIF abgelöst. Sie sollten beim Erstellen von Projektmappen auf Grundlage von WIF in diesen drei Namespaces keine Klassen verwenden.  
  
 <xref:System.IdentityModel?displayProperty=nameWithType>  
 Enthält Klassen, die Cookietransformationen, Sicherheitstokendienste und spezielle XML-Wörterbuch-Reader darstellen.  
  
 <xref:System.IdentityModel.Configuration?displayProperty=nameWithType>  
 Enthält Klassen, die Konfigurationen für Anwendungen und Dienste erstellen, die mit der Windows Identity Foundation (WIF) erstellt wurden. Die Klassen in diesem Namespace stellen Einstellungen unter dem [\<IdentityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)-Element dar.  
  
 <xref:System.IdentityModel.Metadata?displayProperty=nameWithType>  
 Enthält Klassen, die Elemente in einem Verbundmetadatendokument darstellen.  
  
 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>  
 Enthält Klassen, die WS-Trust-Elemente darstellen.  
  
 <xref:System.IdentityModel.Services?displayProperty=nameWithType>  
 Enthält Klassen, die in den passiven (WS-Verbund)-Szenarien verwendet werden. Enthält außerdem einige Klassen, die Einstellungen unter dem [\<System.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)-Element darstellen. Einstellungen unter diesem Element konfigurieren WS-Verbund für Anwendungen. Der `System.IdentityModel.Services.Configuration`-Namespace enthält die meisten Klassen, mit denen der WS-Verbund konfiguriert wird.  
  
 <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>  
 Enthält Klassen, die WIF-Anwendungen, die das WS-Verbundprotokoll verwenden, konfigurieren. Die Klassen in diesem Namespace stellen die Einstellungen unter dem [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)-Element dar. Der `System.IdentityModel.Services`-Namespace enthält auch einige Klassen, mit denen der WS-Verbund konfiguriert wird.  
  
 <xref:System.IdentityModel.Services.Tokens?displayProperty=nameWithType>  
 Enthält spezialisierte Sicherheitstokenhandler für Webfarm-Szenarios.  
  
 <xref:System.IdentityModel.Tokens?displayProperty=nameWithType>  
 Enthält Klassen, die Sicherheitstoken, Sicherheitstokenhandler und andere Sicherheitstokenartefakte darstellen.  
  
 <xref:System.Security.Claims?displayProperty=nameWithType>  
 Enthält Klassen, die Ansprüche, anspruchsbasierte Identitäten, anspruchsbasierte Prinzipale und andere anspruchsbasierte Identitätsmodellartefakte darstellen.  
  
 <xref:System.ServiceModel.Security?displayProperty=nameWithType>  
 Enthält Klassen, die WCF-Verträge, Kanäle, Diensthosts und andere Artefakte darstellen, die in aktiven (WS-Trust)-Szenarios verwendet werden. Dieser Namespace enthält außerdem Klassen, die spezifisch für Windows Communication Foundation (WCF) sind und nicht von WIF verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz zur WIF-Konfiguration](../../../docs/framework/security/wif-configuration-reference.md)  
 [Namespacezuordnung zwischen WIF 3.5 und WIF 4.5](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)
