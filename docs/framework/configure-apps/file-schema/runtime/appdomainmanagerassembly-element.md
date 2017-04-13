---
title: "&lt;appDomainManagerAssembly&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<appDomainManagerAssembly>-Element"
  - "appDomainManagerAssembly-Element"
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;appDomainManagerAssembly&gt;-Element
Gibt die Assembly an, die den Anwendungsdomänen\-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.  
  
## Syntax  
  
```  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`value`|Erforderliches Attribut.  Gibt den Anzeigenamen der Assembly an, die den Anwendungsdomänen\-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Um den Typ des Anwendungsdomänen\-Managers anzugeben, müssen Sie dieses Element und das [\<appDomainManagerType\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)\-Element angeben.  Wenn eines dieser Elemente nicht angegeben wird, wird das andere ignoriert.  
  
 Wenn die Standardanwendungsdomäne geladen wird, wird <xref:System.TypeLoadException> ausgelöst, falls die angegebene Assembly nicht vorhanden ist, oder nicht den Typ enthält, der vom [\<appDomainManagerType\>](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)\-Element angegeben wird; und der Prozess nicht gestartet.  Wenn die Assembly gefunden wird, die Versionsinformationen jedoch nicht übereinstimmen, wird eine <xref:System.IO.FileLoadException> ausgelöst.  
  
 Wenn Sie den Typ des Anwendungsdomänen\-Managers für die Standardanwendungsdomäne angeben, erben andere Anwendungsdomänen, die aus der Standardanwendungsdomäne erstellt wurden, den Typ des Anwendungsdomänen\-Managers.  Verwenden Sie die <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=fullName>\-Eigenschaft und die <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=fullName>\-Eigenschaft, um für eine neue Anwendungsdomäne einen anderen Anwendungsdomänen\-Managertyp anzugeben.  
  
 Um den Anwendungsdomänen\-Managertyp anzugeben, ist vollständige Vertrauenswürdigkeit für die Anwendung erforderlich. \(Eine Anwendung, die auf dem Desktop ausgeführt wird, hat beispielsweise vollständige Vertrauenswürdigkeit.\) Wenn die Anwendung keine vollständige Vertrauenswürdigkeit hat, wird eine <xref:System.TypeLoadException> ausgelöst.  
  
 Informationen zum Format des Anzeigenamens der Assembly finden Sie unter der <xref:System.Reflection.Assembly.FullName%2A?displayProperty=fullName>\-Eigenschaft.  
  
 Dieses Konfigurationselement ist erst ab [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] verfügbar.  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie angegeben werden kann, dass der `MyMgr`\-Typ in der `AdMgrExample`\-Assembly als Anwendungsdomänen\-Manager für die Standardanwendungsdomäne eines Prozesses verwendet wird.  
  
```  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=fullName>   
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=fullName>   
 [\<appDomainManagerType\>\-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)   
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [SetAppDomainManagerType\-Methode](../Topic/ICLRControl::SetAppDomainManagerType%20Method.md)