---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 30ce69a35cfdd34e0dfea5c682347eb9187e04ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152449"
---
# <a name="x509securitytokenhandlerrequirement"></a>\<x509SecurityTokenHandlerRequirement>
Stellt eine optionale Konfiguration für die <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> Klasse oder abgeleitete Klassen bereit.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<hinzufügen>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|certificateValidationMode|Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der den Validierungsmodus angibt, der für das X.509-Zertifikat verwendet werden soll. Der Standardwert ist "PeerOrChainTrust".|  
|mapToWindows|Gibt an, ob der Tokenhandler das Validierungstoken mithilfe des eingehenden UPN-Anspruchs einem Windows-Konto zuordnen soll. Der Standardwert lautet "false".|  
|revocationMode|Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der den Sperrmodus angibt, der für das X.509-Zertifikat verwendet werden soll. Der Standardwert ist "Online".|  
|trustedStoreLocation|Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den X.509-Zertifikatspeicher angibt. Der Standardwert ist "LocalMachine".|  
|certificateValidator|Ein benutzerdefinierter Typ, <xref:System.IdentityModel.Selectors.X509CertificateValidator>der von ableitet. Wenn `certificateValidationMode` das Attribut "Custom" lautet, wird eine Instanz dieses Typs für die Validierung von Ausstellerzertifikaten verwendet.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<hinzufügen>](add.md)|Fügt der Tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.|  
  
## <a name="example"></a>Beispiel  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
