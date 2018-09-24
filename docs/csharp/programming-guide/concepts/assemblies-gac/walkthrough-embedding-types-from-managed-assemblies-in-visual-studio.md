---
title: 'Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (C#)'
ms.date: 07/20/2015
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
ms.openlocfilehash: 1900c62d1ebaf611f141f8f1bdf95f8d11f82140
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46004324"
---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-c"></a>Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (C#)
Wenn Sie Typinformationen von einer verwalteten Assembly mit starkem Namen einbetten, können Sie Typen in einer Anwendung lose koppeln, um versionsunabhängig zu werden. Ihr Programm kann daher für Typen aus unterschiedlichen Versionen einer verwalteten Bibliothek geschrieben werden; eine erneute Kompilierung für jede Version ist nicht erforderlich.  
  
 Das Einbetten von Typen wird häufig mit COM-Interop verwendet, z.B. mit einer Anwendung, die Automatisierungsobjekte von Microsoft Office verwendet. Das Einbetten von Typinformationen lässt zu, dass derselbe Build eines Programms mit unterschiedlichen Versionen von Microsoft Office auf verschiedenen Computern verwendet werden kann. Sie können das Einbetten von Typen jedoch auch mit einer vollständig verwalteten Anwendung verwenden.  
  
 Typinformationen können von einer Assembly aus eingebettet werden, die die folgenden Merkmale aufweist:  
  
-   Die Assembly macht mindestens eine öffentliche Schnittstelle verfügbar.  
  
-   Die eingebetteten Schnittstellen werden mit einem `ComImport`-Attribut und einem `Guid`-Attribut (und einer eindeutigen GUID) kommentiert.  
  
-   Die Assembly wird mit dem `ImportedFromTypeLib`-Attribut oder dem `PrimaryInteropAssembly`-Attribut und einem `Guid`-Attribut auf Assemblyebene kommentiert. (Standardmäßig enthalten Visual C#-Projektvorlagen ein `Guid`-Attribut auf Assemblyebene.)  
  
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
  
1.  Wählen Sie in Visual Studio im Menü **Datei** die Option **Neu** aus, und klicken Sie auf **Projekt**.  
  
2.  Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist. Wählen Sie im Bereich **Vorlagen** die Option **Klassenbibliothek** aus. Geben Sie im Feld **Name** die Bezeichnung `TypeEquivalenceInterface` ein, und klicken Sie dann auf **OK**. Das neue Projekt wird erstellt.  
  
3.  Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei „Class1.cs“, und klicken Sie auf **Umbenennen**. Benennen Sie die Datei in `ISampleInterface.cs` um, und drücken Sie die EINGABETASTE. Durch Umbenennen der Datei wird die Klasse ebenfalls in `ISampleInterface` umbenannt. Diese Klasse stellt die öffentliche Schnittstelle für die Klasse dar.  
  
4.  Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Eigenschaften**. Klicken Sie auf die Registerkarte **Erstellen**. Legen Sie den Ausgabepfad auf einen gültigen Speicherort auf dem Entwicklungscomputer fest, z.B. auf `C:\TypeEquivalenceSample`. Dieser Speicherort wird auch in einem späteren Schritt in dieser exemplarischen Vorgehensweise verwendet.  
  
5.  Klicken Sie auf die Schaltfläche **Signierung**, während Sie noch die Projekteigenschaften bearbeiten. Wählen Sie die Option **Assembly signieren** aus. Klicken Sie in der Liste **Schlüsseldatei mit starkem Namen auswählen** auf **<Neu...>**. Geben Sie im Feld **Schlüsseldateiname** `key.snk`ein. Deaktivieren Sie das Kontrollkästchen **Schlüsseldatei mit Kennwort schützen**. Klicken Sie auf **OK**.  
  
6.  Öffnen Sie die Datei „ISampleInterface.cs“. Fügen Sie den folgenden Code zur Klasse „ISampleInterface“ hinzu, um die ISampleInterface-Schnittstelle zu erstellen.  
  
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
  
7.  Klicken Sie im Menü **Extras** auf den Befehl **GUID erstellen**. Klicken Sie im Dialogfeld **GUID erstellen** auf **Registrierungsformat** und anschließend auf **Kopieren**. Klicken Sie auf **Schließen**.  
  
8.  Löschen Sie die Beispiel-GUID im Attribut `Guid`, und fügen Sie die GUID ein, die Sie aus dem Dialogfeld **GUID erstellen** kopiert haben. Entfernen Sie die geschweiften Klammern ({}) aus der kopierten GUID.  
  
9. Erweitern Sie im **Projektmappen-Explorer** den Ordner **Eigenschaften**. Doppelklicken Sie auf die Datei „AssemblyInfo.cs“. Fügen Sie folgendes Attribut zur Datei hinzu.  
  
    ```csharp  
    [assembly: ImportedFromTypeLib("")]  
    ```  
  
     Speichern Sie die Datei.  
  
10. Speichern Sie das Projekt.  
  
11. Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Erstellen**. Die DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).  
  
## <a name="creating-a-runtime-class"></a>Erstellen einer Runtime-Klasse  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a>So erstellen Sie das Runtime-Projekt mit Typäquivalenz  
  
1.  Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.  
  
2.  Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist. Wählen Sie im Bereich **Vorlagen** die Option **Klassenbibliothek** aus. Geben Sie im Feld **Name** die Bezeichnung `TypeEquivalenceRuntime` ein, und klicken Sie dann auf **OK**. Das neue Projekt wird erstellt.  
  
3.  Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei „Class1.cs“, und klicken Sie auf **Umbenennen**. Benennen Sie die Datei in `SampleClass.cs` um, und drücken Sie die EINGABETASTE. Durch Umbenennen der Datei wird die Klasse ebenfalls in `SampleClass` umbenannt. Diese Klasse implementiert die `ISampleInterface`-Schnittstelle.  
  
4.  Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Eigenschaften**. Klicken Sie auf die Registerkarte **Erstellen**. Legen Sie den Ausgabepfad auf denselben Speicherort fest, den Sie im Projekt „TypeEquivalenceInterface“ verwendet haben, z.B. auf `C:\TypeEquivalenceSample`.  
  
5.  Klicken Sie auf die Schaltfläche **Signierung**, während Sie noch die Projekteigenschaften bearbeiten. Wählen Sie die Option **Assembly signieren** aus. Klicken Sie in der Liste **Schlüsseldatei mit starkem Namen auswählen** auf **<Neu...>**. Geben Sie im Feld **Schlüsseldateiname** `key.snk`ein. Deaktivieren Sie das Kontrollkästchen **Schlüsseldatei mit Kennwort schützen**. Klicken Sie auf **OK**.  
  
6.  Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Verweis hinzufügen**. Klicken Sie auf die Registerkarte **Durchsuchen**, und navigieren Sie zum Ausgabeordner für den Pfad. Wählen Sie die Datei „TypeEquivalenceInterface.dll“ aus, und klicken Sie auf **OK**.  
  
7.  Erweitern Sie im **Projektmappen-Explorer** den Ordner **Verweise**. Wählen Sie den Verweis „TypeEquivalenceInterface“ aus. Legen Sie im Eigenschaftenfenster für den Verweis „TypeEquivalenceInterface“ die Eigenschaft **Spezifische Version** auf **False** fest.  
  
8.  Fügen Sie den folgenden Code zur Klassendatei „SampleClass“ hinzu, um die Klasse SampleClass zu erstellen.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
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
    )  
    ```  
  
9. Speichern Sie das Projekt.  
  
10. Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Erstellen**. Die DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).  
  
## <a name="creating-a-client-project"></a>Erstellen eines Clientprojekts  
  
#### <a name="to-create-the-type-equivalence-client-project"></a>So erstellen Sie das Clientprojekt mit Typäquivalenz  
  
1.  Zeigen Sie in Visual Studio im Menü **Datei** auf **Neu**, und klicken Sie auf **Projekt**.  
  
2.  Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist. Wählen Sie im Bereich **Vorlagen** die Option **Konsolenanwendung** aus. Geben Sie im Feld **Name** die Bezeichnung `TypeEquivalenceClient` ein, und klicken Sie dann auf **OK**. Das neue Projekt wird erstellt.  
  
3.  Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceClient“, und klicken Sie auf **Eigenschaften**. Klicken Sie auf die Registerkarte **Erstellen**. Legen Sie den Ausgabepfad auf denselben Speicherort fest, den Sie im Projekt „TypeEquivalenceInterface“ verwendet haben, z.B. auf `C:\TypeEquivalenceSample`.  
  
4.  Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceClient“, und klicken Sie auf **Verweis Hinzufügen**. Klicken Sie auf die Registerkarte **Durchsuchen**, und navigieren Sie zum Ausgabeordner für den Pfad. Wählen Sie die Datei „TypeEquivalenceInterface.dll“ aus (nicht „TypeEquivalenceRuntime.dll“), und klicken Sie auf **OK**.  
  
5.  Erweitern Sie im **Projektmappen-Explorer** den Ordner **Verweise**. Wählen Sie den Verweis „TypeEquivalenceInterface“ aus. Legen Sie im Eigenschaftenfenster für den Verweis „TypeEquivalenceInterface“ die Eigenschaft **Einbetten von Interop-Typen** auf **True** fest.  
  
6.  Fügen Sie folgenden Code zur Datei „Program.cs“ hinzu, um das Clientprogramm zu erstellen.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using TypeEquivalenceInterface;  
    using System.Reflection;  
  
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
  
7.  Drücken Sie STRG+F5, um das Programm zu erstellen und auszuführen.  
  
## <a name="modifying-the-interface"></a>Ändern der Schnittstelle  
  
#### <a name="to-modify-the-interface"></a>So ändern Sie die Schnittstelle  
  
1.  Zeigen Sie in Visual Studio im Menü **Datei** auf **Öffnen**, und klicken Sie auf **Projekt/Projektmappe**.  
  
2.  Klicken Sie im Dialogfeld **Projekt öffnen** mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Eigenschaften**. Klicken Sie auf die Registerkarte **Anwendung** . Klicken Sie auf die Schaltfläche **Assemblyinformationen**. Ändern Sie die Werte der **Assemblyversion** und der **Dateiversion** in `2.0.0.0`.  
  
3.  Öffnen Sie die Datei „SampleInterface.cs“. Fügen Sie der ISampleInterface-Schnittstelle die folgende Codezeile hinzu.  
  
    ```csharp  
    DateTime GetDate();  
    ```  
  
     Speichern Sie die Datei.  
  
4.  Speichern Sie das Projekt.  
  
5.  Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceInterface“, und klicken Sie auf **Erstellen**. Eine neue Version der DLL-Datei der Klassenbibliothek wird kompiliert und im angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).  
  
## <a name="modifying-the-runtime-class"></a>Ändern der Runtime-Klasse  
  
#### <a name="to-modify-the-runtime-class"></a>So ändern Sie die Runtime-Klasse  
  
1.  Zeigen Sie in Visual Studio im Menü **Datei** auf **Öffnen**, und klicken Sie auf **Projekt/Projektmappe**.  
  
2.  Klicken Sie im Dialogfeld **Projekt öffnen** mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Eigenschaften**. Klicken Sie auf die Registerkarte **Anwendung** . Klicken Sie auf die Schaltfläche **Assemblyinformationen**. Ändern Sie die Werte der **Assemblyversion** und der **Dateiversion** in `2.0.0.0`.  
  
3.  Öffnen Sie die Datei „SampleClass.cs“. Fügen Sie folgenden Codezeilen zur Klasse „SampleClass“ hinzu.  
  
    ```csharp  
    public DateTime GetDate()  
    {  
        return DateTime.Now;  
    }  
    ```  
  
     Speichern Sie die Datei.  
  
4.  Speichern Sie das Projekt.  
  
5.  Klicken Sie mit der rechten Maustaste auf das Projekt „TypeEquivalenceRuntime“, und klicken Sie auf **Erstellen**. Eine aktualisierte Version der DLL-Datei der Klassenbibliothek wird kompiliert und im vorher angegebenen Buildausgabepfad gespeichert (z.B. C:\TypeEquivalenceSample).  
  
6.  Öffnen Sie im Datei-Explorer den Ordner mit dem Ausgabepfad (z.B. C:\TypeEquivalenceSample). Doppelklicken Sie auf die Datei „TypeEquivalenceClient.exe“, um das Programm auszuführen. Das Programm reflektiert die neue Version der TypeEquivalenceRuntime-Assembly, ohne dass sie erneut kompiliert werden muss.  
  
## <a name="see-also"></a>Siehe auch

- [-link (C#-Compileroptionen)](../../../../csharp/language-reference/compiler-options/link-compiler-option.md)  
- [C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md)  
- [Programmieren mit Assemblys](../../../../framework/app-domains/programming-with-assemblies.md)  
- [Assemblies and the Global Assembly Cache (C#) (Assemblys und der globale Assemblycache (C#))](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)
