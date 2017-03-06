---
title: .NET-Assemblydateiformat
description: .NET-Assemblydateiformat
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 6520323e-ff28-4c8a-ba80-e64a413199e6
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: ec5619e164be44205060d790ba1dc66e261faf92
ms.lasthandoff: 03/02/2017

---

# <a name="net-assembly-file-format"></a>.NET-Assemblydateiformat

Die .NET-Plattform definiert ein Binärdateiformat – „Assembly“ – das .NET-Programme vollständig beschreiben und enthalten kann. Assemblys werden sowohl für die Programme selbst als auch alle abhängigen Bibliotheken verwendet. Ein .NET-Programm kann in Form einer oder mehrerer Assemblys, ohne sonstige erforderliche Artefakte, außerhalb der entsprechenden .NET-Runtime ausgeführt werden. Native Abhängigkeiten, einschließlich Betriebssystem-APIs, werden separat berücksichtigt und sind nicht im .NET-Assemblyformat enthalten, obwohl sie manchmal in diesem Format (z.B. WinRT) beschrieben werden.

> Jede CLI-Komponente enthält die Metadaten für Deklarationen, Implementierungen und Verweisen, die für diese Komponente spezifisch sind. Darum werden die komponentenspezifischen Metadaten als Komponentenmetadaten und die resultierende Komponente als selbstbeschreibend bezeichnet – laut ECMA 335 I.9.1, „Components and assemblies“ (Komponenten und Assemblys).

Das Format ist als ECMA 335 vollständig spezifiziert und standardisiert. Alle .NET-Compiler und -Runtimes verwenden dieses Format. Das Vorhandensein eines dokumentierten und unregelmäßig aktualisierten Binärformats ist ein großer Vorteil (wenn nicht gar eine Voraussetzung) für die Interoperabilität gewesen. Das Format wurde zuletzt wesentlich 2005 (.NET 2.0) zur Aufnahme von Generika und Prozessorarchitektur aktualisiert.

Das Format ist agnostisch gegenüber CPU und Betriebssystem. Es wurde als Teil von .NET-Runtimes verwendet, die auf viele Chips und CPUs abzielen. Trotz seines Windows-Erbes ist das Format unter jedem Betriebssystem implementierbar. Das wohl wichtigste Argument für die Betriebssysteminteroperabilität ist, dass die meisten Werte im Little-Endian-Format gespeichert werden. Es besteht keine bestimmte Affinität zur Zeigergröße des Computers (z.B. 32-Bit, 64-Bit).

Das .NET-Assemblyformat ist auch sehr aussagekräftig über die Struktur einer bestimmten Anwendung oder Bibliothek. Es beschreibt die internen Komponenten einer Assembly, speziell: Assemblyverweise und definierte Typen sowie deren interne Struktur. Tools oder APIs können diese Informationen für die Anzeige lesen und verarbeiten, oder um programmatische Entscheidungen zu treffen.

## <a name="format"></a>Format

Das .NET-Binärformat basiert auf dem Windows [PE](http://en.wikipedia.org/wiki/Portable_Executable)-Dateiformat. In der Tat sind .NET-Klassenbibliotheken konforme Windows PE-Dateien und scheinen auf den ersten Blick Windows-Dynamic Link Librarys (DLLs) oder ausführbare Anwendungsdateien (EXE-Dateien) zu sein. Dies ist ein sehr nützliches Merkmal unter Windows, wo sie sich als native ausführbare Binärdateien tarnen können und weithin als solche behandelt werden (z.B. Laden durch das Betriebssystem, PE-Tools).

![Assemblyheader](./media/assembly-format/assembly-headers.png)

Assemblyheader aus ECMA 335 II.25.1, „Structure of the runtime file format“ (Struktur des Runtimedateiformats).

## <a name="processing-the-assemblies"></a>Verarbeiten der Assemblys

Es ist möglich, Tools oder APIs zum Verarbeiten von Assemblys zu schreiben. Assemblyinformationen ermöglichen programmatische Entscheidungen zur Laufzeit, das Umschreiben von Assemblys, Bereitstellen von API-IntelliSense in einem Editor und Generieren von Dokumentation. [System.Reflection](https://msdn.microsoft.com/library/system.reflection.aspx) und [Mono.Cecil](http://www.mono-project.com/docs/tools+libraries/libraries/Mono.Cecil/) sind gute Beispiele für Tools, die häufig für diesen Zweck verwendet werden.

