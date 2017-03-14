---
title: "Objects and Classes in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "classes [Visual Basic]"
  - "objects [Visual Basic]"
ms.assetid: c68c5752-1006-46e1-975a-6717b62a42fc
caps.latest.revision: 26
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 26
---
# Objects and Classes in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

*Objekte* sind Kombinationen von Code und Daten, die als Einheit behandelt werden können.  Sie können Teile von Anwendungen sein, wie Steuerelemente oder Formulare.  Auch ganze Anwendungen können ein Objekt darstellen.  
  
 Beim Erstellen einer Anwendung in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] arbeiten Sie stets mit Objekten.  Sie können von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] bereitgestellte Objekte verwenden, z. B. Steuerelemente, Formulare und Datenzugriffsobjekte.  Sie können in der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Anwendung auch Objekte aus anderen Anwendungen verwenden.  Darüber hinaus können Sie eigene Objekte erstellen und für diese zusätzliche Eigenschaften und Methoden definieren.  Objekte verhalten sich wie vorgefertigte Bausteine für Programme, d. h., mit Objekten können Codeabschnitte einmal geschrieben und dann immer wieder verwendet werden.  
  
 Dieses Thema enthält ausführliche Erläuterungen zu Objekten.  
  
## Objekte und Klassen  
 Jedes Objekt in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] wird von einer *Klasse* definiert.  Eine Klasse beschreibt die Variablen, Eigenschaften, Prozeduren und Ereignisse eines Objekts.  Objekte sind Instanzen von Klassen; sobald Sie eine Klasse definiert haben, können Sie eine beliebige Anzahl von Objekten erstellen.  
  
 Die Beziehung zwischen einem Objekt und seiner Klasse können Sie sich zum besseren Verständnis wie die zwischen Ausstechform und Plätzchen vorstellen.  Die Ausstechform ist die Klasse.  Sie definiert die Merkmale der einzelnen Plätzchen, z. B. die Größe und die Form.  Die Klasse wird zur Erstellung von Objekten verwendet.  Die Objekte sind in diesem Fall die Plätzchen.  
  
 Sie müssen ein Objekt erstellen, bevor Sie auf seine Member zugreifen können.  
  
#### So erstellen Sie ein Objekt aus einer Klasse  
  
1.  Legen Sie fest, aus welcher Klasse Sie ein Objekt erstellen möchten.  
  
2.  Schreiben Sie eine [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), um eine Variable zu erstellen, der Sie eine Klasseninstanz zuweisen können.  Die Variable sollte vom gleichen Typ sein wie die gewünschte Klasse.  
  
    ```  
  
    Dim nextCustomer As customer   
    ```  
  
3.  Fügen Sie das [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md)\-Schlüsselwort hinzu, um die Variable für eine neue Instanz der Klasse zu initialisieren.  
  
    ```  
    Dim nextCustomer As New customer  
    ```  
  
4.  Sie können jetzt über die Objektvariable auf die Member der Klasse zugreifen.  
  
    ```  
  
    nextCustomer.accountNumber = lastAccountNumber + 1  
    ```  
  
> [!NOTE]
>  Wenn möglich, sollten Sie die Variable mit dem Klassentyp deklarieren, den Sie ihr zuweisen möchten.  Dies wird als *frühe Bindung* bezeichnet.  Wenn Sie den Klassentyp zur Kompilierungszeit nicht kennen, können Sie eine *späte Bindung* verwenden, indem Sie die Variable als [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) deklarieren.  Die späte Bindung kann die Leistung jedoch reduzieren und den Zugriff auf die Member des Laufzeitobjekts einschränken.  Weitere Informationen finden Sie unter [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md).  
  
### Mehrere Instanzen  
 Aus einer Klasse neu erstellte Objekte sind häufig identisch.  Sobald sie als einzelne Objekte existieren, können ihre Variablen und Eigenschaften jedoch unabhängig von den anderen Instanzen geändert werden.  Wenn Sie einem Formular beispielsweise drei Kontrollkästchen hinzufügen, ist jedes Kontrollkästchen\-Objekt eine Instanz der <xref:System.Windows.Forms.CheckBox>\-Klasse.  Die einzelnen <xref:System.Windows.Forms.CheckBox>\-Objekte verfügen über eine gemeinsame Gruppe von Merkmalen und Fähigkeiten \(Eigenschaften, Variablen, Prozeduren und Ereignisse\), die durch die Klasse definiert wurde.  Jedes Objekt verfügt jedoch über einen eigenen Namen, kann separat aktiviert und deaktiviert sowie an unterschiedlichen Stellen auf dem Formular abgelegt werden.  
  
## Objektmember  
 Ein Objekt ist ein Element einer Anwendung, das eine *Instanz* einer Klasse darstellt.  Felder, Eigenschaften, Methoden und Ereignisse sind die Bausteine von Objekten und bilden deren *Member*.  
  
### Memberzugriff  
 Sie greifen auf einen Member eines Objekts zu, indem Sie zuerst den Namen der Objektvariablen, dann einen Punkt \(`.`\) und schließlich den Namen des Members angeben.  Im folgenden Beispiel wird die <xref:System.Windows.Forms.Control.Text%2A>\-Eigenschaft eines <xref:System.Windows.Forms.Label>\-Objekts festgelegt.  
  
```  
warningLabel.Text = "Data not saved"  
```  
  
#### IntelliSense\-Auflistung von Membern  
 IntelliSense listet Member einer Klasse auf, wenn Sie die Option Member auflisten aufrufen, z. B. wenn Sie einen Punkt \(`.`\) als Operator für den Memberzugriff eingeben.  Wenn Sie den Punkt nach dem Namen einer Variablen eingeben, die als eine Instanz der betreffenden Klasse deklariert ist, listet IntelliSense alle Instanzmember und keinen freigegebenen Member auf.  Wenn Sie den Punkt nach dem Klassennamen selbst eingeben, listet IntelliSense alle freigegebenen Member und keinen Instanzmember auf.  Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visual-studio/ide/using-intellisense).  
  
### Felder und Eigenschaften  
 *Felder* und *Eigenschaften* stellen die in einem Objekt gespeicherten Informationen dar.  Ebenso wie lokale Variablen in einer Prozedur werden die Werte der Felder und Eigenschaften mit Zuweisungsanweisungen abgerufen und festgelegt.  Im folgenden Beispiel wird die <xref:System.Windows.Forms.Control.Width%2A>\-Eigenschaft eines <xref:System.Windows.Forms.Label>\-Objekts abgerufen und dessen <xref:System.Windows.Forms.Control.ForeColor%2A>\-Eigenschaft festgelegt.  
  
```  
Dim warningWidth As Integer = warningLabel.Width  
warningLabel.ForeColor = System.Drawing.Color.Red  
```  
  
 Ein Feld wird auch als *Membervariable* bezeichnet.  
  
 Verwenden Sie in den folgenden Fällen Eigenschaftenprozeduren:  
  
-   Sie müssen steuern, wann und wie ein Wert festgelegt oder abgerufen wird.  
  
-   Die Eigenschaft besitzt eine Reihe stringenter Werte, die überprüft werden müssen.  
  
-   Das Festlegen des Werts verursacht merkliche Änderungen am Objektzustand, z. B. bei einer `IsVisible`\-Eigenschaft.  
  
-   Das Festlegen der Eigenschaft verursacht Änderungen an anderen internen Variablen oder an Werten anderer Eigenschaften.  
  
-   Eine Reihe von Schritten muss ausgeführt werden, bevor eine Eigenschaft festgelegt oder abgerufen werden kann.  
  
 Verwenden Sie in den folgenden Fällen Felder:  
  
-   Der Wert ist ein selbst überprüfender Typ.  So wird beispielsweise ein Fehler oder eine automatische Datenkonvertierung ausgelöst, wenn einer `Boolean`\-Variablen ein anderer Wert als `True` oder `False` zugewiesen wird.  
  
-   Jeder Wert in dem vom Datentyp unterstützten Bereich ist gültig.  Dies gilt für zahlreiche Eigenschaften des Typs `Single` und `Double`.  
  
-   Die Eigenschaft ist ein `String`\-Datentyp, und es bestehen keine Einschränkungen bezüglich der Größe und des Werts der Zeichenfolge.  
  
-   Weitere Informationen finden Sie unter [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md).  
  
### Methoden  
 Eine *Methode* ist eine Aktion, die von einem Objekt ausgeführt werden kann.  Beispielsweise ist <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A> eine Methode des <xref:System.Windows.Forms.ComboBox>\-Objekts, mit der einem Kombinationsfeld ein neuer Eintrag hinzugefügt wird.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Forms.Timer.Start%2A>\-Methode eines <xref:System.Windows.Forms.Timer>\-Objekts dargestellt.  
  
```  
Dim safetyTimer As New System.Windows.Forms.Timer  
safetyTimer.Start()  
```  
  
 Bei einer Methode handelt es sich einfach um eine *Prozedur*, die von einem Objekt verfügbar gemacht wird.  
  
 Weitere Informationen finden Sie unter [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md).  
  
### Ereignisse  
 Ein Ereignis ist eine Aktion, die von einem Objekt erkannt wird, z. B. Klicken mit der Maus oder Drücken einer Taste, und für die Sie einen Code als Antwort schreiben können.  Ereignisse können als Ergebnis von Benutzeraktionen oder Programmcodes auftreten oder vom System verursacht werden. Folgende Ausdrucksweise ist üblich:  Code, der ein Ereignis signalisiert, *löst* das Ereignis aus, während Code, der auf das Ereignis reagiert, das Ereignis *behandelt*.  
  
 Sie können auch eigene, benutzerdefinierte Ereignisse entwickeln, die von den Objekten ausgelöst und von anderen Objekte verarbeitet werden.  Weitere Informationen finden Sie unter [Events](../../../../visual-basic/programming-guide/language-features/events/events.md).  
  
### Instanzmember und freigegebene Member  
 Wenn Sie ein Objekt von einer Klasse erstellen, ist das Ergebnis eine Instanz der betreffenden Klasse.  Member, die nicht mit dem [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)\-Schlüsselwort deklariert werden, sind *Instanzmember*, die ausschließlich zur betreffenden Instanz gehören.  Ein Instanzmember in einer Instanz ist unabhängig vom gleichen Member in einer anderen Instanz derselben Klasse.  Eine Instanzmembervariable kann z. B. in verschiedenen Instanzen unterschiedliche Werte enthalten.  
  
 Member, die mit dem `Shared`\-Schlüsselwort deklariert werden, sind *freigegebene Member*, die zu der Klasse insgesamt und nicht zu einer bestimmten Instanz gehören.  Ein freigegebener Member existiert nur einmal; dabei spielt es keine Rolle, wie viele Instanzen seiner Klasse Sie erstellen oder ob Sie keine Instanzen erstellen.  Eine freigegebene Membervariable enthält beispielsweise nur einen Wert, der sämtlichem Code zur Verfügung steht, der auf die Klasse zugreifen kann.  
  
#### Zugreifen auf nicht freigegebene Member  
  
###### So greifen Sie auf einen nicht freigegebenen Member eines Objekts zu  
  
1.  Stellen Sie sicher, dass das Objekt aus seiner Klasse erstellt und einer Objektvariablen zugewiesen wurde.  
  
    ```  
    Dim secondForm As New System.Windows.Forms.Form  
    ```  
  
2.  Fügen Sie in der Anweisung, die auf den Member zugreift, nach der Objektvariablen den *Memberzugriff\-Operator* \(`.`\) und dann den Membernamen ein.  
  
    ```  
    secondForm.Show()  
    ```  
  
#### Zugreifen auf Shared\-Member  
  
###### So greifen Sie auf einen Shared\-Member eines Objekts zu  
  
-   Fügen Sie nach dem Klassennamen den *Memberzugriff\-Operator* \(`.`\) und dann den Membernamen ein.  Auf einen `Shared`\-Member des Objekts sollten Sie stets direkt über den Klassennamen zugreifen.  
  
    ```  
    MsgBox("This computer is called " & Environment.MachineName)  
    ```  
  
-   Wenn Sie bereits ein Objekt aus der Klasse erstellt haben, können Sie auch über die Variable des Objekts auf einen `Shared`\-Member zugreifen.  
  
### Unterschiede zwischen Klassen und Modulen  
 Der Hauptunterschied zwischen Klassen und Modulen besteht darin, dass Klassen als Objekte instanziiert werden können, während dies für Standardmodule nicht gilt.  Da jeweils nur eine Kopie der Daten eines Standardmoduls vorhanden ist, führt die Änderung einer öffentlichen Variablen in einem Standardmodul durch einen Teil des Programms dazu, dass jeder andere Teil des Programms denselben Wert erhält, wenn er diese Variable anschließend liest.  Im Gegensatz dazu sind Objektdaten für jedes instanziierte Objekt getrennt vorhanden.  Ein weiterer Unterschied zu Standardmodulen besteht darin, dass Klassen Schnittstellen implementieren können.  
  
> [!NOTE]
>  Wenn der Modifizierer `Shared` auf einen Klassenmember angewendet wird, wird er der Klasse selbst zugeordnet und nicht einer bestimmten Instanz der Klasse.  In derselben Weise, wie auf Modulmember zugegriffen wird, wird über den Klassennamen direkt auf den Member zugegriffen.  
  
 Die Member von Klassen und Modulen besitzen darüber hinaus unterschiedliche Gültigkeitsbereiche.  Die in einer Klasse definierten Member sind innerhalb einer bestimmten Instanz der Klasse und nur über die Lebensdauer des Objekts hinweg gültig.  Um auf Klassenmember von außerhalb der Klasse zuzugreifen, müssen Sie vollständig qualifizierte Namen im Format *Objekt*.*Member* verwenden.  
  
 Andererseits sind die in einem Modul deklarierten Member standardmäßig öffentlich verfügbar, und daher kann jeder Code, der Zugriff auf das Modul hat, auf diese Member zugreifen.  Dies bedeutet, dass Variablen in einem Standardmodul im Prinzip globale Variablen sind, da sie an jeder Stelle im Projekt sichtbar sind und über die gesamte Lebensdauer des Programms hinweg Bestand haben.  
  
## Wiederverwenden von Klassen und Objekten  
 Mit Objekten können Variablen und Prozeduren einmal deklariert und dann bei Bedarf erneut verwendet werden.  Wenn Sie beispielsweise einer Anwendung eine Rechtschreibprüfung hinzufügen möchten, können Sie alle Variablen und Unterstützungsfunktionen definieren, die für die Rechtschreibprüfung erforderlich sind.  Wenn Sie die Rechtschreibprüfung als Klasse erstellen, können Sie sie in anderen Anwendungen erneut verwenden, indem Sie der kompilierten Assembly einen Verweis hinzufügen.  Eine noch bessere Möglichkeit, bei der Sie sich gleichzeitig einigen Arbeitsaufwand sparen, ist die Verwendung einer Rechtschreibprüfungsklasse, die bereits von einem anderen Entwickler entwickelt wurde.  
  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] enthält beispielsweise viele Komponenten, die verwendet werden können.  Im folgenden Beispiel wird die <xref:System.TimeZone>\-Klasse im <xref:System>\-Namespace verwendet.  Die <xref:System.TimeZone>\-Klasse stellt Member zur Verfügung, mit denen Sie Informationen über die Zeitzone des aktuellen Computersystems abrufen können.  
  
```  
Public Sub examineTimeZone()  
    Dim tz As System.TimeZone = System.TimeZone.CurrentTimeZone  
    Dim s As String = "Current time zone is "  
    s &= CStr(tz.GetUtcOffset(Now).Hours) & " hours and "  
    s &= CStr(tz.GetUtcOffset(Now).Minutes) & " minutes "  
    s &= "different from UTC (coordinated universal time)"  
    s &= vbCrLf & "and is currently "  
    If tz.IsDaylightSavingTime(Now) = False Then s &= "not "  
    s &= "on ""summer time""."  
    MsgBox(s)  
End Sub  
```  
  
 Im vorherigen Beispiel wird mit der ersten [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) eine Objektvariable vom Typ <xref:System.TimeZone> deklariert, die einem <xref:System.TimeZone>\-Objekt zugewiesen wird, das von der <xref:System.TimeZone.CurrentTimeZone%2A>\-Eigenschaft zurückgegeben wurde.  
  
## Beziehungen zwischen Objekten  
 Objekte können unterschiedliche Beziehungen zueinander haben.  Bei den Hauptbeziehungen wird zwischen *hierarchischen Beziehungen* und *Kapselungsbeziehungen* unterschieden.  
  
### Hierarchische Beziehung  
 Wenn Klassen von grundlegenderen Klassen abgeleitet werden, wird von einer *hierarchischen Beziehung* gesprochen.  Klassenhierarchien sind bei der Beschreibung von Elementen nützlich, die Untertypen allgemeinerer Klassen sind.  
  
 Im folgenden Beispiel definieren Sie eine spezielle <xref:System.Windows.Forms.Button>\-Klasse, die sich wie eine normale <xref:System.Windows.Forms.Button>\-Klasse verhält, aber eine Methode verfügbar macht, die die Vorder\- und Hintergrundfarben reserviert.  
  
##### So definieren Sie eine Klasse, die von einer bereits vorhandenen Klasse abgeleitet ist  
  
1.  Verwenden Sie eine [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md) zur Definition einer Klasse, aus der das benötigte Objekt erstellt werden soll.  
  
     `Public Class reversibleButton`  
  
     Stellen Sie sicher, dass der letzten Codezeile in der Klasse eine `End Class`\-Anweisung folgt.  Die integrierte Entwicklungsumgebung \(IDE\) generiert standardmäßig automatisch eine `End Class`\-Anweisung, wenn Sie eine `Class`\-Anweisung einfügen.  
  
2.  Fügen Sie unmittelbar nach der `Class`\-Anweisung eine [Inherits Statement](../../../../visual-basic/language-reference/statements/inherits-statement.md) ein.  Geben Sie die Klasse an, von der die neue Klasse abgeleitet wird.  
  
     `Inherits System.Windows.Forms.Button`  
  
     Die neue Klasse erbt alle von der Basisklasse definierten Member.  
  
3.  Fügen Sie den Code für die zusätzlichen Member hinzu, die die abgeleitete Klasse verfügbar macht.  Sie könnten zum Beispiel eine `reverseColors`\-Methode hinzufügen. Die abgeleitete Klasse würde dann wie folgt aussehen:  
  
    ```  
    Public Class reversibleButton  
        Inherits System.Windows.Forms.Button  
        Public Sub reverseColors()   
            Dim saveColor As System.Drawing.Color = Me.BackColor  
            Me.BackColor = Me.ForeColor  
            Me.ForeColor = saveColor  
        End Sub  
    End Class   
    ```  
  
     Wenn Sie ein Objekt aus der `reversibleButton`\-Klasse erstellen, kann es auf alle Member der <xref:System.Windows.Forms.Button>\-Klasse sowie auf die `reverseColors`\-Methode und alle weiteren neuen Member zugreifen, die Sie für `reversibleButton` definieren.  
  
 Abgeleitete Klassen erben Member aus der Klasse, von der sie abgeleitet sind. Dadurch ist es möglich, die Komplexität der Klassen zu erhöhen, je weiter oben sie sich in der Hierarchie befinden.  Weitere Informationen finden Sie unter [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
#### Kompilieren des Codes  
 Stellen Sie sicher, dass der Compiler auf die Klasse zugreifen kann, von der die neue Klasse abgeleitet werden soll.  Dies könnte bedeuten, dass der Name der Klasse wie im vorhergehenden Beispiel voll qualifiziert oder der Namespace der Klasse in einer [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) angegeben werden muss.  Wenn sich die Klasse in einem anderen Projekt befindet, müssen Sie möglicherweise einen Verweis auf dieses Projekt hinzufügen.  Weitere Informationen finden Sie unter [Verwalten von Verweisen in einem Projekt](/visual-studio/ide/managing-references-in-a-project).  
  
### Kapselungsbeziehung  
 Eine andere Möglichkeit, Objekte miteinander in Beziehung zu setzen, ist die *Kapselungsbeziehung*.  Containerobjekte kapseln andere Objekte nach logischen Gesichtspunkten.  So enthält das <xref:System.OperatingSystem>\-Objekt beispielsweise logisch ein <xref:System.Version>\-Objekt, das es über seine <xref:System.OperatingSystem.Version%2A>\-Eigenschaft zurückgibt.  Beachten Sie, dass das Containerobjekt ein anderes Objekt nur logisch enthält.  
  
#### Auflistungen  
 Eine spezielle Art der Objektkapselung stellen *Auflistungen* dar.  Auflistungen sind Gruppen von ähnlichen Objekten, die aufgelistet werden können.  [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] unterstützt eine spezielle Syntax in der [For Each...Next\-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md), mit der Sie die Elemente einer Auflistung durchlaufen können.  Darüber hinaus ermöglichen Auflistungen in vielen Fällen die Verwendung einer <xref:Microsoft.VisualBasic.Collection.Item%2A>, mit der Sie Elemente über ihren Index abrufen können oder indem Sie sie mit einer eindeutigen Zeichenfolge verknüpfen.  Auflistungen können einfacher zu verwenden sein als Arrays, da sie es ermöglichen, Elemente ohne Verwendung von Indizes hinzuzufügen oder zu entfernen.  Aufgrund dieses Vorteils werden Auflistungen häufig dazu verwendet, Formulare und Steuerelemente zu speichern.  
  
## Verwandte Themen  
 [Walkthrough: Defining Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)  
 Stellt eine schrittweise Beschreibung des Erstellens von Klassen bereit.  
  
 [Overloaded Properties and Methods](../../../../visual-basic/programming-guide/language-features/objects-and-classes/overloaded-properties-and-methods.md)  
 Überladene Eigenschaften und Methoden  
  
 [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 Beschreibt Vererbungsmodifizierer, das Überschreiben von Methoden und Eigenschaften, MyClass und MyBase.  
  
 [Object Lifetime: How Objects Are Created and Destroyed](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 Erörtert das Erstellen und Zerstören von Klasseninstanzen.  
  
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 Beschreibt das Erstellen und Verwenden anonymer Typen, mit denen Objekte erstellt werden können, ohne dass für den Datentyp eine Klassendefinition geschrieben werden muss.  
  
 [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 Behandelt Objektinitialisierer, mit denen Instanzen von benannten und anonymen Typen mit einem einzigen Ausdruck erstellt werden können.  
  
 [Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 Erklärt, wie Eigenschaftennamen und Typen in Deklarationen anonymer Typen abgeleitet werden können  Enthält Beispiele mit erfolgreichen Ableitungen und Ableitungsfehlern.