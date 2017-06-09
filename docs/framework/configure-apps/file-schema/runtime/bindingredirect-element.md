---
title: "&lt;bindingRedirect&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<bindingRedirect>-Element"
  - "bindingRedirect-Element"
  - "Containertags, <bindingRedirect>-Element"
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;bindingRedirect&gt;-Element
Leitet eine Assemblyversion in eine andere um.  
  
## Syntax  
  
```  
  
   <bindingRedirect    
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|`oldVersion`|Erforderliches Attribut.<br /><br /> Gibt die Assemblyversion an, die ursprünglich angefordert wurde.  Das Format einer Assemblyversionsnummer ist *major.minor.build.revision*.  Gültige Werte für jeden Abschnitt dieser Versionsnummer sind 0 bis 65535.<br /><br /> Sie können auch einen Bereich an Versionsnummern angeben, und zwar im folgenden Format:<br /><br /> *n.n.n.n \- n.n.n.n*|  
|`newVersion`|Erforderliches Attribut.<br /><br /> Gibt die Assemblyversion an, die anstelle der ursprünglich angeforderten Version verwendet werden soll. Format: *n.n.n.n*<br /><br /> Dieser Wert kann eine frühere Version als `oldVersion` angeben.|  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|Kein||  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|`assemblyBinding`|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`dependentAssembly`|Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly.  Verwenden Sie für jede Assembly ein dependentAssembly\-Element.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Wenn Sie eine .NET Framework\-Anwendung mit einer Assembly mit starkem Namen erstellen, verwendet die Anwendung zur Laufzeit standardmäßig diese Version der Assembly, selbst wenn eine neue Version verfügbar ist.  Sie können die Anwendung jedoch auch so konfigurieren, dass sie mit einer neueren Version der Assembly ausgeführt wird.  Ausführliche Informationen darüber, wie die Runtime anhand dieser Dateien die zu verwendende Assemblyversion ermittelt, finden Sie unter [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Sie können mehrere Assemblyversionen umleiten, indem Sie mehrere `bindingRedirect`\-Elemente in ein `dependentAssembly`\-Element aufnehmen.  Sie können auch von einer neueren Version zu einer früheren Version der Assembly umleiten.  
  
 Für die explizite Umleitung einer Assemblybindung in einer Anwendungskonfigurationsdatei ist eine Sicherheitsberechtigung erforderlich.  Dies betrifft die Umleitung von .NET Framework\-Assemblys und Assemblys von Drittanbietern.  Die Berechtigung wird erteilt, indem das [BindingRedirects](frlrfSystemSecurityPermissionsSecurityPermissionFlagClassTopic)\-Flag für die [SecurityPermission\-Klasse](frlrfSystemSecurityPermissionsSecurityPermissionClassTopic) festgelegt wird.  Weitere Informationen finden Sie unter [Sicherheitsberechtigung für die Umleitung der Assemblybindung](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht, wie Sie eine Assemblyversion zu einer anderen umleiten.  
  
```  
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
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Umleiten von Assemblyversionen](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)