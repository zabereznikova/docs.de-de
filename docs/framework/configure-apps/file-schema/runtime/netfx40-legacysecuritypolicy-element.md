---
title: "&lt;NetFx40_LegacySecurityPolicy&gt;-Element | Microsoft Docs"
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
  - "<NetFx40_LegacySecurityPolicy>-Element"
  - "NetFx40_LegacySecurityPolicy-Element"
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# &lt;NetFx40_LegacySecurityPolicy&gt;-Element
Gibt an, ob die Laufzeit Legacyrichtlinien für die Codezugriffssicherheit \(CAS, Code Access Security\) verwendet.  
  
## Syntax  
  
```  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Laufzeit Legacyrichtlinien für die Codezugriffssicherheit \(CAS\) verwendet.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`false`|Die Laufzeit verwendet keine Legacyrichtlinien für die Codezugriffssicherheit \(CAS\).  Dies ist der Standardwert.|  
|`true`|Die Laufzeit verwendet Legacyrichtlinien für die Codezugriffssicherheit \(CAS\).|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## Hinweise  
 In .NET Framework 3.5 und älteren Versionen ist die CAS\-Richtlinie immer aktiv.  In [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] muss die CAS\-Richtlinie aktiviert werden.  
  
 Die CAS\-Richtlinie ist versionsspezifisch.  Benutzerdefinierte CAS\-Richtlinien, die in früheren Versionen von .NET Framework vorhanden sind, müssen in [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] erneut angegeben werden.  
  
 Anwenden des `<NetFx40_LegacySecurityPolicy>`\-Element auf eine [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]\-Assembly wirkt sich nicht auf [sicherheitstransparenten Code](../../../../../docs/framework/misc/security-transparent-code.md) aus; die Transparenzregeln gelten weiterhin.  
  
> [!IMPORTANT]
>  Anwenden des `<NetFx40_LegacySecurityPolicy>`\-Elements kann zu bedeutenden Leistungseinbußen für systemeigene Image\-Assemblys führen, die vom [systemeigenen Image\-Generator \(Ngen.exe\)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) erstellt wurden und nicht im [globalen Assemblycache](../../../../../docs/framework/app-domains/gac.md) installiert sind.  Der Leistungsabfall wird von der Unfähigkeit der Laufzeit verursacht, die Assemblys als systemeigene Images zu laden, wenn das Attribut übernommen wird, was dazu führt, dass sie als Just\-In\-Time\-Assemblys geladen werden.  
  
> [!NOTE]
>  Wenn Sie in den Projekteinstellungen für das Visual Studio\-Projekt eine Ziel\-.NET Framework\-Version angeben, die älter als [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] ist, wird CAS\-Richtlinie aktiviert, einschließlich aller benutzerdefinierten CAS\-Richtlinien, die Sie für diese Version angegeben haben.  Sie können jedoch keine neuen [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]\-Typen und \-Member verwenden.  Sie können eine frühere Version von .NET Framework angeben, indem Sie [\<supportedRuntime\>\-Element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) im Starteinstellungsschema in der [Anwendungskonfigurationsdatei](../../../../../docs/framework/configure-apps/index.md) verwenden.  
  
> [!NOTE]
>  In der Syntax von Konfigurationsdateien wird Groß\- und Kleinschreibung berücksichtigt.  Verwenden Sie die Syntax wie in den Abschnitten Syntax und Beispiel angegeben.  
  
## Konfigurationsdatei  
 Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie das Legacyverhalten für die Codezugriffssicherheit \(CAS\) für eine Anwendung aktiviert wird.  
  
```  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)