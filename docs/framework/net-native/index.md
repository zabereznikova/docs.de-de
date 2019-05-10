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
ms.openlocfilehash: c3c845cefad451c608f5c095e4941c3368dc9975
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650546"
---
# <a name="compiling-apps-with-net-native"></a>Kompilieren von Anwendungen mit .NET Native
[!INCLUDE[net_native](../../../includes/net-native-md.md)] ist eine vorkompilierungstechnologie für die Erstellung und Bereitstellung von Windows-apps, die mit Visual Studio 2015 und späteren Versionen enthalten ist. Die in verwaltetem Code (C# oder Visual Basic) geschriebene Releaseversion von Apps mit .NET Framework und Windows 10 als Ziel für systemeigenen Code werden automatisch kompiliert.  
  
 In der Regel werden Anwendungen, die auf .NET Framework ausgerichtet sind, in Intermediate Language (IL) kompiliert. Zur Laufzeit übersetzt ein JIT-Compiler (Just-In-Time) die IL in systemeigenen Code. Im Gegensatz dazu kompiliert [!INCLUDE[net_native](../../../includes/net-native-md.md)] Windows-Apps direkt in systemeigenen Code. Für Entwickler bedeutet das Folgendes:  
  
- Ihre apps bieten die Leistungsfähigkeit von systemeigenem Code. In der Regel werden besser als Code, die zuerst in der IL kompiliert und dann vom JIT-Compiler in nativen Code kompiliert wird. 
  
- Sie können weiterhin in C# oder Visual Basic programmieren.  
  
- Sie können weiterhin die vom .NET Framework bereitgestellten Ressourcen nutzen, einschließlich Klassenbibliothek, automatische Speicherverwaltung und Garbage Collection sowie Ausnahmebehandlung.  
  
 Für Benutzer Ihrer Anwendungen bietet [!INCLUDE[net_native](../../../includes/net-native-md.md)] die folgenden Vorteile:  
  
- Für die Mehrzahl der App- und szenariotypen, schnellere Ausführungszeiten.
  
- Für die Mehrzahl der App- und szenariotypen, schnellere Startzeiten. 
  
- Niedrige Kosten für Bereitstellung und Aktualisierung.  
  
- Optimierte anwendungsspeichernutzung.  

> [!IMPORTANT]
> Für die überwiegende Mehrheit der App- und szenariotypen bietet .NET Native, deutlich schnellere Startzeiten und eine bessere Leistung im Vergleich zu einer app, die kompilierte IL oder ein NGEN-Image. Allerdings können die Ergebnisse variieren. Um sicherzustellen, dass Ihre app über die leistungsverbesserungen von .NET Native profitiert hat, sollten Sie die Leistung, der ohne .NET Native-Version Ihrer App vergleichen. Weitere Informationen finden Sie unter [Übersicht über Leistungssitzungen](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).
 
Aber [!INCLUDE[net_native](../../../includes/net-native-md.md)] umfasst mehr als nur eine Kompilierung in systemeigenem Code. Es ändert die Art und Weise, in der .NET Framework-Anwendungen erstellt und ausgeführt werden. Insbesondere:  
  
- Bei der Vorkompilierung werden erforderlichen Bestandteile von .NET Framework statisch mit Ihrer App verknüpft. Dadurch kann die Anwendung mit lokalen Appbibliotheken von .NET Framework ausgeführt werden, und der Compiler kann eine globale Analyse ausführen, um Leistungszuwächse bereitzustellen. Daher starten Anwendungen konsistent schneller – sogar nach .NET Framework-Updates.  
  
- Die [!INCLUDE[net_native](../../../includes/net-native-md.md)] Runtime ist für die statische Vorkompilierung optimiert und bietet eine bessere Leistung in der Mehrzahl der Fälle. Gleichzeitig werden aber die zentralen Reflektionsfeatures beibehalten, die Entwickler so produktiv finden.  
  
- [!INCLUDE[net_native](../../../includes/net-native-md.md)] verwendet das gleiche Back-End wie der C++-Compiler, der für statische Vorkompilierungsszenarios optimiert ist.  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] kann die Leistungsvorteile von C++ auf Entwickler von verwaltetem Code übertragen, da im Endeffekt die gleichen oder ähnliche Tools wie für C++ verwendet werden, wie in dieser Tabelle gezeigt wird.  
  
||[!INCLUDE[net_native](../../../includes/net-native-md.md)]|C++|  
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
