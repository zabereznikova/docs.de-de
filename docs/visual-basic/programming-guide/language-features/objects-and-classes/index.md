---
title: Objekte und Klassen
ms.date: 05/26/2020
helpviewer_keywords:
- classes [Visual Basic]
- objects [Visual Basic]
ms.assetid: c68c5752-1006-46e1-975a-6717b62a42fc
ms.openlocfilehash: 10e257a1cbc8778565a9838aeef423522f9d2970
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290616"
---
# <a name="objects-and-classes-in-visual-basic"></a>Objekte und Klassen in Visual Basic

Ein *Objekt* ist eine Kombination aus Code und Daten, die als Einheit behandelt werden kann. Ein Objekt kann ein Teil einer Anwendung sein wie ein Steuerelement oder ein Formular. Eine vollständige Anwendung kann auch ein Objekt sein.

Wenn Sie eine Anwendung in Visual Basic erstellen, arbeiten Sie ständig mit-Objekten. Sie können Objekte verwenden, die von Visual Basic bereitgestellt werden, z. b. Steuerelemente, Formulare und Datenzugriffs Objekte. Sie können auch Objekte aus anderen Anwendungen in Ihrer Visual Basic Anwendung verwenden. Sie können sogar eigene Objekte erstellen und für diese zusätzliche Eigenschaften und Methoden definieren. Objekte verhalten sich wie vorgefertigte Bausteine für Programme – Sie können ein Stück Code einmal schreiben und immer wieder verwenden.

Dieses Thema beschreibt Objekte im Detail.

## <a name="objects-and-classes"></a>Objekte und Klassen

Jedes Objekt in Visual Basic wird von einer *Klasse*definiert. Eine Klasse beschreibt die Variablen, Eigenschaften, Prozeduren und Ereignisse eines Objekts. Objekte sind Instanzen von Klassen. Sie können beliebig viele Objekte erstellen, die Sie benötigen, sobald Sie eine Klasse definiert haben.

Um die Beziehung zwischen einem Objekt und seiner Klasse zu verstehen, stellen Sie sich Ausstechformen und Kekse vor. Die Ausstechform ist die Klasse. Sie definiert die Merkmale der einzelnen Kekse, z.B. die Größe und Form. Die Klasse wird verwendet, um Objekte zu erstellen. Die Objekte sind die Kekse.

Sie müssen ein-Objekt erstellen, bevor Sie auf seine Member zugreifen können, mit Ausnahme von Membern, auf [`Shared`](../../../language-reference/modifiers/shared.md) die ohne ein Objekt der-Klasse zugegriffen werden kann.

### <a name="create-an-object-from-a-class"></a>Erstellen eines Objekts aus einer Klasse

1. Bestimmen Sie, von welcher Klasse Sie ein Objekt erstellen möchten, oder definieren Sie eine eigene Klasse. Beispiel:

   ```vb
   Public Class Customer
       Public Property AccountNumber As Integer
   End Class
   ```

2. Schreiben Sie eine [Dim-Anweisung](../../../language-reference/statements/dim-statement.md), um eine Variable zu erstellen, der Sie eine Klasseninstanz zuweisen können. Die Variable sollte vom Typ der gewünschten Klasse sein.

   ```vb
   Dim nextCustomer As Customer
   ```

3. Fügen Sie das Schlüsselwort [Neuer Operator](../../../language-reference/operators/new-operator.md) hinzu, um die Variable für eine neue Instanz der Klasse zu initialisieren.

   ```vb
   Dim nextCustomer As New Customer
   ```

4. Sie können jetzt die Member der Klasse über die Objektvariable aufrufen.

   ```vb
   nextCustomer.AccountNumber = lastAccountNumber + 1
   ```

> [!NOTE]
> Sie sollten die Variable möglichst so deklarieren, dass sie den Klassentyp aufweist, den Sie ihr zuweisen möchten. Dies wird als *frühe Bindung* bezeichnet. Wenn Sie den Klassentyp zur Kompilierungszeit nicht kennen, können Sie *Späte Bindung* aufrufen, indem Sie für die Variable den [Objekt-Datentyp](../../../language-reference/data-types/object-data-type.md) deklarieren. Allerdings kann die späte Bindung zu Leistungseinbußen und Einschränkungen des Zugriffs auf die Member des Laufzeitobjekts führen. Weitere Informationen finden Sie unter [Object Variable Declaration](../variables/object-variable-declaration.md).

### <a name="multiple-instances"></a>Mehrere Instanzen

Neu erstellte Objekte aus einer Klasse sind häufig identisch. Sobald sie als einzelne Objekte vorhanden sind, können jedoch ihre Variablen und Eigenschaften unabhängig von den anderen Instanzen geändert werden. Beispiel: Wenn Sie drei Kontrollkästchen zu einem Formular hinzufügen, ist jedes Kontrollkästchenobjekt eine Instanz der Klasse <xref:System.Windows.Forms.CheckBox>. Die einzelnen <xref:System.Windows.Forms.CheckBox>-Objekte verfügen über einen gemeinsamen Satz von Merkmalen und Funktionen (Eigenschaften, Variablen, Prozeduren und Ereignisse), die anhand der Klasse definiert sind. Alle verfügen jedoch über einen eigenen Namen, können separat aktiviert und deaktiviert sowie an einer anderen Stelle im Formular platziert werden.

## <a name="object-members"></a>Objektmember

Ein Objekt ist ein Element einer Anwendung, das eine *Instanz* einer Klasse darstellt. Felder, Eigenschaften, Methoden und Ereignisse sind die Bausteine von Objekten und bilden ihre *Member*.

### <a name="member-access"></a>Memberzugriff

Sie greifen auf einen Member eines Objekts zu, indem Sie nacheinander den Namen der Objektvariablen, einen Zeitraum (`.`) und den Namen des Members angeben. Im folgenden Beispiel wird die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft eines <xref:System.Windows.Forms.Label>-Objekts festgelegt.

```vb
warningLabel.Text = "Data not saved"
```

#### <a name="intellisense-listing-of-members"></a>IntelliSense-Auflistung von Membern

IntelliSense listet die Member einer Klasse auf, wenn Sie die Option „Member auflisten“ aufrufen, beispielsweise wenn Sie einen Punkt (`.`) als Memberzugriffsoperator eingeben. Wenn Sie den Punkt nach dem Namen einer Variablen eingeben, die als Instanz dieser Klasse deklariert war, listet IntelliSense alle Instanzmember und keinen der freigegebenen Member auf. Wenn Sie den Punkt nach dem Klassennamen selbst eingeben, listet IntelliSense alle freigegebenen Member und keinen der Instanzmember auf. Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense).

### <a name="fields-and-properties"></a>Felder und Eigenschaften

*Felder* und *Eigenschaften* stellen die in einem Objekt enthaltenen Informationen dar. Sie rufen ihre Werte ab und legen diese mit Zuweisungsanweisungen ebenso fest, wie Sie lokale Variablen in einer Prozedur abrufen und festlegen. Das folgende Beispiel ruft die <xref:System.Windows.Forms.Control.Width%2A>-Eigenschaft ab und legt die <xref:System.Windows.Forms.Control.ForeColor%2A>-Eigenschaft eines <xref:System.Windows.Forms.Label>-Objekts fest.

```vb
Dim warningWidth As Integer = warningLabel.Width
warningLabel.ForeColor = System.Drawing.Color.Red
```

Beachten Sie, dass ein Feld auch als *Membervariable* bezeichnet wird.

Verwenden Sie Eigenschaftenprozeduren in folgenden Fällen:

- Sie müssen steuern, wann und wie ein Wert festgelegt oder abgerufen wird.

- Die Eigenschaft weist einen genau definierten Satz von Werten auf, die überprüft werden müssen.

- Das Festlegen des Werts führt zu einer wahrnehmbaren Änderung am Zustand des Objekts, z.B. einer `IsVisible`-Eigenschaft.

- Das Festlegen der Eigenschaft führt zu Änderungen an anderen internen Variablen oder den Werten anderer Eigenschaften.

- Eine Reihe von Schritten muss ausgeführt werden, bevor die Eigenschaft festgelegt oder abgerufen werden kann.

Verwenden Sie Felder in folgenden Fällen:

- Der Wert ist der eines sich selbst überprüfenden Typs. Beispiel: Ein Fehler oder die automatische Datenkonvertierung erfolgt, wenn ein anderer Wert als `True` oder `False` einer `Boolean`-Variable zugewiesen wird.

- Jeder Wert im vom Datentyp unterstützten Bereich ist ungültig. Dies gilt für zahlreiche Eigenschaften vom Typ `Single` oder `Double`.

- Die Eigenschaft ist ein `String`-Datentyp, und es gibt keine Einschränkung für die Größe oder den Wert der Zeichenfolge.

- Weitere Informationen finden Sie unter [Property Procedures](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) (Eigenschaftenprozeduren).

> [!TIP]
> Behalten Sie immer die nicht konstanten Felder privat. Wenn Sie es als öffentlich festlegen möchten, verwenden Sie stattdessen eine Eigenschaft.

### <a name="methods"></a>Methoden

Eine *Methode* ist eine Aktion, die von einem Objekt ausgeführt werden kann. Beispielsweise ist <xref:System.Windows.Forms.ComboBox.ObjectCollection.Add%2A> eine Methode des <xref:System.Windows.Forms.ComboBox>-Objekts, die einen neuen Eintrag zu einem Kombinationsfeld hinzufügt.

Im folgenden Beispiel wird die Verwendung der <xref:System.Windows.Forms.Timer.Start%2A>-Methode eines <xref:System.Windows.Forms.Timer>-Objekts gezeigt.

```vb
Dim safetyTimer As New System.Windows.Forms.Timer
safetyTimer.Start()
```

Beachten Sie, dass eine Methode einfach eine *Prozedur* ist, die von einem Objekt zur Verfügung gestellt wird.

Weitere Informationen finden Sie unter [Prozeduren](../procedures/index.md).

### <a name="events"></a>Events

Ein Ereignis ist eine Aktion, die von einem Objekt erkannt wird, etwa durch Klicken mit der Maus oder Drücken einer Taste, und für die Sie Code als Reaktion verfassen können. Ereignisse können als Ergebnis einer Benutzeraktion oder von Programmcode auftreten bzw. vom System verursacht werden. Code, der ein Ereignis signalisiert, soll das Ereignis *auslösen*, und Code, der darauf antwortet, soll es *abwickeln*.

Sie können auch eigene, benutzerdefinierte Ereignisse entwickeln, die von Ihren Objekten ausgelöst und von anderen Objekten abgewickelt werden sollen. Weitere Informationen finden Sie unter [Ereignisse](../events/index.md).

### <a name="instance-members-and-shared-members"></a>Instanzmember und freigegebene Member

Wenn Sie ein Objekt aus einer Klasse erstellen, ist das Ergebnis eine Instanz dieser Klasse. Member, die nicht mit dem Schlüsselwort [Freigegeben](../../../language-reference/modifiers/shared.md) deklariert werden, sind *Instanzmember*, die ausschließlich zu dieser betreffenden Instanz gehören. Ein Instanzmember in einer Instanz ist unabhängig vom gleichen Member in einer anderen Instanz derselben Klasse. Eine Instanzmembervariable kann beispielsweise unterschiedliche Werte in verschiedenen Instanzen aufweisen.

Elemente, die mit dem Schlüsselwort `Shared` deklariert werden, sind *freigegebene Member*, die zu einer Klasse als Ganzes und nicht zu einer bestimmten Instanz gehören. Ein freigegebener Member ist nur einmal vorhanden, unabhängig davon, wie viele Instanzen seiner Klasse Sie erstellen oder ob Sie keine Instanzen erstellen. Eine Variable für einen freigegebenen Member enthält beispielsweise nur einen Wert, der für den gesamten Code zur Verfügung steht, der auf die Klasse zugreifen kann.

#### <a name="accessing-non-shared-members"></a>Zugreifen auf nicht freigegebene Member

1. Stellen Sie sicher, dass das Objekt aus seiner Klasse erstellt und einer Objektvariablen zugewiesen wurde.

   ```vb
   Dim secondForm As New System.Windows.Forms.Form
   ```

2. Befolgen Sie in der Anweisung, die auf den Member zugreift, den Namen der Objektvariablen mit dem *Member-Access-Operator* ( `.` ) und dann dem Elementnamen.

   ```vb
   secondForm.Show()
   ```

#### <a name="accessing-shared-members"></a>Zugreifen auf freigegebene Member

- Befolgen Sie den Klassennamen mit dem *Member-Access-Operator* ( `.` ) und dann dem Elementnamen. Sie sollten einen `Shared`-Member des Objekts immer direkt über den Klassennamen aufrufen.

   ```vb
   Console.WriteLine("This computer is called " & Environment.MachineName)
   ```

- Wenn Sie bereits ein Objekt aus der Klasse erstellt haben, können Sie alternativ einen `Shared`-Member über die Variable des Objekts aufrufen.

### <a name="differences-between-classes-and-modules"></a>Unterschiede zwischen Klassen und Modulen

Der Hauptunterschied zwischen Klassen und Modulen besteht darin, dass Klassen als Objekte instanziiert werden können, während dies für Standardmodule nicht möglich ist. Da nur eine Kopie der Daten eines Standardmoduls vorhanden ist, wenn ein Teil Ihres Programms eine öffentliche Variable in einem Standardmodul ändert, erhält jeder andere Teil des Programms denselben Wert, wenn er diese Variable anschließend liest. Im Gegensatz dazu sind Objektdaten für jedes instanziierte Objekt separat vorhanden. Ein weiterer Unterschied ist, dass Klassen im Gegensatz zu Standardmodulen Schnittstellen implementieren können. Wenn eine Klasse mit dem [MustInherit](../../../language-reference/modifiers/mustinherit.md) -Modifizierer markiert ist, kann Sie nicht direkt instanziiert werden. Es unterscheidet sich jedoch immer noch von einem Modul, da es vererbt werden kann, während Module nicht vererbt werden können.

> [!NOTE]
> Wenn der `Shared`-Modifizierer auf einen Klassenmember angewendet wird, wird er der Klasse selbst statt einer bestimmten Instanz der Klasse zugeordnet. Der Member wird direkt mithilfe des Klassennamens aufgerufen, und zwar auf dieselbe Weise wie Modulmember.

Klassen und Module verwenden auch verschiedene Geltungsbereiche für ihre Mitglieder. Member, die innerhalb einer Klasse definiert sind, sind auf eine bestimmte Instanz der Klasse beschränkt und nur für die Lebensdauer des Objekts vorhanden. Zum Zugriff auf Member der Klasse von außerhalb einer Klasse müssen Sie vollqualifizierte Namen im Format *Objekt*.*Member* verwenden.

Andererseits können die in einem Modul deklarierten Member standardmäßig öffentlich und mit jedem beliebigen Code aufgerufen werden, mit dem das Modul aufgerufen werden kann. Das bedeutet, dass Variablen in einem Standardmodul letztendlich globale Variablen sind, da sie an jeder beliebigen Stelle im Projekt sichtbar sind und für die Lebensdauer des Programms vorhanden sind.

## <a name="reusing-classes-and-objects"></a>Wiederverwenden von Klassen und Objekten

Mit Objekten können Sie Variablen und Prozeduren einmal deklarieren und anschließend bei Bedarf jederzeit wiederverwenden. Beispiel: Wenn Sie einer Anwendung eine Rechtschreibprüfung hinzufügen möchten, können Sie sämtliche Variablen und Supportfunktionen definieren, um die Rechtschreibprüfungsfunktion bereitzustellen. Wenn Sie Ihre Rechtschreibprüfung als Klasse erstellen, können Sie sie anschließend in anderen Anwendungen wiederverwenden, indem Sie einen Verweis auf die kompilierte Assembly hinzufügen. Sie können sich möglicherweise sogar selbst etwas Arbeit sparen, indem Sie eine Rechtschreibprüfungsklasse verwenden, die bereits von jemand anderem entwickelt wurde.

.Net bietet viele Beispiele für Komponenten, die zur Verwendung verfügbar sind. Das folgende Beispiel verwendet die <xref:System.TimeZone>-Klasse im <xref:System>-Namespace. <xref:System.TimeZone> enthält Member, die Ihnen das Abrufen von Informationen über die Zeitzone des aktuellen Computersystems ermöglichen.

```vb
Public Sub ExamineTimeZone()
    Dim tz As System.TimeZone = System.TimeZone.CurrentTimeZone
    Dim s As String = "Current time zone is "
    s &= CStr(tz.GetUtcOffset(Now).Hours) & " hours and "
    s &= CStr(tz.GetUtcOffset(Now).Minutes) & " minutes "
    s &= "different from UTC (coordinated universal time)"
    s &= vbCrLf & "and is currently "
    If tz.IsDaylightSavingTime(Now) = False Then s &= "not "
    s &= "on ""summer time""."
    Console.WriteLine(s)
End Sub
```

Im vorherigen Beispiel deklariert die erste [Dim-Anweisung](../../../language-reference/statements/dim-statement.md) eine Objektvariable des Typs <xref:System.TimeZone> und weist sie einem <xref:System.TimeZone>-Objekt hinzu, das von der <xref:System.TimeZone.CurrentTimeZone%2A>-Eigenschaft zurückgegeben wurde.

## <a name="relationships-among-objects"></a>Beziehungen zwischen Objekten

Objekte können auf verschiedene Weisen miteinander verknüpft werden. Die grundsätzlichen Arten von Beziehungen sind *Hierarchisch* und *Einschluss*.

### <a name="hierarchical-relationship"></a>Hierarchische Beziehung

Wenn Klassen von grundlegenderen Klassen abgeleitet werden, wird von einer *hierarchischen Beziehung* gesprochen. Klassenhierarchien sind nützlich, wenn Elemente beschrieben werden, die einen Untertyp einer allgemeineren Klasse darstellen.

Im folgenden Beispiel nehmen wir an, Sie möchten eine besondere Art eines <xref:System.Windows.Forms.Button>-Elements definieren, das wie ein normales <xref:System.Windows.Forms.Button>-Element agiert, aber auch eine Methode zur Verfügung stellt, die die Vordergrund- und Hintergrundfarben umkehrt.

#### <a name="define-a-class-that-is-derived-from-an-already-existing-class"></a>Definieren einer Klasse, die von einer bereits vorhandenen Klasse abgeleitet ist

1. Verwenden Sie eine [Class-Anweisung](../../../language-reference/statements/class-statement.md) zur Definition einer Klasse, aus der das benötigte Objekt erstellt werden soll.

   ```vb
   Public Class ReversibleButton
   ```

   Achten Sie darauf, dass der letzten Codezeile in der Klasse eine `End Class`-Anweisung folgt. Standardmäßig generiert die integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) bei der Eingabe einer `Class`-Anweisung automatisch ein `End Class`-Element.

2. Der `Class`-Anweisung muss sofort eine [Inherits-Anweisung](../../../language-reference/statements/inherits-statement.md) folgen. Geben Sie die Klasse an, von der Ihre neue Klasse abgeleitet wird.

   ```vb
   Inherits System.Windows.Forms.Button
   ```

   Ihre neue Klasse erbt alle Member, die von der Basisklasse definiert wurden.

3. Fügen Sie den Code für die zusätzlichen Member hinzu, die Ihre abgeleitete Klasse zur Verfügung stellt. Sie können z.B. eine `ReverseColors`-Methode hinzufügen, und die abgeleitete Klasse könnte wie folgt aussehen:

   ```vb
   Public Class ReversibleButton
       Inherits System.Windows.Forms.Button
           Public Sub ReverseColors()
               Dim saveColor As System.Drawing.Color = Me.BackColor
               Me.BackColor = Me.ForeColor
               Me.ForeColor = saveColor
          End Sub
   End Class
   ```

   Wenn Sie ein Objekt aus der- `ReversibleButton` Klasse erstellen, kann es auf alle Member der <xref:System.Windows.Forms.Button> -Klasse sowie `ReverseColors` auf die-Methode und alle anderen neuen Member zugreifen, die Sie in definieren `ReversibleButton` .

Abgeleitete Klassen erben Member aus der Klasse, auf der sie basieren. So können Sie die Komplexität beim Vordringen in einer Klassenhierarchie steigern. Weitere Informationen finden Sie unter [Grundlagen der Vererbung](inheritance-basics.md).

### <a name="compile-the-code"></a>Kompilieren des Codes

Achten Sie darauf, dass der Compiler die Klasse aufrufen kann, von der Ihre neue Klasse abgeleitet werden soll. Dies kann das vollständige Qualifizieren des Namens beinhalten, wie im vorherigen Beispiel, oder das Identifizieren des Namespace in einer [Imports-Anweisung (.NET Namespace und Typ)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md). Wenn sich die Klasse in einem anderen Projekt befindet, müssen Sie möglicherweise einen Verweis auf das Projekt hinzufügen. Weitere Informationen finden Sie unter [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project).

### <a name="containment-relationship"></a>Einschlussbeziehung

Eine andere Möglichkeit zur Verknüpfung von Objekten ist eine *Einschlussbeziehung*. Containerobjekte schließen andere Objekte logisch ein. Beispielsweise enthält das <xref:System.OperatingSystem>-Objekt ein <xref:System.Version>-Objekt logisch, das es durch seine <xref:System.OperatingSystem.Version%2A>-Eigenschaft zurückgibt. Beachten Sie, dass das Container-Objekt physisch kein anderes Objekt enthält.

#### <a name="collections"></a>Sammlungen

Ein bestimmter Typ des Objekteinschlusses wird dargestellt durch *Auflistungen*. Auflistungen sind Gruppen ähnlicher Objekte, die aufgelistet werden können. Visual Basic unterstützt eine bestimmte Syntax in der [for each... Die nächste Anweisung](../../../language-reference/statements/for-each-next-statement.md) , die das Durchlaufen der Elemente einer Auflistung ermöglicht. Zudem ermöglichen Auflistungen die Verwendung eines <xref:Microsoft.VisualBasic.Collection.Item%2A>-Elements zum Abrufen von Elementen anhand ihres Indexes oder anhand der Zuordnung zu einer eindeutigen Zeichenfolge. Auflistungen können einfacher verwendet werden als Arrays, denn Sie können sie zum Hinzufügen oder Entfernen von Elementen ohne Indizes verwenden. Aufgrund ihrer Benutzerfreundlichkeit werden Auflistungen häufig zum Speichern von Formularen und Steuerelementen verwendet.

## <a name="related-topics"></a>Zugehörige Themen

[Exemplarische Vorgehensweise: Definieren von Klassen](walkthrough-defining-classes.md)\
Stellt eine schrittweise Beschreibung des Erstellens einer Klasse bereit.

[Überladene Eigenschaften und Methoden](overloaded-properties-and-methods.md)\
Überladene Eigenschaften und Methoden

[Vererbungs Grundlagen](inheritance-basics.md)\
Beschreibt die Vererbungsmodifizierer, das Außerkraftsetzen von Methoden und Eigenschaften, MyClass und MyBase.

[Objekt Lebensdauer: Erstellen und zerstören von Objekten](object-lifetime-how-objects-are-created-and-destroyed.md)\
Erläutert das Erstellen und Entfernen von Klasseninstanzen.

[Anonyme Typen](anonymous-types.md)\
Beschreibt das Erstellen und Verwenden von anonymen Typen, die Ihnen das Erstellen von Objekten ermöglichen, ohne eine Klassendefinition für den Datentyp zu schreiben.

[Objektinitialisierer: benannte und anonyme Typen](object-initializers-named-and-anonymous-types.md)\
Erläutert Objektinitialisierer, die zum Erstellen von Instanzen von benannten und anonymen Typen mit einem einzelnen Ausdruck verwendet werden.

[Gewusst wie: Ableiten von Eigenschaften Namen und Typen in Deklarationen anonymer Typen](how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)\
Erklärt das Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen. Stellt Beispiele für erfolgreiche und fehlgeschlagene Ableitungen bereit.
