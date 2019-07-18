---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 6e8267f170dbb26381564be7b66df5f617156885
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790441"
---
# <a name="x509securitytokenhandlerrequirement"></a>\<x509SecurityTokenHandlerRequirement>
Bietet optionale Konfiguration für die <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> Klasse oder abgeleitete Klassen.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<add>  
\<x509SecurityTokenHandlerRequirement>  
  
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
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|certificateValidationMode|Ein <xref:System.ServiceModel.Security.X509CertificateValidationMode> Wert, der angibt, den Validierungsmodus für das x. 509-Zertifikat verwenden. Der Standardwert ist "PeerOrChainTrust".|  
|mapToWindows|Gibt an, ob der Tokenhandler das überprüfende Token zu einem Windows-Konto zuordnen soll, mithilfe des eingehenden UPN-Anspruchs. Der Standardwert ist "false".|  
|revocationMode|Ein <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Wert, der angibt, den Sperrmodus für das x. 509-Zertifikat verwenden. Der Standardwert lautet "Online".|  
|trustedStoreLocation|Ein <xref:System.Security.Cryptography.X509Certificates.StoreLocation> Wert, der den x. 509-Zertifikatspeicher angibt. Der Standardwert ist "LocalMachine".|  
|certificateValidator|Ein benutzerdefinierter Typ, die von abgeleitet <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Wenn die `certificateValidationMode` -Attribut ist "Custom", wird eine Instanz dieses Typs für die Überprüfung des Ausstellers Zertifikat verwendet.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Der Tokenhandler-Auflistung hinzugefügt den angegebenen Sicherheitstokenhandler.|  
  
## <a name="example"></a>Beispiel  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
