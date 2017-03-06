---
title: Erste Schritte mit .NET Core unter Windows mit Visual Studio 2017 | Microsoft-Dokumentation
description: Erste Schritte mit .NET Core unter Windows mit Visual Studio 2017
keywords: .NET, .NET Core
author: bleroy
ms.author: mairaw
ms.date: 01/18/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 613c65d0-f773-41b8-ba0e-83f6a82a0b30
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: cc2c2853bc31e161d1fe0de4edc71d15281c6d24

---

# <a name="getting-started-with-net-core-on-windows-using-visual-studio-2017-net-core-tools-rc4"></a>Erste Schritte mit .NET Core unter Windows mit Visual Studio 2017 (.NET Core Tools RC4)

> [!WARNING]
> Dieses Thema gilt für .NET Core Tools RC4. Informationen zu .NET Core Preview 2-Tools für Visual Studio 2015 finden Sie im Thema [Erste Schritte mit .NET Core unter Windows mit Visual Studio 2015](../../tutorials/using-on-windows.md).

Visual Studio 2017 bietet eine umfassende Entwicklungsumgebung für die Entwicklung von .NET Core-Anwendungen. In diesem Dokument werden die erforderlichen Schritte zum Erstellen einer sehr einfachen Konsolenanwendung mit Visual Studio und .NET Core beschrieben.

## <a name="prerequisites"></a>Erforderliche Komponenten

Befolgen Sie die Anweisungen auf [unserer Seite über erforderliche Komponenten](../windows-prerequisites.md), um Ihre Umgebung anzupassen.

## <a name="getting-started"></a>Erste Schritte

Mit den folgenden Schritten richten Sie Visual Studio 2017 für die Entwicklung von .NET Core-Konsolenanwendungen ein:

1. Öffnen Sie Visual Studio, und wählen Sie im Menü **Datei** die Option **Neu** > **Projekt**.

2. Erweitern Sie im Dialogfeld **Neues Projekt** in der Liste **Vorlagen** den Knoten **Visual C#**, und wählen Sie **.NET Core** aus. Es werden fünf Projektvorlagen für **Konsolen-App (.NET Core)**, **Klassenbibliothek (.NET Standard)**, **Komponententestprojekt (.NET Core)**, **Klassenbibliothek (.NET Core)** und **ASP.NET Core-Webanwendung (.NET Core)** angezeigt. Wählen Sie **Konsolen-App (.NET Core)**, geben Sie einen Namen für das Projekt ein, wählen Sie einen Speicherort aus, und klicken Sie auf „OK“.

  ![Neues Projekt: Konsolen-App](media/new-project-console-app.png)

3. Das resultierende Projekt verfügt über eine einzelne C#-Datei, die „Hello World“ in der Konsole ausgibt.

  ![Das Konsolen-App-Projekt](media/console-app-solution.png)

Sie können diese Anwendung durch Drücken von F5 im Debugmodus oder durch Drücken von STRG+F5 im Releasemodus ausführen. Sie können auch Haltepunkte festlegen, um die Ausführung zu unterbrechen und Variablen zu untersuchen, oder mit dem Schreiben von weiterem interessanten Code beginnen.

Viel Spaß beim Programmieren!

## <a name="next-steps"></a>Nächste Schritte

Im Anschluss an diese einfache Einführung fragen Sie sich wahrscheinlich, wie anspruchsvollere Lösungen mit wiederverwendbaren Bibliotheken und Tests erstellt werden. Das erfahren Sie im Thema [Erstellen einer vollständigen .NET Core-Lösung unter Windows mit Visual Studio 2017](using-on-windows-vs-2017-full-solution.md).



<!--HONumber=Feb17_HO2-->


