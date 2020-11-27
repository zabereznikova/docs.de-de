---
title: .NET Native-Reflektions-API-Referenz
ms.date: 03/30/2017
ms.assetid: 0429c049-22a3-4ba1-9cc8-f6ee91e31d9c
ms.openlocfilehash: 4cded310397ffa4dea057899b6f008146d35a03b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250878"
---
# <a name="net-native-reflection-api-reference"></a>.NET Native-Reflektions-API-Referenz

.Net Native enthält drei neue Ausnahme Typen: [System. Runtime. CompilerServices. missinginteropdataexception](missinginteropdataexception-class-net-native.md), [System. Reflection. MissingMetadataException](missingmetadataexception-class-net-native.md)und [System. Reflection. missingruntimeartifaktexception](missingruntimeartifactexception-class-net-native.md). Beachten Sie für alle drei Ausnahmetypen die folgenden Punkte:  
  
 Diese Typen sind nur zur internen Verwendung vorgesehen.  
 Diese drei Ausnahme Typen sind nur für die Verwendung der .net Native-Toolkette vorgesehen. Die Ausnahmen werden ausgelöst, wenn die .net Native-Toolkette fehlende Daten erkennt, die keine Fortsetzung der Programmausführung zulassen.  
  
 Diese Ausnahmen dürfen im eigenen Code nicht behandelt werden.  
 Diese Ausnahmen geben entweder an, dass von der Anwendung benötigte Metadaten fehlen (Ausnahmen [MissingInteropDataException](missinginteropdataexception-class-net-native.md) und [MissingMetadataException](missingmetadataexception-class-net-native.md) ), oder dass von der Anwendung benötigter Implementierungscode fehlt (Ausnahme [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) ). Sie beheben diese Ausnahmebedingungen, indem Sie eine Laufzeitdirektivendatei (.rd.xml) so ändern, dass die benötigten Metadaten bzw. Implementierungscodes zur Laufzeit verfügbar sind. Weitere Informationen finden Sie unter [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md). Es sind zwei Problembehandlungen verfügbar, die die entsprechenden Einträge für die Laufzeitdirektivendatei bereitstellen, mit der die [MissingMetadataException](missingmetadataexception-class-net-native.md) - und [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) -Ausnahmen beseitigt werden:  
  
- Die [MissingMetadataException-Problembehandlung](https://dotnet.github.io/native/troubleshooter/type.html) für Typen.  
  
- Die [MissingMetadataException-Problembehandlung](https://dotnet.github.io/native/troubleshooter/method.html) für Methoden.  
  
> [!NOTE]
> In diesem Verweis werden drei Ausnahme Typen dokumentiert, die für .net Native eindeutig sind. Eine Referenz Dokumentation für die .NET Framework-kernreflektionsapi finden Sie unter den <xref:System.Reflection> <xref:System.Reflection.Context> <xref:System.Reflection.Emit> Namespaces, und. Eine Referenzdokumentation für die zentrale .NET Framework-Interop-API finden Sie unter <xref:System.Runtime.InteropServices>.  
  
## <a name="systemreflection-namespace"></a>System.Reflection-Namespace  

 Der <xref:System.Reflection> -Namespace enthält die grundlegenden Typen, die für die Reflektion im .NET Framework verwendet werden. Für .net Native enthält es auch zwei neue Ausnahme Typen:  
  
|Klasse|BESCHREIBUNG|  
|-----------|-----------------|  
|[MissingMetadataException](missingmetadataexception-class-net-native.md)|Die Ausnahme, die ausgelöst wird, wenn Reflektion verwendet wird, um Metadaten abzurufen, die nicht vorhanden sind.|  
|[MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)|Die Ausnahme, die ausgelöst wird, wenn Metadaten für einen Typ oder Typmember verfügbar sind, aber dessen Implementierung entfernt wurde.|  
  
 Eine Dokumentation zu den anderen Typen in diesem Namespace finden Sie auf der <xref:System.Reflection> -Referenzseiten in der .NET Framework-Dokumentationsgruppe.  
  
## <a name="systemruntimecompilerservices-namespace"></a>System.Runtime.CompilerServices-Namespace  

 Der <xref:System.Runtime.CompilerServices> -Namespace enthält für Benutzer entworfene Typen nach Sprachcompilern. Für .net Native enthält Sie auch einen neuen Ausnahmetyp:  
  
|Klasse|BESCHREIBUNG|  
|-----------|-----------------|  
|[MissingInteropDataException](missinginteropdataexception-class-net-native.md)|Die Ausnahme, die ausgelöst wird, wenn eine manuelle Marshallingmethode aufgerufen wird, aber keine Metadaten für einen Typ durch statische Analyse oder in einer Laufzeitrichtliniendatei gefunden werden.|  
  
 Eine Dokumentation zu den anderen Typen in diesem Namespace finden Sie auf der <xref:System.Runtime.CompilerServices> -Referenzseiten in der .NET Framework-Dokumentationsgruppe.  
  
## <a name="see-also"></a>Weitere Informationen

- [MissingInteropDataException-Klasse](missinginteropdataexception-class-net-native.md)
- [MissingMetadataException-Klasse](missingmetadataexception-class-net-native.md)
- [MissingRuntimeArtifactException-Klasse](missingruntimeartifactexception-class-net-native.md)
- [Erste Schritte](getting-started-with-net-native.md)
