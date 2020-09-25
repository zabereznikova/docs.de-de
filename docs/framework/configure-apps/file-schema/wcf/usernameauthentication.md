---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: 30fd78d6c56e8b22e0e744a38f18ac076dc70162
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178033"
---
# \<userNameAuthentication>

Gibt die Anmeldeinformationen eines Diensts basierend auf Benutzername und Kennwort an.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameAuthentication>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|Eine <xref:System.TimeSpan>, die angibt, wie lange ein Token maximal zwischengespeichert wird. Der Standardwert ist 00:15:00.|  
|`cacheLogonTokens`|Ein boolescher Wert, der angibt, ob Anmeldetoken zwischengespeichert werden. Der Standardwert lautet `false`.|  
|`customUserNamePasswordValidatorType`|Eine Zeichenfolge, die angibt, welche benutzerdefinierte Prüfung für Benutzername und Kennwort verwendet werden soll. Der Standardwert ist eine leere Zeichenfolge.|  
|`includeWindowsGroups`|Ein boolescher Wert, der angibt, ob Windows-Gruppen im Sicherheitskontext enthalten sind. Der Standardwert lautet `true`.<br /><br /> Wird dieses Attribut auf `true` festgelegt, hat dies Auswirkungen auf die Leistung, da dabei eine vollständige Gruppenerweiterung durchgeführt wird. Legen Sie diese Eigenschaft auf `false` fest, wenn Sie die Liste der Gruppen, zu denen ein Benutzer gehört, nicht einrichten müssen.|  
|`maxCacheLogonTokens`|Eine ganze Zahl, die die maximale Anzahl an Anmeldetoken angibt, die zwischengespeichert werden können. Dieser Wert muss größer als null sein. Der Standardwert ist 128.|  
|`membershipProviderName`|Wenn das `clientCredentialType`-Attribut einer Bindung auf `username` festgelegt ist, wird der Benutzername Windows-Konten zugewiesen. Sie können dieses Verhalten mit diesem Attribut überschreiben. Bei dem Attribut handelt es sich um eine Zeichenfolge mit dem Namen des <xref:System.Web.Security.MembershipProvider>-Werts, der den relevanten Mechanismus zur Kennwortvalidierung bereitstellt.|  
|`userNamePasswordValidationMode`|Gibt die Art und Weise an, in der der Benutzername und das Kennwort überprüft werden. Gültige Werte sind:<br /><br /> -Windows<br />-Mitgliedshipprovider<br />-Benutzer definiert<br /><br /> Der Standardwert ist Windows. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|Gibt die Anmeldeinformationen an, die beim Authentifizieren des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.|  
  
## <a name="remarks"></a>Bemerkungen  

 Wenn keine der von einem Dienst verwendeten Bindungen für die Benutzername/Kennwort-basierte Authentifizierung konfiguriert ist, werden die Attribute für dieses Element ignoriert. Dazu gehören `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` und `userNamePasswordValidationMode`.  
  
 Wenn keine der von einem Dienst verwendeten Bindungen für die Windows-Authentifizierung von Benutzername/Kennwort konfiguriert ist, werden die mit der Zwischenspeicherung von Anmeldetoken zusammenhängenden Eigenschaften ignoriert. Dazu gehören `cacheLogonTokenLifetime`, `cacheLogonTokens` und `maxCacheLogonTokens`.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
