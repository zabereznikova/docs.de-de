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
ms.openlocfilehash: 7601a6d5e7f49b6d8fc434ef772e2e69740f02cf
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543932"
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
> Bei den meisten apps und Szenarien bietet .net Native deutlich schnellere Startzeiten und eine bessere Leistung im Vergleich zu einer in Il kompilierten APP oder zu einem NGen-Image. Ihre Ergebnisse können jedoch variieren. Um sicherzustellen, dass Ihre APP von den Leistungsverbesserungen .net Native profitiert, sollten Sie die Leistung mit der Non-.net nativen Version Ihrer APP vergleichen. Weitere Informationen finden Sie unter [Übersicht über die Leistungs Sitzung](/visualstudio/profiling/performance-session-overview).

.Net Native umfasst jedoch mehr als eine Kompilierung in nativem Code. Es ändert die Art und Weise, in der .NET Framework-Anwendungen erstellt und ausgeführt werden. Dies gilt insbesondere für:

- Bei der Vorkompilierung werden erforderlichen Bestandteile von .NET Framework statisch mit Ihrer App verknüpft. Dadurch kann die Anwendung mit lokalen Appbibliotheken von .NET Framework ausgeführt werden, und der Compiler kann eine globale Analyse ausführen, um Leistungszuwächse bereitzustellen. Daher starten Anwendungen konsistent schneller – sogar nach .NET Framework-Updates.

- Die .net Native-Laufzeit ist für die statische Vorkompilierung optimiert, und in der Mehrzahl der Fälle bietet eine bessere Leistung. Gleichzeitig werden aber die zentralen Reflektionsfeatures beibehalten, die Entwickler so produktiv finden.

- .Net Native verwendet das gleiche Back-End wie der C++-Compiler, der für statische vorkompilierungs Szenarios optimiert ist.

.Net Native ist in der Lage, die Leistungsvorteile von C++ für Entwickler von verwaltetem Code zu nutzen, da Sie die gleichen oder ähnliche Tools wie C++ im Hintergrund verwendet, wie in dieser Tabelle dargestellt.

||.NET systemeigen|C++|
|-|----------------------------------------------------------------|-----------|
|Bibliotheken|.NET Framework + Windows-Runtime|Win32 + Windows-Runtime|
|Compiler|UTC-Optimierungscompiler|UTC-Optimierungscompiler|
|Bereitgestellt|Sofort ausführbare Binärdateien|Sofort ausführbare Binärdateien (ASM)|
|Laufzeit|MRT.dll (minimale CLR-Laufzeit)|CRT.dll (C-Laufzeit)|

Für Windows-Apps für Windows 10 laden Sie Binärdateien für die Kompilierung von systemeigenem .NET-Code in App-Paketen (APPX-Dateien) in den Windows Store hoch.

## <a name="in-this-section"></a>In diesem Abschnitt

Weitere Informationen zum Entwickeln von Anwendungen mit der .NET Native-Codekompilierung finden Sie in den folgenden Themen:

- [Erste Schritte mit der .NET Native-Codekompilierung: exemplarische Vorgehensweise für Entwickler](getting-started-with-net-native.md)

- [.NET Native und Kompilierung:](net-native-and-compilation.md) So kompiliert .NET Native Ihr Projekt in systemeigenen Code.

- [Reflektion und .NET Native](reflection-and-net-native.md)

  - [APIs, die auf Refelktion beruhen](apis-that-rely-on-reflection.md)

  - [Reflektions-API-Referenz](net-native-reflection-api-reference.md)

  - [Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz](runtime-directives-rd-xml-configuration-file-reference.md)

- [Serialisierung und Metadaten](serialization-and-metadata.md)

- [Migrieren der Windows Store-App auf .NET Native](migrating-your-windows-store-app-to-net-native.md)

- [.NET Native Allgemeine Problembehandlung](net-native-general-troubleshooting.md)
