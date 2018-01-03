---
title: .NET Native-Reflektions-API-Referenz
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0429c049-22a3-4ba1-9cc8-f6ee91e31d9c
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae0037377e9cf092888febb4d74f353ddd8234cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="net-native-reflection-api-reference"></a>.NET Native-Reflektions-API-Referenz
[!INCLUDE[net_native](../../../includes/net-native-md.md)] enthält drei neue Ausnahmetypen: [System.Runtime.CompilerServices.MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md), [System.Reflection.MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)und [System.Reflection.MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md). Beachten Sie für alle drei Ausnahmetypen die folgenden Punkte:  
  
 Diese Typen sind nur zur internen Verwendung vorgesehen.  
 Diese drei Ausnahmetypen sind für die Verwendung durch die [!INCLUDE[net_native](../../../includes/net-native-md.md)] -Toolkette gedacht. Die Ausnahmen werden ausgelöst, wenn die [!INCLUDE[net_native](../../../includes/net-native-md.md)] -Toolkette fehlende Daten erkennt, was dazu führt, dass die Ausführung des Programms nicht fortgesetzt werden kann.  
  
 Diese Ausnahmen dürfen im eigenen Code nicht behandelt werden.  
 Diese Ausnahmen geben entweder an, dass von der Anwendung benötigte Metadaten fehlen (Ausnahmen [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) und [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) ), oder dass von der Anwendung benötigter Implementierungscode fehlt (Ausnahme [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) ). Sie beheben diese Ausnahmebedingungen, indem Sie eine Laufzeitdirektivendatei (.rd.xml) so ändern, dass die benötigten Metadaten bzw. Implementierungscodes zur Laufzeit verfügbar sind. Weitere Informationen finden Sie unter [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md). Es sind zwei Problembehandlungen verfügbar, die die entsprechenden Einträge für die Laufzeitdirektivendatei bereitstellen, mit der die [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) - und [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) -Ausnahmen beseitigt werden:  
  
-   Die [MissingMetadataException-Problembehandlung](http://dotnet.github.io/native/troubleshooter/type.html) für Typen.  
  
-   Die [MissingMetadataException-Problembehandlung](http://dotnet.github.io/native/troubleshooter/method.html) für Methoden.  
  
> [!NOTE]
>  In dieser Referenz werden drei Ausnahmetypen dokumentiert, die für [!INCLUDE[net_native](../../../includes/net-native-md.md)]eindeutig sind. Eine Referenzdokumentation für die zentrale .NET Framework-Reflektions-API finden Sie unter [System.Reflection-Namespaces](http://msdn.microsoft.com/library/gg145033.aspx). Eine Referenzdokumentation für die zentrale .NET Framework-Interop-API finden Sie unter <xref:System.Runtime.InteropServices>.  
  
## <a name="systemreflection-namespace"></a>System.Reflection-Namespace  
 Der <xref:System.Reflection> -Namespace enthält die grundlegenden Typen, die für die Reflektion im .NET Framework verwendet werden. Für [!INCLUDE[net_native](../../../includes/net-native-md.md)]enthält er auch zwei neue Ausnahmetypen:  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|[MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)|Die Ausnahme, die ausgelöst wird, wenn Reflektion verwendet wird, um Metadaten abzurufen, die nicht vorhanden sind.|  
|[MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)|Die Ausnahme, die ausgelöst wird, wenn Metadaten für einen Typ oder Typmember verfügbar sind, aber dessen Implementierung entfernt wurde.|  
  
 Eine Dokumentation zu den anderen Typen in diesem Namespace finden Sie auf der <xref:System.Reflection> -Referenzseiten in der .NET Framework-Dokumentationsgruppe.  
  
## <a name="systemruntimecompilerservices-namespace"></a>System.Runtime.CompilerServices-Namespace  
 Der <xref:System.Runtime.CompilerServices> -Namespace enthält für Benutzer entworfene Typen nach Sprachcompilern. Für [!INCLUDE[net_native](../../../includes/net-native-md.md)]enthält er auch einen neuen Ausnahmetyp:  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|[MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md)|Die Ausnahme, die ausgelöst wird, wenn eine manuelle Marshallingmethode aufgerufen wird, aber keine Metadaten für einen Typ durch statische Analyse oder in einer Laufzeitrichtliniendatei gefunden werden.|  
  
 Eine Dokumentation zu den anderen Typen in diesem Namespace finden Sie auf der <xref:System.Runtime.CompilerServices> -Referenzseiten in der .NET Framework-Dokumentationsgruppe.  
  
## <a name="see-also"></a>Siehe auch  
 [MissingInteropDataException-Klasse](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md)  
 [MissingMetadataException-Klasse](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md)  
 [MissingRuntimeArtifactException-Klasse](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md)  
 [Erste Schritte](../../../docs/framework/net-native/getting-started-with-net-native.md)
