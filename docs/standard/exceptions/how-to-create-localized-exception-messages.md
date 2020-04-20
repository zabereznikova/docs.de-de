---
title: 'Vorgehensweise: Erstellen benutzerdefinierter Ausnahmen mit lokalisierten Ausnahmemeldungen'
description: Erfahren Sie, wie benutzerdefinierte Ausnahmen mit lokalisierten Ausnahmemeldungen erstellt werden.
author: Youssef1313
dev_langs:
- csharp
- vb
ms.date: 09/13/2019
ms.openlocfilehash: fa0bbfdbfc9408302eec2edd4e4ee4503d2612c7
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243348"
---
# <a name="how-to-create-user-defined-exceptions-with-localized-exception-messages"></a>Vorgehensweise: Erstellen benutzerdefinierter Ausnahmen mit lokalisierten Ausnahmemeldungen

In diesem Artikel erfahren Sie, wie Sie benutzerdefinierte Ausnahmen mit lokalisierten Ausnahmemeldungen mithilfe von Satellitenassemblys erstellen, die von der Basisklasse <xref:System.Exception> geerbt werden.

## <a name="create-custom-exceptions"></a>Erstellen benutzerdefinierter Ausnahmen

.NET enthält viele verschiedene Ausnahmen, die Sie verwenden können. In einigen Fällen, in denen keine von ihnen Ihre Anforderungen erfüllt, können Sie jedoch auch eigene benutzerdefinierte Ausnahmen erstellen.

Angenommen, Sie möchten eine `StudentNotFoundException` erstellen, die eine `StudentName`-Eigenschaft enthält.
Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Ausnahme zu erstellen:

1. Erstellen Sie eine serialisierbare Klasse, die von <xref:System.Exception> erbt. Der Klassenname muss auf „Exception“ enden:

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

1. Fügen Sie die Standardkonstruktoren hinzu:

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

1. Definieren Sie alle zusätzlichen Eigenschaften und Konstruktoren:

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

## <a name="create-localized-exception-messages"></a>Erstellen lokalisierter Ausnahmemeldungen

Sie haben eine benutzerdefinierte Ausnahme erstellt, und Sie können sie an beliebiger Stelle mit Code wie dem folgenden auslösen:

```csharp
throw new StudentNotFoundException("The student cannot be found.", "John");
```

```vb
Throw New StudentNotFoundException("The student cannot be found.", "John")
```

Das Problem mit der vorherigen Zeile besteht darin, dass `"The student cannot be found."` nur eine konstante Zeichenfolge ist. In einer lokalisierten Anwendung möchten Sie abhängig von der Benutzerkultur verschiedene Meldungen verwenden.
[Satellitenassemblys](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md) bieten eine gute Möglichkeit dazu. Eine Satellitenassembly ist eine DLL-Datei, die Ressourcen für eine bestimmte Sprache enthält. Wenn Sie zur Laufzeit eine bestimmte Ressource anfordern, ermittelt die CLR diese Ressource abhängig von der Benutzerkultur. Wenn keine Satellitenassembly für diese Kultur gefunden wird, werden die Ressourcen der Standardkultur verwendet.

So erstellen Sie lokalisierte Ausnahmemeldungen:

1. Erstellen Sie einen neuen Ordner mit dem Namen *Resources*, um darin Ressourcendateien zu speichern.
1. Fügen Sie diesem Ordner eine neue Ressourcendatei hinzu. Um dies in Visual Studio auszuführen, klicken Sie mit der rechten Maustaste auf den Ordner im **Projektmappen-Explorer**, und wählen Sie dann **Hinzufügen** > **Neues Element** > **Ressourcendatei** aus. Nennen Sie die Datei *ExceptionMessages.resx*. Dies ist die Standardressourcendatei.
1. Fügen Sie ein Name-Wert-Paar für die Ausnahmemeldung hinzu, wie in der folgenden Abbildung gezeigt:

   ![Hinzufügen von Ressourcen zur Standardkultur](media/add-resources-to-default-culture.jpg)

1. Fügen Sie eine neue Ressourcendatei für Französisch hinzu. Nennen Sie sie *ExceptionMessages.fr-FR.resx*.
1. Fügen Sie erneut ein Name-Wert-Paar für die Ausnahmemeldung hinzu, aber mit einem französischen Wert:

   ![Hinzufügen von Ressourcen zur Kultur „fr-FR“](media/add-resources-to-fr-culture.jpg)

1. Nachdem Sie das Projekt erstellt haben, sollte der Buildausgabeordner den Ordner *fr-FR* mit einer *DLL*-Datei enthalten, bei der es sich um die Satellitenassembly handelt.
1. Sie lösen die Ausnahme mit Code wie dem folgenden aus:

    ```csharp
    var resourceManager = new ResourceManager("FULLY_QUALIFIED_NAME_OF_RESOURCE_FILE", Assembly.GetExecutingAssembly());
    throw new StudentNotFoundException(resourceManager.GetString("StudentNotFound"), "John");
    ```

    ```vb
    Dim resourceManager As New ResourceManager("FULLY_QUALIFIED_NAME_OF_RESOURCE_FILE", Assembly.GetExecutingAssembly())
    Throw New StudentNotFoundException(resourceManager.GetString("StudentNotFound"), "John")
    ```

    > [!NOTE]
    > Wenn der Projektname `TestProject` lautet und die Ressourcendatei *ExceptionMessages.resx* im Ordner *Resources* des Projekts gespeichert ist, lautet der vollqualifizierte Name der Ressourcendatei `TestProject.Resources.ExceptionMessages`.

## <a name="see-also"></a>Weitere Informationen

- [Erstellen benutzerdefinierter Ausnahmen](how-to-create-user-defined-exceptions.md)
- [Erstellen von Satellitenassemblys für Desktop-Apps](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md)
- [base (C#-Referenz)](../../csharp/language-reference/keywords/base.md)
- [this (C#-Referenz)](../../csharp/language-reference/keywords/this.md)
