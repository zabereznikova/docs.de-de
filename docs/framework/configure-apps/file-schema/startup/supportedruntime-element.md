---
title: "&lt;supportedRuntime&gt;-Element | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<supportedRuntime>-Element"
  - "supportedRuntime-Element"
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
caps.latest.revision: 33
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 28
---
# &lt;supportedRuntime&gt;-Element
Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden. Dieses Element sollte von allen Anwendungen verwendet werden, die mit Version 1.1 oder höher von .NET Framework erstellt wurden.  
  
 [\<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<startup\>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)  
  
 **\<supportedRuntime\>**  
  
## Syntax  
  
```  
  
<supportedRuntime version="runtime version" sku="sku id"/>  
```  
  
## Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|**Version**|Optionales Attribut.<br /><br /> Ein Zeichenfolgenwert, der die Version der Common Language Runtime \(CLR\) angibt, die diese Anwendung unterstützt. Gültige Werte des `version`\-Attributs finden Sie im Abschnitt [„runtime version“-Werte](#version). **Note:**  Durch das .NET Framework 3.5 nimmt der Wert „*Laufzeitversion*“ die Form *Hauptversion*.*Nebenversion*.*Buildnummer* an. Beginnend mit [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] sind nur die Haupt\- und Nebenversionsnummern erforderlich \(d. h. "v4.0" anstelle von "v4.0.30319"\). Die kürzere Zeichenfolge wird empfohlen.|  
|**sku**|Optionales Attribut.<br /><br /> Ein Zeichenfolgenwert, der die SKU \(Stock Keeping Unit\) angibt, die wiederum angibt, welche .NET Framework\-Version von dieser Anwendung unterstützt wird.<br /><br /> Beginnend mit .NET Framework 4.0 wird die Verwendung des `sku`\-Attributs empfohlen.  Wenn vorhanden, gibt es die Version des .NET Frameworks an, auf die die App aufgerichtet ist.<br /><br /> Gültige Werte des sku\-Attributs finden Sie im Abschnitt ["sku id"-Werte](#sku).|  
  
## Hinweise  
 Wenn das **\<supportedRuntime\>**\-Element nicht in der Anwendungskonfigurationsdatei vorhanden ist, wird die Version der Laufzeit verwendet, die zum Erstellen der Anwendung verwendet wurde.  
  
 Das **\<supportedRuntime\>**\-Element sollte von allen Anwendungen verwendet werden, die mit Version 1.1 oder einer höheren Version der Laufzeit erstellt wurden. Anwendungen, die nur Version 1.0 der Laufzeit unterstützen, müssen das [\<requiredRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)\-Element verwenden.  
  
> [!NOTE]
>  Wenn Sie die Konfigurationsdatei mithilfe der [CorBindToRuntimeByCfg](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)\-Funktion angeben, müssen Sie das `<requiredRuntime>`\-Element für alle Versionen der Laufzeit verwenden. Das `<supportedRuntime>`\-Element wird ignoriert, wenn Sie [CorBindToRuntimeByCfg](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) verwenden.  
  
 Bei Apps, die Versionen der Laufzeit aus .NET Framework 1.1 bis 3.5 unterstützen, sollte, wenn mehrere Versionen der Laufzeit unterstützt werden, das erste Element die bevorzugte Version der Laufzeit angeben, und das letzte die am wenigsten bevorzugte Version. Bei Apps, die .NET Framework 4.0 oder höhere Versionen unterstützen, gibt das `version`\-Attribut die CLR\-Version an, die für .NET Framework 4 und höhere Versionen gängig ist, und das `sku`\-Attribut gibt die einzelne .NET Framework\-Version an, auf die die App ausgerichtet ist.  
  
> [!NOTE]
>  Wenn Ihre Anwendung Legacy\-Aktivierungspfade verwendet, z. B. die [CorBindToRuntimeEx\-Funktion](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), und Sie möchten, dass diese Pfade Version 4 der CLR anstelle von einer früheren Version aktivieren, oder wenn Ihre Anwendung mit [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] erstellt wurde, aber eine Abhängigkeit auf eine gemischte Assembly hat, die mit einer früheren Version von .NET Framework erstellt wurde, ist es nicht ausreichend, [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] in der Liste der unterstützten Laufzeiten angeben. Außerdem müssen Sie in der Konfigurationsdatei im [\<startup\>\-Element](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) das `useLegacyV2RuntimeActivationPolicy`\-Attribut auf `true` festlegen. Wenn jedoch dieses Attribut auf `true` festgelegt ist, werden alle Komponenten, die mit früheren Versionen von .NET Framework erstellt wurden, mit [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] ausgeführt statt den Laufzeiten, mit denen sie erstellt wurden.  
  
 Es wird empfohlen, dass Sie die Anwendungen mit allen .NET Framework\-Versionen testen, in denen sie ausgeführt werden können.  
  
<a name="version"></a>   
## „runtime version“\-Werte  
 In der folgenden Tabelle sind gültige Werte für den *runtime version*\-Wert des `version`\-Attributs aufgeführt.  
  
|.NET Framework\-Version|`version`\-Attribut|  
|-----------------------------|-------------------------|  
|1,0|"v1.0.3705"|  
|1,1|"v1.1.4322"|  
|2,0|"v2.0.50727"|  
|3,0|"v2.0.50727"|  
|3,5|"v2.0.50727"|  
|4.0|"v4.0"|  
|4.5|"v4.0"|  
|4.5.1|"v4.0"|  
|4.5.2|"v4.0"|  
|4.6|"v4.0"|  
|4.6.1|"v4.0"|  
  
<a name="sku"></a>   
## "sku id"\-Werte  
 Die folgende Tabelle führt die Versionen von .NET Framework auf, beginnend mit .NET Framework 4, die vom `sku`\-Attribut unterstützt werden.  Beachten Sie, dass, das `sku`\-Attribut, beginnend mit .NET Framework 4, die Version des .NET Frameworks angibt, auf die die App aufgerichtet ist.  
  
|.NET Framework\-Version|`sku`\-Attribut|  
|-----------------------------|---------------------|  
|4.0|".NETFramework,Version\=v4.0"|  
|4.0, Clientprofil|".NETFramework,Version\=v4.0,Profile\=Client"|  
|4.0, Plattformupdate 1|.NETFramework, Version\=v4.0.1|  
|4.0, Clientprofil, Update 1|.NETFramework, Version\=v4.0.1, Profile\=Client|  
|4.0, Plattformupdate 2|.NETFramework, Version\=v4.0.2|  
|4.0, Clientprofil, Update 2|.NETFramework, Version\=v4.0.2, Profile\=Client|  
|4.0, Plattformupdate 3|.NETFramework, Version\=v4.0.3|  
|4.0, Clientprofil, Update 3|.NETFramework, Version\=v4.0.3, Profile\=Client|  
|4.5|".NETFramework,Version\=v4.5"|  
|4.5.1|".NETFramework,Version\=v4.5.1"|  
|4.5.2|".NETFramework,Version\=v4.5.2"|  
|4.6|".NETFramework,Version\=v4.6"|  
|4.6.1|".NETFramework,Version\=v4.6.1"|  
  
 In der folgenden Tabelle wird dargestellt, unter welchen installierten Versionen von .NET Framework 4.0 eine Anwendung ausgeführt werden kann, für verschiedene Werte des `sku`\-Attributs, wenn das `version`\-Attribut „v4.0“ ist und das `sku`\-Attribut das .NET Framework 4 oder eins seiner Plattformupdates \(PU\) angibt.  
  
|Wert des `sku`\-Attributs|4.0 Client|4.0 Full|4.0 Client \+ PU 1|4.0 Voll \+ PU 1|4.0 Client \+ PU 2|4.0 Full \+ PU 2|4.0 Client \+ PU 3|4.0 Full \+ PU 3|4.5 und höher|  
|-------------------------------|----------------|--------------|------------------------|----------------------|------------------------|----------------------|------------------------|----------------------|-------------------|  
|.NETFramework, Version\=v4.0, Profile\=Client|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|  
|.NETFramework, Version\=v4.0||Ja||Ja||Ja||Ja|Ja|  
|.NETFramework, Version\=v4.0.1, Profile\=Client|||Ja|Ja|Ja|Ja|Ja|Ja|Ja|  
|.NETFramework, Version\=v4.0.1||||Ja||Ja||Ja|Ja|  
|.NETFramework, Version\=v4.0.2, Profile\=Client|||||Ja|Ja|Ja|Ja|Ja|  
|.NETFramework, Version\=v4.0.2||||||Ja||Ja|Ja|  
|.NETFramework, Version\=v4.0.3, Profile\=Client|||||||Ja|Ja|Ja|  
|.NETFramework, Version\=v4.0.3||||||||Ja|Ja|  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht, wie Sie die unterstützte Laufzeitversion in einer Konfigurationsdatei angeben. Die Konfigurationsdatei gibt an, dass die App auf .NET Framework 4.6 ausgerichtet ist.  
  
```xml  
  
<configuration> <startup> <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" /> </startup> </configuration>  
  
```  
  
## Konfigurationsdatei  
 Dieses Element kann in der Anwendungskonfigurationsdatei verwendet werden.  
  
## Siehe auch  
 [Schema für Starteinstellungen](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> Festlegen der zu verwendenden Laufzeitversion](http://msdn.microsoft.com/de-de/c376208d-980d-42b4-865b-fbe0d9cc97c2)   
 [Prozessinterne parallele Ausführung](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)