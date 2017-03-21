---
title: 'Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 56ed12ba-adff-4e9c-a668-7fcba80c4795
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: adc58e081cd9b874a841d84b11d92cbffb6ba6b8
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-visual-basic"></a>Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio (Visual Basic)
Wenn Sie Typinformationen von einer verwalteten Assembly mit starkem Namen einbetten, können Sie Typen in einer Anwendung versionsunabhängig lose gekoppelt. Also kann Ihr Programm geschrieben werden, um Typen aus unterschiedlichen Versionen einer verwalteten Bibliothek zu verwenden, ohne dass für jede Version neu kompiliert werden.  
  
 Einbetten von Typ dienen häufig mit COM-Interop, z. B. eine Anwendung, die Automatisierungsobjekte von Microsoft Office verwendet. Einbetten von Typinformationen kann ein Build eines Programms verschiedene Versionen von Microsoft Office auf unterschiedlichen Computern arbeiten. Sie können jedoch auch Typ eine vollständig verwaltete Lösung einbetten.  
  
 Typinformationen kann aus einer Assembly eingebettet werden, die folgende Merkmale aufweist:  
  
-   Die Assembly macht mindestens eine öffentliche Schnittstelle verfügbar.  
  
-   Die eingebetteten Schnittstellen werden mit versehen einer `ComImport` Attribut und ein `Guid` -Attribut (und eine eindeutige GUID).  
  
-   Die Assembly mit dem versehen ist die `ImportedFromTypeLib` Attribut oder `PrimaryInteropAssembly` -Attribut, und eine Assembly-Ebene `Guid` Attribut. (Visual Basic-Projektvorlagen enthalten standardmäßig eine Assembly-Ebene `Guid` Attribut.)  
  
 Nachdem Sie die öffentlichen Schnittstellen angegeben haben, die eingebettet werden können, können Sie Laufzeitklassen erstellen, die diese Schnittstellen implementieren. Ein Clientprogramm können Sie die Typinformationen für diese Schnittstellen zur Entwurfszeit durch Verweisen auf die Assembly mit den öffentlichen Schnittstellen und Einstellung Einbetten der `Embed Interop Types` -Eigenschaft des Verweises auf `True`. Dies entspricht dem Verwenden des Befehlszeilencompilers und verweisen auf die Assembly mit der `/link` -Compileroption. Die Client-Anwendung kann dann Instanzen der Common Language Runtime-Objekte als Schnittstellen geladen werden. Wenn Sie eine neue Version einer Assembly mit starkem Namen Runtime erstellen, muss die Client-Anwendung nicht mit der aktualisierten Laufzeitassembly neu kompiliert werden. Stattdessen wird das Clientprogramm verwenden, unabhängig davon, welche Version der Common Language Runtime-Assembly verfügbar, verwenden die eingebetteten Typinformationen für die öffentlichen Schnittstellen.  
  
 Da die primäre Funktion von Typ einbetten unterstützen das Einbetten von Typinformationen aus COM-Interop-Assemblys ist, gelten die folgenden Einschränkungen beim Einbetten von Typinformationen in eine vollständig verwaltete Lösung:  
  
-   Nur die COM-Interop spezifische Attribute werden eingebettet; andere Attribute werden ignoriert.  
  
-   Wenn ein Typ generische Parameter verwendet, und der Typ des generischen Parameters ein eingebetteter Typ ist, kann dieses Typs über eine Assembly hinweg verwendet werden. Beispiele für das Überschreiten einer Assemblygrenze einschließen Aufrufen einer Methode in einer anderen Assembly oder Ableiten eines Typs von einem Typ in einer anderen Assembly definiert.  
  
-   Konstanten werden nicht eingebettet.  
  
-   Die <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>Klasse unterstützt keine eingebetteten Typ als Schlüssel.</xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> Sie können einen eigenen Wörterbuchtyp zur Unterstützung von eingebetteten Typs als Schlüssel implementieren.  
  
 In dieser exemplarischen Vorgehensweise werden Sie Folgendes ein:  
  
-   Erstellen Sie eine Assembly mit starkem Namen, die eine öffentliche Schnittstelle Typinformationen eingebettet werden kann.  
  
-   Erstellen Sie eine Laufzeitassembly mit starkem Namen, die diese öffentliche Schnittstelle implementiert.  
  
-   Erstellen Sie ein Clientprogramm, bettet die Typinformationen aus der öffentlichen Schnittstelle und erstellt eine Instanz der Klasse aus der Laufzeitassembly.  
  
-   Ändern und die Common Language Runtime-Assembly neu.  
  
-   Führen Sie die Client-Anwendung zu erkennen, dass die neue Version der Common Language Runtime-Assembly verwendet wird, ohne dass das Clientprogramm neu kompiliert.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-an-interface"></a>Erstellen einer Schnittstelle  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a>Zum Erstellen des Typs Äquivalenz Schnittstelle-Projekts  
  
1.  In Visual Studio auf die **Datei** auf **neu** , und klicken Sie dann auf **Projekt**.  
  
2.  In der **neues Projekt** im Feld der **Projekttypen** Bereich, stellen Sie sicher, dass **Windows** ausgewählt ist. Wählen Sie **-Klassenbibliothek** in der **Vorlagen** Bereich. In der **Namen** geben `TypeEquivalenceInterface`, und klicken Sie dann auf **OK**. Das neue Projekt wird erstellt.  
  
3.  In **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei "Class1.vb" um, und klicken Sie auf **umbenennen**. Benennen Sie die Datei `ISampleInterface.vb` , und drücken Sie die EINGABETASTE. Umbenennen der Datei wird auch die Klasse umbenennen `ISampleInterface`. Diese Klasse stellt die öffentliche Schnittstelle für die Klasse dar.  
  
4.  Mit der rechten Maustaste TypeEquivalenceInterface-Projekt, und klicken Sie auf **Eigenschaften**. Klicken Sie auf die **Kompilieren** Registerkarte. Legen Sie den Ausgabepfad auf einen gültigen Speicherort auf dem Entwicklungscomputer wie `C:\TypeEquivalenceSample`. Dieser Speicherort wird auch in einem späteren Schritt in dieser exemplarischen Vorgehensweise verwendet werden.  
  
5.  Ohne die Bearbeitung der Projekteigenschaften, klicken Sie auf die **Signierung** Registerkarte. Wählen Sie die **zum Signieren der Assembly** Option. In der **Schlüsseldatei mit starkem Namen auswählen** auf ** <New...> **.</New...> In der **Schlüsseldateiname** geben `key.snk`. Deaktivieren der **Schlüsseldatei mit Kennwort schützen** das Kontrollkästchen. Klicken Sie auf **OK**.  
  
6.  Öffnen Sie die Datei ISampleInterface.vb. Fügen Sie den folgenden Code in der Klassendatei ISampleInterface ISampleInterface-Schnittstelle zu erstellen.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
7.  Auf der **Tools** Menü klicken Sie auf **Guid erstellen**. In der **GUID erstellen** im Dialogfeld klicken Sie auf **Registrierungsformat** , und klicken Sie dann auf **Kopie**. Klicken Sie auf **beenden**.  
  
8.  In der `Guid` -Attribut, löschen Sie die Beispiel-GUID aus, und fügen Sie die GUID, die Sie kopiert haben die **GUID erstellen** Dialogfeld. Entfernen Sie die geschweiften Klammern ({}) aus der kopierten GUID.  
  
9. Auf der **Projekt** Menü klicken Sie auf **alle Dateien anzeigen**.  
  
10. In **Projektmappen-Explorer**, erweitern Sie die **Mein Projekt** Ordner. Doppelklicken Sie auf die Datei AssemblyInfo.vb. Fügen Sie der Datei das folgende Attribut hinzu.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
     Speichern Sie die Datei.  
  
11. Speichern Sie das Projekt.  
  
12. Mit der rechten Maustaste TypeEquivalenceInterface-Projekt, und klicken Sie auf **erstellen**. Die Klasse Library-DLL-Datei wird kompiliert und die angegebenen Buildausgabepfad (z. B. C:\TypeEquivalenceSample) gespeichert.  
  
## <a name="creating-a-runtime-class"></a>Erstellen einer Common Language Runtime-Klasse  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a>Zum Erstellen des Typs Äquivalenz Common Language Runtime-Projekts  
  
1.  In Visual Studio auf die **Datei** auf **neu** , und klicken Sie dann auf **Projekt**.  
  
2.  In der **neues Projekt** im Feld der **Projekttypen** Bereich, stellen Sie sicher, dass **Windows** ausgewählt ist. Wählen Sie **-Klassenbibliothek** in der **Vorlagen** Bereich. In der **Namen** geben `TypeEquivalenceRuntime`, und klicken Sie dann auf **OK**. Das neue Projekt wird erstellt.  
  
3.  In **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei "Class1.vb" um, und klicken Sie auf **umbenennen**. Benennen Sie die Datei `SampleClass.vb` , und drücken Sie die EINGABETASTE. Die Datei auch umbenennen, wird die Klasse `SampleClass`. Diese Klasse implementiert die `ISampleInterface` Schnittstelle.  
  
4.  Mit der rechten Maustaste des TypeEquivalenceRuntime-Projekts, und klicken Sie auf **Eigenschaften**. Klicken Sie auf die **Kompilieren** Registerkarte. Legen Sie den Ausgabepfad an demselben Speicherort in das TypeEquivalenceInterface-Projekt, z. B. verwendet `C:\TypeEquivalenceSample`.  
  
5.  Ohne die Bearbeitung der Projekteigenschaften, klicken Sie auf die **Signierung** Registerkarte. Wählen Sie die **zum Signieren der Assembly** Option. In der **Schlüsseldatei mit starkem Namen auswählen** auf ** <New...> **.</New...> In der **Schlüsseldateiname** geben `key.snk`. Deaktivieren der **Schlüsseldatei mit Kennwort schützen** das Kontrollkästchen. Klicken Sie auf **OK**.  
  
6.  Mit der rechten Maustaste des TypeEquivalenceRuntime-Projekts, und klicken Sie auf **Verweis hinzufügen**. Klicken Sie auf die **Durchsuchen** Registerkarte, und navigieren Sie in den Ausgabeordner für den Pfad. Wählen Sie die Datei "TypeEquivalenceInterface.dll" aus, und klicken Sie auf **OK**.  
  
7.  Auf der **Projekt** Menü klicken Sie auf **alle Dateien anzeigen**.  
  
8.  In **Projektmappen-Explorer**, erweitern Sie die **Verweise** Ordner. Wählen Sie den TypeEquivalenceInterface-Verweis. Legen Sie im Eigenschaftenfenster für den TypeEquivalenceInterface-Verweis, der **bestimmte Version** -Eigenschaft **False**.  
  
9. Fügen Sie den folgenden Code in der Klassendatei SampleClass SampleClass-Klasse zu erstellen.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
10. Speichern Sie das Projekt.  
  
11. Mit der rechten Maustaste des TypeEquivalenceRuntime-Projekts, und klicken Sie auf **erstellen**. Die Klasse Library-DLL-Datei wird kompiliert und die angegebenen Buildausgabepfad (z. B. C:\TypeEquivalenceSample) gespeichert.  
  
## <a name="creating-a-client-project"></a>Erstellen ein Clientprojekt  
  
#### <a name="to-create-the-type-equivalence-client-project"></a>Typ Äquivalenz Client-Projekt erstellen  
  
1.  In Visual Studio auf die **Datei** auf **neu** , und klicken Sie dann auf **Projekt**.  
  
2.  In der **neues Projekt** im Feld der **Projekttypen** Bereich, stellen Sie sicher, dass **Windows** ausgewählt ist. Wählen Sie **Konsolenanwendung** in der **Vorlagen** Bereich. In der **Namen** geben `TypeEquivalenceClient`, und klicken Sie dann auf **OK**. Das neue Projekt wird erstellt.  
  
3.  Mit der rechten Maustaste des TypeEquivalenceClient-Projekts, und klicken Sie auf **Eigenschaften**. Klicken Sie auf die **Kompilieren** Registerkarte. Legen Sie den Ausgabepfad an demselben Speicherort in das TypeEquivalenceInterface-Projekt, z. B. verwendet `C:\TypeEquivalenceSample`.  
  
4.  Mit der rechten Maustaste des TypeEquivalenceClient-Projekts, und klicken Sie auf **Verweis hinzufügen**. Klicken Sie auf die **Durchsuchen** Registerkarte, und navigieren Sie in den Ausgabeordner für den Pfad. Wählen Sie die Datei "TypeEquivalenceInterface.dll" aus (und nicht die Datei "TypeEquivalenceRuntime.dll"), und klicken Sie auf **OK**.  
  
5.  Auf der **Projekt** Menü klicken Sie auf **alle Dateien anzeigen**.  
  
6.  In **Projektmappen-Explorer**, erweitern Sie die **Verweise** Ordner. Wählen Sie den TypeEquivalenceInterface-Verweis. Legen Sie im Eigenschaftenfenster für den TypeEquivalenceInterface-Verweis, der **Embed Interop Types** -Eigenschaft **True**.  
  
7.  Fügen Sie den folgenden Code in die Datei "Module1.vb" die Client-Anwendung zu erstellen.  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
8.  Drücken Sie STRG + F5 zum Erstellen und Ausführen des Programms.  
  
## <a name="modifying-the-interface"></a>Ändern der Schnittstelle  
  
#### <a name="to-modify-the-interface"></a>So ändern Sie die Schnittstelle  
  
1.  In Visual Studio auf die **Datei** auf **öffnen**, und klicken Sie dann auf **Projekt/Projektmappe**.  
  
2.  In der **Projekt öffnen** klicken Sie im Dialogfeld mit der rechten Maustaste TypeEquivalenceInterface-Projekt, und klicken Sie dann auf **Eigenschaften**. Klicken Sie auf die Registerkarte **Anwendung** . Klicken Sie auf die **Assemblyinformationen** Schaltfläche. Ändern der **Assemblyversion** und **Dateiversion** Werte `2.0.0.0`.  
  
3.  Öffnen Sie die Datei ISampleInterface.vb. Fügen Sie der ISampleInterface-Schnittstelle die folgende Codezeile hinzu.  
  
<CodeContentPlaceHolder>4</CodeContentPlaceHolder>  
     Speichern Sie die Datei.  
  
4.  Speichern Sie das Projekt.  
  
5.  Mit der rechten Maustaste TypeEquivalenceInterface-Projekt, und klicken Sie auf **erstellen**. Eine neue Version der Klasse Library-DLL-Datei ist kompiliert und im angegebenen Buildausgabepfad (z. B. C:\TypeEquivalenceSample) gespeichert.  
  
## <a name="modifying-the-runtime-class"></a>Ändern der Laufzeitklasse  
  
#### <a name="to-modify-the-runtime-class"></a>So ändern Sie die Common Language Runtime-Klasse  
  
1.  In Visual Studio auf die **Datei** auf **öffnen**, und klicken Sie dann auf **Projekt/Projektmappe**.  
  
2.  In der **Projekt öffnen** Dialogfeld Feld rechten Maustaste auf das TypeEquivalenceRuntime-Projekt aus, und klicken Sie auf **Eigenschaften**. Klicken Sie auf die Registerkarte **Anwendung** . Klicken Sie auf die **Assemblyinformationen** Schaltfläche. Ändern der **Assemblyversion** und **Dateiversion** Werte `2.0.0.0`.  
  
3.  Öffnen Sie die SampleClass.vbfile. Fügen Sie der SampleClass-Klasse die folgenden Codezeilen hinzu.  
  
```vb  
Public Function GetDate() As DateTime Implements ISampleInterface.GetDate  
    Return Now  
End Function  
```  
  
     Save the file.  
  
4.  Speichern Sie das Projekt.  
  
5.  Mit der rechten Maustaste des TypeEquivalenceRuntime-Projekts, und klicken Sie auf **erstellen**. Eine aktualisierte Version der Klasse Library-DLL-Datei wird kompiliert und im zuvor angegebenen Buildausgabepfad (z. B. C:\TypeEquivalenceSample) gespeichert.  
  
6.  Öffnen Sie im Datei-Explorer den Ausgabeordner Pfad (z. B. C:\TypeEquivalenceSample). Doppelklicken Sie auf die TypeEquivalenceClient.exe um das Programm auszuführen. Die Anwendung wird die neue Version der TypeEquivalenceRuntime-Assembly aktualisiert, ohne dass neu kompiliert worden.  
  
## <a name="see-also"></a>Siehe auch  
 [/ Link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md)   
 [Programmierkonzepte](../../../../visual-basic/programming-guide/concepts/index.md)   
 [Programmieren mit Assemblys](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)   
 [Assemblys und dem globalen Assemblycache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)

