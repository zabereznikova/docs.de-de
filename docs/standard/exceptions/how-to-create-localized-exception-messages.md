---
title: 'Vorgehensweise: Erstellen benutzerdefinierter Ausnahmen mit lokalisierten Ausnahmemeldungen'
description: Erfahren Sie, wie benutzerdefinierte Ausnahmen mit lokalisierten Ausnahmemeldungen erstellt werden.
author: Youssef1313
dev_langs:
- csharp
- vb
ms.date: 09/13/2019
ms.openlocfilehash: 9360fccf27a0900d8380461e03baa5806ce1e0da
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708917"
---
# <a name="how-to-create-user-defined-exceptions-with-localized-exception-messages"></a><span data-ttu-id="4de6b-103">Vorgehensweise: Erstellen benutzerdefinierter Ausnahmen mit lokalisierten Ausnahmemeldungen</span><span class="sxs-lookup"><span data-stu-id="4de6b-103">How to create user-defined exceptions with localized exception messages</span></span>

<span data-ttu-id="4de6b-104">In diesem Artikel erfahren Sie, wie Sie benutzerdefinierte Ausnahmen mit lokalisierten Ausnahmemeldungen mithilfe von Satellitenassemblys erstellen, die von der Basisklasse <xref:System.Exception> geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="4de6b-104">In this article, you will learn how to create user-defined exceptions that are inherited from the base <xref:System.Exception> class with localized exception messages using satellite assemblies.</span></span>

## <a name="create-custom-exceptions"></a><span data-ttu-id="4de6b-105">Erstellen benutzerdefinierter Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="4de6b-105">Create custom exceptions</span></span>

<span data-ttu-id="4de6b-106">.NET enthält viele verschiedene Ausnahmen, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4de6b-106">.NET contains many different exceptions that you can use.</span></span> <span data-ttu-id="4de6b-107">In einigen Fällen, in denen keine von ihnen Ihre Anforderungen erfüllt, können Sie jedoch auch eigene benutzerdefinierte Ausnahmen erstellen.</span><span class="sxs-lookup"><span data-stu-id="4de6b-107">However, in some cases when none of them meets your needs, you can create your own custom exceptions.</span></span>

<span data-ttu-id="4de6b-108">Angenommen, Sie möchten eine `StudentNotFoundException` erstellen, die eine `StudentName`-Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="4de6b-108">Let's assume you want to create a `StudentNotFoundException` that contains a `StudentName` property.</span></span>
<span data-ttu-id="4de6b-109">Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Ausnahme zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="4de6b-109">To create a custom exception, follow these steps:</span></span>

1. <span data-ttu-id="4de6b-110">Erstellen Sie eine serialisierbare Klasse, die von <xref:System.Exception> erbt.</span><span class="sxs-lookup"><span data-stu-id="4de6b-110">Create a serializable class that inherits from <xref:System.Exception>.</span></span> <span data-ttu-id="4de6b-111">Der Klassenname muss auf „Exception“ enden:</span><span class="sxs-lookup"><span data-stu-id="4de6b-111">The class name should end in "Exception":</span></span>

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception { }
    ```
    
    ```vb
    <Serializable>
    Public Class StudentNotFoundException
        Inherits Exception
    End Class
    ```

1. <span data-ttu-id="4de6b-112">Fügen Sie die Standardkonstruktoren hinzu:</span><span class="sxs-lookup"><span data-stu-id="4de6b-112">Add the default constructors:</span></span>

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception
    {
        public StudentNotFoundException() { }

        public StudentNotFoundException(string message)
            : base(message) { }

        public StudentNotFoundException(string message, Exception inner)
            : base(message, inner) { }
    }
    ```
    
    ```vb
    <Serializable>
    Public Class StudentNotFoundException
        Inherits Exception

        Public Sub New()
        End Sub

        Public Sub New(message As String)
            MyBase.New(message)
        End Sub

        Public Sub New(message As String, inner As Exception)
            MyBase.New(message, inner)
        End Sub
    End Class
    ```

1. <span data-ttu-id="4de6b-113">Definieren Sie alle zusätzlichen Eigenschaften und Konstruktoren:</span><span class="sxs-lookup"><span data-stu-id="4de6b-113">Define any additional properties and constructors:</span></span>

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception
    {
        public string StudentName { get; }

        public StudentNotFoundException() { }

        public StudentNotFoundException(string message)
            : base(message) { }

        public StudentNotFoundException(string message, Exception inner)
            : base(message, inner) { }

        public StudentNotFoundException(string message, string studentName)
            : this(message)
        {
            StudentName = studentName;
        }
    }
    ```

    ```vb
    <Serializable>
    Public Class StudentNotFoundException
        Inherits Exception

        Public ReadOnly Property StudentName As String

        Public Sub New()
        End Sub

        Public Sub New(message As String)
            MyBase.New(message)
        End Sub

        Public Sub New(message As String, inner As Exception)
            MyBase.New(message, inner)
        End Sub

        Public Sub New(message As String, studentName As String)
            Me.New(message)
            StudentName = studentName
        End Sub
    End Class
    ```

## <a name="create-localized-exception-messages"></a><span data-ttu-id="4de6b-114">Erstellen lokalisierter Ausnahmemeldungen</span><span class="sxs-lookup"><span data-stu-id="4de6b-114">Create localized exception messages</span></span>

<span data-ttu-id="4de6b-115">Sie haben eine benutzerdefinierte Ausnahme erstellt, und Sie können sie an beliebiger Stelle mit Code wie dem folgenden auslösen:</span><span class="sxs-lookup"><span data-stu-id="4de6b-115">You have created a custom exception, and you can throw it anywhere with code like the following:</span></span>

```csharp
throw new StudentNotFoundException("The student cannot be found.", "John");
```

```vb
Throw New StudentNotFoundException("The student cannot be found.", "John")
```

<span data-ttu-id="4de6b-116">Das Problem mit der vorherigen Zeile besteht darin, dass `"The student cannot be found."` nur eine konstante Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="4de6b-116">The problem with the previous line is that `"The student cannot be found."` is just a constant string.</span></span> <span data-ttu-id="4de6b-117">In einer lokalisierten Anwendung möchten Sie abhängig von der Benutzerkultur verschiedene Meldungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4de6b-117">In a localized application, you want to have different messages depending on user culture.</span></span>
<span data-ttu-id="4de6b-118">[Satellitenassemblys](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md) bieten eine gute Möglichkeit dazu.</span><span class="sxs-lookup"><span data-stu-id="4de6b-118">[Satellite Assemblies](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md) are a good way to do that.</span></span> <span data-ttu-id="4de6b-119">Eine Satellitenassembly ist eine DLL-Datei, die Ressourcen für eine bestimmte Sprache enthält.</span><span class="sxs-lookup"><span data-stu-id="4de6b-119">A satellite assembly is a .dll that contains resources for a specific language.</span></span> <span data-ttu-id="4de6b-120">Wenn Sie zur Laufzeit eine bestimmte Ressource anfordern, ermittelt die CLR diese Ressource abhängig von der Benutzerkultur.</span><span class="sxs-lookup"><span data-stu-id="4de6b-120">When you ask for a specific resources at run time, the CLR finds that resource depending on user culture.</span></span> <span data-ttu-id="4de6b-121">Wenn keine Satellitenassembly für diese Kultur gefunden wird, werden die Ressourcen der Standardkultur verwendet.</span><span class="sxs-lookup"><span data-stu-id="4de6b-121">If no satellite assembly is found for that culture, the resources of the default culture are used.</span></span>

<span data-ttu-id="4de6b-122">So erstellen Sie lokalisierte Ausnahmemeldungen:</span><span class="sxs-lookup"><span data-stu-id="4de6b-122">To create the localized exception messages:</span></span>

1. <span data-ttu-id="4de6b-123">Erstellen Sie einen neuen Ordner mit dem Namen *Resources*, um darin Ressourcendateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4de6b-123">Create a new folder named *Resources* to hold the resource files.</span></span>
1. <span data-ttu-id="4de6b-124">Fügen Sie diesem Ordner eine neue Ressourcendatei hinzu.</span><span class="sxs-lookup"><span data-stu-id="4de6b-124">Add a new resource file to it.</span></span> <span data-ttu-id="4de6b-125">Um dies in Visual Studio auszuführen, klicken Sie mit der rechten Maustaste auf den Ordner im **Projektmappen-Explorer**, und wählen Sie dann **Hinzufügen** > **Neues Element** > **Ressourcendatei** aus.</span><span class="sxs-lookup"><span data-stu-id="4de6b-125">To do that in Visual Studio, right-click the folder in **Solution Explorer**, and select **Add** > **New Item** > **Resources File**.</span></span> <span data-ttu-id="4de6b-126">Nennen Sie die Datei *ExceptionMessages.resx*.</span><span class="sxs-lookup"><span data-stu-id="4de6b-126">Name the file *ExceptionMessages.resx*.</span></span> <span data-ttu-id="4de6b-127">Dies ist die Standardressourcendatei.</span><span class="sxs-lookup"><span data-stu-id="4de6b-127">This is the default resources file.</span></span>
1. <span data-ttu-id="4de6b-128">Fügen Sie ein Name-Wert-Paar für die Ausnahmemeldung hinzu, wie in der folgenden Abbildung gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4de6b-128">Add a name/value pair for your exception message, like the following image shows:</span></span>

   ![Hinzufügen von Ressourcen zur Standardkultur](media/add-resources-to-default-culture.jpg)

1. <span data-ttu-id="4de6b-130">Fügen Sie eine neue Ressourcendatei für Französisch hinzu.</span><span class="sxs-lookup"><span data-stu-id="4de6b-130">Add a new resource file for French.</span></span> <span data-ttu-id="4de6b-131">Nennen Sie sie *ExceptionMessages.fr-FR.resx*.</span><span class="sxs-lookup"><span data-stu-id="4de6b-131">Name it *ExceptionMessages.fr-FR.resx*.</span></span>
1. <span data-ttu-id="4de6b-132">Fügen Sie erneut ein Name-Wert-Paar für die Ausnahmemeldung hinzu, aber mit einem französischen Wert:</span><span class="sxs-lookup"><span data-stu-id="4de6b-132">Add a name/value pair for the exception message again, but with a French value:</span></span>

   ![Hinzufügen von Ressourcen zur Kultur „fr-FR“](media/add-resources-to-fr-culture.jpg)

1. <span data-ttu-id="4de6b-134">Nachdem Sie das Projekt erstellt haben, sollte der Buildausgabeordner den Ordner *fr-FR* mit einer *DLL*-Datei enthalten, bei der es sich um die Satellitenassembly handelt.</span><span class="sxs-lookup"><span data-stu-id="4de6b-134">After you build the project, the build output folder should contain the *fr-FR* folder with a *.dll* file, which is the satellite assembly.</span></span>
1. <span data-ttu-id="4de6b-135">Sie lösen die Ausnahme mit Code wie dem folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="4de6b-135">You throw the exception with code like the following:</span></span>

    ```csharp
    var resourceManager = new ResourceManager("FULLY_QIALIFIED_NAME_OF_RESOURCE_FILE", Assembly.GetExecutingAssembly());
    throw new StudentNotFoundException(resourceManager.GetString("StudentNotFound"), "John");
    ```

    > [!NOTE]
    > <span data-ttu-id="4de6b-136">Wenn der Projektname `TestProject` lautet und die Ressourcendatei *ExceptionMessages.resx* im Ordner *Resources* des Projekts gespeichert ist, lautet der vollqualifizierte Name der Ressourcendatei `TestProject.Resources.ExceptionMessages`.</span><span class="sxs-lookup"><span data-stu-id="4de6b-136">If the project name is `TestProject` and the resource file *ExceptionMessages.resx* resides in the *Resources* folder of the project, the fully qualified name of the resource file is `TestProject.Resources.ExceptionMessages`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4de6b-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4de6b-137">See also</span></span>

- [<span data-ttu-id="4de6b-138">Erstellen benutzerdefinierter Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="4de6b-138">How to create user-defined exceptions</span></span>](how-to-create-user-defined-exceptions.md)
- [<span data-ttu-id="4de6b-139">Erstellen von Satellitenassemblys für Desktop-Apps</span><span class="sxs-lookup"><span data-stu-id="4de6b-139">Creating Satellite Assemblies for Desktop Apps</span></span>](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md)
- [<span data-ttu-id="4de6b-140">base (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4de6b-140">base (C# Reference)</span></span>](../../csharp/language-reference/keywords/base.md)
- [<span data-ttu-id="4de6b-141">this (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4de6b-141">this (C# Reference)</span></span>](../../csharp/language-reference/keywords/this.md)
