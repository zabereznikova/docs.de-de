---
title: "Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten (C# und Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Dynamische Objekte"
  - "Dynamische Objekte [C#]"
  - "Dynamische Objekte [Visual Basic]"
ms.assetid: 568f1645-1305-4906-8625-5d77af81e04f
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten (C# und Visual Basic)
Dynamische Objekte stellen Member, z. B. Eigenschaften oder Methoden, anstatt zum Zeitpunkt der Kompilierung zur Laufzeit bereit.  So können Objekte erstellt werden, die mit Strukturen funktionieren, die keine Entsprechung in einem statischen Typ oder Format finden.  Sie können das HTML\-Dokument\-Objektmodell \(DOM\), das eine beliebige Kombination von gültigen HTML\-Markup\-Elementen und Attributen enthalten kann, mithilfe eines dynamischen Objekts mit Verweisen versehen.  Da jedes HTML\-Dokument eindeutig ist, werden die Member für ein bestimmtes HTML\-Dokument zur Laufzeit bestimmt.  Eine gängige Methode für das Hinzufügen eines Verweises zu einem Attribut eines HTML\-Elements ist die Weitergabe des Attributnamens an die `GetProperty`\-Methode des Elements.  Rufen Sie zuerst einen Verweis auf das `<div>`\-Element ab, und verwenden Sie dann `divElement.GetProperty("id")`, um auf das `id`\-Attribut des HTML\-Elements `<div id="Div1">` zu verweisen.  Wenn Sie ein dynamisches Objekt verwenden, können Sie auf das `id`\-Attribut als `divElement.id` verweisen.  
  
 Dynamische Objekte bieten außerdem einfachen Zugriff auf dynamische Sprachen, z. B. IronPython und IronRuby.  Sie können ein dynamisches Objekt verwenden, um auf ein dynamisches Skript zu verweisen, das zur Laufzeit interpretiert wird.  
  
 Sie versehen ein dynamisches Objekt mithilfe der Funktion zur späten Bindung mit einem Verweis.  In C\# geben Sie den Typ eines spät gebundenen Objekts als `dynamic` an.  In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] geben Sie den Typ eines spät gebundenen Objekts als `Object` an.  Weitere Informationen finden Sie unter [dynamic](../../../csharp/language-reference/keywords/dynamic.md) und [Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md).  
  
 Sie können benutzerdefinierte dynamische Objekte mit den Klassen im <xref:System.Dynamic?displayProperty=fullName>\-Namespace erstellen.  Sie können z. B. ein <xref:System.Dynamic.ExpandoObject> erstellen und die Member dieses Objekts zur Laufzeit angeben.  Sie können auch einen eigenen Typ erstellen, der die <xref:System.Dynamic.DynamicObject>\-Klasse erbt.  Anschließend können Sie die Member der <xref:System.Dynamic.DynamicObject>\-Klasse überschreiben, um laufzeitbezogene dynamische Funktionalität bereitzustellen.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise erfahren Sie, wie folgende Aufgaben ausgeführt werden:  
  
-   Erstellen eines benutzerdefinierten Objekts, das den Inhalt einer Textdatei als Eigenschaften eines Objekts dynamisch bereitstellt.  
  
-   Erstellen Sie ein Projekt, in dem eine `IronPython`\-Bibliothek verwendet wird.  
  
## Vorbereitungsmaßnahmen  
 Sie benötigen IronPython 2.6.1 for .NET 4.0, um diese exemplarische Vorgehensweise auszuführen.  Sie können IronPython 2.6.1 for .NET 4.0 von [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187223) herunterladen.  
  
 [!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
## Erstellen eines benutzerdefinierten dynamischen Objekts  
 Im ersten Projekt, das wir in dieser exemplarischen Vorgehensweise erstellen, wird ein benutzerdefiniertes dynamisches Objekt definiert, das den Inhalt einer Textdatei durchsucht.  Der Suchtext wird durch die Bezeichnung einer dynamischen Eigenschaft angegeben.  Wenn im Aufrufcode z. B. `dynamicFile.Sample` angegeben wird, gibt die dynamische Klasse eine generische Liste von Zeichenfolgen zurück, die alle Zeilen der Datei enthält, die mit "Sample" beginnen.  Bei der Suche wird die Groß\- und Kleinschreibung nicht berücksichtigt.  Von der dynamischen Klasse werden auch zwei optionale Argumente unterstützt.  Das erste Argument ist ein Suchoptionsenumerationswert, der angibt, dass die dynamische Klasse am Anfang, am Ende oder an einer beliebigen Position in der Zeile nach Übereinstimmungen suchen soll.  Das zweite Argument gibt an, dass die dynamische Klasse vor dem Suchen vorangestellte und nachgestellte Leerzeichen in jeder Zeile abschneiden soll.  Wenn im Aufrufode z. B. `dynamicFile.Sample(StringSearchOption.Contains)` angegeben wird, wird von der dynamischen Klasse an einer beliebigen Zeilenposition nach "Sample" gesucht.  Wird im Aufrufcode `dynamicFile.Sample(StringSearchOption.StartsWith, false)` angegeben, sucht die dynamische Klasse am Anfang jeder Zeile nach "Sample" und entfernt keine vorangestellten und nachgestellten Leerzeichen.  Standardmäßig sucht die dynamische Klasse am Zeilenanfang nach einer Übereinstimmung und entfernt vorangestellte und nachgestellte Leerzeichen.  
  
#### So erstellen Sie eine benutzerdefinierte dynamische Klasse  
  
1.  Starten Sie [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)].  
  
2.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
3.  Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist.  Wählen Sie im Bereich **Vorlagen** die Option **Konsolenanwendung** aus.  Geben Sie im Feld **Name** die Bezeichnung `DynamicSample` ein, und klicken Sie auf **OK**.  Das neue Projekt wird erstellt.  
  
4.  Klicken Sie mit der rechten Maustaste auf das Projekt "DynamicSample", zeigen Sie auf **Hinzufügen**, und klicken Sie dann auf **Klasse**.  Geben Sie im Feld **Name** die Bezeichnung `ReadOnlyFile` ein, und klicken Sie auf **OK**.  Eine neue Datei, die die ReadOnlyFile\-Klasse enthält, wird hinzugefügt.  
  
5.  Fügen Sie am Anfang von "ReadOnlyFile.cs" oder "ReadOnlyFile.vb" den folgenden Code hinzu, um den <xref:System.IO?displayProperty=fullName>\-Namespace und den <xref:System.Dynamic?displayProperty=fullName>\-Namespace zu importieren.  
  
     [!code-cs[VbDynamicWalkthrough#1](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_1.cs)]
     [!code-vb[VbDynamicWalkthrough#1](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_1.vb)]  
  
6.  Die Suchkriterien werden vom benutzerdefinierten dynamischen Objekt mithilfe einer Enumeration bestimmt.  Fügen Sie vor der Klassenanweisung die folgende Enumerationsdefinition hinzu.  
  
     [!code-cs[VbDynamicWalkthrough#2](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_2.cs)]
     [!code-vb[VbDynamicWalkthrough#2](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_2.vb)]  
  
7.  Aktualisieren Sie, wie im folgenden Codebeispiel gezeigt, die Klassenanweisung, um die `DynamicObject`\-Klasse zu erben.  
  
     [!code-cs[VbDynamicWalkthrough#3](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_3.cs)]
     [!code-vb[VbDynamicWalkthrough#3](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_3.vb)]  
  
8.  Fügen Sie der `ReadOnlyFile`\-Klasse den folgenden Code hinzu, um ein privates Feld für den Dateipfad und einen Konstruktor für die `ReadOnlyFile`\-Klasse zu definieren.  
  
     [!code-cs[VbDynamicWalkthrough#4](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_4.cs)]
     [!code-vb[VbDynamicWalkthrough#4](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_4.vb)]  
  
9. Fügen Sie der `ReadOnlyFile`\-Klasse die `GetPropertyValue`\-Methode hinzu.  Die `GetPropertyValue`\-Methode akzeptiert Suchkriterien als Eingabe und gibt die Zeilen einer Textdatei zurück, die mit den Suchkriterien übereinstimmen.  Die dynamischen, von der `ReadOnlyFile`\-Klasse bereitgestellten Methoden rufen die `GetPropertyValue`\-Methode auf, um die jeweiligen Ergebnisse abzurufen.  
  
     [!code-cs[VbDynamicWalkthrough#5](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_5.cs)]
     [!code-vb[VbDynamicWalkthrough#5](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_5.vb)]  
  
10. Fügen Sie nach der `GetPropertyValue`\-Methode den folgenden Code zum Überschreiben der <xref:System.Dynamic.DynamicObject.TryGetMember%2A>\-Methode der <xref:System.Dynamic.DynamicObject>\-Klasse hinzu.  Die <xref:System.Dynamic.DynamicObject.TryGetMember%2A>\-Methode wird aufgerufen, wenn ein Member einer dynamischen Klasse angefordert wird und keine Argumente angegeben werden.  Das `binder`\-Argument enthält Informationen zum Member, auf den verwiesen wird, und das `result`\-Argument verweist auf das für den angegebenen Member zurückgegebene Ergebnis.  Die <xref:System.Dynamic.DynamicObject.TryGetMember%2A>\-Methode gibt einen booleschen Wert zurück, der `true` zurückgibt, wenn der angeforderte Member vorhanden ist. Andernfalls wird `false` zurückgegeben.  
  
     [!code-cs[VbDynamicWalkthrough#6](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_6.cs)]
     [!code-vb[VbDynamicWalkthrough#6](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_6.vb)]  
  
11. Fügen Sie nach der `TryGetMember`\-Methode den folgenden Code zum Überschreiben der <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A>\-Methode der <xref:System.Dynamic.DynamicObject>\-Klasse hinzu.  Die <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A>\-Methode wird aufgerufen, wenn ein Member einer dynamischen Klasse mit Argumenten angefordert wird.  Das `binder`\-Argument enthält Informationen zum Member, auf den verwiesen wird, und das `result`\-Argument verweist auf das für den angegebenen Member zurückgegebene Ergebnis.  Das `args`\-Argument enthält ein Array der Argumente, die an den Member weitergegeben werden.  Die <xref:System.Dynamic.DynamicObject.TryInvokeMember%2A>\-Methode gibt einen booleschen Wert zurück, der `true` zurückgibt, wenn der angeforderte Member vorhanden ist. Andernfalls wird `false` zurückgegeben.  
  
     Die benutzerdefinierte Version der `TryInvokeMember`\-Methode erwartet, dass das erste Argument ein Wert der `StringSearchOption`\-Enumeration ist, der in einem der vorherigen Schritt definiert wurde.  Die `TryInvokeMember`\-Methode erwartet, dass das zweite Argument ein boolescher Wert ist.  Wenn ein Argument bzw. beide Argumente gültige Werte sind, werden sie an die `GetPropertyValue`\-Methode übergeben, um die Ergebnisse abzurufen.  
  
     [!code-cs[VbDynamicWalkthrough#7](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_7.cs)]
     [!code-vb[VbDynamicWalkthrough#7](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_7.vb)]  
  
12. Speichern und schließen Sie die Datei.  
  
#### So erstellen Sie eine Beispieltextdatei  
  
1.  Klicken Sie mit der rechten Maustaste auf das Projekt "DynamicSample", zeigen Sie auf **Hinzufügen**, und klicken Sie dann auf **Neues Element**.  Wählen Sie im Bereich **Installierte Vorlagen** die Option **Allgemein** und anschließend die Vorlage **Textdatei** aus.  Lassen Sie den Standardnamen von "TextFile1.txt" im Feld **Name** unverändert, und klicken Sie auf **Hinzufügen**.  Dem Projekt wird die neue Textdatei hinzugefügt.  
  
2.  Kopieren Sie den folgenden Text in die Datei "TextFile1.txt".  
  
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
  
#### So erstellen Sie eine Beispielanwendung, die das benutzerdefinierte dynamische Objekt verwendet  
  
1.  Doppelklicken Sie im **Projektmappen\-Explorer** auf die Datei "Module1.vb", wenn Sie [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] verwenden, oder auf die Datei "Program.cs", wenn Sie Visual C\# verwenden.  
  
2.  Fügen Sie der Main\-Prozedur den folgenden Code hinzu, um für die Datei "TextFile1.txt" eine Instanz der `ReadOnlyFile`\-Klasse zu erstellen.  Der Code verwendet späte Bindung, um dynamische Member aufzurufen und Textzeilen abzurufen, die die Zeichenfolge "Customer" enthalten.  
  
     [!code-cs[VbDynamicWalkthrough#8](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_8.cs)]
     [!code-vb[VbDynamicWalkthrough#8](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_8.vb)]  
  
3.  Speichern Sie die Datei, und drücken Sie STRG\+F5, um die Anwendung zu erstellen und auszuführen.  
  
## Aufrufen einer Bibliothek für eine dynamische Sprache  
 Das nächste Projekt, das Sie in dieser exemplarischen Vorgehensweise erstellen, greift auf eine Bibliothek zu, die in der dynamischen Sprache IronPython geschrieben ist.  Bevor Sie dieses Projekt erstellen, muss IronPython 2.6.1 for .NET 4.0. installiert sein.  Sie können IronPython 2.6.1 for .NET 4.0 von [CodePlex](http://go.microsoft.com/fwlink/?LinkId=187223) herunterladen.  
  
#### So erstellen Sie eine benutzerdefinierte dynamische Klasse  
  
1.  Zeigen Sie in [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
2.  Überprüfen Sie, ob im Dialogfeld **Neues Projekt** im Bereich **Projekttypen** der Eintrag **Windows** ausgewählt ist.  Wählen Sie im Bereich **Vorlagen** die Option **Konsolenanwendung** aus.  Geben Sie im Feld **Name** den Namen `DynamicIronPythonSample` ein, und klicken Sie dann auf **OK**.  Das neue Projekt wird erstellt.  
  
3.  Wenn Sie [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] verwenden, klicken Sie mit der rechten Maustaste auf das DynamicIronPythonSample\-Projekt, und klicken Sie dann auf **Eigenschaften**.  Klicken Sie auf die Registerkarte **Verweise**.  Klicken Sie auf die Schaltfläche **Hinzufügen**.  Wenn Sie Visual C\#, verwenden, klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf den Ordner **Verweise** und dann auf **Verweis hinzufügen**.  
  
4.  Navigieren Sie auf der Registerkarte **Durchsuchen** zu dem Ordner, in dem die IronPython\-Bibliotheken installiert sind.  Beispiel: C:\\Programme\\IronPython 2.6 for .NET 4.0.  Wählen Sie die Bibliotheken **IronPython.dll**, **IronPython.Modules.dll**, **Microsoft.Scripting.dll** und **Microsoft.Dynamic.dll** aus.  Klicken Sie auf **OK**.  
  
5.  Wenn Sie [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] verwenden, bearbeiten Sie die Datei Module1.vb.  Wenn Sie Visual C\# verwenden, bearbeiten Sie die Datei Program.cs.  
  
6.  Fügen Sie am Anfang der Datei folgenden Code hinzu, um den `IronPython.Hosting`\-Namespace und den `Microsoft.Scripting.Hosting`\-Namespace aus den IronPython\-Bibliotheken zu importieren.  
  
     [!code-cs[VbDynamicWalkthroughIronPython#1](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_9.cs)]
     [!code-vb[VbDynamicWalkthroughIronPython#1](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_9.vb)]  
  
7.  Fügen Sie in der Main\-Methode folgenden Code hinzu, um ein neues `Microsoft.Scripting.Hosting.ScriptRuntime`\-Objekt zum Hosten der IronPython\-Bibliotheken zu erstellen.  Das `ScriptRuntime`\-Objekt lädt das IronPython\-Bibliotheksmodul random.py.  
  
     [!code-cs[VbDynamicWalkthroughIronPython#2](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_10.cs)]
     [!code-vb[VbDynamicWalkthroughIronPython#2](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_10.vb)]  
  
8.  Fügen Sie nach dem Code zum Laden des Moduls random.py folgenden Code hinzu, um ein Array von ganzen Zahlen zu erstellen.  Das Array wird an die `shuffle`\-Methode des Moduls random.py übergeben, das die Werte im Array nach dem Zufallsprinzip sortiert.  
  
     [!code-cs[VbDynamicWalkthroughIronPython#3](../../../csharp/programming-guide/types/codesnippet/CSharp/walkthrough-creating-and-using-dynamic-objects_11.cs)]
     [!code-vb[VbDynamicWalkthroughIronPython#3](../../../csharp/programming-guide/types/codesnippet/VisualBasic/walkthrough-creating-and-using-dynamic-objects_11.vb)]  
  
9. Speichern Sie die Datei, und drücken Sie STRG\+F5, um die Anwendung zu erstellen und auszuführen.  
  
## Siehe auch  
 <xref:System.Dynamic?displayProperty=fullName>   
 <xref:System.Dynamic.DynamicObject?displayProperty=fullName>   
 [Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md)   
 [Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)   
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)   
 [Dynamische Schnittstellen \(externes Blog\) implementieren](http://go.microsoft.com/fwlink/?LinkId=230895)