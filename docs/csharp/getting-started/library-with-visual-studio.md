---
title: Erstellen einer Klassenbibliothek mit C# und .NET Core in Visual Studio 2017
description: Erfahren Sie, wie Sie eine in C# geschriebene Klassenbibliothek mithilfe von Visual Studio 2017 erstellen.
keywords: .NET Core, .NET Standard-Klassenbibliothek, Visual Studio 2017
author: BillWagner
ms.author: wiwagn
ms.date: 04/17/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: c849ca26-6a25-4d35-9544-f343af88e0e7
ms.translationtype: HT
ms.sourcegitcommit: 3155295489e1188640dae5aa5bf9fdceb7480ed6
ms.openlocfilehash: 96a6a936ad1dbd412bfa07bc642eef975dd80e6c
ms.contentlocale: de-de
ms.lasthandoff: 08/05/2017

---

# <a name="building-a-class-library-with-c-and-net-core-in-visual-studio-2017"></a>Erstellen einer Klassenbibliothek mit C# und .NET Core in Visual Studio 2017

Eine *Klassenbibliothek* definiert die Typen und Methoden, die von einer Anwendung aufgerufen werden können. Eine mit .NET Core entwickelte Klassenbibliothek unterstützt .NET Standard, sodass die Bibliothek aus jeder .NET-Implementierung aufgerufen werden kann, die diese Version von .NET Standard unterstützt. Wenn Sie die Klassenbibliothek fertig stellen, können Sie entscheiden, ob Sie sie als Drittanbieterkomponente verteilen oder als Komponente mit einer oder mehreren Anwendungen in ein Paket einbeziehen möchten.

> [!NOTE]
> Eine Liste der .NET Standard-Versionen und der Plattformen, die sie unterstützen, finden Sie unter [.NET-Standard](../../standard/net-standard.md).

In diesem Thema erstellen Sie eine einfache Hilfsprogrammbibliothek, die eine einzelne Methode zur Behandlung von Zeichenfolgen enthält. Sie implementieren sie als [Erweiterungsmethode](../../csharp/programming-guide/classes-and-structs/extension-methods.md), damit sie aufgerufen werden kann, als wäre sie ein Mitglied der @System.String Klasse.

## <a name="creating-a-class-library-solution"></a>Erstellen einer Klassenbibliotheks-Projektmappe

Zunächst erstellen Sie eine Projektmappe für Ihre Klassenbibliotheksprojekt und die zugehörigen Projekte. Eine Visual Studio-Projektmappe dient nur als Container für ein oder mehrere Projekte. So erstellen Sie die Projektmappe:

1. Wählen Sie auf der Visual Studio-Menüleiste **Datei** > **Neu** > **Projekt** aus.

1. Erweitern Sie im Dialogfeld **Neues Projekt** den Knoten **Andere Projekttypen**, und wählen Sie **Visual Studio-Projektmappen** aus. Nennen Sie die Projektmappe „ClassLibraryProjects“, und wählen Sie die **OK**-Schaltfläche aus.

   ![Dialogfeld "Neues Projekt"](./media/library-with-visual-studio/newproject.png)

## <a name="creating-the-class-library-project"></a>Erstellen des Klassenbibliotheksprojekts

Erstellen Sie Ihr Klassenbibliotheksprojekt:

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappendatei **ClassLibraryProjects**, und wählen Sie im Kontextmenü **Hinzufügen** > **Neues Projekt** aus.

1. Wählen Sie im Dialogfeld **Neues Projekt hinzufügen** den Knoten **.NET Core**, gefolgt von der Projektvorlage **Klassenbibliothek (.NET Core)**. Geben Sie im Textfeld **Name** „StringLibrary“ als Namen des Projekts ein. Wählen Sie **OK**, um das Klassenbibliotheksprojekt zu erstellen.

   ![Dialogfeld „Neues Projekt hinzufügen“](./media/library-with-visual-studio/libproject.png)

   ![Visual Studio-Anwendungsfenster, das die den Standardvorlagencode der Klassenbibliothek zeigt](./media/library-with-visual-studio/stringlibrary.png)

1. Ersetzen Sie den Code im Codefenster durch den folgenden Code, und speichern Sie die Datei:

   [!CODE-csharp[ClassLib #1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs#1)]

   Die Klassenbibliothek, `UtilityLibraries.StringLibrary`, enthält eine Methode namens `StartsWithUpper`, welche einen @System.Boolean Wert zurückgibt, der angibt, ob die aktuelle Zeichenfolgeninstanz mit einem Großbuchstaben beginnt. Der Unicode-Standard unterscheidet Groß- und Kleinschreibung. In .NET Core gibt die [`Char.IsUpper`](xref:System.Char.IsUpper(System.Char))-Methode `true` zurück, wenn ein Zeichen ein Großbuchstabe ist.

1. Wählen Sie auf der Menüleiste **Erstellen** > **Projektmappe erstellen** aus. Das Projekt sollte fehlerfrei kompiliert werden.

   ![Ausgabebereich, der zeigt, dass der Buildvorgang erfolgreich war](./media/library-with-visual-studio/buildsucceeds.png)

## <a name="next-step"></a>Nächster Schritt

Sie haben die Bibliothek erfolgreich erstellt. Aber da Sie keine ihrer Methoden aufgerufen haben, wissen Sie nicht, ob sie wie erwartet funktioniert. Der nächste Schritt bei der Entwicklung Ihrer Bibliothek ist ihr Test mithilfe eines [C#-Komponententestprojekts](testing-library-with-visual-studio.md).

