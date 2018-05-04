---
title: '&lt;BindingRedirect&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 08dc7a55b5b0c580f19d137496b9405fa4e18a5f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltbindingredirectgt-element"></a>&lt;BindingRedirect&gt; Element
Leitet eine Assemblyversion in eine andere um.  
  
 \<configuration>  
\<Common Language Runtime >  
\<assemblyBinding>  
\<DependentAssembly >  
\<BindingRedirect >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
   <bindingRedirect    
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`oldVersion`|Erforderliches Attribut.<br /><br /> Gibt die Assemblyversion an, die ursprünglich angefordert wurde. Das Format der Versionsnummer einer Assembly ist *"Hauptversion.Nebenversion.Build.Revision" vorliegen*. Gültige Werte für jeden Abschnitt dieser Versionsnummer sind 0 bis 65535.<br /><br /> Sie können auch einen Bereich an Versionsnummern angeben, und zwar im folgenden Format:<br /><br /> *n.n.n.n - n.n.n.n*|  
|`newVersion`|Erforderliches Attribut.<br /><br /> Gibt die Version der Assembly, die anstelle der ursprünglich angeforderten Version das Format verwenden: *n.n.n.n*<br /><br /> Dieser Wert kann eine frühere Version als `oldVersion` angeben.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|Keiner||  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`assemblyBinding`|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`dependentAssembly`|Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly. Verwenden Sie für jede Assembly ein dependentAssembly-Element.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie eine .NET Framework-Anwendung mit einer Assembly mit starkem Namen erstellen, verwendet die Anwendung zur Laufzeit standardmäßig diese Version der Assembly, selbst wenn eine neue Version verfügbar ist. Sie können die Anwendung jedoch auch so konfigurieren, dass sie mit einer neueren Version der Assembly ausgeführt wird. Weitere Informationen dazu, wie die Common Language Runtime diese Dateien verwendet, um zu bestimmen, welche Version der Assembly zu verwenden, finden Sie unter [so sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Sie können mehrere Assemblyversionen umleiten, indem Sie mehrere `bindingRedirect`-Elemente in ein `dependentAssembly`-Element aufnehmen. Sie können auch von einer neueren Version zu einer früheren Version der Assembly umleiten.  
  
 Für die explizite Umleitung einer Assemblybindung in einer Anwendungskonfigurationsdatei ist eine Sicherheitsberechtigung erforderlich. Dies betrifft die Umleitung von .NET Framework-Assemblys und Assemblys von Drittanbietern. Die Berechtigung wird erteilt, indem die <xref:System.Security.Permissions.SecurityPermissionFlag> flag für die <xref:System.Security.Permissions.SecurityPermission>. Weitere Informationen finden Sie unter [Sicherheitsberechtigung für die Umleitung der Assemblybindung](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht, wie Sie eine Assemblyversion zu einer anderen umleiten.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Umleiten von Assemblyversionen](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
