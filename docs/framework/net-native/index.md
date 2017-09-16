---
title: Kompilieren von Anwendungen mit .NET Native
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
- native compilation
- .NET and native code
- compilation with .NET Native
- .NET Native
- C# and native compilation
ms.assetid: 47cd5648-9469-4b1d-804c-43cc04384045
caps.latest.revision: 27
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 76645ae43ce6754ffdf505729ec1198785a71561
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="compiling-apps-with-net-native"></a>Kompilieren von Anwendungen mit .NET Native
[!INCLUDE[net_native](../../../includes/net-native-md.md)] ist eine Vorkompilierungstechnologie für die Erstellung und Bereitstellung von Windows-Apps, die in [!INCLUDE[vs_dev14](../../../includes/vs-dev14-md.md)]enthalten ist. Die in verwaltetem Code (C# oder Visual Basic) geschriebene Releaseversion von Apps mit .NET Framework und Windows 10 als Ziel für systemeigenen Code werden automatisch kompiliert.  
  
 In der Regel werden Anwendungen, die auf .NET Framework ausgerichtet sind, in Intermediate Language (IL) kompiliert. Zur Laufzeit übersetzt ein JIT-Compiler (Just-In-Time) die IL in systemeigenen Code. Im Gegensatz dazu kompiliert [!INCLUDE[net_native](../../../includes/net-native-md.md)] Windows-Apps direkt in systemeigenen Code. Für Entwickler bedeutet das Folgendes:  
  
-   Ihre Anwendungen bieten die überragende Leistung von systemeigenem Code.  
  
-   Sie können weiterhin in C# oder Visual Basic programmieren.  
  
-   Sie können weiterhin die vom .NET Framework bereitgestellten Ressourcen nutzen, einschließlich Klassenbibliothek, automatische Speicherverwaltung und Garbage Collection sowie Ausnahmebehandlung.  
  
 Für Benutzer Ihrer Anwendungen bietet [!INCLUDE[net_native](../../../includes/net-native-md.md)] die folgenden Vorteile:  
  
-   Schnelle Ausführungszeiten  
  
-   Gleichbleibend schnelle Startzeiten  
  
-   Niedrige Kosten für Bereitstellung und Update  
  
-   Optimierte Anwendungsspeichernutzung  
  
 Aber [!INCLUDE[net_native](../../../includes/net-native-md.md)] umfasst mehr als nur eine Kompilierung in systemeigenem Code. Es ändert die Art und Weise, in der .NET Framework-Anwendungen erstellt und ausgeführt werden. Insbesondere:  
  
-   Bei der Vorkompilierung werden erforderlichen Bestandteile von .NET Framework statisch mit Ihrer App verknüpft. Dadurch kann die Anwendung mit lokalen Appbibliotheken von .NET Framework ausgeführt werden, und der Compiler kann eine globale Analyse ausführen, um Leistungszuwächse bereitzustellen. Daher starten Anwendungen konsistent schneller – sogar nach .NET Framework-Updates.  
  
-   Die [!INCLUDE[net_native](../../../includes/net-native-md.md)] -Laufzeit ist für die statische Vorkompilierung optimiert und kann somit eine bessere Leistung bieten. Gleichzeitig werden aber die zentralen Reflektionsfeatures beibehalten, die Entwickler so produktiv finden.  
  
-   [!INCLUDE[net_native](../../../includes/net-native-md.md)] verwendet das gleiche Back-End wie der C++-Compiler, der für statische Vorkompilierungsszenarios optimiert ist.  
  
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
  
-   [Erste Schritte mit der .NET Native-Codekompilierung: exemplarische Vorgehensweise für Entwickler](../../../docs/framework/net-native/getting-started-with-net-native.md)  
  
-   [.NET Native und Kompilierung:](../../../docs/framework/net-native/net-native-and-compilation.md) So kompiliert .NET Native Ihr Projekt in systemeigenen Code.  
  
-   [Reflection and .NET Native (Reflektion und .NET Native)](../../../docs/framework/net-native/reflection-and-net-native.md)  
  
    -   [APIs That Rely on Reflection (APIs, die auf Reflektion beruhen)](../../../docs/framework/net-native/apis-that-rely-on-reflection.md)  
  
    -   [Reflektions-API-Referenz](../../../docs/framework/net-native/net-native-reflection-api-reference.md)  
  
    -   [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  
  
-   [Serialization and Metadata (Serialisierung und Metadaten)](../../../docs/framework/net-native/serialization-and-metadata.md)  
  
-   [Migrating Your Windows Store App to .NET Native (Migrieren der Windows Store-App auf .NET Native)](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)  
  
-   [.NET Native General Troubleshooting (Allgemeine Problembehandlung für .NET Native)](../../../docs/framework/net-native/net-native-general-troubleshooting.md)  
  
## <a name="see-also"></a>Siehe auch  
 [.NET systemeigen – häufig gestellte Fragen](http://msdn.microsoft.com/vstudio/dn642499.aspx)

