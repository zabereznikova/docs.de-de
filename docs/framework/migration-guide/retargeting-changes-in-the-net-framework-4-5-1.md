---
title: "Änderungen der Neuzuweisungen in .NET Framework 4.5.1 | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- retargeting changes
- .NET Framework 4.5.1
- retargeting changes, .NET Framework 4.5.1
- retargeting changes, .NET Framework
ms.assetid: 8087326d-77e9-4804-ba33-ff1bb1bec2b8
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0c497561254c0f97f22ac05c7d44224b30ef74d0
ms.lasthandoff: 04/18/2017

---
# <a name="retargeting-changes-in-the-net-framework-451"></a>Änderungen der Neuzuweisungen in .NET Framework 4.5.1
In seltenen Fällen wirken sich Neuausrichtungsänderungen auf Apps aus, die für [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] neu kompiliert wurden. Sie wirken sich auch nicht auf Binärdateien aus, die auf eine frühere Version von .NET Framework abzielen, jedoch in Version 4.5.1 ausgeführt werden. [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] umfasst Neuausrichtungsänderungen in den folgenden Bereichen:  
  
-   [Kernspeicher](#Core)  
  
-   [ADO.NET](#ADO)  
  
-   [MSBuild](#MSBuild)  
  
 Die Spalte "Umfang" in den folgenden Tabellen gibt den Schweregrad der einzelnen Änderungen an:  
  
-   Schwerwiegend. Eine wesentliche Änderung, die viele Apps beeinflusst oder erhebliche Änderungen des Codes erforderlich macht. Beachten Sie, dass keine der Neuausrichtungsänderungen in diese Kategorie fallen.  
  
-   Gering. Eine Änderung, die entweder eine kleine Anzahl von Apps beeinflusst oder geringfügige Änderungen des Codes erforderlich macht.  
  
-   Grenzfall. Eine Änderung, die nur Apps in sehr spezifischen Szenarien beeinflusst, die nicht üblich sind.  
  
-   Transparent. Eine Änderung, die keine nennenswerten Auswirkungen hat, die Entwickler oder Benutzer beachten müssten. Die App sollte keine Änderung benötigen.  
  
<a name="Core"></a>   
## <a name="core-retargeting-changes"></a>Neuausrichtungsänderungen des Kerns  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.ObsoleteAttribute?displayProperty=fullName>-Attribut|Wenn Sie eine Windows-Metadatenbibliothek (WINMD-Datei) erstellen, wird das <xref:System.ObsoleteAttribute>-Attribut sowohl als <xref:System.ObsoleteAttribute> als auch als [Windows.Foundation.DeprecatedAttribute](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.deprecatedattribute.aspx) exportiert.|Die Neukompilierung des vorhandenen Quellcodes, der das <xref:System.ObsoleteAttribute>-Attribut verwendet, generiert möglicherweise Warnungen beim Verarbeiten des Codes in C++/CX oder JavaScript.<br /><br /> Sowohl für das <xref:System.ObsoleteAttribute>-Attribut als auch das [Windows.Foundation.DeprecatedAttribute](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.deprecatedattribute.aspx) ist die Anwendung auf Code in verwalteten Assemblys nicht zu empfehlen, da dies zu Buildwarnungen führen kann.<br /><br /> Weitere Informationen finden Sie unter dem Referenzthema <xref:System.ObsoleteAttribute>.|Kante|  
  
<a name="ADO"></a>   
## <a name="adonet-retargeting-changes"></a>ADO.NET-Neuausrichtungsänderungen  
  
|Funktion|Änderung|Auswirkungen|Bereich|  
|-------------|------------|------------|-----------|  
|<xref:System.Data.Common.DbParameter?displayProperty=fullName>-Klasse|<xref:System.Data.Common.DbParameter.Precision%2A?displayProperty=fullName> und <xref:System.Data.Common.DbParameter.Scale%2A?displayProperty=fullName> sind als öffentliche virtuelle Eigenschaften implementiert. Sie ersetzen die entsprechenden expliziten Schnittstellenimplementierungen, <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision%2A?displayProperty=fullName> und <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale%2A?displayProperty=fullName>.|Die Änderung betrifft nur Entwickler, die einen ADO.NET-Datenbankanbieter erstellen.|Rand|  
  
<a name="MSBuild"></a>   
## <a name="msbuild-retargeting-changes"></a>MSBuild-Neuausrichtungsänderungen  
  
|Funktion|Änderung|Auswirkungen|Umfang|  
|-------------|------------|------------|-----------|  
|`ResolveAssemblyReference`-Aufgabe|Die Aufgabe gibt die Warnung MSB3270 aus, die angibt, dass ein Verweis oder eine seiner Abhängigkeiten nicht der Architektur der App entspricht. Dies erfolgt z. B., wenn eine App, die mit der `anycpu`-Option kompiliert wurde, einen x86-Verweis enthält. Ein solches Szenario kann einen App-Fehler zur Laufzeit ergeben (in diesem Fall, wenn die App als x64-Prozess bereitgestellt wird).|Es gibt zwei Bereiche mit Auswirkungen:<br /><br /> – Bei der Neukompilierung werden Warnungen generiert, die nicht angezeigt wurden, als die App mit einer früheren Version von MSBuild kompiliert wurde. Da die Warnung eine potenzielle Quelle des Laufzeitfehlers angibt, sollte sie untersucht werden.<br />– Wenn Warnungen als Fehler behandelt werden, kann die Anwendung nicht kompiliert werden.|Gering|  
  
## <a name="see-also"></a>Siehe auch  
 [Änderungen zur Laufzeit](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)   
 [Anwendungskompatibilität in 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Anwendungskompatibilität in 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)
