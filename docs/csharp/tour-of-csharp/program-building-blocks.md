---
title: Bausteine der C#-Programme
description: Hier lernen Sie Member, Ausdrücke und Anweisungen von C# kennen. Typen enthalten Member, die Sie schreiben. Diese Member werden aus Anweisungen und Ausdrücken erstellt.
ms.date: 08/06/2020
ms.openlocfilehash: e4350f2c2b6005fb59dd868f0f7f628bd07b0053
ms.sourcegitcommit: ffd4d5e824db6c5f0c3521c0e802fd9e8f0edcbe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "93342695"
---
# <a name="program-building-blocks"></a>Programmbausteine

Die im vorherigen Artikel beschriebenen Typen werden mithilfe der folgenden Bausteine erstellt: [***Member** _](../programming-guide/classes-and-structs/members.md), [_*_Ausdrücke_*_ und _*_Anweisungen_*_](../programming-guide/statements-expressions-operators/index.md).

## <a name="members"></a>Member

Die Member von `class` sind entweder _*_statische Member_*_ oder _*_Instanzmember_*_. Statische Member gehören zu Klassen, Instanzmember gehören zu Objekten (Instanzen von Klassen).

In der folgenden Liste finden Sie einen Überblick über die Memberarten, die eine Klasse enthalten kann.

- _*Konstanten**: Konstante Werte, die der Klasse zugeordnet sind
- **Felder:**  Variablen, die der Klasse zugeordnet werden
- **Methods** (Methoden):  Aktionen, die von der Klasse ausgeführt werden
- **Properties:** Aktionen im Zusammenhang mit dem Lesen und Schreiben von benannten Eigenschaften der Klasse
- **Indexer:** Aktionen im Zusammenhang mit dem Indizieren von Instanzen der Klasse, z.B. einem Array
- **Ereignisse:** Benachrichtigungen, die von der Klasse generiert werden können
- **Operatoren:** Operatoren für Konvertierungen und Ausdrücke, die von der Klasse unterstützt werden
- **Konstruktoren:** Aktionen, die zum Initialisieren von Instanzen der Klasse oder der Klasse selbst benötigt werden
- **Finalizer:** Aktionen, die ausgeführt werden, bevor Instanzen der Klasse dauerhaft verworfen werden
- **Typen:** Geschachtelte Typen, die von der Klasse deklariert werden

## <a name="accessibility"></a>Barrierefreiheit

Jeder Member einer Klasse ist mit einem Zugriff verknüpft, der die Regionen des Programmtexts steuert, die auf den Member zugreifen können. Es gibt sechs mögliche Formen des Zugriffs. Die Zugriffsmodifizierer werden im Folgenden zusammengefasst.

- `public`: Der Zugriff ist nicht eingeschränkt.
- `private`: Der Zugriff ist auf diese Klasse beschränkt.
- `protected`: Der Zugriff ist auf diese Klasse oder von dieser abgeleiteten Klassen beschränkt.
- `internal`: Der Zugriff ist auf die aktuelle Assembly (`.exe` oder `.dll`) beschränkt.
- `protected internal`: Der Zugriff ist auf diese Klasse, auf Klassen, die von dieser Klasse abgeleitet wurden, oder auf Klassen innerhalb der gleichen Assembly beschränkt.
- `private protected`: Der Zugriff ist auf diese Klasse und auf Klassen in derselben Assembly beschränkt, die von diesem Typ abgeleitet wurden.

## <a name="fields"></a>Felder

Ein *Feld* ist eine Variable, die einer Klasse oder einer Instanz einer Klasse zugeordnet ist.

Ein Feld, das mit dem static-Modifizierer deklariert wurde, definiert ein statisches Feld. Ein statisches Feld identifiziert genau einen Speicherort. Unabhängig davon, wie viele Instanzen einer Klasse erstellt werden, gibt es immer nur eine Kopie eines statischen Felds.

Ein Feld, das ohne den static-Modifizierer deklariert wurde, definiert ein Instanzfeld. Jede Instanz einer Klasse enthält eine separate Kopie aller Instanzfelder dieser Klasse.

Im folgenden Beispiel weist jede Instanz der `Color`-Klasse eine separate Kopie der Instanzfelder `R`, `G` und `B` auf, aber es gibt nur eine Kopie der statischen Felder `Black`, `White`, `Red`, `Green` und `Blue`:

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="ColorClassDefinition":::

Wie im vorherigen Beispiel gezeigt, können *schreibgeschützte Felder* mit einem `readonly`-Modifizierer deklariert werden. Zuweisungen zu einem schreibgeschützten Feld können nur im Rahmen der Deklaration des Felds oder in einem Konstruktor derselben Klasse auftreten.

## <a name="methods"></a>Methoden

Eine *Methode* ist ein Member, das eine Berechnung oder eine Aktion implementiert, die durch ein Objekt oder eine Klasse durchgeführt werden kann. Auf *statische Methoden* wird über die Klasse zugegriffen. Auf *Instanzmethoden* wird über Instanzen der Klasse zugegriffen.

Methoden verfügen über eine Liste von *Parametern* , die Werte oder Variablenverweise darstellen, die an die Methode übergeben werden. Methoden besitzen einen *Rückgabetyp* , der den Typ des Werts festlegt, der von der Methode berechnet und zurückgegeben wird. Der Rückgabetyp einer Methode lautet `void`, wenn kein Wert zurückgegeben wird.

Ebenso wie Typen können Methoden einen Satz an Typparametern aufweisen, für den beim Aufruf der Methode Typargumente angegeben werden müssen. Im Gegensatz zu Typen können die Typargumente häufig aus den Argumenten eines Methodenaufrufs abgeleitet werden und müssen nicht explizit angegeben werden.

Die *Signatur* einer Methode muss innerhalb der Klasse eindeutig sein, in der die Methode deklariert ist. Die Signatur einer Methode besteht aus dem Namen der Methode, der Anzahl von Typparametern und der Anzahl, den Modifizierern und den Typen der zugehörigen Parameter. Die Signatur einer Methode umfasst nicht den Rückgabetyp.

Wenn es sich bei einem Methodenkörper um einen einzelnen Ausdruck handelt, kann die Methode mithilfe eines kompakten Ausdrucksformat definiert werden. Dies wird im folgenden Beispiel veranschaulicht:

```csharp
public override string ToString() => "This is an object";
```

### <a name="parameters"></a>Parameter

Parameter werden dazu verwendet, Werte oder Variablenverweise an Methoden zu übergeben. Die Parameter einer Methode erhalten ihre tatsächlichen Werte über *Argumente* , die angegeben werden, wenn die Methode aufgerufen wird. Es gibt vier Arten von Parametern: Wertparameter, Verweisparameter, Ausgabeparameter und Parameterarrays.

Ein *Wertparameter* wird zum Übergeben von Eingabeargumenten verwendet. Ein Wertparameter entspricht einer lokalen Variablen, die ihren Anfangswert von dem Argument erhält, das für den Parameter übergeben wurde. Änderungen an einem Wertparameter wirken sich nicht auf das Argument aus, das für den Parameter übergeben wurde.

Wertparameter können optional sein, indem ein Standardwert festgelegt wird, damit die zugehörigen Argumente weggelassen werden können.

Ein *Verweisparameter* wird zum Übergeben von Argumenten als Verweis verwendet. Das für einen Verweisparameter übergebene Argument muss eine Variable mit einem definitiven Wert sein. Währen der Ausführung der Methode stellt der Verweisparameter denselben Speicherort wie die Argumentvariable dar. Ein Verweisparameter wird mit dem `ref`-Modifizierer deklariert. Das folgende Beispiel veranschaulicht die Verwendung des `ref`-Parameters.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="RefExample":::

Ein *Ausgabeparameter* wird zum Übergeben von Argumenten als Verweis verwendet. Er ist einem Verweisparameter ähnlich, außer dass er nicht erfordert, dass Sie explizit dem vom Aufrufer bereitgestellten Argument einen Wert zuweisen. Ein Ausgabeparameter wird mit dem `out`-Modifizierer deklariert. Das folgende Beispiel zeigt die Verwendung von `out`-Parametern mithilfe der in C# 7 eingeführten Syntax.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="OutExample":::

Ein *Parameterarray* ermöglicht es, eine variable Anzahl von Argumenten an eine Methode zu übergeben. Ein Parameterarray wird mit dem `params`-Modifizierer deklariert. Nur der letzte Parameter einer Methode kann ein Parameterarray sein, und es muss sich um ein eindimensionales Parameterarray handeln. Die Methoden `Write` und `WriteLine` der Klasse <xref:System.Console?displayProperty=nameWithType> sind gute Beispiele für die Nutzung eines Parameterarrays. Sie werden folgendermaßen deklariert.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="ConsoleExtract":::

Innerhalb einer Methode mit einem Parameterarray verhält sich das Parameterarray wie ein regulärer Parameter des Arraytyps. Beim Aufruf einer Methode mit einem Parameterarray ist es jedoch möglich, entweder ein einzelnes Argument des Parameterarraytyps oder eine beliebige Anzahl von Argumenten des Elementtyps des Parameterarrays zu übergeben. Im letzteren Fall wird automatisch eine Arrayinstanz erstellt und mit den vorgegebenen Argumenten initialisiert. Dieses Beispiel:

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="UseParamsArgs":::

...entspricht dem folgenden Code:

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="CompilerParams":::

### <a name="method-body-and-local-variables"></a>Methodenkörper und lokale Variablen

Der Methodenkörper gibt die Anweisungen an, die beim Aufruf der Methode ausgeführt werden sollen.

Ein Methodenkörper kann Variablen deklarieren, die für den Aufruf der Methode spezifisch sind. Diese Variable werden *lokale Variablen* genannt. Die Deklaration einer lokalen Variable gibt einen Typnamen, einen Variablennamen und eventuell einen Anfangswert an. Im folgenden Beispiel wird eine lokale Variable `i` mit einem Anfangswert von 0 und einer lokalen Variablen `j` ohne Anfangswert deklariert.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="SquaresClass":::

In C# muss eine lokale Variable *definitiv zugewiesen* sein, bevor ihr Wert abgerufen werden kann. Wenn die vorherige Deklaration von `i` beispielsweise keinen Anfangswert enthält, würde der Compiler bei der späteren Verwendung von `i` einen Fehler melden, weil `i` zu diesen Zeitpunkten im Programm nicht definitiv zugewiesen ist.

Eine Methode kann `return`-Anweisungen verwenden, um die Steuerung an den zugehörigen Aufrufer zurückzugeben. In einer Methode, die `void` zurückgibt, können `return`-Anweisungen keinen Ausdruck angeben. In einer Methode, die nicht „void“ zurückgibt, müssen`return`-Anweisungen einen Ausdruck enthalten, der den Rückgabewert berechnet.

### <a name="static-and-instance-methods"></a>Statische Methoden und Instanzmethoden

Eine Methode, die mit einem `static`-Modifizierer deklariert wird, ist eine *statische Methode*. Eine statische Methode führt keine Vorgänge für eine spezifische Instanz aus und kann nur direkt auf statische Member zugreifen.

Eine Methode, die ohne einen `static`-Modifizierer deklariert wird, ist eine *Instanzmethode*. Eine Instanzmethode führt Vorgänge für eine spezifische Instanz aus und kann sowohl auf statische Member als auch auf Instanzmember zugreifen. Auf die Instanz, für die eine Instanzmethode aufgerufen wurde, kann explizit als `this` zugegriffen werden. Es ist ein Fehler, in einer statischen Methode auf `this` zu verweisen.

Die folgende `Entity`-Klasse umfasst sowohl statische Member als auch Instanzmember.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="EntityClass":::

Jede `Entity`-Instanz enthält eine Seriennummer (und vermutlich weitere Informationen, die hier nicht angezeigt werden). Der `Entity`-Konstruktor (der einer Instanzmethode ähnelt) initialisiert die neue Instanz mit der nächsten verfügbaren Seriennummer. Da der Konstruktor ein Instanzmember ist, kann er sowohl auf das `_serialNo`-Instanzfeld als auch auf das statische `s_nextSerialNo`-Feld zugreifen.

Die statischen Methoden `GetNextSerialNo` und `SetNextSerialNo` können auf das statische Feld `s_nextSerialNo` zugreifen, aber es wäre ein Fehler, über diese Methoden direkt auf das Instanzfeld `_serialNo` zuzugreifen.

Im folgenden Beispiel wird die Verwendung der `Entity`-Klasse veranschaulicht.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="UsingEntity":::

Die statischen Methoden `SetNextSerialNo` und `GetNextSerialNo` werden für die Klasse aufgerufen, während die `GetSerialNo`-Instanzmethode für Instanzen der Klasse aufgerufen wird.

### <a name="virtual-override-and-abstract-methods"></a>Virtuelle, überschriebene und abstrakte Methoden

Wenn die Deklaration einer Instanzmethode einen `virtual`-Modifizierer enthält, wird die Methode als *virtuelle Methode* bezeichnet. Ist kein virtual-Modifizierer vorhanden, spricht man von einer *nicht virtuellen Methode*.

Beim Aufruf einer virtuellen Methode bestimmt der *Laufzeittyp* der Instanz, für die der Aufruf erfolgt, die tatsächlich aufzurufende Methodenimplementierung. Beim Aufruf einer nicht virtuellen Methode ist der *Kompilierzeittyp* der bestimmende Faktor.

Eine virtuelle Methode kann in einer abgeleiteten Klasse *überschrieben* werden. Wenn eine Instanzmethodendeklaration einen override-Modifizierer enthält, überschreibt die Methode eine geerbte virtuelle Methode mit derselben Signatur. Mit der virtuellen Methodendeklaration wird eine neue Methode eingeführt. Eine Deklaration einer Überschreibungsmethode spezialisiert eine vorhandene geerbte virtuelle Methode, indem eine neue Implementierung dieser Methode bereitgestellt wird.

Eine *abstrakte Methode* ist eine virtuelle Methode ohne Implementierung. Eine abstrakte Methode wird mit dem Modifizierer `abstract` deklariert und ist nur in einer abstrakten Klasse zulässig. Eine abstrakte Methode muss in jeder nicht abstrakten abgeleiteten Klasse überschrieben werden.

Im folgenden Beispiel wird die abstrakte Klasse `Expression` deklariert, die einen Ausdrucksbaumstrukturknoten sowie drei abgeleitete Klassen repräsentiert: `Constant`, `VariableReference` und `Operation`. Diese implementieren Ausdrucksbaumstrukturknoten für Konstanten, variable Verweise und arithmetische Operationen. (Dieses Beispiel ähnelt den Ausdrucksbaumstrukturtypen, ist aber nicht mit diesen verwandt.)

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="WorkingWithExpressions":::

Die vorherigen vier Klassen können zum Modellieren arithmetischer Ausdrücke verwendet werden. Beispielsweise kann mithilfe von Instanzen dieser Klassen der Ausdruck `x + 3` folgendermaßen dargestellt werden.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="UseExpressions":::

Die `Evaluate`-Methode einer `Expression`-Instanz wird aufgerufen, um den vorgegebenen Ausdruck auszuwerten und einen `double`-Wert zu generieren. Die Methode verwendet ein `Dictionary`-Argument, das Variablennamen (als Schlüssel der Einträge) und Werte (als Werte der Einträge) enthält. Da `Evaluate` eine abstrakte Methode ist, müssen nicht-abstrakte Klassen, die von `Expression` abgeleitet sind, `Evaluate` außer Kraft setzen.

Eine Implementierung von `Constant` für `Evaluate` gibt lediglich die gespeicherte Konstante zurück. Eine Implementierung von `VariableReference` sucht im Wörterbuch nach dem Variablennamen und gibt den Ergebniswert zurück. Eine Implementierung von `Operation` wertet zunächst (durch einen rekursiven Aufruf der zugehörigen `Evaluate`-Methoden) den linken und rechten Operanden aus und führt dann die vorgegebene arithmetische Operation aus.

Das folgende Programm verwendet die `Expression`-Klassen zum Auswerten des Ausdrucks `x * (y + 2)` für verschiedene Werte von `x` und `y`.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="UsingExpressions":::

### <a name="method-overloading"></a>Methodenüberladung

Das *Überladen* von Methoden macht es möglich, dass mehrere Methoden in derselben Klasse denselben Namen verwenden, solange sie eindeutige Signaturen aufweisen. Beim Kompilieren des Aufrufs einer überladenen Methode verwendet der Compiler die *Überladungsauflösung* , um die spezifische Methode zu ermitteln, die aufgerufen werden soll. Die Überladungsauflösung ermittelt die Methode, die den Argumenten am besten entspricht. Wenn keine optimale Übereinstimmung gefunden wird, wird ein Fehler gemeldet. Das folgende Beispiel zeigt die Verwendung der Überladungsauflösung. Der Kommentar für jeden Aufruf in der `UsageExample`-Methode zeigt, welche Methode aufgerufen wird.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="Overloading":::

Wie im Beispiel gezeigt, kann eine bestimmte Methode immer ausgewählt werden, indem die Argumente explizit in die exakten Parametertypen und Typargumente umgewandelt werden.

## <a name="other-function-members"></a>Andere Funktionsmember

Member, die ausführbaren Code enthalten, werden als *Funktionsmember* einer Klasse bezeichnet. Im vorherigen Abschnitt wurden Methoden beschrieben, die die Haupttypen von Funktionsmembern sind. In diesem Abschnitt werden die weiteren Funktionsmember behandelt, die C# unterstützt: Konstruktoren, Eigenschaften, Indexer, Ereignisse, Operatoren und Finalizer.

Im folgenden Beispiel wird eine generische Klasse namens `MyList<T>` gezeigt, die eine wachsende Liste von Objekten implementiert. Die Klasse enthält verschiedene Beispiele der gängigsten Arten von Funktionsmembern.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="ListExample":::

### <a name="constructors"></a>Konstruktoren

C# unterstützt sowohl Instanzkonstruktoren als auch statische Konstruktoren. Ein *Instanzkonstruktor* ist ein Member, der die erforderlichen Aktionen zum Initialisieren einer Instanz einer Klasse implementiert. Ein *statischer Konstruktor* ist ein Member, der die zum Initialisieren einer Klasse erforderlichen Aktionen implementiert, um die Klasse beim ersten Laden selbst zu initialisieren.

Ein Konstruktor wird wie eine Methode ohne Rückgabetyp und mit demselben Namen wie die enthaltende Klasse deklariert. Wenn eine Konstruktordeklaration einen `static`-Modifizierer enthält, deklariert diese einen statischen Konstruktor. Andernfalls wird ein Instanzkonstruktor deklariert.

Instanzkonstruktoren können überladen werden und optionale Parameter verwenden. Die `MyList<T>`-Klasse deklariert z.B. einen Instanzkonstruktor mit einem einzelnen optionalen `int`-Parameter. Instanzkonstruktoren werden über den `new`-Operator aufgerufen. Die folgenden Anweisungen weisen zwei Instanzen von `MyList<string>` unter Verwendung des Konstruktors der `MyList`-Klasse zu, mit dem optionalen Argument und ohne das optionale Argument.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="CreateLists":::

Im Gegensatz zu anderen Membern werden Instanzkonstruktoren nicht geerbt. Eine Klasse weist keine anderen Instanzkonstruktoren auf als diejenigen, die tatsächlich in der Klasse deklariert wurden. Wenn kein Instanzkonstruktor für eine Klasse angegeben ist, wird automatisch ein leerer Instanzkonstruktor ohne Parameter bereitgestellt.

### <a name="properties"></a>Eigenschaften

*Eigenschaften* sind eine natürliche Erweiterung der Felder. Beide sind benannte Member mit zugeordneten Typen, und für den Zugriff auf Felder und Eigenschaften wird dieselbe Syntax verwendet. Im Gegensatz zu Feldern geben Eigenschaften jedoch keine Speicherorte an. Stattdessen verfügen Eigenschaften über *Zugriffsmethoden* , die die ausgeführten Anweisungen angeben, wenn ihre Werte gelesen oder geschrieben werden.

Eine Eigenschaft wird wie ein Feld deklariert, abgesehen davon, dass die Deklaration nicht auf ein Semikolon, sondern auf einen get- oder set-Accessor endet, der von den Trennzeichen `{` und `}` umschlossen wird. Eine Eigenschaft, die sowohl einen get- als auch einen set-Accessor aufweist, ist eine *Eigenschaft mit Lese- und Schreibzugriff*. Eine Eigenschaft, die nur einen get-Accessor aufweist, ist *schreibgeschützt* , eine Eigenschaft, die nur einen set-Accessor aufweist, ist *lesegeschützt*.

Ein get-Accessor entspricht einer Methode ohne Parameter mit einem Rückgabewert des Eigenschaftstyps. Ein set-Accessor entspricht einer Methode mit einem einzigen Parameter namens „value“ ohne Rückgabetyp. Die get-Zugriffsmethode berechnet den Wert der Eigenschaft. Die set-Zugriffsmethode stellt einen neuen Wert für die Eigenschaft bereit. Wenn die Eigenschaft das Ziel einer Zuweisung oder der Operand von `++` oder `--` ist, wird die set-Zugriffsmethode aufgerufen. In anderen Fällen, in denen die Eigenschaft referenziert wird, wird die get-Zugriffsmethode aufgerufen.

Die `MyList<T>`-Klasse deklariert die beiden Eigenschaften „`Count`“ und „`Capacity`“, von denen die eine schreibgeschützt ist und die andere Lese- und Schreibzugriff besitzt. Im folgenden Beispielcode wird die Verwendung dieser Eigenschaften veranschaulicht:

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="AccessProperties":::

Ähnlich wie bei Feldern und Methoden unterstützt C# sowohl Instanzeigenschaften als auch statische Eigenschaften. Statische Eigenschaften werden mit dem static-Modifizierer, Instanzeigenschaften werden ohne static-Modifizierer deklariert.

Die Accessors einer Eigenschaft können virtuell sein. Wenn eine Eigenschaftendeklaration einen `virtual`-, `abstract`- oder `override`-Modifizierer enthält, wird dieser auf den Accessor der Eigenschaft angewendet.

### <a name="indexers"></a>Indexer

Ein *Indexer* ist ein Member, mit dem Objekte wie ein Array indiziert werden können. Ein Indexer wird wie eine Eigenschaft deklariert, abgesehen davon, dass der Name des Members `this` ist, gefolgt von einer Parameterliste, die zwischen die Trennzeichen `[` und `]` geschrieben wird. Die Parameter stehen im Accessor des Indexers zur Verfügung. Ähnlich wie Eigenschaften können Indexer Lese-/Schreibzugriff besitzen, schreibgeschützt und lesegeschützt sein und virtuelle Accessors verwenden.

Die `MyList<T>`-Klasse deklariert einen einzigen Indexer mit Lese-/Schreibzugriff, der einen `int`-Parameter akzeptiert. Der Indexer ermöglicht es, Instanzen von `MyList<T>` mit `int`-Werten zu indizieren. Beispiel:

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="ListAccess":::

Indexer können überladen werden. Eine Klasse kann mehrere Indexer deklarieren, solange sich die Anzahl oder die Typen ihrer Parameter unterscheiden.

### <a name="events"></a>Events

Ein *Ereignis* ist ein Member, der es einer Klasse oder einem Objekt ermöglicht, Benachrichtigungen bereitzustellen. Ein Ereignis wird wie ein Feld deklariert, abgesehen davon, dass es ein `event`-Schlüsselwort enthält und einen Delegattyp aufweisen muss.

Innerhalb einer Klasse, die einen Ereignismember deklariert, verhält sich das Ereignis wie ein Feld des Delegattyps (vorausgesetzt, das Ereignis ist nicht abstrakt und deklariert keine Zugriffsmethoden). Das Feld speichert einen Verweis auf einen Delegaten, der die Ereignishandler repräsentiert, die dem Ereignis hinzugefügt wurden. Wenn keine Ereignishandler vorhanden sind, ist das Feld `null`.

Die `MyList<T>`-Klasse deklariert einen einzigen Ereignismember namens `Changed`, der angibt, dass der Liste ein neues Element hinzugefügt wurde. Das Changed-Ereignis wird durch die virtuelle Methode `OnChanged` ausgelöst, die zunächst prüft, ob das Ereignis `null` ist (d.h. nicht über Handler verfügt). Das Auslösen eines Ereignisses entspricht exakt dem Aufrufen des Delegats, der durch das Ereignis repräsentiert wird. Es gibt keine speziellen Sprachkonstrukte zum Auslösen von Ereignissen.

Clients reagieren über *Ereignishandler* auf Ereignisse. Ereignishandler werden unter Verwendung des `+=`-Operators angefügt und mit dem `-=`-Operator entfernt. Im folgenden Beispiel wird dem `Changed`-Ereignis von `MyList<string>` ein Ereignishandler hinzugefügt.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="RespondToEvents":::

In fortgeschrittenen Szenarios, in denen die zugrunde liegende Speicherung eines Ereignisses gesteuert werden soll, kann eine Ereignisdeklaration explizit die Zugriffsmethoden `add` und `remove` bereitstellen, die der Zugriffsmethode `set` einer Eigenschaft ähneln.

### <a name="operators"></a>Operatoren

Ein *Operator* ist ein Member, der die Bedeutung der Anwendung eines bestimmten Ausdrucksoperators auf Instanzen einer Klasse definiert. Es können drei Arten von Operatoren definiert werden: unäre Operatoren, binäre Operatoren und Konvertierungsoperatoren. Alle Operatoren müssen als `public` und `static` deklariert werden.

Die `MyList<T>`-Klasse deklariert zwei Operatoren: `operator ==` und `operator !=`. Diese überschriebenen Operatoren verleihen Ausdrücken eine neue Bedeutung, die diese Operatoren auf `MyList`-Instanzen anwenden. Insbesondere die Operatoren definieren die Gleichheit für zwei Instanzen von `MyList<T>`, indem alle enthaltenen Objekte mithilfe ihrer `Equals`-Methoden verglichen werden. Im folgenden Beispiel wird der `==`-Operator verwendet, um zwei Instanzen von `MyList<int>` zu vergleichen.

:::code language="csharp" source="./snippets/shared/ClassesObjects.cs" ID="ListAddition":::

Die erste Methode `Console.WriteLine` gibt `True` aus, weil die zwei Listen dieselbe Anzahl von Objekten mit denselben Werten in derselben Reihenfolge enthalten. Wenn `MyList<T>` nicht `operator ==` definieren würde, würde die Ausgabe der ersten `Console.WriteLine`-Methode `False` lauten, weil `a` und `b` auf unterschiedliche `MyList<int>`-Instanzen verweisen.

### <a name="finalizers"></a>Finalizer

Ein *Finalizer* ist ein Member, der die erforderlichen Aktionen zum Bereinigen einer Instanz einer Klasse implementiert. In der Regel ist ein Finalizer erforderlich, um nicht verwaltete Ressourcen freizugeben. Finalizer können weder Parameter noch Zugriffsmodifizierer aufweisen und können nicht explizit aufgerufen werden. Der Finalizer für eine Instanz wird bei der Garbagecollection automatisch aufgerufen. Weitere Details finden Sie im Artikel zum Thema [Finalizer](../programming-guide/classes-and-structs/destructors.md).

Der Garbage Collector kann weitestgehend selbst über den Zeitpunkt der Objektbereinigung und die Ausführung der Finalizer entscheiden. Insbesondere der Zeitpunkt für den Aufruf der Finalizer ist nicht festgelegt, und Finalizer können für beliebige Threads ausgeführt werden. Aus diesen und weiteren Gründen sollten Klassen Finalizer nur dann implementieren, wenn keine andere Lösung möglich ist.

Die `using`-Anweisung bietet einen besseren Ansatz für die Objektzerstörung.

## <a name="expressions"></a>Ausdrücke

*Ausdrücke* bestehen aus *Operanden* und *Operatoren*. Die Operatoren eines Ausdrucks geben an, welche Operationen auf die Operanden angewendet werden. Beispiele für Operatoren sind `+`, `-`, `*`, `/` und `new`. Beispiele für Operanden sind Literale, Felder, lokale Variablen und Ausdrücke.

Wenn ein Ausdruck mehrere Operatoren enthält, steuert die *Rangfolge* der Operatoren die Reihenfolge, in der die einzelnen Operatoren ausgewertet werden. Der Ausdruck `x + y * z` wird z.B. als `x + (y * z)` ausgewertet, da der `*`-Operator Vorrang vor dem `+`-Operator hat.

Tritt ein Operand zwischen zwei Operatoren mit gleicher Rangfolge auf, steuert die *Assoziativität* der Operatoren die Reihenfolge, in der die Vorgänge ausgeführt werden:

* Mit Ausnahme der Zuweisungs- und NULL-Sammeloperatoren sind alle binären Operatoren *linksassoziativ* , was bedeutet, dass Vorgänge von links nach rechts ausgeführt werden. `x + y + z` wird beispielsweise als `(x + y) + z` ausgewertet.
* Die Zuweisungsoperatoren, die NULL-Sammeloperatoren `??` und `??=` und der bedingte Operator `?:` sind *rechtsassoziativ* , d.h., die Operationen werden von rechts nach links ausgeführt. `x = y = z` wird beispielsweise als `x = (y = z)` ausgewertet.

Rangfolge und Assoziativität können mit Klammern gesteuert werden. In `x + y * z` wird beispielsweise zuerst `y` mit `z` multipliziert und dann das Ergebnis zu `x` addiert, aber in `(x + y) * z` werden zunächst `x` und `y` addiert, und dann wird das Ergebnis mit `z` multipliziert.

Die meisten Operatoren können [*überladen*](../language-reference/operators/operator-overloading.md) werden. Das Überladen von Operatoren ermöglicht die Angabe benutzerdefinierter Operatorimplementierungen für Vorgänge, in denen einer der Operanden oder beide einer benutzerdefinierten Klasse oder einem benutzerdefinierten Strukturtyp angehören.

C# bietet eine Reihe von Operatoren für [arithmetische](../language-reference/operators/arithmetic-operators.md), [logische](../language-reference/operators/boolean-logical-operators.md), [bitweise und Verschiebungsvorgänge](../language-reference/operators/bitwise-and-shift-operators.md) sowie Vergleiche von [Gleichheit](../language-reference/operators/equality-operators.md) und [Reihenfolge](../language-reference/operators/comparison-operators.md).

Die vollständige Liste der nach Rangfolgenebene sortierten C#-Operatoren finden Sie unter [C#-Operatoren](../language-reference/operators/index.md).

## <a name="statements"></a>Anweisungen

Die Aktionen eines Programms werden mit *Anweisungen* ausgedrückt. C# unterstützt verschiedene Arten von Anweisungen, von denen ein Teil als eingebettete Anweisungen definiert ist.

- Ein *Block* ermöglicht, mehrere Anweisungen in Kontexten zu schreiben, in denen eine einzelne Anweisung zulässig ist. Ein Block besteht aus einer Liste von Anweisungen, die zwischen den Trennzeichen `{` und `}` geschrieben sind.
- *Deklarationsanweisungen* werden verwendet, um lokale Variablen und Konstanten deklarieren.
- *Ausdrucksanweisungen* werden zum Auswerten von Ausdrücken verwendet. Ausdrücke, die als Anweisungen verwendet werden können, enthalten Methodenaufrufe, Objektzuordnungen mit dem `new`-Operator, Zuweisungen mit `=` und den Verbundzuweisungsoperatoren, Inkrementier- und Dekrementiervorgänge unter Verwendung des `++`- und `--`-Operators und `await`-Ausdrücke.
- *Auswahlanweisungen* werden verwendet, um eine Anzahl von möglichen Anweisungen für die Ausführung anhand des Werts eines Ausdrucks auszuwählen. Diese Gruppe enthält die Anweisungen `if` und `switch`.
- *Iterationsanweisungen* werden verwendet, um eine eingebettete Anweisung wiederholt auszuführen. Diese Gruppe enthält die Anweisungen `while`, `do`, `for` und `foreach`.
- *Sprunganweisungen* werden verwendet, um die Steuerung zu übertragen. Diese Gruppe enthält die Anweisungen `break`, `continue`, `goto`, `throw`, `return` und `yield`.
- Mit der `try`... `catch`-Anweisung werden Ausnahmen abgefangen, die während der Ausführung eines Blocks auftreten, und mit der `try`... `finally`-Anweisung wird Finalisierungscode angegeben, der immer ausgeführt wird, unabhängig davon, ob eine Ausnahme aufgetreten ist oder nicht.
- Mit den Anweisungen `checked` und `unchecked` wird der Überlaufüberprüfungs-Kontext für arithmetische Operationen für Ganzzahltypen und Konvertierungen gesteuert.
- Die `lock`-Anweisung wird verwendet, um die Sperre für gegenseitigen Ausschluss für ein bestimmtes Objekt abzurufen, eine Anweisung auszuführen und die Sperre aufzuheben.
- Die `using`-Anweisung wird verwendet, um eine Ressource abzurufen, eine Anweisung auszuführen und dann diese Ressource zu verwerfen.

In der folgenden Liste werden die Arten von Anweisungen aufgeführt, die verwendet werden können:

* Deklaration lokaler Variablen
* Deklaration lokaler Konstanten
* Ausdrucksanweisung
* `if`-Anweisung
* `switch`-Anweisung
* `while`-Anweisung
* `do`-Anweisung
* `for`-Anweisung
* `foreach`-Anweisung
* `break`-Anweisung
* `continue`-Anweisung
* `goto`-Anweisung
* `return`-Anweisung
* `yield`-Anweisung
* `throw`-Anweisungen und `try`-Anweisungen
* `checked`- und `unchecked`-Anweisungen
* `lock`-Anweisung
* `using`-Anweisung

>[!div class="step-by-step"]
>[Zurück](types.md)
>[Weiter](features.md)
