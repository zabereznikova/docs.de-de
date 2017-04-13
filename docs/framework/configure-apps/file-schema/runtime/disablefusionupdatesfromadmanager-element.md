---
title: "&lt;disableFusionUpdatesFromADManager&gt;-Element | Microsoft Docs"
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
  - "<disableFusionUpdatesFromADManager>-Element"
  - "disableFusionUpdatesFromADManager-Element"
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;disableFusionUpdatesFromADManager&gt;-Element
Gibt an, ob das Standardverhalten, also das Überschreiben der Konfigurationseinstellungen für eine Anwendungsdomäne durch den Laufzeithost deaktiviert ist.  
  
## Syntax  
  
```  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob die Standardeinstellung, also das Überschreiben der Fusion\-Einstellungen, deaktiviert ist.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|0|Möglichkeit zum Überschreiben der Fusion\-Einstellungen nicht deaktivieren.  Dies ist das Standardverhalten ab [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
|1|Möglichkeit zum Überschreiben der Fusion\-Einstellungen deaktivieren.  Dies stellt das Verhalten früherer Versionen von .NET Framework wieder her.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## Hinweise  
 Seit [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] besteht das Standardverhalten darin, dass Konfigurationseinstellungen in der Unterklasse von <xref:System.AppDomainManager> vom <xref:System.AppDomainManager>\-Objekt überschrieben werden können, indem die <xref:System.AppDomainSetup.ConfigurationFile%2A>\-Eigenschaft oder die <xref:System.AppDomainSetup.SetConfigurationBytes%2A>\-Methode des <xref:System.AppDomainSetup>\-Objekts verwendet wird, das an die Implementierung der <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=fullName>\-Methode übergeben wird.  In der Standardanwendungsdomäne überschreiben die geänderten Einstellungen die Einstellungen, die von der Anwendungskonfigurationsdatei angegeben wurden.  In anderen Anwendungsdomänen werden die Konfigurationseinstellungen überschrieben, die an die <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=fullName>\-Methode oder an die <xref:System.AppDomain.CreateDomain%2A?displayProperty=fullName>\-Methode übergeben wurden.  
  
 Sie können entweder neue Konfigurationsinformationen oder NULL \(`Nothing` in Visual Basic\) übergeben, um übergebene Konfigurationsinformationen auszuschließen.  
  
 Übergeben Sie Konfigurationsinformationen nicht sowohl an die <xref:System.AppDomainSetup.ConfigurationFile%2A>\-Eigenschaft als auch an die <xref:System.AppDomainSetup.SetConfigurationBytes%2A>\-Methode.  Andernfalls werden die Informationen ignoriert, die an die <xref:System.AppDomainSetup.ConfigurationFile%2A>\-Eigenschaft übergeben werden, da Konfigurationsinformationen aus der Anwendungskonfigurationsdatei von der <xref:System.AppDomainSetup.SetConfigurationBytes%2A>\-Methode überschrieben werden.  Wenn Sie die <xref:System.AppDomainSetup.ConfigurationFile%2A>\-Eigenschaft verwenden, können Sie NULL \(`Nothing` in Visual Basic\) an die <xref:System.AppDomainSetup.SetConfigurationBytes%2A>\-Methode übergeben, um Konfigurationsbytes auszuschließen, die im Aufruf der <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=fullName>\-Methode oder <xref:System.AppDomain.CreateDomain%2A?displayProperty=fullName>\-Methode angegeben wurden.  
  
 Neben den Konfigurationsinformationen können Sie folgende Einstellungen im <xref:System.AppDomainSetup>\-Objekt ändern, das an die Implementierung der <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=fullName>\-Methode übergeben wird: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> und <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.  
  
 Als Alternative zur Verwendung des `<disableFusionUpdatesFromADManager>`\-Elements können Sie das Standardverhalten deaktivieren, indem Sie eine Registrierungseinstellung erstellen oder eine Umgebungsvariable festlegen.  Erstellen Sie in der Registrierung einen DWORD\-Wert mit Namen `COMPLUS_disableFusionUpdatesFromADManager` unter `HKCU\Software\Microsoft\.NETFramework` oder `HKLM\Software\Microsoft\.NETFramework`, und legen Sie den Wert auf 1 fest.  Legen Sie in der Befehlszeile die `COMPLUS_disableFusionUpdatesFromADManager`\-Umgebungsvariable auf 1 fest.  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie die Möglichkeit zum Überschreiben der Fusion\-Einstellungen mit dem `<disableFusionUpdatesFromADManager>`\-Element deaktiviert wird.  
  
```  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)