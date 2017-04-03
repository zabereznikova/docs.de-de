---
title: Erstellen einer Klassenbibliothek mit C# und .NET Core in Visual Studio 2017
description: Erfahren Sie, wie Sie eine in C# geschriebene Klassenbibliothek mithilfe von Visual Studio 2017 erstellen.
keywords: .NET Core, .NET Standard-Klassenbibliothek, Visual Studio 2017
author: stevehoag
ms.author: shoag
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: c849ca26-6a25-4d35-9544-f343af88e0e7
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 28fa60cdcf8e0056314af271208759eadd8503a5
ms.lasthandoff: 03/13/2017

---

# <a name="building-a-class-library-with-c-and-net-core-in-visual-studio-2017"></a>Erstellen einer Klassenbibliothek mit C# und .NET Core in Visual Studio 2017 #

Eine Klassenbibliothek definiert die Typen und Methoden, die von einer Anwendung aufgerufen werden können. Eine mit .NET Core entwickelte Klassenbibliothek unterstützt die .NET Standard-Bibliothek, wodurch die Bibliothek von jeder .NET-Plattform aus aufgerufen werden kann, die diese Version der .NET Standard-Bibliothek unterstützt. Wenn Sie die Klassenbibliothek fertig stellen, können Sie entscheiden, ob Sie sie als Drittanbieterkomponente verteilen oder als Komponente mit einer oder mehreren Anwendungen in ein Paket einbeziehen möchten.

> [!NOTE]
> Eine Liste der .NET Standard-Versionen und der Plattformen, die sie unterstützen, finden Sie unter [.NET-Standardbibliothek](../../standard/library.md).

In diesem Thema erstellen wir eine einfache Hilfsprogrammbibliothek, die eine einzelne Methode zur Behandlung von Zeichenfolgen enthält. Wir implementieren sie als [Erweiterungsmethode](../../csharp/programming-guide/classes-and-structs/extension-methods.md), damit sie aufgerufen werden kann, als wäre sie ein Mitglied der @System.String-Klasse.

## <a name="creating-a-class-library-solution"></a>Erstellen einer Klassenbibliotheks-Projektmappe ##

Zunächst erstellen wir eine Projektmappe für unser Klassenbibliotheksprojekt und die zugehörigen Projekte. Eine Visual Studio-Projektmappe dient nur als Container für ein oder mehrere Projekte. So erstellen Sie die Projektmappe:

1. Wählen Sie auf der Visual Studio-Menüleiste **Datei**, **Neu** und **Projekt** aus.

1. Erweitern Sie im Dialogfeld **Neue Projekte** den Knoten **Andere Projekttypen**, und wählen Sie **Visual Studio-Projektmappen**, wie die folgende Abbildung zeigt.

   ![Bild](./media/solution.jpg)

1. Nennen Sie die Projektmappe „ClassLibraryProjects“, und wählen Sie die **OK**-Schaltfläche. Die folgende Abbildung zeigt das Ergebnis.

   ![Bild](./media/vs_with_solution.jpg)

## <a name="creating-the-class-library-project"></a>Erstellen des Klassenbibliotheksprojekts ##

Jetzt können wir unser Klassenbibliotheksprojekt erstellen:

1. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü des Knotens **ClassLibraryProjects**, und wählen Sie **Hinzufügen**, **Neues Projekt** aus.

1. Wählen Sie im Dialogfeld **Neues Projekt hinzufügen** den Knoten **.NET Core**, und wählen Sie die Projektvorlage **Klassenbibliothek (.NET Standard)** aus.

1. Geben Sie im Textfeld **Name** „StringLibrary“ als Namen des Projekts ein, wie in der folgenden Abbildung dargestellt.

   ![Bild](./media/lib_project.jpg)

1. Wählen Sie **OK**, um das Klassenbibliotheksprojekt zu erstellen. Die folgende Abbildung zeigt das Ergebnis.

   ![Bild](./media/class_library.jpg)

1. Ersetzen Sie den Code im Codefenster durch den folgenden Code:

   [!CODE-csharp[ClassLib #1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs#1)]

   Die Klassenbibliothek, `UtilityLibraries.StringLibrary`, enthält eine Methode namens `StartsWithUpper`, welche einen @System.Boolean-Wert zurückgibt, der angibt, ob die aktuelle Zeichenfolgeninstanz mit einem Großbuchstaben beginnt. Welche Zeichen Großbuchstaben sind, definiert der Unicode-Standard. In .NET Core gibt die [Char.IsUpper](xref:System.Char.IsUpper(System.Char))-Methode `true` zurück, wenn ein Zeichen ein Großbuchstabe ist.

1. Wählen Sie in der Menüleiste **Erstellen**, **Projektmappe erstellen**. Das Projekt sollte fehlerfrei kompiliert werden.

## <a name="the-next-step"></a>Der nächste Schritt ##

Bisher haben wir die Bibliothek erfolgreich erstellt. Aber da wir keine ihrer Methoden aufgerufen haben, wissen wir nicht, ob sie wie erwartet funktioniert. Der nächste Schritt bei der Entwicklung unserer Bibliothek ist ihr Test mithilfe eines [C#-Komponententestprojekts](testing-library-with-visual-studio.md).



