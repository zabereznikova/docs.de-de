---
title: 'Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten (C# und Visual Basic)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- dynamic objects [Visual Basic]
- dynamic objects
- dynamic objects [C#]
ms.assetid: 568f1645-1305-4906-8625-5d77af81e04f
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e82af926b9f040fb7c7cabf0dd9babe0b5d44901
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-creating-and-using-dynamic-objects-c-and-visual-basic"></a>Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten (C# und Visual Basic)
Dynamische Objekte machen Member wie etwa Eigenschaften und Methoden zur Laufzeit anstatt zur Kompilierzeit verfügbar. Dadurch können Sie Objekte erstellen, mit denen Sie mit Strukturen arbeiten können, die keinem statischen Typ oder Format entsprechen. Sie können z.B. ein dynamisches Objekt verwenden, um auf das HTML-DOM (Document Object Model) zu verweisen, das eine Kombination aus gültigen HTML-Markupelementen und Attributen enthalten kann. Da jedes HTML-Dokument eindeutig ist, werden die Elemente für ein bestimmtes HTML-Dokument zur Laufzeit bestimmt. Eine gängige Methode zum Verweisen eines Attributes auf ein HTML-Element ist, den Namen des Attributs an die `GetProperty`-Methode des Elements weiterzugeben. Rufen Sie zum Verweisen des `id`-Attributs auf das HTML-Element `<div id="Div1">` zuerst einen Verweis auf das `<div>`-Element ab, und verwenden Sie anschließend `divElement.GetProperty("id")`. Wenn Sie ein dynamisches Objekt verwenden, können Sie auf das `id`-Attribut als `divElement.id` verweisen.  
  
 Dynamische Objekte bieten außerdem einfachen Zugriff auf dynamische Sprachen wie IronPython und IronRuby. Sie können ein dynamisches Objekt verwenden, um sich auf ein dynamisches Skript zu beziehen, das zur Laufzeit ausgeführt wird.  
  
 Sie verweisen auf ein dynamisches Objekt mithilfe der späten Bindung. Geben Sie in C# den Typ eines spät gebundenen Objekts als `dynamic` an. Geben Sie in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] den Typ eines spät gebundenen Objekts als `Object` an. Weitere Informationen finden Sie unter [dynamic](../../../csharp/language-reference/keywords/dynamic.md) und [Frühes und spätes Binden](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md).  
  
 Sie können benutzerdefinierte dynamische Objekte erstellen, indem Sie die Klassen im <xref:System.Dynamic?displayProperty=fullName>-Namespace verwenden. Sie können z.B. ein <xref:System.Dynamic.ExpandoObject> erstellen und die Member dieses Objekts zur Laufzeit angeben. Sie können auch einen eigenen Typ erstellen, der die <xref:System.Dynamic.DynamicObject>-Klasse erbt. Sie können die Member dieser <xref:System.Dynamic.DynamicObject>-Klasse anschließend außer Kraft setzen, um dynamische Funktionen zur Laufzeit bereitzustellen.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie folgende Aufgaben aus:  
  
-   Erstellen Sie ein benutzerdefiniertes Objekt, das die Inhalte einer Textdatei als Eigenschaften eines Objekts weitergibt.  
  
-   Erstellen Sie ein Objekt, das die `IronPython`-Bibliothek verwendet.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Sie benötigen IronPython 2.6.1 für .NET 4.0 für diese exemplarische Vorgehensweise. Sie können IronPython 2.6.1 für .NET 4.0 von [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187223) herunterladen.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-a-custom-dynamic-object"></a>Erstellen eines benutzerdefinierten dynamischen Objekts  
 Das erste Projekt, das Sie in dieser exemplarischen Vorgehensweise erstellen definiert ein benutzerdefiniertes dynamisches Objekt, das die Inhalte einer Textdatei durchsucht. Der Text, nach dem gesucht werden soll, wird vom Namen einer dynamischen Eigenschaft angegeben. Wenn aufrufender Code z.B. `dynamicFile.Sample` angibt, gibt die dynamische Klasse eine generische Liste von Zeichenfolgen zurück, die alle Zeilen aus der Datei enthält, die mit „Sample“ anfangen. Die Groß- und Kleinschreibung wird bei der Suche nicht berücksichtigt. Die dynamische Klasse unterstützt auch zwei optionale Argumente. Das erste Argument ist ein Enumerationswert einer Suchoption, der angibt, dass die dynamische Klasse am Beginn, am Ende oder an einer beliebigen Stelle der Zeile nach Übereinstimmungen suchen soll. Das zweite Argument gibt an, dass die dynamische Klasse führende und nachfolgende Leerzeichen vor dem Suchvorgang aus jeder Zeile entfernen soll. Wenn aufrufender Code z.B. `dynamicFile.Sample(StringSearchOption.Contains)` angibt, sucht die dynamische Klasse an einer beliebigen Stelle in der Zeile nach „Sample“. Wenn der aufrufende Code `dynamicFile.Sample(StringSearchOption.StartsWith, false)` angibt, sucht die dynamische Klasse am Beginn jeder Zeile nach „Sample“ und entfernt keine führenden oder nachfolgenden Leerzeichen. Standardmäßig sucht die dynamische Klasse nach Übereinstimmungen am Beginn jeder Zeile und entfernt führende oder nachfolgende Leerzeichen.  
  
#### <a name="to-create-a-custom-dynamic-class"></a>So erstellen Sie eine benutzerdefinierte dynamische Klasse  
  
1.  Starten Sie [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].  
  
2.  Zeigen Sie im Menü **Datei** auf **Neu** , und klicken Sie dann auf **Projekt**.  
  
3.  Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist. Wählen Sie im Bereich **Vorlagen** die Option **Konsolenanwendung** aus. Geben Sie im Feld **Name** die Bezeichnung `DynamicSample` ein, und klicken Sie dann auf **OK**. Das neue Projekt wird erstellt.  
  
4.  Klicken Sie mit der rechten Maustaste auf das Projekt „DynamicSample“ und halten Sie den Mauszeiger auf **Hinzufügen**. Klicken Sie anschließend auf **Klasse**. Geben Sie im Feld **Name** die Bezeichnung `ReadOnlyFile` ein, und klicken Sie dann auf **OK**. Eine neue Datei wird hinzugefügt, die die Klasse „ReadOnlyFile“ enthält.  
  
5.  Fügen Sie am Anfang der Dateien „ReadOnlyFile.cs“ oder „ReadOnlyFile.vb“ den folgenden Code zum Importieren der <xref:System.IO?displayProperty=fullName>- und <xref:System.Dynamic?displayProperty=fullName>-Namespaces hinzu.  
  
     [!code-cs[VbDynamicWalkthrough#1](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_1.cs)]  [!code-vb[VbDynamicWalkthrough#1](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_1.vb)]  
  
6.  Das benutzerdefinierte dynamische Objekt verwendet einen Enumerationswert, um die Suchkriterien zu bestimmen. Fügen Sie vor der class-Anweisung die folgende Enumerationsdefinition ein.  
  
     [!code-cs[VbDynamicWalkthrough#2](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_2.cs)]  [!code-vb[VbDynamicWalkthrough#2](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_2.vb)]  
  
7.  Aktualisieren Sie die class-Anweisung wie im folgenden Beispiel, um die `DynamicObject`-Klasse zu erben.  
  
     [!code-cs[VbDynamicWalkthrough#3](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_3.cs)]  [!code-vb[VbDynamicWalkthrough#3](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_3.vb)]  
  
8.  Fügen Sie den folgenden Code zur `ReadOnlyFile`-Klasse hinzu, um ein privates Feld für den Dateipfad und einen Konstruktor für die `ReadOnlyFile`-Klasse zu definieren.  
  
     [!code-cs[VbDynamicWalkthrough#4](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_4.cs)]  [!code-vb[VbDynamicWalkthrough#4](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_4.vb)]  
  
9. Fügen Sie die folgende `GetPropertyValue`-Methode zu der `ReadOnlyFile`-Klasse hinzu. Die `GetPropertyValue`-Methode akzeptiert Suchkriterien als Eingabe und gibt die Zeilen aus einer Textdatei zurück, die den Suchkriterien entsprechen. Die von der `ReadOnlyFile`-Klasse bereitgestellten Methoden rufen die `GetPropertyValue`-Methode auf, um ihre entsprechenden Ergebnisse abzurufen.  
  
     [!code-cs[VbDynamicWalkthrough#5](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_5.cs)]   [!code-vb[VbDynamicWalkthrough#5](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_5.vb)]  
  
10. Fügen Sie nach der `GetPropertyValue`-Methode den folgenden Code hinzu, um die <xref:System.Dynamic.DynamicObject.TryGetMember%2A>-Methode der <xref:System.Dynamic.DynamicObject>-Klasse zu überschreiben. Die Methode <xref:System.Dynamic.DynamicObject.TryGetMember%2A> wird aufgerufen, wenn ein Member einer dynamischen Klasse angefordert wird und keine Argumente angegeben werden. Das Argument `binder` enthält Informationen über den Member, auf den verwiesen wurde. Das Argument `result` verweist auf das Ergebnis, das für den angegebenen Member zurückgegeben wird. Die Methode <xref:System.Dynamic.DynamicObject.TryGetMember%2A> gibt einen booleschen Wert zurück, der `true` zurückgibt, wenn der angeforderte Member vorhanden ist; andernfalls wird `false` zurückgegeben.  
  
     [!code-cs[VbDynamicWalkthrough#6](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_6.cs)]  [!code-vb[VbDynamicWalkthrough#6](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_6.vb)]  
  
11. Fügen Sie nach der `TryGetMember`-Methode den folgenden Code hinzu, um die <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A>-Methode der <xref:System.Dynamic.DynamicObject>-Klasse zu überschreiben. Die <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A>-Methode wird aufgerufen, wenn ein Mitglied einer dynamischen Klasse mit Argumenten angefordert wird. Das Argument `binder` enthält Informationen über den Member, auf den verwiesen wurde. Das Argument `result` verweist auf das Ergebnis, das für den angegebenen Member zurückgegeben wird. Das Argument `args` enthält ein Array von Argumenten, die an den Member weitergegeben werden. Die Methode <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A> gibt einen booleschen Wert zurück, der `true` zurückgibt, wenn der angeforderte Member vorhanden ist; andernfalls wird `false` zurückgegeben.  
  
     Die benutzerdefinierte Version der Methode `TryInvokeMember` erwartet, dass es sich beim ersten Argument um einen Wert der `StringSearchOption`-Enumeration handelt, die Sie in einem vorherigen Schritt definiert haben. Die Methode `TryInvokeMember` erwartet, dass es sich beim zweiten Argument um einen booleschen Wert handelt. Wenn es sich bei einem oder beiden Argumenten um gültige Werte handelt, werden sie an die Methode `GetPropertyValue` zum Abrufen der Werte weitergegeben.  
  
     [!code-cs[VbDynamicWalkthrough#7](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_7.cs)]  [!code-vb[VbDynamicWalkthrough#7](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_7.vb)]  
  
12. Speichern und schließen Sie die Datei.  
  
#### <a name="to-create-a-sample-text-file"></a>So erstellen Sie eine Beispieltextdatei  
  
1.  Klicken Sie mit der rechten Maustaste auf das Projekt „DynamicSample“ und halten Sie den Mauszeiger auf **Hinzufügen**. Klicken Sie anschließend auf **Neues Element**. Wählen Sie im Bereich **Installierte Vorlagen** **Allgemein** aus, und wählen Sie anschließend die Vorlage **Textdatei** aus. Übernehmen Sie den Standardnamen der Datei „TextFile1.txt“ im Feld **Name**, und klicken Sie auf **Hinzufügen**. Eine neue Textdatei wird zum Projekt hinzugefügt.  
  
2.  Kopieren Sie den folgenden Text in die Datei „TextFile1.txt“.  
  
    ```  
    List of customers and suppliers  
  
    Supplier: Lucerne Publishing (http://www.lucernepublishing.com/)  
    Customer: Preston, Chris  
    Customer: Hines, Patrick  
    Customer: Cameron, Maria  
    Supplier: Graphic Design Institute (http://www.graphicdesigninstitute.com/)   
    Supplier: Fabrikam, Inc. (http://www.fabrikam.com/)   
    Customer: Seubert, Roxanne  
    Supplier: Proseware, Inc. (http://www.proseware.com/)   
    Customer: Adolphi, Stephan  
    Customer: Koch, Paul  
    ```  
  
3.  Speichern und schließen Sie die Datei.  
  
#### <a name="to-create-a-sample-application-that-uses-the-custom-dynamic-object"></a>So erstellen Sie eine Beispielanwendung, die das benutzerdefinierte dynamische Objekt enthält  
  
1.  Doppelklicken Sie im **Projektmappen-Explorer** auf die Datei „Module1.vb“, wenn Sie [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] verwenden, oder auf die Datei „Program.cs“, wenn Sie Visual C# verwenden.  
  
2.  Fügen Sie den folgenden Code zur Main-Prozedur hinzu, um eine Instanz der Klasse `ReadOnlyFile` für die Datei „TextFile1.txt“ zu erstellen. Der Code verwendet spätes Binden, um dynamische Member aufzurufen und die Textzeilen abzurufen, die die Zeichenfolge „Customer“ (Kunde) enthalten.  
  
     [!code-cs[VbDynamicWalkthrough#8](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_8.cs)]  [!code-vb[VbDynamicWalkthrough#8](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_8.vb)]  
  
3.  Speichern Sie die Datei und drücken Sie STRG+F5, um die Anwendung zu erstellen und auszuführen.  
  
## <a name="calling-a-dynamic-language-library"></a>Aufrufen einer Bibliothek in einer dynamischen Sprache  
 Das nächste Projekt, das Sie in dieser exemplarischen Vorgehensweise erstellen, greift auf eine Bibliothek zu, die in der dynamischen Sprache IronPython geschrieben ist. Bevor Sie dieses Projekt erstellen, müssen Sie IronPython 2.6.1 für .NET 4.0 installieren. Sie können IronPython 2.6.1 für .NET 4.0 von [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187223) herunterladen.  
  
#### <a name="to-create-a-custom-dynamic-class"></a>So erstellen Sie eine benutzerdefinierte dynamische Klasse  
  
1.  Zeigen Sie in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
2.  Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist. Wählen Sie im Bereich **Vorlagen** die Option **Konsolenanwendung** aus. Geben Sie im Feld **Name** die Bezeichnung `DynamicIronPythonSample` ein, und klicken Sie dann auf **OK**. Das neue Projekt wird erstellt.  
  
3.  Klicken Sie, wenn Sie [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] verwenden, mit der rechten Maustaste auf das Projekt „DynamicIronPythonSample“ und klicken Sie dann auf **Eigenschaften**. Klicken Sie auf die Registerkarte **Verweise**. Klicken Sie auf die Schaltfläche **Hinzufügen**. Klicken Sie wenn Sie Visual C# verwenden im **Projektmappen-Explorer** mit der rechten Maustaste auf den Ordner **Verweise** und klicken Sie dann auf **Verweis hinzufügen**.  
  
4.  Navigieren Sie auf der Registerkarte **Durchsuchen** zum Ordner, in dem die IronPython-Bibliotheken installiert sind. Z.B. C:\Programme\IronPython 2.6 für .NET 4.0. Wählen Sie die Bibliotheken **IronPython.dll**, **IronPython.Modules.dll**, **Microsoft.Scripting.dll** und **Microsoft.Dynamic.dll**. Klicken Sie auf **OK**.  
  
5.  Wenn Sie [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] verwenden, bearbeiten Sie die Datei „Module1.vb“. Wenn Sie Visual C# verwenden, bearbeiten Sie die Datei „Program.cs“.  
  
6.  Fügen Sie am Anfang der Datei den folgenden Code zum Importieren der `Microsoft.Scripting.Hosting`- und `IronPython.Hosting`-Namespaces aus den IronPython-Bibliotheken ein.  
  
     [!code-cs[VbDynamicWalkthroughIronPython#1](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_9.cs)]  [!code-vb[VbDynamicWalkthroughIronPython#1](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_9.vb)]  
  
7.  Fügen Sie in der Main-Methode den folgenden Code zum Erstellen eines neuen `Microsoft.Scripting.Hosting.ScriptRuntime`-Objekts zum Hosten der IronPython-Bibliotheken hinzu. Das `ScriptRuntime`-Objekt lädt das IronPython-Bibliotheksmodul „random.py“.  
  
     [!code-cs[VbDynamicWalkthroughIronPython#2](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_10.cs)]  [!code-vb[VbDynamicWalkthroughIronPython#2](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_10.vb)]  
  
8.  Fügen Sie nach dem Code zum Laden des Moduls „random.py“ den folgenden Code zum Erstellen eines Arrays von ganzen Zahlen hinzu. Das Array wird an die `shuffle`-Methode des Moduls „random.py“ übergeben, das die Werte im Array per Zufall sortiert.  
  
     [!code-cs[VbDynamicWalkthroughIronPython#3](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_11.cs)]  [!code-vb[VbDynamicWalkthroughIronPython#3](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_11.vb)]  
  
9. Speichern Sie die Datei und drücken Sie STRG+F5, um die Anwendung zu erstellen und auszuführen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Dynamic?displayProperty=fullName>   
 <xref:System.Dynamic.DynamicObject?displayProperty=fullName>   
 [Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Frühes und spätes Binden](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [Implementieren von dynamischen Schnittstellen (externer Blog)](http://go.microsoft.com/fwlink/?LinkId=230895)

