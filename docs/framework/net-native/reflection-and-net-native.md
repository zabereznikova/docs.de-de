---
title: Reflektion und .NET Native
ms.date: 03/30/2017
ms.assetid: 91c9eae4-c641-476c-a06e-d7ce39709763
ms.openlocfilehash: c38070ec4afe0a7311133e0ef7b5b24eb2fe4fb5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287838"
---
# <a name="reflection-and-net-native"></a>Reflektion und .NET Native

Die verwaltete Entwicklung in .NET Framework unterstützt Metaprogrammierung durch die Reflektions-API. Durch Reflektion können Sie Objekte in einer App überprüfen, Methoden für bei der Überprüfung ermittelte Objekte aufrufen und neue Typen zur Laufzeit generieren. Außerdem werden viele weitere Szenarien mit dynamischem Code unterstützt. Zudem werden die Serialisierung und Deserialisierung unterstützt, wodurch die Feldwerte eines Objekts beibehalten und später wiederhergestellt werden können. All diese Szenarien erfordern den .NET Framework Just-In-Time-Compiler (JIT) zur Generierung von nativem Code basierend auf verfügbaren Metadaten.  
  
 Die .net Native Runtime enthält keinen JIT-Compiler. Daher muss sämtlicher notwendiger systemeigener Code vorab generiert werden. Eine Reihe von Heuristiken wird verwendet, um zu bestimmen, welcher Code generiert werden soll, aber diese Heuristiken können nicht alle möglichen Metaprogrammierungsszenarien abdecken.  Daher müssen Sie mit [Laufzeitanweisungen](runtime-directives-rd-xml-configuration-file-reference.md) Hinweise für diese Metaprogrammierungsszenarios bereitstellen. Wenn die erforderlichen Metadaten oder der Implementierungscode nicht zur Laufzeit verfügbar sind, wird durch die App [MissingMetadataException](missingmetadataexception-class-net-native.md), [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) oder[MissingInteropDataException](missinginteropdataexception-class-net-native.md) ausgelöst. Es sind zwei Problembehandlungen verfügbar, die den entsprechenden Eintrag für die Laufzeitdirektivendatei zur Beseitigung der Ausnahme generieren:  
  
- Die [MissingMetadataException-Problembehandlung](https://dotnet.github.io/native/troubleshooter/type.html) für Typen.  
  
- Die [MissingMetadataException-Problembehandlung](https://dotnet.github.io/native/troubleshooter/method.html) für Methoden.  
  
> [!NOTE]
> Eine Übersicht über den .NET Native-Kompilierungsprozess mit Hintergrundinformationen, die verdeutlichen, warum eine Laufzeitdirektivendatei erforderlich ist, finden Sie unter [.NET Native und Kompilierung](net-native-and-compilation.md).  
  
 Darüber hinaus können .net Native nicht über private Member der .NET Framework-Klassenbibliothek reflektieren. Beispielsweise gibt ein Aufruf der <xref:System.Reflection.TypeInfo.DeclaredFields%2A?displayProperty=nameWithType>-Eigenschaft zum Abrufen der Felder einer .NET Framework-Klassenbibliothek nur öffentliche oder geschützte Felder zurück.  
  
 Die folgenden Themen enthalten die konzeptionelle Dokumentation und die Referenzdokumentation, die Sie benötigen, um Reflektion und Serialisierung in Ihren Apps zu unterstützen:  
  
- [APIs, die auf Refelktion beruhen](apis-that-rely-on-reflection.md)  
  
- [Reflektions-API-Referenz](net-native-reflection-api-reference.md)  
  
- [Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz](runtime-directives-rd-xml-configuration-file-reference.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Kompilieren von Apps mit .NET Native](index.md)
- [.NET Native und Kompilierung](net-native-and-compilation.md)
