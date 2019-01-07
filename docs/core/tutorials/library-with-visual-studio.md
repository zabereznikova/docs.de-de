---
title: Erstellen einer .NET Standard-Klassenbibliothek mit C# mit Visual Studio 2017
description: Erfahren Sie, wie Sie eine in C# geschriebene .NET Standard-Klassenbibliothek mithilfe von Visual Studio 2017 erstellen.
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 0c98f8c8fc4847570964d8d4ea8deb221164441d
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168935"
---
# <a name="build-a-net-standard-class-library-with-c-and-the-net-core-sdk-in-visual-studio-2017"></a><span data-ttu-id="58edf-103">Erstellen einer .NET Standard-Klassenbibliothek mit C# und .NET Core SDK in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="58edf-103">Build a .NET Standard class library with C# and the .NET Core SDK in Visual Studio 2017</span></span>

<span data-ttu-id="58edf-104">Eine *Klassenbibliothek* definiert die Typen und Methoden, die von einer Anwendung aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="58edf-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="58edf-105">Eine Klassenbibliothek, die sich auf .NET Standard 2.0 bezieht, ermöglicht das Aufrufen der Bibliothek aus jeder .NET-Implementierung, die diese Version von .NET Standard unterstützt.</span><span class="sxs-lookup"><span data-stu-id="58edf-105">A class library that targets the .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of the .NET Standard.</span></span> <span data-ttu-id="58edf-106">Wenn Sie die Klassenbibliothek fertig stellen, können Sie entscheiden, ob Sie sie als Drittanbieterkomponente verteilen oder als Komponente mit einer oder mehreren Anwendungen in ein Paket einbeziehen möchten.</span><span class="sxs-lookup"><span data-stu-id="58edf-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="58edf-107">Eine Liste der .NET Standard-Versionen und der Plattformen, die sie unterstützen, finden Sie unter [.NET-Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="58edf-107">For a list of the .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="58edf-108">In diesem Thema erstellen Sie eine einfache Hilfsprogrammbibliothek, die eine einzelne Methode zur Behandlung von Zeichenfolgen enthält.</span><span class="sxs-lookup"><span data-stu-id="58edf-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="58edf-109">Sie implementieren sie als [Erweiterungsmethode](../../csharp/programming-guide/classes-and-structs/extension-methods.md), damit sie aufgerufen werden kann, als wäre sie ein Mitglied der <xref:System.String> Klasse.</span><span class="sxs-lookup"><span data-stu-id="58edf-109">You'll implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="creating-a-class-library-solution"></a><span data-ttu-id="58edf-110">Erstellen einer Klassenbibliotheks-Projektmappe</span><span class="sxs-lookup"><span data-stu-id="58edf-110">Creating a class library solution</span></span>

<span data-ttu-id="58edf-111">Zunächst erstellen Sie eine Projektmappe für Ihre Klassenbibliotheksprojekt und die zugehörigen Projekte.</span><span class="sxs-lookup"><span data-stu-id="58edf-111">Start by creating a solution for your class library project and its related projects.</span></span> <span data-ttu-id="58edf-112">Eine Visual Studio-Projektmappe dient nur als Container für ein oder mehrere Projekte.</span><span class="sxs-lookup"><span data-stu-id="58edf-112">A Visual Studio Solution just serves as a container for one or more projects.</span></span> <span data-ttu-id="58edf-113">So erstellen Sie die Projektmappe:</span><span class="sxs-lookup"><span data-stu-id="58edf-113">To create the solution:</span></span>

1. <span data-ttu-id="58edf-114">Wählen Sie auf der Visual Studio-Menüleiste **Datei** > **Neu** > **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="58edf-114">On the Visual Studio menu bar, choose **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="58edf-115">Erweitern Sie im Dialogfeld **Neues Projekt** den Knoten **Andere Projekttypen**, und wählen Sie **Visual Studio-Projektmappen** aus.</span><span class="sxs-lookup"><span data-stu-id="58edf-115">In the **New Project** dialog, expand the **Other Project Types** node, and select **Visual Studio Solutions**.</span></span> <span data-ttu-id="58edf-116">Nennen Sie die Projektmappe „ClassLibraryProjects“, und wählen Sie die **OK**-Schaltfläche aus.</span><span class="sxs-lookup"><span data-stu-id="58edf-116">Name the solution "ClassLibraryProjects" and select the **OK** button.</span></span>

   ![Dialogfeld „Neues Projekt“ mit hervorgehobener neuer leerer Projektmappe](./media/library-with-visual-studio/new-project-dialog.png)

## <a name="creating-the-class-library-project"></a><span data-ttu-id="58edf-118">Erstellen des Klassenbibliotheksprojekts</span><span class="sxs-lookup"><span data-stu-id="58edf-118">Creating the class library project</span></span>

<span data-ttu-id="58edf-119">Erstellen Sie Ihr Klassenbibliotheksprojekt:</span><span class="sxs-lookup"><span data-stu-id="58edf-119">Create your class library project:</span></span>

1. <span data-ttu-id="58edf-120">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappendatei **ClassLibraryProjects**, und wählen Sie im Kontextmenü **Hinzufügen** > **Neues Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="58edf-120">In **Solution Explorer**, right-click on the **ClassLibraryProjects** solution file and from the context menu, select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="58edf-121">Erweitern Sie den Knoten **Visual C#** im Dialogfeld **Neues Projekt hinzufügen**, klicken Sie dann auf den Knoten **.NET Standard** und anschließend auf die Projektvorlage **Klassenbibliothek (.NET Standard)**.</span><span class="sxs-lookup"><span data-stu-id="58edf-121">In the **Add New Project** dialog, expand the **Visual C#** node, then select the **.NET Standard** node followed by the **Class Library (.NET Standard)** project template.</span></span> <span data-ttu-id="58edf-122">Geben Sie im Textfeld **Name** „StringLibrary“ als Namen des Projekts ein.</span><span class="sxs-lookup"><span data-stu-id="58edf-122">In the **Name** text box, enter "StringLibrary" as the name of the project.</span></span> <span data-ttu-id="58edf-123">Wählen Sie **OK**, um das Klassenbibliotheksprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="58edf-123">Select **OK** to create the class library project.</span></span>

   ![Dialogfeld „Neues Bibliotheksprojekt hinzufügen“](./media/library-with-visual-studio/add-new-library-project.png)

   <span data-ttu-id="58edf-125">Das Codefenster öffnet sich dann in der Visual Studio-Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="58edf-125">The code window then opens in the Visual Studio development environment.</span></span>

   ![Visual Studio-Anwendungsfenster, das die den Standardvorlagencode der Klassenbibliothek zeigt](./media/library-with-visual-studio/string-library-project.png)

1. <span data-ttu-id="58edf-127">Stellen Sie sicher, dass die Bibliothek die richtige Version von .NET Standard als Ziel verwendet.</span><span class="sxs-lookup"><span data-stu-id="58edf-127">Check to make sure that our library targets the correct version of the .NET Standard.</span></span> <span data-ttu-id="58edf-128">Klicken Sie mit der rechten Maustaste auf das Bibliotheksprojekt im Fenster des **Projektmappen-Explorer**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="58edf-128">Right-click on the library project in the **Solution Explorer** windows, then select **Properties**.</span></span> <span data-ttu-id="58edf-129">Das Textfeld **Zielframework** zeigt dann, dass .NET Standard 2.0 als Ziel verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="58edf-129">The **Target Framework** text box shows that we're targeting .NET Standard 2.0.</span></span>

   ![Projekteigenschaften für die Klassenbibliothek](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="58edf-131">Ersetzen Sie den Code im Codefenster durch den folgenden Code, und speichern Sie die Datei:</span><span class="sxs-lookup"><span data-stu-id="58edf-131">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   <span data-ttu-id="58edf-132">Die Klassenbibliothek, `UtilityLibraries.StringLibrary`, enthält eine Methode namens `StartsWithUpper`, welche einen <xref:System.Boolean> Wert zurückgibt, der angibt, ob die aktuelle Zeichenfolgeninstanz mit einem Großbuchstaben beginnt.</span><span class="sxs-lookup"><span data-stu-id="58edf-132">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`, which returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="58edf-133">Der Unicode-Standard unterscheidet Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="58edf-133">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="58edf-134">Die Methode <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> gibt `true` zurück, wenn ein Zeichen ein Großbuchstabe ist.</span><span class="sxs-lookup"><span data-stu-id="58edf-134">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="58edf-135">Wählen Sie auf der Menüleiste **Erstellen** > **Projektmappe erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="58edf-135">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="58edf-136">Das Projekt sollte fehlerfrei kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="58edf-136">The project should compile without error.</span></span>

   ![Ausgabebereich, der zeigt, dass der Buildvorgang erfolgreich war](./media/library-with-visual-studio/output-pane-successful-build.png)

## <a name="next-step"></a><span data-ttu-id="58edf-138">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="58edf-138">Next step</span></span>

<span data-ttu-id="58edf-139">Sie haben die Bibliothek erfolgreich erstellt.</span><span class="sxs-lookup"><span data-stu-id="58edf-139">You've successfully built the library.</span></span> <span data-ttu-id="58edf-140">Aber da Sie keine ihrer Methoden aufgerufen haben, wissen Sie nicht, ob sie wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="58edf-140">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="58edf-141">Der nächste Schritt bei der Entwicklung Ihrer Bibliothek ist ihr Test mithilfe eines [Komponententestprojekts](testing-library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="58edf-141">The next step in developing your library is to test it by using a [Unit Test Project](testing-library-with-visual-studio.md).</span></span>