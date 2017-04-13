---
title: "&#196;nderungen der Neuzuweisungen in .NET Framework 4.5.1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8087326d-77e9-4804-ba33-ff1bb1bec2b8
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# &#196;nderungen der Neuzuweisungen in .NET Framework 4.5.1
In seltenen Fällen wirken sich Neuausrichtungsänderungen auf Apps aus, die für [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] neu kompiliert wurden. Sie wirken sich auch nicht auf Binärdateien aus, die auf eine frühere Version von .NET Framework abzielen, jedoch in Version 4.5.1 ausgeführt werden.[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] umfasst Neuausrichtungsänderungen in den folgenden Bereichen:  
  
-   [Kernspeicher](#Core)  
  
-   [ADO.NET](#ADO)  
  
-   [MSBuild](#MSBuild)  
  
 Die Spalte "Umfang" in den folgenden Tabellen gibt den Schweregrad der einzelnen Änderungen an:  
  
-   Schwerwiegend. Eine wesentliche Änderung, die viele Apps beeinflusst oder erhebliche Änderungen des Codes erforderlich macht. Beachten Sie, dass keine der Neuausrichtungsänderungen in diese Kategorie fallen.  
  
-   Gering. Eine Änderung, die entweder eine kleine Anzahl von Apps beeinflusst oder geringfügige Änderungen des Codes erforderlich macht.  
  
-   Grenzfall. Eine Änderung, die nur Apps in sehr spezifischen Szenarien beeinflusst, die nicht üblich sind.  
  
-   Transparent. Eine Änderung, die keine nennenswerten Auswirkungen hat, die Entwickler oder Benutzer beachten müssten. Die App sollte keine Änderung benötigen.  
  
<a name="Core"></a>   
## Neuausrichtungsänderungen des Kerns  
  
|Funktion|Änderung|Auswirkungen|Umfang|  
|--------------|--------------|------------------|------------|  
|<xref:System.ObsoleteAttribute?displayProperty=fullName>\-Attribut|Wenn Sie eine Windows\-Metadatenbibliothek \(WINMD\-Datei\) erstellen, wird das <xref:System.ObsoleteAttribute> als <xref:System.ObsoleteAttribute> und als [Windows.Foundation.DeprecatedAttribute](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.deprecatedattribute.aspx) exportiert.|Die Neukompilierung des vorhandenen Quellcodes, der das <xref:System.ObsoleteAttribute> verwendet, generiert möglicherweise Warnungen beim Verarbeiten des Codes in C\+\+\/CX oder JavaScript.<br /><br /> Es empfiehlt sich nicht, sowohl das <xref:System.ObsoleteAttribute> als auch das [Windows.Foundation.DeprecatedAttribute](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.deprecatedattribute.aspx) auf Code in verwalteten Assemblys anzuwenden, da dies zu Buildwarnungen führen kann.<br /><br /> Weitere Informationen finden Sie im Referenzthema <xref:System.ObsoleteAttribute>.|Rand|  
  
<a name="ADO"></a>   
## ADO.NET\-Neuausrichtungsänderungen  
  
|Funktion|Änderung|Auswirkungen|Umfang|  
|--------------|--------------|------------------|------------|  
|<xref:System.Data.Common.DbParameter?displayProperty=fullName>\-Klasse|<xref:System.Data.Common.DbParameter.Precision%2A?displayProperty=fullName> und <xref:System.Data.Common.DbParameter.Scale%2A?displayProperty=fullName> werden als öffentliche virtuelle Eigenschaften implementiert. Sie ersetzen die entsprechenden expliziten Schnittstellenimplementierungen <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision%2A?displayProperty=fullName> und <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale%2A?displayProperty=fullName>.|Die Änderung betrifft nur Entwickler, die einen ADO.NET\-Datenbankanbieter erstellen.|Rand|  
  
<a name="MSBuild"></a>   
## MSBuild\-Neuausrichtungsänderungen  
  
|Funktion|Änderung|Auswirkungen|Umfang|  
|--------------|--------------|------------------|------------|  
|`ResolveAssemblyReference`\-Aufgabe|Die Aufgabe gibt die Warnung MSB3270 aus, die angibt, dass ein Verweis oder eine seiner Abhängigkeiten nicht der Architektur der App entspricht. Dies erfolgt z. B., wenn eine App, die mit der `anycpu`\-Option kompiliert wurde, einen x86\-Verweis enthält. Ein solches Szenario kann einen App\-Fehler zur Laufzeit ergeben \(in diesem Fall, wenn die App als x64\-Prozess bereitgestellt wird\).|Es gibt zwei Bereiche mit Auswirkungen:<br /><br /> -   Bei der Neukompilierung werden Warnungen generiert, die nicht angezeigt wurden, als die App mit einer früheren Version von MSBuild kompiliert wurde. Da die Warnung eine potenzielle Quelle des Laufzeitfehlers angibt, sollte sie untersucht werden.<br />-   Wenn Warnungen wie Fehler behandelt werden, kann die Anwendung nicht kompiliert werden.|Nebenversion|  
  
## Siehe auch  
 [Änderungen zur Laufzeit](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)   
 [Anwendungskompatibilität in 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Anwendungskompatibilität in 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)