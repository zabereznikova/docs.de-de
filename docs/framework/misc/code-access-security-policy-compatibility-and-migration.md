---
title: "Code Access Security Policy Compatibility and Migration | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
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
  - "policy migration, compatibility"
  - "CLR poliicy migration"
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Code Access Security Policy Compatibility and Migration
Der Richtlinienteil für Codezugriffssicherheit \(CAS\) ist seit [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] veraltet.  Als Ergebnis treten ggf. Kompilierungswarnungen Laufzeitausnahmen auf, wenn Sie die veralteten Richtlinientypen und Elemente [explizit](#explicit_use) oder [implizit](#implicit_use) \(durch andere Typen oder Elemente\) aufrufen.  
  
 Sie können die Warnungen und Fehler folgendermaßen vermeiden:  
  
-   [Migrieren](#migration) in die [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]\-Ersetzungen für die veralteten Aufrufe.  
  
     \- oder \-  
  
-   Verwenden des [\< NetFx40\_LegacySecurityPolicy\>\-Konfigurationselements](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md), um das CAS\-Legacyrichtlinienverhalten zu nutzen.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Explizite Verwendung](#explicit_use)  
  
-   [Implizite Verwendung](#implicit_use)  
  
-   [Fehler und Warnungen](#errors_and_warnings)  
  
-   [Migration: Ersatz für veraltete Aufrufe](#migration)  
  
-   [Kompatibilität: Verwenden der CAS\-Legacyrichtlinienoption](#compatibility)  
  
> [!CAUTION]
>  Codezugriffssicherheit und teilweise vertrauenswürdiger Code  
>   
>  .NET Framework bietet einen Mechanismus namens Codezugriffssicherheit \(Code Access Security, CAS\) zur Erzwingung verschiedener Vertrauensebenen für anderen Code, der in der gleichen Anwendung ausgeführt wird.  Sie sollten die Codezugriffssicherheit in .NET Framework nicht als Sicherheitsbegrenzung bei teilweise vertrauenswürdigem Code verwenden. Dies gilt insbesondere für Code unbekannter Herkunft.  Wir raten davon ab, Code unbekannter Herkunft zu laden und auszuführen, ohne alternative Sicherheitsmaßnahmen zu treffen.  
>   
>  Diese Richtlinie gilt für alle Versionen von .NET Framework mit Ausnahme der in Silverlight enthaltenen .NET Framework\-Version.  
  
<a name="explicit_use"></a>   
## Explizite Verwendung  
 Elemente, die die Sicherheitsrichtlinie direkt bearbeiten oder die CAS\-Richtlinie für den Sandkasten benötigen, sind veraltet und generieren standardmäßig Fehler.  
  
 Beispiele:  
  
-   <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=fullName>  
  
-   <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=fullName>  
  
<a name="implicit_use"></a>   
## Implizite Verwendung  
 Mehrere Überladungen beim Laden einer Assembly generieren Fehler aufgrund ihrer impliziten Verwendung der CAS\-Richtlinie.  Diese Überladungen nehmen einen Parameter <xref:System.Security.Policy.Evidence> an, der verwendet wird, um die CAS\-Richtlinie aufzulösen und einen Berechtigungssatz für eine Assembly bereitzustellen.  
  
 Im Folgenden finden Sie einige Beispiele.  Die veralteten Überladungen sind die Überladungen, die <xref:System.Security.Policy.Evidence> als Parameter annehmen:  
  
-   <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=fullName>  
  
<a name="errors_and_warnings"></a>   
## Fehler und Warnungen  
 Die veralteten Typen und Elemente generieren die folgenden Fehlermeldungen, wenn sie verwendet werden.  Beachten Sie, dass der Typ <xref:System.Security.Policy.Evidence?displayProperty=fullName> selbst nicht veraltet ist.  
  
 Warnung zur Kompilierzeit:  
  
 `warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework.  Please use <suggested alternate API>.  See <link> for more information.'`  
  
 Laufzeitausnahme:  
  
 <xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`  
  
<a name="migration"></a>   
## Migration: Ersatz für veraltete Aufrufe  
  
### Bestimmen der Vertrauensebene einer Assembly  
 Die CAS\-Richtlinie wird häufig verwendet, um den Berechtigungssatz einer Assembly oder Anwendungsdomäne oder die Vertrauensebene zu bestimmen.  Die [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] stellt die folgenden nützlichen Eigenschaften bereit, die keine Sicherheitsrichtlinie auflösen müssen:  
  
-   <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=fullName>  
  
-   <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.PermissionSet%2A?displayProperty=fullName>  
  
-   <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=fullName>  
  
### Sandkasten für Anwendungsdomänen  
 Die Methode <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=fullName> wird in der Regel verwendet, um Assemblys in einer Anwendungsdomäne in einem Sandkasten auszuführen.  Die [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] stellt Elemente bereit, die zu diesem Zweck nicht verwenden <xref:System.Security.Policy.PolicyLevel> verwenden müssen. Weitere Informationen finden Sie unter [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).  
  
### Bestimmen eines sicheren oder geeigneten Berechtigungssatzes für teilweise vertrauenswürdigen Code  
 Hosts müssen häufig die Berechtigungen ermitteln, die für das Ausführen von gehostetem Code in einem Sandkasten geeignet sind.  Zuvor hat die CAS\-Richtlinie von [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] diese Möglichkeit über die Methode <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=fullName> bereitgestellt.  Als Ersatz bietet [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] die Methode <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=fullName>, die einen sicheren Standardberechtigungssatz für die bereitgestellten Beweisinformationen zurückgibt.  
  
### Szenarien ohne Sandkasten: Überladungen für das Laden von Assemblys  
 Der Grund für die Verwendung einer Überladung für das Laden einer Assembly kann die Verwendung von Parametern sein, die andernfalls nicht verfügbar sind, anstatt die Assembly in einem Sandkastens auszuführen.  Ab [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] ermöglichen Überladungen für das Laden einer  Assembly, die kein <xref:System.Security.Policy.Evidence?displayProperty=fullName>\-Objekt als Parameter benötigen \(z. B. [AppDomain.ExecuteAssembly\(String, String\[\], Byte\<xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=fullName>\) dieses Szenario.  
  
 Wenn Sie einen Sandkasten für eine Assembly verwenden möchten, verwenden Sie die [AppDomain.CreateDomain\(String, Evidence, AppDomainSetup, PermissionSet, StrongName\<xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=fullName>\-Überladung.  
  
<a name="compatibility"></a>   
## Kompatibilität: Verwenden der CAS\-Legacyrichtlinienoption  
 Mit dem [\< NetFx40\_LegacySecurityPolicy\>\-Konfigurationselements](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) können Sie angeben, dass ein Prozess oder eine Bibliothek eine CAS\-Legacyrichtlinie verwendet.  Wenn Sie dieses Element aktivieren, funktionieren die Richtlinien\- und Beweisüberladungen wie in früheren Versionen des Frameworks.  
  
> [!NOTE]
>  Das CAS\-Richtlinienverhalten wird auf der Grundlage einer Laufzeitversion angegeben. Das Ändern der CAS\-Richtlinie für eine Laufzeitversion besitzt daher keine Auswirkungen auf die CAS\-Richtlinie einer anderen Version.  
  
```  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)