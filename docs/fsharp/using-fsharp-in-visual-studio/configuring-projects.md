---
title: Konfigurieren von Projekten (f#)
description: Erfahren Sie, wie die Projekt-Designer verwenden, bei der Arbeit mit F#-Projekten in Visual Studio.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8b2ed206-34e4-4256-a6ce-0c2499561165
ms.openlocfilehash: d2a92f725c40443c8dc6af593d28deccd3ee88de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="configuring-projects-in-visual-studio"></a>Konfigurieren von Projekten in Visual Studio

> [!NOTE]
Dieser Artikel ist nicht auf dem neuesten Stand mit den neuesten Visual Studio.  Es werden aktualisiert.

Dieses Thema enthält Informationen zum Verwenden der **Projekt-Designer** beim Arbeiten mit f#-Projekten. Arbeiten mit f#-Projekten unterscheidet sich nicht erheblich von der Arbeit mit Visual Basic oder C#-Projekten. Häufig können Sie die allgemeine Visual Studio-Projekt-Dokumentation als primäre Referenz verwenden, wenn Sie f# verwenden. In diesem Thema enthält Links zu relevanten Informationen in der Visual Studio-Dokumentation für Einstellungen, die mit anderen Visual Studio-Sprachen gemeinsam genutzt werden, sowie eine Beschreibung der Einstellungen für spezifische f#.

## <a name="project-designer"></a>Projekt-Designer
Die **Projekt-Designer** und Allgemeine Verwendungsmöglichkeiten sind vollständig in diesem Thema beschriebenen [Einführung in den Projekt-Designer](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7) in der Visual Studio-Dokumentation. Die **Projekt-Designer** umfasst mehrere Seiten, die nach Funktionsbereichen gruppiert. Die Seiten für f#-Projekte verfügbar sind meistens eine Teilmenge der für andere Sprachen verfügbar sind. Die Seiten, die in f# unterstützt werden in der folgenden Tabelle beschrieben. Die Seiten, die nicht verfügbar sind, beziehen sich auf Funktionen, die nicht in f# verfügbar sind, oder nur durch Ändern einer Befehlszeilenoption erhältlich sind. Seiten, die in f# verfügbar sind, ähneln die C#-Seiten am ehesten ein Link zu den entsprechenden C#-ist **Projekt-Designer** Seite.

|Projekt-Designer-Seite|Verwandte links|Beschreibung|
|---------------------|-------------|-----------|
|`Application`|[Seite "Anwendung", Projekt-Designer &#40; C &#35; &#41;](https://msdn.microsoft.com/library/ms247046.aspx)|Ermöglicht es Ihnen anzugeben, auf Anwendungsebene Einstellungen und Eigenschaften, z. B., ob Sie erstellen eine Bibliothek oder eine ausführbare Datei, welche Version von .NET Framework die Anwendung abzielt und Informationen zu, in dem die Ressource, die Dateien der Anwendung verwendet werden gespeichert.|
|`Build`|[Erstellen Sie die Seite, Projekt-Designer &#40; C &#35; &#41;](https://msdn.microsoft.com/library/kb4wyys2.aspx)|Können Sie steuern, wie der Code kompiliert wird.|
|`Build Events`|[Erstellen Sie die Seite "Ereignisse", Projekt-Designer &#40; C &#35; &#41;](https://msdn.microsoft.com/library/kb4wyys2.aspx)|Können Sie Befehle zum Ausführen vor oder nach der Kompilierung angeben.|
|`Debug`|[Seite „Debuggen“, Projekt-Designer](https://msdn.microsoft.com/library/2wcdezs5.aspx)|Können Sie steuern, wie die Anwendung während des Debuggens ausgeführt wird. Dazu gehören, was zu übergebende Befehlszeile verwenden und Neuigkeiten in das Verzeichnis der Anwendung ab, und alle speziellen Modi werden z. B. systemeigenem Code und SQL, soll-Debuggen.|
|`Reference Paths`|[Verwalten von Verweisen in einem Projekt](https://msdn.microsoft.com/library/ez524kew.aspx)|Ermöglicht es Ihnen anzugeben, wo nach Assemblys suchen soll, von denen der Code abhängt.|

## <a name="f-specific-settings"></a>F#-spezifischen Einstellungen
Die folgende Tabelle fasst die Einstellungen, die für f# spezifisch sind:

|Projekt-Designer-Seite|Einstellung|Beschreibung|
|---------------------|-------|-----------|
|`Build`|`Generate tail calls`|Wenn ausgewählt, können die Verwendung der Tail-Anweisung Microsoft intermediate Language (MSIL). Dies bewirkt, dass die für endrekursive Funktionen die Wiederverwendung des Stapelrahmens. Entspricht der `--tailcalls` -Compileroption.|
|`Build`|`Other flags`|Ermöglicht Ihnen, zusätzliche Compilerbefehlszeilenoptionen anzugeben.|

## <a name="see-also"></a>Siehe auch
 [Erste Schritte mit f# in Visual Studio](../get-started/get-started-visual-studio.md)  
 [Compileroptionen](../language-reference/compiler-options.md)  
 [Introduction to the Project Designer (Einführung in den Projekt-Designer)](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7(v=vs.100))
