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
ms.openlocfilehash: 5993cfdb0f50d8e474a4f18280d181d9ec2fdfa4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049656"
---
# <a name="compiling-apps-with-net-native"></a>Kompilieren von Anwendungen mit .NET Native

.Net Native ist eine vorkompilierungs Technologie zum entwickeln und Bereitstellen von Windows-apps, die in Visual Studio 2015 und höheren Versionen enthalten sind. Die in verwaltetem Code (C# oder Visual Basic) geschriebene Releaseversion von Apps mit .NET Framework und Windows 10 als Ziel für systemeigenen Code werden automatisch kompiliert.

In der Regel werden Anwendungen, die auf .NET Framework ausgerichtet sind, in Intermediate Language (IL) kompiliert. Zur Laufzeit übersetzt ein JIT-Compiler (Just-In-Time) die IL in systemeigenen Code. Im Gegensatz dazu werden von .net Native Windows-apps direkt in systemeigenen Code kompiliert. Für Entwickler bedeutet das Folgendes:

- Ihre apps verfügen über die Leistung von System eigenem Code. In der Regel ist die Leistung für Code, der zuerst in IL kompiliert und dann vom JIT-Compiler in systemeigenen Code kompiliert wird, übergeordneter.

- Sie können weiterhin in C# oder Visual Basic programmieren.

- Sie können weiterhin die vom .NET Framework bereitgestellten Ressourcen nutzen, einschließlich Klassenbibliothek, automatische Speicherverwaltung und Garbage Collection sowie Ausnahmebehandlung.

Für Benutzer Ihrer Apps bietet .net Native folgende Vorteile:

- Schnellere Ausführungszeiten für die Mehrzahl der apps und Szenarios.

- Schnellere Startzeiten für die Mehrzahl der apps und Szenarios.

- Niedrige Kosten für Bereitstellung und Update.

- Optimierte App-Speicherauslastung.

> [!IMPORTANT]
> Bei den meisten apps und Szenarien bietet .net Native deutlich schnellere Startzeiten und eine bessere Leistung im Vergleich zu einer in Il kompilierten APP oder zu einem NGen-Image. Ihre Ergebnisse können jedoch variieren. Um sicherzustellen, dass Ihre APP von den Leistungsverbesserungen .net Native profitiert, sollten Sie die Leistung mit der Non-.net nativen Version Ihrer APP vergleichen. Weitere Informationen finden Sie unter [Übersicht über die Leistungs Sitzung](https://docs.microsoft.com/visualstudio/profiling/performance-session-overview).

.Net Native umfasst jedoch mehr als eine Kompilierung in nativem Code. Es ändert die Art und Weise, in der .NET Framework-Anwendungen erstellt und ausgeführt werden. Insbesondere:

- Bei der Vorkompilierung werden erforderlichen Bestandteile von .NET Framework statisch mit Ihrer App verknüpft. Dadurch kann die Anwendung mit lokalen Appbibliotheken von .NET Framework ausgeführt werden, und der Compiler kann eine globale Analyse ausführen, um Leistungszuwächse bereitzustellen. Daher starten Anwendungen konsistent schneller – sogar nach .NET Framework-Updates.

- Die .net Native-Laufzeit ist für die statische Vorkompilierung optimiert, und in der Mehrzahl der Fälle bietet eine bessere Leistung. Gleichzeitig werden aber die zentralen Reflektionsfeatures beibehalten, die Entwickler so produktiv finden.

- .Net Native verwendet das gleiche Back-End wie C++ der Compiler, der für statische vorkompilierungs Szenarios optimiert ist.

.Net Native ist in der Lage, die Leistungsvorteile C++ von Entwicklern von verwaltetem Code zu bieten, da die gleichen oder C++ ähnliche Tools wie in der folgenden Tabelle verwendet werden.

||.NET systemeigen|C++|
|-|----------------------------------------------------------------|-----------|
|Bibliotheken|.NET Framework + Windows-Runtime|Win32 + Windows-Runtime|
|Compiler|UTC-Optimierungscompiler|UTC-Optimierungscompiler|
|Bereitgestellt|Sofort ausführbare Binärdateien|Sofort ausführbare Binärdateien (ASM)|
|Laufzeit|MRT.dll (minimale CLR-Laufzeit)|CRT.dll (C-Laufzeit)|

Für Windows-Apps für Windows 10 laden Sie Binärdateien für die Kompilierung von systemeigenem .NET-Code in App-Paketen (APPX-Dateien) in den Windows Store hoch.

## <a name="in-this-section"></a>In diesem Abschnitt

Weitere Informationen zum Entwickeln von Anwendungen mit der .NET Native-Codekompilierung finden Sie in den folgenden Themen:

- [Einführung in die .net Native Code Kompilierung: Exemplarische Vorgehensweise für Entwickler](getting-started-with-net-native.md)

- [.Net Native und Kompilierung:](net-native-and-compilation.md) Wie .net Native das Projekt in systemeigenen Code kompiliert.

- [Reflection and .NET Native (Reflektion und .NET Native)](reflection-and-net-native.md)

  - [APIs That Rely on Reflection (APIs, die die Reflektion benötigen)](apis-that-rely-on-reflection.md)

  - [Reflektions-API-Referenz](net-native-reflection-api-reference.md)

  - [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](runtime-directives-rd-xml-configuration-file-reference.md)

- [Serialization and Metadata (Serialisierung und Metadaten)](serialization-and-metadata.md)

- [Migrating Your Windows Store App to .NET Native (Migrieren der Windows Store-App auf .NET Native)](migrating-your-windows-store-app-to-net-native.md)

- [.NET Native General Troubleshooting (Allgemeine Problembehandlung für .NET Native)](net-native-general-troubleshooting.md)
