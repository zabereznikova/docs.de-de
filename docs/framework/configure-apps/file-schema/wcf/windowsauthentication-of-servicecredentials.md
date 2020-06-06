---
title: <windowsAuthentication> von <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: ded04f6e87fce2e12dac8f681ba2d4178f8fd204
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399114"
---
# <a name="windowsauthentication-of-servicecredentials"></a>\<windowsAuthentication> von \<serviceCredentials>
Gibt die Einstellungen der Windows-Dienstanmeldeinformationen an.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsAuthentication>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`includeWindowsGroups`|Ein optionales boolesches Attribut, das angibt, ob das System im Sicherheitskontext Windows-Gruppen enthält. Der Standardwert lautet `true`.<br /><br /> Wird dieses Attribut auf `true` festgelegt, hat dies Auswirkungen auf die Leistung, da dabei eine vollständige Gruppenerweiterung durchgeführt wird. Legen Sie dieses Attribut auf `false` fest, wenn Sie die Liste der Gruppen, zu denen ein Benutzer gehört, nicht angeben müssen.|  
|`allowAnonymousLogons`|Ein optionales boolesches Attribut, das angibt, ob anonyme, nicht authentifizierte Aufrufer zulässig sind. Der Standardwert lautet `false`.<br /><br /> Wenn das `clientCredentialType`-Attribut einer Bindung auf `Windows` festgelegt ist, sind im System keine anonymen Aufrufer zulässig. Dies bedeutet, dass nur authentifizierte Domänen- oder Arbeitsgruppenaufrufer berechtigt sind, auf das System zuzugreifen. Sie können dieses Verhalten mit diesem Attribut überschreiben.<br /><br /> Verwenden Sie daher diese Einstellung nur mit extremer Vorsicht.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Verwenden Sie dieses Element, um anzugeben, ob anonyme Windows-Benutzer Zugriff haben, indem Sie das `allowAnonymousLogons`-Attribut festlegen. Weiterhin können Sie angeben, ob Informationen zu der Gruppe, der die Benutzer angehören, in den Autorisierungskontext eingeschlossen werden, indem Sie das `includeWindowsGroups`-Attribut festlegen. Wenn das Attribut auf `true` (Standardeinstellung) festgelegt ist, kann der Dienst die Windows-Gruppen ermitteln, zu denen der Client gehört.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
