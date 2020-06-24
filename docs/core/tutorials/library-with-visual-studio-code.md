---
title: Erstellen einer .NET Standard-Klassenbibliothek in Visual Studio Code
description: Hier erfahren Sie, wie Sie eine .NET Standard-Klassenbibliothek mit Visual Studio Code erstellen.
ms.date: 06/08/2020
ms.openlocfilehash: f7d2319bcea58f63ca40e43ba39745bdf1b394ce
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2020
ms.locfileid: "84701798"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio-code"></a>Tutorial: Erstellen einer .NET-Standard-Bibliothek in Visual Studio Code

In diesem Tutorial erstellen Sie eine einfache Hilfsprogrammbibliothek, die eine einzelne Methode zur Behandlung von Zeichenfolgen enthält. Sie implementieren sie als [Erweiterungsmethode](../../csharp/programming-guide/classes-and-structs/extension-methods.md), damit sie aufgerufen werden kann, als wäre sie ein Mitglied der <xref:System.String>-Klasse.

Eine *Klassenbibliothek* definiert die Typen und Methoden, die von einer Anwendung aufgerufen werden können. Eine Klassenbibliothek, die sich auf .NET Standard 2.0 bezieht, ermöglicht das Aufrufen der Bibliothek aus jeder .NET-Implementierung, die diese Version von .NET Standard unterstützt. Wenn Sie Ihre Klassenbibliothek fertig gestellt haben, können Sie sie als Komponente eines Drittanbieters oder als gebündelte Komponente mit einer oder mehreren Anwendungen verteilen.

## <a name="prerequisites"></a>Voraussetzungen

1. [Visual Studio Code](https://code.visualstudio.com/) mit installierter [C#-Erweiterung](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp). Informationen zum Installieren von Erweiterungen für Visual Studio Code finden Sie unter [Marketplace für VS Code-Erweiterungen](https://code.visualstudio.com/docs/editor/extension-gallery).
2. [.NET Core 3.1 SDK oder höher](https://dotnet.microsoft.com/download)

## <a name="create-a-solution"></a>Erstellen einer Projektmappe

Beginnen Sie, indem Sie eine leere Projektmappe erstellen, um das Klassenbibliotheksprojekt darin zu speichern. Eine Projektmappe dient als ein Container für mindestens ein Projekt. Sie fügen der gleichen Projektmappe weitere verwandte Projekte hinzu.

1. Starten Sie Visual Studio Code.

1. Wählen Sie im Hauptmenü **Datei** > **Ordner öffnen** (**Öffnen...** unter macOS) aus.

1. Erstellen Sie im Dialogfeld **Ordner öffnen** den Ordner *ClassLibraryProjects*, und klicken Sie auf **Ordner auswählen** (**Öffnen** unter macOS).

1. Öffnen Sie das **Terminal** in Visual Studio Code, indem Sie im Hauptmenü **Ansicht** > **Terminal** auswählen.

   Das **Terminal** wird mit der Eingabeaufforderung im Ordner *ClassLibraryProjects* geöffnet.

1. Geben Sie im **Terminal** den folgenden Befehl ein:

   ```dotnetcli
   dotnet new sln
   ```

   Die Terminalausgabe sieht wie das folgende Beispiel aus:

   ```
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a>Erstellen eines Klassenbibliotheksprojekts

Fügen Sie der Projektmappe ein neues .NET Standard-Klassenbibliotheksprojekt mit dem Namen „StringLibrary“ hinzu.

1. Führen Sie im Terminal den folgenden Befehl aus, um das Bibliotheksprojekt zu erstellen:

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   Die Terminalausgabe sieht wie das folgende Beispiel aus:

   ```
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restore completed in 328.13 ms for C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj.
   Restore succeeded.
   ```

1. Führen Sie den folgenden Befehl aus, um das Bibliotheksprojekt zur Projektmappe hinzuzufügen:

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   Die Terminalausgabe sieht wie das folgende Beispiel aus:

   ```
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. Stellen Sie sicher, dass die Bibliothek die richtige Version von .NET Standard als Ziel verwendet. Öffnen Sie im **Explorer** die Datei *StringLibrary/StringLibrary.csproj*.

   Das Element `TargetFramework` gibt an, dass das Projekt für .NET Standard 2.0 vorgesehen ist.

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>netstandard2.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. Öffnen Sie die Datei *Class1.cs*, und ersetzen Sie den Code durch den folgenden:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   Die Klassenbibliothek (`UtilityLibraries.StringLibrary`) enthält eine Methode namens `StartsWithUpper`. Diese Methode gibt einen <xref:System.Boolean>-Wert zurück, der angibt, ob die aktuelle Zeichenfolgeninstanz mit einem Großbuchstaben beginnt. Der Unicode-Standard unterscheidet Groß- und Kleinschreibung. Die Methode <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> gibt `true` zurück, wenn ein Zeichen ein Großbuchstabe ist.

1. Speichern Sie die Datei.

1. Führen Sie den folgenden Befehl aus, um die Projektmappe zu erstellen und zu überprüfen, ob das Projekt fehlerfrei kompiliert wird:

   ```dotnetcli
   dotnet build
   ```

   Die Terminalausgabe sieht wie das folgende Beispiel aus:

   ```
   Microsoft (R) Build Engine version 16.6.0 for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     You are using a preview version of .NET Core. See: https://aka.ms/dotnet-core-preview
     StringLibrary -> C:\Projects\ClassLibraryProjects\StringLibrary\bin\Debug\netstandard2.0\StringLibrary.dll
   Build succeeded.
       0 Warning(s)
       0 Error(s)
   Time Elapsed 00:00:02.78
   ```

## <a name="add-a-console-app-to-the-solution"></a>Hinzufügen einer Konsolen-App zur Projektmappe

Im Folgenden fügen Sie eine Konsolenanwendung hinzu, die die Klassenbibliothek verwendet. Die App fordert den Benutzer dazu auf, eine Zeichenfolge einzugeben, und meldet, ob die Zeichenfolge mit einem Großbuchstaben beginnt.

1. Führen Sie im Terminal den folgenden Befehl aus, um das Konsolen-App-Projekt zu erstellen:

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   Die Terminalausgabe sieht wie das folgende Beispiel aus:

   ```
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restore completed in 210.78 ms for C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj.
   Restore succeeded.
   ```

1. Führen Sie den folgenden Befehl aus, um das Konsolen-App-Projekt zur Projektmappe hinzuzufügen:

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   Die Terminalausgabe sieht wie das folgende Beispiel aus:

   ```
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. Öffnen Sie die Datei *ShowCase/Program.cs*, und ersetzen Sie den gesamten Code durch den folgenden:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   Der Code verwendet die `row`-Variable, um die Anzahl der in das Konsolenfenster geschriebenen Datenzeilen festzuhalten. Wenn sie mindestens 25 beträgt, löscht der Code das Konsolenfenster und zeigt eine Meldung für den Benutzer an.

   Das Programm selbst fordert den Benutzer zur Eingabe einer Zeichenfolge auf. Es zeigt an, ob die Zeichenfolge mit einem Großbuchstaben beginnt. Wenn der Benutzer die <kbd>EINGABETASTE</kbd> drückt, ohne eine Zeichenfolge einzugeben, wird die Anwendung beendet und das Konsolenfenster geschlossen.

1. Speichern Sie die Änderungen.

## <a name="add-a-project-reference"></a>Hinzufügen eines Projektverweises

Anfänglich besitzt das neue Konsolen-App-Projekt keinen Zugriff auf die Klassenbibliothek. Damit es Methoden in der Klassenbibliothek aufrufen kann, erstellen Sie einen Projektverweis auf das Klassenbibliotheksprojekt.

1. Führen Sie den folgenden Befehl aus:

   ```dotnetcli
   dotnet add ShowCase/Showcase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   Die Terminalausgabe sieht wie das folgende Beispiel aus:

   ```
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

## <a name="run-the-app"></a>Ausführen der App

1. Führen Sie die folgenden Befehle im Terminal aus:

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. Testen Sie das Programm, indem Sie Zeichenfolgen eingeben und die <kbd>EINGABETASTE</kbd> drücken, und drücken Sie dann die <kbd>EINGABETASTE</kbd>, um das Programm zu beenden.

   Die Terminalausgabe sieht wie das folgende Beispiel aus:

   ```
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   A string that starts with a lowercase letter
   Input: A string that starts with a lowercase letter
   Begins with uppercase? : Yes
   ```

## <a name="additional-resources"></a>Zusätzliche Ressourcen

* [Entwickeln von Bibliotheken mit der .NET Core-CLI](libraries.md)
* [.NET Standard-Versionen und die von ihnen unterstützten Plattformen](../../standard/net-standard.md).

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine Projektmappe erstellt, ein Bibliotheksprojekt hinzugefügt und ein Konsolen-App-Projekt hinzugefügt, das die Bibliothek verwendet. Im nächsten Tutorial fügen Sie der Projektmappe ein Komponententestprojekt hinzu.

> [!div class="nextstepaction"]
> [Testen einer .NET Standard-Bibliothek mit .NET Core in Visual Studio Code](testing-library-with-visual-studio-code.md)
