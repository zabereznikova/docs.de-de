---
title: <windowsAuthentication> von <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: f366c85f895356594cf8bd9049ca41c8fb458c4c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55280956"
---
# <a name="windowsauthentication-of-servicecredentials"></a>\<WindowsAuthentication > von \<ServiceCredentials >
Gibt die Einstellungen der Windows-Dienstanmeldeinformationen an.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceCredentials>  
\<windowsAuthentication>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`includeWindowsGroups`|Ein optionales boolesches Attribut, das angibt, ob das System im Sicherheitskontext Windows-Gruppen enthält. Die Standardeinstellung ist `true`.<br /><br /> Wird dieses Attribut auf `true` festgelegt, hat dies Auswirkungen auf die Leistung, da dabei eine vollständige Gruppenerweiterung durchgeführt wird. Legen Sie dieses Attribut auf `false` fest, wenn Sie die Liste der Gruppen, zu denen ein Benutzer gehört, nicht angeben müssen.|  
|`allowAnonymousLogons`|Ein optionales boolesches Attribut, das angibt, ob anonyme, nicht authentifizierte Aufrufer zulässig sind. Die Standardeinstellung ist `false`.<br /><br /> Wenn das `clientCredentialType`-Attribut einer Bindung auf `Windows` festgelegt ist, sind im System keine anonymen Aufrufer zulässig. Dies bedeutet, dass nur authentifizierte Domänen- oder Arbeitsgruppenaufrufer berechtigt sind, auf das System zuzugreifen. Sie können dieses Verhalten mit diesem Attribut überschreiben.<br /><br /> Verwenden Sie daher diese Einstellung nur mit extremer Vorsicht.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<serviceCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Element, um anzugeben, ob anonyme Windows-Benutzer Zugriff haben, indem Sie das `allowAnonymousLogons`-Attribut festlegen. Weiterhin können Sie angeben, ob Informationen zu der Gruppe, der die Benutzer angehören, in den Autorisierungskontext eingeschlossen werden, indem Sie das `includeWindowsGroups`-Attribut festlegen. Wenn das Attribut auf `true` (Standardeinstellung) festgelegt ist, kann der Dienst die Windows-Gruppen ermitteln, zu denen der Client gehört.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
