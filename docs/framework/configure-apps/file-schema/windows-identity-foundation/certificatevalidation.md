---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: c2d1a5d36cb5616ef06eedc093dd70a68a164a81
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252134"
---
# \<certificateValidation>
Steuert die Einstellungen, die von tokenhandlern zum Überprüfen von Zertifikaten verwendet werden. Diese Einstellungen werden überschrieben, wenn ein bestimmter Handler mit einem eigenen Validierungs Steuerelement konfiguriert ist.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|certificateValidationMode|Ein- <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der den Validierungs Modus angibt, der für das X. 509-Zertifikat verwendet werden soll. Der Standardwert ist "Peer-ChainTrust". Um ein benutzerdefiniertes Validierungs Steuerelement anzugeben, legen Sie dieses Attribut auf "Custom" fest, und geben Sie das Validierungs Steuerelement mithilfe des- [\<certificateValidator>](certificatevalidator.md) Elements an (Optional)|  
|revocationMode|Ein- <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der den Sperrmodus angibt, der für das X. 509-Zertifikat verwendet werden soll. Der Standardwert ist "Online". (Optional)|  
|trustedStoreLocation|Ein- <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den X. 509-Zertifikat Speicher angibt. Der Standardwert ist "LocalMachine". (Optional)|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<certificateValidator>](certificatevalidator.md)|Gibt einen benutzerdefinierten Typ für die Zertifikats Überprüfung an. Dieser Typ wird nur verwendet, wenn das- `certificateValidationMode` Attribut des- [\<certificateValidation>](certificatevalidation.md) Elements auf "Custom" festgelegt ist.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Gibt Identitäts Einstellungen auf Dienst Ebene an.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.|  
  
## <a name="remarks"></a>Bemerkungen  
 Ein- `<certificateValidation>` Element kann auf der Dienst Ebene unterhalb des- `<identityConfiguration>` Elements oder auf der Auflistungs Ebene des Sicherheitstokenhandlers unter dem-Element angegeben werden `<securityTokenHandlerConfiguration>` . Einstellungen für eine tokenhandlerauflistung überschreiben die für den Dienst angegebenen. Einige Tokenhandler ermöglichen es Ihnen, Zertifikat Überprüfungs Einstellungen in der Konfiguration anzugeben. Einstellungen in einzelnen tokenhandlern überschreiben die Angaben auf Dienst Ebene und in der Auflistung der Sicherheitstokenhandler.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
