---
title: Erste Schritte mit .NET Core unter Windows mit Visual Studio 2017
description: Erste Schritte mit .NET Core unter Windows mit Visual Studio 2017
keywords: .NET, .NET Core
author: bleroy
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: d743134a-08a3-4ff6-aab7-49f71f0568c3
translationtype: Human Translation
ms.sourcegitcommit: 71eab6216e116b99927dfeaa8ce3cf70bcc08a5e
ms.openlocfilehash: 4437f44523bcc4e8517de5b6be42a63439f817d7

---

# <a name="getting-started-with-net-core-on-windows-using-visual-studio-2017"></a>Erste Schritte mit .NET Core unter Windows mit Visual Studio 2017

von [Bertrand Le Roy](https://github.com/bleroy) und [Phillip Carter](https://github.com/cartermp)

Visual Studio 2017 bietet eine umfassende Entwicklungsumgebung für die Entwicklung von .NET Core-Anwendungen. In diesem Dokument werden die erforderlichen Schritte zum Erstellen einer sehr einfachen Konsolenanwendung mit Visual Studio und .NET Core beschrieben.

## <a name="prerequisites"></a>Erforderliche Komponenten

Befolgen Sie die Anweisungen auf [unserer Seite über erforderliche Komponenten](../windows-prerequisites.md), um Ihre Umgebung anzupassen.

## <a name="getting-started"></a>Erste Schritte

Mit den folgenden Schritten richten Sie Visual Studio 2017 für die Entwicklung von .NET Core-Konsolenanwendungen ein:

1. Öffnen Sie Visual Studio, und wählen Sie im Menü **Datei** die Option **Neu** > **Projekt**.

2. Erweitern Sie im Dialogfeld **Neues Projekt** in der Liste **Vorlagen** den Knoten **Visual C#**, und wählen Sie **.NET Core** aus. Es werden vier neue Projektvorlagen für **Konsolen-App (.NET Core)**, **Komponententestprojekt (.NET Core)**, **Klassenbibliothek (.NET Core)** und **ASP.NET Core-Webanwendung (.NET Core)** angezeigt. Wählen Sie **Konsolen-App (.NET Core)**, geben Sie einen Namen für das Projekt ein, wählen Sie einen Speicherort aus, und klicken Sie auf „OK“.

  ![Neues Projekt: Konsolen-App](media/new-project-console-app.png)

3. Das resultierende Projekt verfügt über eine einzelne C#-Datei, die „Hello World“ in der Konsole ausgibt.

  ![Das Konsolen-App-Projekt](media/console-app-solution.png)

Sie können diese Anwendung durch Drücken von F5 im Debugmodus oder durch Drücken von STRG+F5 im Releasemodus ausführen. Sie können auch Haltepunkte festlegen, um die Ausführung zu unterbrechen und Variablen zu untersuchen, oder mit dem Schreiben von weiterem interessanten Code beginnen.

Viel Spaß beim Programmieren!

## <a name="what-to-do-next"></a>Nächste Schritte

Im Anschluss an diese einfache Einführung fragen Sie sich wahrscheinlich, wie anspruchsvollere Lösungen mit wiederverwendbaren Bibliotheken und Tests erstellt werden. Das erfahren Sie im Thema [Erstellen einer vollständigen .NET Core-Lösung unter Windows mit Visual Studio 2017](using-on-windows-vs-2017-full-solution.md).



<!--HONumber=Nov16_HO3-->


