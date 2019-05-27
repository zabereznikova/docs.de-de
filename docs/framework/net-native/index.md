---
title: Kompilieren von Anwendungen mit .NET Native
ms.date: 03/30/2017
helpviewer_keywords:
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28b09bf07d831747be0006ffe1f1d8c5ac5171ce
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052644"
---
# <a name="compiling-apps-with-net-native"></a>Kompilieren von Anwendungen mit .NET Native
.NET native ist eine vorkompilierungstechnologie für die Erstellung und Bereitstellung von Windows-apps, die mit Visual Studio 2015 und späteren Versionen enthalten ist. Die in verwaltetem Code (C# oder Visual Basic) geschriebene Releaseversion von Apps mit .NET Framework und Windows 10 als Ziel für systemeigenen Code werden automatisch kompiliert.  
  
 In der Regel werden Anwendungen, die auf .NET Framework ausgerichtet sind, in Intermediate Language (IL) kompiliert. Zur Laufzeit übersetzt ein JIT-Compiler (Just-In-Time) die IL in systemeigenen Code. Im Gegensatz dazu kompiliert .NET Native Windows-apps direkt in systemeigenen Code. Für Entwickler bedeutet das Folgendes:  
  
- Ihre apps bieten die Leistungsfähigkeit von systemeigenem Code. In der Regel werden besser als Code, die zuerst in der IL kompiliert und dann vom JIT-Compiler in nativen Code kompiliert wird. 
  
- Sie können weiterhin in C# oder Visual Basic programmieren.  
  
- Sie können weiterhin die vom .NET Framework bereitgestellten Ressourcen nutzen, einschließlich Klassenbibliothek, automatische Speicherverwaltung und Garbage Collection sowie Ausnahmebehandlung.  
  
 Für Benutzer Ihrer Anwendungen bietet .NET Native folgende Vorteile:  
  
- Für die Mehrzahl der App- und szenariotypen, schnellere Ausführungszeiten.
  
- Für die Mehrzahl der App- und szenariotypen, schnellere Startzeiten. 
  
- Niedrige Kosten für Bereitstellung und Aktualisierung.  
  
- Optimierte anwendungsspeichernutzung.  

> [!IMPORTANT]
> Für die überwiegende Mehrheit der App- und szenariotypen bietet .NET Native, deutlich schnellere Startzeiten und eine bessere Leistung im Vergleich zu einer app, die kompilierte IL oder ein NGEN-Image. Allerdings können die Ergebnisse variieren. Um sicherzustellen, dass Ihre app über die leistungsverbesserungen von .NET Native profitiert hat, sollten Sie die Leistung, der ohne .NET Native-Version Ihrer App vergleichen. Weitere Informationen finden Sie unter [Übersicht über Leistungssitzungen](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).
 
Aber .NET Native umfasst mehr als nur eine Kompilierung in systemeigenem Code. Es ändert die Art und Weise, in der .NET Framework-Anwendungen erstellt und ausgeführt werden. Insbesondere:  
  
- Bei der Vorkompilierung werden erforderlichen Bestandteile von .NET Framework statisch mit Ihrer App verknüpft. Dadurch kann die Anwendung mit lokalen Appbibliotheken von .NET Framework ausgeführt werden, und der Compiler kann eine globale Analyse ausführen, um Leistungszuwächse bereitzustellen. Daher starten Anwendungen konsistent schneller – sogar nach .NET Framework-Updates.  
  
- Die .NET Native-Runtime ist für die statische Vorkompilierung optimiert und bietet eine bessere Leistung in der Mehrzahl der Fälle. Gleichzeitig werden aber die zentralen Reflektionsfeatures beibehalten, die Entwickler so produktiv finden.  
  
- .NET native verwendet das gleiche Back-End als die C++ -Compiler, die für statische vorkompilierungsszenarios optimiert ist.  
  
 .NET native kann die Leistungsvorteile bringen C++ an verwalteten Entwickler code, da sie die gleichen oder ähnliche Tools als verwendet C++ in die Hintergründe, wie in dieser Tabelle gezeigt.  
  
||.NET systemeigen|C++|  
|-|----------------------------------------------------------------|-----------|  
|Bibliotheken|.NET Framework + Windows-Runtime|Win32 + Windows-Runtime|  
|Compiler|UTC-Optimierungscompiler|UTC-Optimierungscompiler|  
|Bereitgestellt|Sofort ausführbare Binärdateien|Sofort ausführbare Binärdateien (ASM)|  
|Laufzeit|MRT.dll (minimale CLR-Laufzeit)|CRT.dll (C-Laufzeit)|  
  
 Für Windows-Apps für Windows 10 laden Sie Binärdateien für die Kompilierung von systemeigenem .NET-Code in App-Paketen (APPX-Dateien) in den Windows Store hoch.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 Weitere Informationen zum Entwickeln von Anwendungen mit der .NET Native-Codekompilierung finden Sie in den folgenden Themen:  
  
- [Erste Schritte mit .NET Native-Codekompilierung: Die exemplarische Vorgehensweise für Entwickler](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
- [.NET Native und Kompilierung:](../../../docs/framework/net-native/net-native-and-compilation.md) Wie .NET Native Ihr Projekt in systemeigenen Code kompiliert.  
  
- [Reflection and .NET Native (Reflektion und .NET Native)](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    - [APIs That Rely on Reflection (APIs, die die Reflektion benötigen)](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    - [Reflektions-API-Referenz](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    - [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
- [Serialization and Metadata (Serialisierung und Metadaten)](../../../docs/framework/net-native/serialization-and-metadata.md)  
  
- [Migrating Your Windows Store App to .NET Native (Migrieren der Windows Store-App auf .NET Native)](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)  
  
- [.NET Native General Troubleshooting (Allgemeine Problembehandlung für .NET Native)](../../../docs/framework/net-native/net-native-general-troubleshooting.md)
