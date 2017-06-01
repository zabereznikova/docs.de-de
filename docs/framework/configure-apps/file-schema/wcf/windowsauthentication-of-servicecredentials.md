---
title: "&lt;windowsAuthentication&gt; von &lt;serviceCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;windowsAuthentication&gt; von &lt;serviceCredentials&gt;
Gibt die Einstellungen der Windows\-Dienstanmeldeinformationen an.  
  
## Syntax  
  
```  
  
<windowsAuthentication  
      allowAnonymousLogons="Boolean"  
      includeWindowsGroups="Boolean" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`includeWindowsGroups`|Ein optionales boolesches Attribut, das angibt, ob das System im Sicherheitskontext Windows\-Gruppen enthält.  Die Standardeinstellung ist `true`.<br /><br /> Wird dieses Attribut auf `true` festgelegt, hat dies Auswirkungen auf die Leistung, da dabei eine vollständige Gruppenerweiterung durchgeführt wird.  Legen Sie dieses Attribut auf `false` fest, wenn Sie die Liste der Gruppen, zu denen ein Benutzer gehört, nicht angeben müssen.|  
|`allowAnonymousLogons`|Ein optionales boolesches Attribut, das angibt, ob anonyme, nicht authentifizierte Aufrufer zulässig sind.  Die Standardeinstellung ist `false`.<br /><br /> Wenn das `clientCredentialType`\-Attribut einer Bindung auf `Windows` festgelegt ist, sind im System keine anonymen Aufrufer zulässig.  Dies bedeutet, dass nur authentifizierte Domänen\- oder Arbeitsgruppenaufrufer berechtigt sind, auf das System zuzugreifen.  Sie können dieses Verhalten mit diesem Attribut überschreiben.<br /><br /> Verwenden Sie daher diese Einstellung nur mit extremer Vorsicht.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Überprüfung der Clientanmeldeinformationen.|  
  
## Hinweise  
 Verwenden Sie dieses Element, um anzugeben, ob anonyme Windows\-Benutzer Zugriff haben, indem Sie das `allowAnonymousLogons`\-Attribut festlegen.  Weiterhin können Sie angeben, ob Informationen zu der Gruppe, der die Benutzer angehören, in den Autorisierungskontext eingeschlossen werden, indem Sie das `includeWindowsGroups`\-Attribut festlegen.  Wenn das Attribut auf `true` \(Standardeinstellung\) festgelegt ist, kann der Dienst die Windows\-Gruppen ermitteln, zu denen der Client gehört.  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.WindowsServiceElement>   
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>   
 <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>   
 <xref:System.ServiceModel.Security.WindowsServiceCredential>