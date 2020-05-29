---
title: 'Exemplarische Vorgehensweise: Einbetten von Typen verwalteter Assemblys in Visual Studio'
description: In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie mit Visual Studio Typen aus verwalteten Assemblys in .NET einbetten. Eingebettete Typen können Versionsunabhängigkeit unterstützen.
ms.date: 08/19/2019
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
dev_langs:
- csharp
- vb
ms.openlocfilehash: 636e5f8095b64cd0f445555c96d00945ccf7eaf8
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378986"
---
# <a name="walkthrough-embed-types-from-managed-assemblies-in-visual-studio"></a>Exemplarische Vorgehensweise: Einbetten von Typen verwalteter Assemblys in Visual Studio

Wenn Sie Typinformationen von einer verwalteten Assembly mit starkem Namen einbetten, können Sie Typen in einer Anwendung lose koppeln, um versionsunabhängig zu werden. Das heißt, Ihr Programm kann so geschrieben werden, dass Typen aus einer beliebigen Version einer verwalteten Bibliothek verwendet werden, ohne dass es für jede neue Version neu kompiliert werden muss.

Das Einbetten von Typen wird häufig mit COM-Interop verwendet, z.B. mit einer Anwendung, die Automatisierungsobjekte von Microsoft Office verwendet. Das Einbetten von Typinformationen lässt zu, dass derselbe Build eines Programms mit unterschiedlichen Versionen von Microsoft Office auf verschiedenen Computern verwendet werden kann. Allerdings können Sie die Typeinbettung mit vollständig verwalteten Lösungen verwenden.

Nachdem Sie die öffentlichen Schnittstellen angegeben haben, die eingebettet werden können, können Sie Laufzeitklassen erstellen, die diese Schnittstellen implementieren. Ein Clientprogramm kann die Typinformationen für die Schnittstellen zur Entwurfszeit einbetten, indem auf die Assembly verwiesen wird, die die öffentlichen Schnittstellen enthält und die Eigenschaft `Embed Interop Types` des Verweises auf `True` festgelegt wird. Das Clientprogramm kann dann Instanzen Ihrer Laufzeitobjekte laden, die als diese Schnittstellen typisiert sind. Dies entspricht dem Verwenden des Befehlszeilencompilers und Verweisen auf die Assembly mit der [Compileroption -link](../../csharp/language-reference/compiler-options/link-compiler-option.md).

Wenn Sie eine neue Version Ihrer Runtimeassembly mit starkem Namen erstellen, muss das Clientprogramm nicht neu kompiliert werden. Das Clientprogramm verwendet weiterhin die verfügbare Version der Runtimeassembly und die eingebetteten Typinformationen für die öffentlichen Schnittstellen.

In dieser exemplarischen Vorgehensweise:

1. Erstellen Sie eine Assembly mit starkem Namen mit einer öffentlichen Schnittstelle, die Typinformationen enthält, die eingebettet werden können.
1. Erstellen Sie eine Runtimeassembly mit starkem Namen, die diese öffentliche Schnittstelle implementiert.
1. Erstellen Sie ein Clientprogramm, das die Typinformationen aus der öffentlichen Schnittstelle einbettet und eine Instanz der Klasse aus der Runtime-Assembly erstellt.
1. Ändern Sie die Runtime-Assembly, und erstellen Sie sie erneut.
1. Führen Sie das Clientprogramm aus, um zu überprüfen, dass es die neue Version der Runtimeassembly verwendet, ohne eine erneute Kompilierung zu erfordern.

[!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]

## <a name="conditions-and-limitations"></a>Bedingungen und Einschränkungen

Sie können Typinformationen einer Assembly unter folgenden Bedingungen einbetten:

- Die Assembly macht mindestens eine öffentliche Schnittstelle verfügbar.
- Die eingebetteten Schnittstellen werden mit `ComImport`- und `Guid`-Attributen mit eindeutigen GUIDs versehen.
- Die Assembly wird mit dem `ImportedFromTypeLib`-Attribut oder dem `PrimaryInteropAssembly`-Attribut und einem `Guid`-Attribut auf Assemblyebene kommentiert. Die Visual C#- und Visual Basic-Projektvorlagen enthalten standardmäßig ein `Guid`-Attribut auf Assemblyebene.

Da die primäre Funktion der Typeinbettung in der Unterstützung von COM-Interop-Assemblys besteht, gelten die folgenden Einschränkungen, wenn Sie Typinformationen in eine vollständig verwaltete Lösung einbetten:

- Nur die für COM-Interop spezifischen Attribute werden eingebettet. Andere Attribute werden ignoriert.
- Wenn ein Typ generische Parameter verwendet, und der Typ des generischen Parameters ein eingebetteter Typ ist, kann dieser Typ nicht über die Grenze einer Assembly hinaus verwendet werden. Beispiele für das Überschreiten der Grenze einer Assembly umfassen das Aufrufen einer Methode von einer anderen Assembly aus oder das Ableiten eines Typs von einem Typ, der in einer anderen Assembly definiert wurde.
- Konstanten werden nicht eingebettet.
- Die <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>-Klasse unterstützt keinen eingebetteten Typ als Schlüssel. Sie können Ihren eigenen Wörterbuchtyp implementieren, um einen eingebetteten Typ als Schlüssel zu unterstützen.

## <a name="create-an-interface"></a>Erstellen einer Schnittstelle

Der erste Schritt besteht darin, die Schnittstellenassembly mit Typäquivalenz zu erstellen.

1. Klicken Sie in Visual Studio auf **Datei** > **Neu** > **Projekt**.

1. Geben Sie *Klassenbibliothek* im Feld **Nach Vorlagen suchen** des Dialogfelds **Neues Projekt erstellen** ein. Wählen Sie die Vorlage **Klassenbibliothek (.NET Framework)** für C# oder Visual Basic aus der Liste aus, und klicken Sie dann auf **Weiter**.

1. Geben Sie *TypeEquivalenceInterface* im Dialogfeld **Neues Projekt konfigurieren** unter **Projektname** ein, und klicken Sie dann auf **Erstellen**. Das neue Projekt wird erstellt.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei *Class1.cs* oder *Class1.vb*, wählen Sie **Umbenennen** aus, und benennen Sie die Datei *Class1* in *ISampleInterface* um. Wählen Sie bei der Eingabeaufforderung **Ja** aus, um auch die Klasse in `ISampleInterface` umzubenennen. Diese Klasse stellt die öffentliche Schnittstelle für die Klasse dar.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceInterface**, und wählen Sie dann **Eigenschaften** aus.

1. Klicken Sie im linken Bereich der **Eigenschaften** auf **Erstellen**, und legen Sie einen Speicherort auf Ihrem Computer als **Ausgabepfad** fest, z. B. *C:\TypeEquivalenceSample*. Diesen Speicherort werden Sie im Rahmen dieser exemplarischen Vorgehensweise häufiger verwenden.

1. Klicken Sie im linken Bereich der **Eigenschaften** auf **Signierung**, und aktivieren Sie dann das Kontrollkästchen **Assembly signieren**. Klicken Sie im Dropdownfeld **Schlüsseldatei mit starkem Namen auswählen** auf **Neu**.

1. Geben Sie *key.snk* im Dialogfeld **Schlüssel für einen starken Namen erstellen** unter **Schlüsseldateiname** ein. Deaktivieren Sie das Kontrollkästchen **Schlüsseldatei mit Kennwort schützen**, und klicken Sie dann auf **OK**.

1. Öffnen Sie die Klassendatei *ISampleInterface* im Code-Editor, und ersetzen Sie ihren Inhalt durch den folgenden Code, um die `ISampleInterface`-Schnittstelle zu erstellen:

   ```csharp
   using System;
   using System.Runtime.InteropServices;

   namespace TypeEquivalenceInterface
   {
       [ComImport]
       [Guid("8DA56996-A151-4136-B474-32784559F6DF")]
       public interface ISampleInterface
       {
           void GetUserInput();
           string UserInput { get; }
       }
   }
   ```

   ```vb
   Imports System.Runtime.InteropServices

   <ComImport()>
   <Guid("8DA56996-A151-4136-B474-32784559F6DF")>
   Public Interface ISampleInterface
       Sub GetUserInput()
       ReadOnly Property UserInput As String
   End Interface
   ```

1. Klicken Sie im Menü **Extras** auf **GUID erstellen**, und wählen Sie dann im Dialogfeld **GUID erstellen** das **Registrierungsformat** aus. Klicken Sie auf **Kopieren** und dann auf **Beenden**.

1. Ersetzen Sie die Beispiel-GUID im `Guid`-Attribut Ihres Codes durch die kopierte GUID, und entfernen Sie die Klammern ( **{ }** ).

1. Erweitern Sie den Ordner **Eigenschaften** im **Projektmappen-Explorer**, und wählen Sie die Datei *AssemblyInfo.cs* oder *AssemblyInfo.vb* aus. Fügen Sie das folgende Attribut im Code-Editor zur Datei hinzu:

   ```csharp
   [assembly: ImportedFromTypeLib("")]
   ```

   ```vb
   <Assembly: ImportedFromTypeLib("")>
   ```

1. Klicken Sie auf **Datei** > **Alle speichern**, oder drücken Sie **STRG**+**UMSCHALT**+**S**, um die Dateien und das Projekt zu speichern.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceInterface**, und wählen Sie dann **Erstellen** aus. Die DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert, z. B. *C:\TypeEquivalenceSample*.

## <a name="create-a-runtime-class"></a>Erstellen einer Laufzeitklasse

Als Nächstes erstellen Sie die Lauftzeitklasse für die Typäquivalenz.

1. Klicken Sie in Visual Studio auf **Datei** > **Neu** > **Projekt**.

1. Geben Sie *Klassenbibliothek* im Feld **Nach Vorlagen suchen** des Dialogfelds **Neues Projekt erstellen** ein. Wählen Sie die Vorlage **Klassenbibliothek (.NET Framework)** für C# oder Visual Basic aus der Liste aus, und klicken Sie dann auf **Weiter**.

1. Geben Sie *TypeEquivalenceRuntime* unter **Projektname** im Dialogfeld **Neues Projekt konfigurieren** ein, und klicken Sie dann auf **Erstellen**. Das neue Projekt wird erstellt.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei *Class1.cs* oder *Class1.vb*, wählen Sie **Umbenennen** aus, und benennen Sie die Datei *Class1* in *SampleClass* um. Wählen Sie bei der Eingabeaufforderung **Ja** aus, um auch die Klasse in `SampleClass` umzubenennen. Diese Klasse implementiert die `ISampleInterface` -Schnittstelle.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceInterface**, und wählen Sie **Eigenschaften** aus.

1. Klicken Sie im linken Bereich der **Eigenschaften** auf **Erstellen**, und legen Sie dann denselben Speicherort als **Ausgabepfad** fest, den Sie für das TypeEquivalenceInterface-Projekt verwendet haben, z. B. *C:\TypeEquivalenceSample*.

1. Klicken Sie im linken Bereich der **Eigenschaften** auf **Signierung**, und aktivieren Sie dann das Kontrollkästchen **Assembly signieren**. Klicken Sie im Dropdownfeld **Schlüsseldatei mit starkem Namen auswählen** auf **Neu**.

1. Geben Sie *key.snk* im Dialogfeld **Schlüssel für einen starken Namen erstellen** unter **Schlüsseldateiname** ein. Deaktivieren Sie das Kontrollkästchen **Schlüsseldatei mit Kennwort schützen**, und klicken Sie dann auf **OK**.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceRuntime**, und wählen Sie dann **Hinzufügen** > **Verweis** aus.

1. Klicken Sie im Dialogfeld **Verweis-Manager** auf **Durchsuchen**, und navigieren Sie zum Ausgabepfadordner. Wählen Sie die Datei *TypeEquivalenceInterface.dll* aus, und klicken Sie dann auf **Hinzufügen** und auf **OK**.

1. Erweitern Sie im **Projektmappen-Explorer** den Ordner **Verweise**, und wählen Sie den Verweis **TypeEquivalenceInterface** aus. Legen Sie für **Spezifische Version** im Bereich **Eigenschaften** die Option **FALSE** fest, wenn das noch nicht der Fall ist.

1. Öffnen Sie die Klassendatei *SampleClass* im Code-Editor, und ersetzen Sie ihren Inhalt durch den folgenden Code, um die `SampleClass`-Klasse zu erstellen:

   ```csharp
   using System;
   using TypeEquivalenceInterface;

   namespace TypeEquivalenceRuntime
   {
       public class SampleClass : ISampleInterface
       {
           private string p_UserInput;
           public string UserInput { get { return p_UserInput; } }

           public void GetUserInput()
           {
               Console.WriteLine("Please enter a value:");
               p_UserInput = Console.ReadLine();
           }
       }
   }
   ```

   ```vb
   Imports TypeEquivalenceInterface

   Public Class SampleClass
       Implements ISampleInterface

       Private p_UserInput As String
       Public ReadOnly Property UserInput() As String Implements ISampleInterface.UserInput
           Get
               Return p_UserInput
           End Get
       End Property

       Public Sub GetUserInput() Implements ISampleInterface.GetUserInput
           Console.WriteLine("Please enter a value:")
           p_UserInput = Console.ReadLine()
       End Sub
   End Class
   ```

1. Klicken Sie auf **Datei** > **Alle speichern**, oder drücken Sie **STRG**+**UMSCHALT**+**S**, um die Dateien und das Projekt zu speichern.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceRuntime**, und wählen Sie dann **Erstellen** aus. Die DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert.

## <a name="create-a-client-project"></a>Erstellen eines Clientprojekts

Schließlich erstellen Sie ein Typäquivalenz-Clientprogramm, das auf die Schnittstellenassembly verweist.

1. Klicken Sie in Visual Studio auf **Datei** > **Neu** > **Projekt**.

1. Geben Sie *Konsole* im Feld **Nach Vorlagen suchen** des Dialogfelds **Neues Projekt erstellen** ein. Wählen Sie die Vorlage **Konsolen-App (.NET Framework)** für C# oder Visual Basic aus der Liste aus, und klicken Sie dann auf **Weiter**.

1. Geben Sie *TypeEquivalenceClient* unter **Projektname** im Dialogfeld **Neues Projekt konfigurieren** ein, und klicken Sie dann auf **Erstellen**. Das neue Projekt wird erstellt.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceClient**, und wählen Sie dann **Eigenschaften** aus.

1. Klicken Sie im linken Bereich der **Eigenschaften** auf **Erstellen**, und legen Sie dann denselben Speicherort als **Ausgabepfad** fest, den Sie für das TypeEquivalenceInterface-Projekt verwendet haben, z. B. *C:\TypeEquivalenceSample*.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceClient**, und wählen Sie dann **Hinzufügen** > **Verweis** aus.

1. Wenn die Datei **TypeEquivalenceInterface.dll** bereits im Dialogfeld **Verweis-Manager** aufgeführt wird, wählen Sie sie aus. Wenn nicht, klicken Sie auf **Durchsuchen**, navigieren Sie zum Ausgabepfadordner, wählen Sie die Datei *TypeEquivalenceInterface.dll* aus (nicht die Datei *TypeEquivalenceRuntime.dll*), und klicken Sie schließlich auf **Hinzufügen**. Klicken Sie auf **OK**.

1. Erweitern Sie im **Projektmappen-Explorer** den Ordner **Verweise**, und wählen Sie den Verweis **TypeEquivalenceInterface** aus. Legen Sie für **Interoptypen einbetten** im Bereich **Eigenschaften** die Option **TRUE** fest.

1. Öffnen Sie die Datei *Program.cs* oder *Module1.vb* im Code-Editor, und ersetzen Sie ihren Inhalt durch den folgenden Code, um das Clientprogramm zu erstellen:

   ```csharp
   using System;
   using System.Reflection;
   using TypeEquivalenceInterface;

   namespace TypeEquivalenceClient
   {
       class Program
       {
           static void Main(string[] args)
           {
               Assembly sampleAssembly = Assembly.Load("TypeEquivalenceRuntime");
               ISampleInterface sampleClass =
                   (ISampleInterface)sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass");
               sampleClass.GetUserInput();
               Console.WriteLine(sampleClass.UserInput);
               Console.WriteLine(sampleAssembly.GetName().Version.ToString());
               Console.ReadLine();
           }
       }
   }
   ```

   ```vb
   Imports System.Reflection
   Imports TypeEquivalenceInterface

   Module Module1

       Sub Main()
           Dim sampleAssembly = Assembly.Load("TypeEquivalenceRuntime")
           Dim sampleClass As ISampleInterface = CType( _
               sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass"), ISampleInterface)
           sampleClass.GetUserInput()
           Console.WriteLine(sampleClass.UserInput)
           Console.WriteLine(sampleAssembly.GetName().Version)
           Console.ReadLine()
       End Sub

   End Module
   ```

1. Klicken Sie auf **Datei** > **Alle speichern**, oder drücken Sie **STRG**+**UMSCHALT**+**S**, um die Dateien und das Projekt zu speichern.

1. Drücken Sie **STRG**+**F5**, um das Programm zu erstellen und auszuführen. Beachten Sie, dass die Konsolenausgabe die Assemblyversion **1.0.0.0** zurückgibt.

## <a name="modify-the-interface"></a>Anpassen der Schnittstelle

Im Folgenden passen Sie de Schnittstellenassembly an und ändern ihre Version.

1. Klicken Sie in Visual Studio auf **Datei** > **Öffnen** > **Projekt/Projektmappe**, und öffnen Sie das Projekt **TypeEquivalenceInterface**.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceInterface**, und wählen Sie **Eigenschaften** aus.

1. Klicken Sie im linken Bereich der **Eigenschaften** auf **Anwendung**, und klicken Sie dann auf **Assemblyinformationen**.

1. Ändern Sie die Werte für **Assemblyversion** und **Dateiversion** im Dialogfeld **Assemblyinformationen** in *2.0.0.0*, und klicken Sie dann auf **OK**.

1. Öffnen Sie die Datei *SampleInterface.cs* oder *SampleInterface.vb*, und fügen Sie die folgende Codezeile zur `ISampleInterface`-Schnittstelle hinzu:

   ```csharp
   DateTime GetDate();
   ```

   ```vb
   Function GetDate() As Date
   ```

1. Klicken Sie auf **Datei** > **Alle speichern**, oder drücken Sie **STRG**+**UMSCHALT**+**S**, um die Dateien und das Projekt zu speichern.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceInterface**, und wählen Sie dann **Erstellen** aus. Eine neue Version der DLL-Datei für die Klassenbibliothek wird kompiliert und im Buildausgabepfad gespeichert.

## <a name="modify-the-runtime-class"></a>Anpassen der Laufzeitklasse

Ändern Sie außerdem die Laufzeitklasse, und aktualisieren Sie ihre Version.

1. Klicken Sie in Visual Studio auf **Datei** > **Öffnen** > **Projekt/Projektmappe**, und öffnen Sie das Projekt **TypeEquivalenceRuntime**.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceRuntime**, und wählen Sie dann **Eigenschaften** aus.

1. Klicken Sie im linken Bereich der **Eigenschaften** auf **Anwendung**, und klicken Sie dann auf **Assemblyinformationen**.

1. Ändern Sie die Werte für **Assemblyversion** und **Dateiversion** im Dialogfeld **Assemblyinformationen** in *2.0.0.0*, und klicken Sie dann auf **OK**.

1. Öffnen Sie die Datei *SampleClass.cs* oder *SampleClass.vb*, und fügen Sie den folgenden Code zur `SampleClass`-Klasse hinzu:

   ```csharp
    public DateTime GetDate()
    {
        return DateTime.Now;
    }
   ```

   ```vb
   Public Function GetDate() As DateTime Implements ISampleInterface.GetDate
       Return Now
   End Function
   ```

1. Klicken Sie auf **Datei** > **Alle speichern**, oder drücken Sie **STRG**+**UMSCHALT**+**S**, um die Dateien und das Projekt zu speichern.

1. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt **TypeEquivalenceRuntime**, und wählen Sie dann **Erstellen** aus. Eine neue Version der DLL-Datei für die Klassenbibliothek wird kompiliert und im Buildausgabepfad gespeichert.

## <a name="run-the-updated-client-program"></a>Ausführen des aktualisierten Clientprogramms

Öffnen Sie den Speicherort des Buildausgabeordners, und führen Sie die Datei *TypeEquivalenceClient.exe* aus. Beachten Sie, dass die Konsolenausgabe nun die neue Version der `TypeEquivalenceRuntime`-Assembly (*2.0.0.0*) darstellt, ohne dass das Programm neu kompiliert werden musste.

## <a name="see-also"></a>Siehe auch

- [-link (C#-Compileroptionen)](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md)
- [C#-Programmierhandbuch](../../csharp/programming-guide/index.md)
- [Programmierkonzepte (Visual Basic)](../../visual-basic/programming-guide/concepts/index.md)
- [Assemblys in .NET](index.md)
