---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 3f3d79d3567c1714a79423b7767ce3f454b9d52d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152787"
---
# <a name="certificatevalidator"></a>\<CertificateValidator>
Gibt einen benutzerdefinierten Typ für die Zertifikatvalidierung an. Dieser Typ wird nur `certificateValidationMode` verwendet, wenn das Attribut des [ \<certificateValidation>-Elements](certificatevalidation.md) auf "Custom" festgelegt ist.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<CertificateValidator>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|type|Gibt einen benutzerdefinierten Typ an, <xref:System.IdentityModel.Selectors.X509CertificateValidator> der von der Klasse abstammt. Legen `certificateValidationMode` Sie das Attribut des [ \<certificateValidation>-Elements](certificatevalidation.md) auf "Custom" fest, um diesen Typ zu verwenden. Weitere Informationen zum Angeben `type` des Attributs finden Sie unter [Benutzerdefinierte Typreferenzen](../windows-workflow-foundation/index.md). Optional.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<certificateValidation>](certificatevalidation.md)|Steuert die Einstellungen, die Tokenhandler zum Überprüfen von Zertifikaten verwenden.|  
  
## <a name="example"></a>Beispiel  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```
