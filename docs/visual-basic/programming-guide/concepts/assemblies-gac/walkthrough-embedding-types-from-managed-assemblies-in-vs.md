---
title: 'Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 56ed12ba-adff-4e9c-a668-7fcba80c4795
ms.openlocfilehash: 1f6176746b783d020c809fb0b5d55d741ce0148b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644185"
---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-visual-basic"></a>Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (Visual Basic)
Wenn Sie Typinformationen von einer verwalteten Assembly mit starkem Namen einbetten, können Sie Typen in einer Anwendung lose koppeln, um versionsunabhängig zu werden. Ihr Programm kann daher für Typen aus unterschiedlichen Versionen einer verwalteten Bibliothek geschrieben werden; eine erneute Kompilierung für jede Version ist nicht erforderlich.  
  
 Das Einbetten von Typen wird häufig mit COM-Interop verwendet, z.B. mit einer Anwendung, die Automatisierungsobjekte von Microsoft Office verwendet. Das Einbetten von Typinformationen lässt zu, dass derselbe Build eines Programms mit unterschiedlichen Versionen von Microsoft Office auf verschiedenen Computern verwendet werden kann. Sie können das Einbetten von Typen jedoch auch mit einer vollständig verwalteten Anwendung verwenden.  
  
 Typinformationen können von einer Assembly aus eingebettet werden, die die folgenden Merkmale aufweist:  
  
-   Die Assembly macht mindestens eine öffentliche Schnittstelle verfügbar.  
  
-   Die eingebetteten Schnittstellen werden mit einem `ComImport`-Attribut und einem `Guid`-Attribut (und einer eindeutigen GUID) kommentiert.  
  
-   Die Assembly wird mit dem `ImportedFromTypeLib`-Attribut oder dem `PrimaryInteropAssembly`-Attribut und einem `Guid`-Attribut auf Assemblyebene kommentiert. (Visual Basic-Projektvorlagen enthalten standardmäßig einen auf Assemblyebene `Guid` Attribut.)  
  
 Nachdem Sie die öffentlichen Schnittstellen angegeben haben, die eingebettet werden können, können Sie Laufzeitklassen erstellen, die diese Schnittstellen implementieren. Ein Clientprogramm kann dann die Typinformationen für diese Schnittstellen zur Entwurfszeit einbetten, indem auf die Assembly verwiesen wird, die die öffentlichen Schnittstellen enthält und die Eigenschaft `Embed Interop Types` des Verweises auf `True` festgelegt wird. Dies entspricht dem Verwenden des Befehlszeilencompilers und Verweisen auf die Assembly mit der Compileroption `/link`. Das Clientprogramm kann dann Instanzen Ihrer Laufzeitobjekte laden, die als diese Schnittstellen typisiert sind. Wenn Sie eine neue Version Ihrer Runtime-Assembly mit starkem Namen erstellen, muss das Clientprogramm nicht erneut mit der aktualisierten Runtime-Assembly kompiliert werden. Stattdessen verwendet das Clientprogramm weiterhin die verfügbare Version der Runtime-Assembly und verwendet die eingebetteten Typinformationen für die öffentlichen Schnittstellen.  
  
 Da die primäre Funktion des Einbettens von Typen die Unterstützung des Einbettens von Typinformationen von COM-Interop-Assemblys ist, gelten die folgenden Einschränkungen, wenn Sie Typinformationen in eine vollständig verwaltete Lösung einbetten:  
  
-   Nur die für COM-Interop spezifischen Attribute werden eingebettet; andere Attribute werden ignoriert.  
  
-   Wenn ein Typ generische Parameter verwendet, und der Typ des generischen Parameters ein eingebetteter Typ ist, kann dieser Typ nicht über die Grenze einer Assembly hinaus verwendet werden. Beispiele für das Überschreiten der Grenze einer Assembly umfassen das Aufrufen einer Methode von einer anderen Assembly aus oder das Ableiten eines Typs von einem Typ, der in einer anderen Assembly definiert wurde.  
  
-   Konstanten werden nicht eingebettet.  
  
-   Die <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>-Klasse unterstützt keinen eingebetteten Typ als Schlüssel. Sie können Ihren eigenen Wörterbuchtyp implementieren, um einen eingebetteten Typ als Schlüssel zu unterstützen.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:  
  
-   Erstellen Sie eine Assembly mit starkem Namen mit einer öffentlichen Schnittstelle, die Typinformationen enthält, die eingebettet werden können.  
  
-   Erstellen Sie eine Runtime-Assembly mit starkem Namen, die diese öffentliche Schnittstelle implementiert.  
  
-   Erstellen Sie ein Clientprogramm, das die Typinformationen aus der öffentlichen Schnittstelle einbettet und eine Instanz der Klasse aus der Runtime-Assembly erstellt.  
  
-   Ändern Sie die Runtime-Assembly, und erstellen Sie sie erneut.  
  
-   Führen Sie das Clientprogramm aus, um zu prüfen, dass die neue Version der Runtime-Assembly verwendet wird, ohne dass das Clientprogramm erneut kompiliert werden muss.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-an-interface"></a>Erstellen einer Schnittstelle  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a>So erstellen Sie das Schnittstellenprojekt mit Typäquivalenz  
  
1.  Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.  
  
2.  Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist. Wählen Sie im Bereich **Vorlagen** die Option **Klassenbibliothek** aus. Geben Sie im Feld **Name** die Bezeichnung `TypeEquivalenceInterface` ein, und klicken Sie dann auf **OK**. Das neue Projekt wird erstellt.  
  
3.  In **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei Class1.vb, und klicken Sie auf **umbenennen**. Benennen Sie die Datei in `ISampleInterface.vb` um, und drücken Sie die EINGABETASTE. Durch Umbenennen der Datei wird die Klasse ebenfalls in `ISampleInterface` umbenannt. Diese Klasse stellt die öffentliche Schnittstelle für die Klasse dar.  
  
4.  Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Eigenschaften**. Klicken Sie auf die Registerkarte **Kompilieren**. Legen Sie den Ausgabepfad auf einen gültigen Speicherort auf dem Entwicklungscomputer fest, z.B. auf `C:\TypeEquivalenceSample`. Dieser Speicherort wird auch in einem späteren Schritt in dieser exemplarischen Vorgehensweise verwendet.  
  
5.  Klicken Sie auf die Schaltfläche **Signierung**, während Sie noch die Projekteigenschaften bearbeiten. Wählen Sie die Option **Assembly signieren** aus. Klicken Sie in der Liste **Schlüsseldatei mit starkem Namen auswählen** auf **<Neu...>**. Geben Sie im Feld **Schlüsseldateiname** `key.snk`ein. Deaktivieren Sie das Kontrollkästchen **Schlüsseldatei mit Kennwort schützen**. Klicken Sie auf **OK**.  
  
6.  Öffnen Sie die ISampleInterface.vb-Datei. Fügen Sie den folgenden Code zur Klasse „ISampleInterface“ hinzu, um die ISampleInterface-Schnittstelle zu erstellen.  
  
    ```vb  
    Imports System.Runtime.InteropServices  
  
    <ComImport()>  
    <Guid("8DA56996-A151-4136-B474-32784559F6DF")>  
    Public Interface ISampleInterface  
        Sub GetUserInput()  
        ReadOnly Property UserInput As String  
    End Interface  
    ```  
  
7.  Klicken Sie im Menü **Extras** auf den Befehl **GUID erstellen**. Klicken Sie im Dialogfeld **GUID erstellen** auf **Registrierungsformat** und anschließend auf **Kopieren**. Klicken Sie auf **Schließen**.  
  
8.  Löschen Sie die Beispiel-GUID im Attribut `Guid`, und fügen Sie die GUID ein, die Sie aus dem Dialogfeld **GUID erstellen** kopiert haben. Entfernen Sie die geschweiften Klammern ({}) aus der kopierten GUID.  
  
9. Klicken Sie im Menü **Projekt** auf **Alle Dateien anzeigen**.  
  
10. In **Projektmappen-Explorer**, erweitern Sie die **Mein Projekt** Ordner. Doppelklicken Sie auf die Datei AssemblyInfo.vb. Fügen Sie folgendes Attribut zur Datei hinzu.  
  
    ```vb  
    <Assembly: ImportedFromTypeLib("")>  
    ```  
  
     Speichern Sie die Datei.  
  
11. Speichern Sie das Projekt.  
  
12. Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Erstellen**. Die DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).  
  
## <a name="creating-a-runtime-class"></a>Erstellen einer Runtime-Klasse  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a>So erstellen Sie das Runtime-Projekt mit Typäquivalenz  
  
1.  Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.  
  
2.  Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist. Wählen Sie im Bereich **Vorlagen** die Option **Klassenbibliothek** aus. Geben Sie im Feld **Name** die Bezeichnung `TypeEquivalenceRuntime` ein, und klicken Sie dann auf **OK**. Das neue Projekt wird erstellt.  
  
3.  In **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei Class1.vb, und klicken Sie auf **umbenennen**. Benennen Sie die Datei in `SampleClass.vb` um, und drücken Sie die EINGABETASTE. Durch Umbenennen der Datei wird die Klasse ebenfalls in `SampleClass` umbenannt. Diese Klasse implementiert die `ISampleInterface`-Schnittstelle.  
  
4.  Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Eigenschaften**. Klicken Sie auf die Registerkarte **Kompilieren**. Legen Sie den Ausgabepfad auf denselben Speicherort fest, den Sie im Projekt „TypeEquivalenceInterface“ verwendet haben, z.B. auf `C:\TypeEquivalenceSample`.  
  
5.  Klicken Sie auf die Schaltfläche **Signierung**, während Sie noch die Projekteigenschaften bearbeiten. Wählen Sie die Option **Assembly signieren** aus. Klicken Sie in der Liste **Schlüsseldatei mit starkem Namen auswählen** auf **<Neu...>**. Geben Sie im Feld **Schlüsseldateiname** `key.snk`ein. Deaktivieren Sie das Kontrollkästchen **Schlüsseldatei mit Kennwort schützen**. Klicken Sie auf **OK**.  
  
6.  Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Verweis hinzufügen**. Klicken Sie auf die Registerkarte **Durchsuchen**, und navigieren Sie zum Ausgabeordner für den Pfad. Wählen Sie die Datei „TypeEquivalenceInterface.dll“ aus, und klicken Sie auf **OK**.  
  
7.  Klicken Sie im Menü **Projekt** auf **Alle Dateien anzeigen**.  
  
8.  Erweitern Sie im **Projektmappen-Explorer** den Ordner **Verweise**. Wählen Sie den Verweis „TypeEquivalenceInterface“ aus. Legen Sie im Eigenschaftenfenster für den Verweis „TypeEquivalenceInterface“ die Eigenschaft **Spezifische Version** auf **False** fest.  
  
9. Fügen Sie den folgenden Code zur Klassendatei „SampleClass“ hinzu, um die Klasse SampleClass zu erstellen.  
  
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
  
10. Speichern Sie das Projekt.  
  
11. Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Erstellen**. Die DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).  
  
## <a name="creating-a-client-project"></a>Erstellen eines Clientprojekts  
  
#### <a name="to-create-the-type-equivalence-client-project"></a>So erstellen Sie das Clientprojekt mit Typäquivalenz  
  
1.  Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.  
  
2.  Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist. Wählen Sie im Bereich **Vorlagen** die Option **Konsolenanwendung** aus. Geben Sie im Feld **Name** die Bezeichnung `TypeEquivalenceClient` ein, und klicken Sie dann auf **OK**. Das neue Projekt wird erstellt.  
  
3.  Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceClient“, und klicken Sie auf **Eigenschaften**. Klicken Sie auf die Registerkarte **Kompilieren**. Legen Sie den Ausgabepfad auf denselben Speicherort fest, den Sie im Projekt „TypeEquivalenceInterface“ verwendet haben, z.B. auf `C:\TypeEquivalenceSample`.  
  
4.  Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceClient“, und klicken Sie auf **Verweis Hinzufügen**. Klicken Sie auf die Registerkarte **Durchsuchen**, und navigieren Sie zum Ausgabeordner für den Pfad. Wählen Sie die Datei „TypeEquivalenceInterface.dll“ aus (nicht „TypeEquivalenceRuntime.dll“), und klicken Sie auf **OK**.  
  
5.  Klicken Sie im Menü **Projekt** auf **Alle Dateien anzeigen**.  
  
6.  Erweitern Sie im **Projektmappen-Explorer** den Ordner **Verweise**. Wählen Sie den Verweis „TypeEquivalenceInterface“ aus. Legen Sie im Eigenschaftenfenster für den Verweis „TypeEquivalenceInterface“ die Eigenschaft **Einbetten von Interop-Typen** auf **True** fest.  
  
7.  Fügen Sie den folgenden Code, um die Datei "Module1.vb" So erstellen Sie die Clientprogramm.  
  
    ```vb  
    Imports TypeEquivalenceInterface  
    Imports System.Reflection  
  
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
  
8.  Drücken Sie STRG+F5, um das Programm zu erstellen und auszuführen.  
  
## <a name="modifying-the-interface"></a>Ändern der Schnittstelle  
  
#### <a name="to-modify-the-interface"></a>So ändern Sie die Schnittstelle  
  
1.  Zeigen Sie in Visual Studio im Menü **Datei** auf **Öffnen**, und klicken Sie auf **Projekt/Projektmappe**.  
  
2.  Klicken Sie im Dialogfeld **Projekt öffnen** mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Eigenschaften**. Klicken Sie auf die Registerkarte **Anwendung** . Klicken Sie auf die Schaltfläche **Assemblyinformationen**. Ändern Sie die Werte der **Assemblyversion** und der **Dateiversion** in `2.0.0.0`.  
  
3.  Öffnen Sie die ISampleInterface.vb-Datei. Fügen Sie der ISampleInterface-Schnittstelle die folgende Codezeile hinzu.  
  
    ```vb  
    Function GetDate() As Date  
    ```  
  
     Speichern Sie die Datei.  
  
4.  Speichern Sie das Projekt.  
  
5.  Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Erstellen**. Eine neue Version der DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).  
  
## <a name="modifying-the-runtime-class"></a>Ändern der Runtime-Klasse  
  
#### <a name="to-modify-the-runtime-class"></a>So ändern Sie die Runtime-Klasse  
  
1.  Zeigen Sie in Visual Studio im Menü **Datei** auf **Öffnen**, und klicken Sie auf **Projekt/Projektmappe**.  
  
2.  Klicken Sie im Dialogfeld **Projekt öffnen** mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Eigenschaften**. Klicken Sie auf die Registerkarte **Anwendung** . Klicken Sie auf die Schaltfläche **Assemblyinformationen**. Ändern Sie die Werte der **Assemblyversion** und der **Dateiversion** in `2.0.0.0`.  
  
3.  Öffnen Sie die SampleClass.vbfile. Fügen Sie folgenden Codezeilen zur Klasse „SampleClass“ hinzu.  
  
```vb  
Public Function GetDate() As DateTime Implements ISampleInterface.GetDate  
    Return Now  
End Function  
```  
  
     Save the file.  
  
4.  Speichern Sie das Projekt.  
  
5.  Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Erstellen**. Eine aktualisierte Version der DLL-Datei der Klassenbibliothek wird kompiliert und im vorher angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).  
  
6.  Öffnen Sie im Datei-Explorer den Ordner mit dem Ausgabepfad (z.B. C:\TypeEquivalenceSample). Doppelklicken Sie auf die Datei „TypeEquivalenceClient.exe“, um das Programm auszuführen. Das Programm reflektiert die neue Version der TypeEquivalenceRuntime-Assembly, ohne dass sie erneut kompiliert werden muss.  
  
## <a name="see-also"></a>Siehe auch  
 [/link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)  
 [Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md)  
 [Programmieren mit Assemblys](../../../../framework/app-domains/programming-with-assemblies.md)  
 [Assemblys und der globale Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
