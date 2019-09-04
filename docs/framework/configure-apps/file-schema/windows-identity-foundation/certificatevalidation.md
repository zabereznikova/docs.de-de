---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: c2d1a5d36cb5616ef06eedc093dd70a68a164a81
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252134"
---
# <a name="certificatevalidation"></a>\<certificateValidation>
Steuert die Einstellungen, die von tokenhandlern zum Überprüfen von Zertifikaten verwendet werden. Diese Einstellungen werden überschrieben, wenn ein bestimmter Handler mit einem eigenen Validierungs Steuerelement konfiguriert ist.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<certifialievalidation->**  
  
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
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|certificateValidationMode|Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> -Wert, der den Validierungs Modus angibt, der für das X. 509-Zertifikat verwendet werden soll. Der Standardwert ist "Peer-ChainTrust". Wenn Sie ein benutzerdefiniertes Validierungs Steuerelement angeben möchten, legen Sie dieses Attribut auf "Custom" fest, und geben Sie das Validierungs Steuerelement mithilfe [ \<von "certifiinitievalidator" >](certificatevalidator.md) Optional.|  
|revocationMode|Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> -Wert, der den Sperrmodus angibt, der für das X. 509-Zertifikat verwendet werden soll. Der Standardwert ist "Online". Optional.|  
|trustedStoreLocation|Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> -Wert, der den X. 509-Zertifikat Speicher angibt. Der Standardwert ist "LocalMachine". Optional.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<certificateValidator>](certificatevalidator.md)|Gibt einen benutzerdefinierten Typ für die Zertifikats Überprüfung an. Dieser Typ wird nur verwendet, wenn `certificateValidationMode` das-Attribut [ \<des certifiinitievalidation->](certificatevalidation.md) -Elements auf "Custom" festgelegt ist.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Gibt Identitäts Einstellungen auf Dienst Ebene an.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Stellt die Konfiguration für eine Auflistung von Sicherheitstokenhandlern bereit.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `<certificateValidation>` -Element kann auf der Dienst Ebene unterhalb des `<identityConfiguration>` -Elements oder auf der Auflistungs Ebene des Sicherheitstokenhandlers unter dem `<securityTokenHandlerConfiguration>` -Element angegeben werden. Einstellungen für eine tokenhandlerauflistung überschreiben die für den Dienst angegebenen. Einige Tokenhandler ermöglichen es Ihnen, Zertifikat Überprüfungs Einstellungen in der Konfiguration anzugeben. Einstellungen in einzelnen tokenhandlern überschreiben die Angaben auf Dienst Ebene und in der Auflistung der Sicherheitstokenhandler.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
