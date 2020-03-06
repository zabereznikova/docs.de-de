---
title: Klassen und Objekte in C# – Überblick über C#
description: Neu bei C#? Lesen Sie diese Übersicht über Klassen, Objekte und Vererbung.
ms.date: 02/27/2020
ms.assetid: 63a89bde-0f05-4bc4-b0cd-4f693854f0cd
ms.openlocfilehash: c178e11b5667905f75538555c8a309e2fdb4a9ef
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159181"
---
# <a name="classes-and-objects"></a>Klassen und Objekte

*Klassen* sind die grundlegendsten der C#-Typen. Eine Klasse ist eine Datenstruktur, die einen Zustand (Felder) und Aktionen (Methoden und andere Funktionsmember) in einer einzigen Einheit kombiniert. Eine Klasse stellt eine Definition für dynamisch erstellte *Instanzen* der Klasse, auch bekannt als *Objekte* bereit. Klassen unterstützen *Vererbung* und *Polymorphie*. Dies sind Mechanismen, durch die *abgeleitete Klassen* erweitert und *Basisklassen* spezialisiert werden können.

Neue Klassen werden mithilfe von Klassendeklarationen erstellt. Eine Klassendeklaration beginnt mit einem Header, der die Attribute und Modifizierer der Klasse, den Namen der Klasse, die Basisklasse (sofern vorhanden) und die von der Klasse implementierten Schnittstellen angibt. Auf den Header folgt der Klassenkörper. Dieser besteht aus einer Liste der Memberdeklarationen, die zwischen den Trennzeichen `{` und `}` eingefügt werden.

Im folgenden Code wird die Deklaration einer einfachen Klasse namens `Point` veranschaulicht:

[!code-csharp[PointClass](~/samples/snippets/csharp/tour/classes-and-objects/Point.cs#L3-L11)]

Instanzen von Klassen werden mit dem `new`-Operator erstellt. Dieser reserviert Speicher für eine neue Instanz, ruft einen Konstruktor zum Initialisieren der Instanz auf und gibt einen Verweis auf die Instanz zurück. Mit den folgenden Anweisungen werden zwei Point-Objekte erstellt und Verweise auf diese Objekte in zwei Variablen gespeichert:

[!code-csharp[PointExample](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L9-L10)]

Der von einem Objekt belegte Speicher wird automatisch wieder freigegeben, wenn das Objekt nicht mehr erreichbar ist. Es ist weder erforderlich noch möglich, die Zuweisung von Objekten in C# explizit aufzuheben.

## <a name="members"></a>Member

Die Member einer Klasse sind entweder statische Member oder Instanzmember. Statische Member gehören zu Klassen, Instanzmember gehören zu Objekten (Instanzen von Klassen).

In der folgenden Liste finden Sie einen Überblick über die Memberarten, die eine Klasse enthalten kann.

- Konstanten
  - Konstante Werte, die der Klasse zugeordnet sind
- Felder
  - Variablen der Klasse
- Methoden
  - Berechnungen und Aktionen, die von der Klasse ausgeführt werden
- Eigenschaften
  - Aktionen im Zusammenhang mit dem Lesen und Schreiben von benannten Eigenschaften der Klasse
- Indexer
  - Aktionen im Zusammenhang mit dem Indizieren von Instanzen der Klasse, z.B. einem Array
- Ereignisse
  - Benachrichtigungen, die von der Klasse generiert werden können
- Operatoren
  - Operatoren für Konvertierungen und Ausdrücke, die von der Klasse unterstützt werden
- Konstruktoren
  - Aktionen, die zum Initialisieren von Instanzen der Klasse oder der Klasse selbst benötigt werden
- Finalizer
  - Aktionen, die ausgeführt werden, bevor Instanzen der Klasse dauerhaft verworfen werden
- Typen
  - Geschachtelte Typen, die von der Klasse deklariert werden

## <a name="accessibility"></a>Zugriff

Jeder Member einer Klasse ist mit einem Zugriff verknüpft, der die Regionen des Programmtexts steuert, die auf den Member zugreifen können. Es gibt sechs mögliche Formen des Zugriffs. Die Zugriffsmodifizierer werden im Folgenden zusammengefasst.

- `public`
  - Der Zugriff ist nicht eingeschränkt.
- `protected`
  - Der Zugriff ist auf diese Klasse oder von dieser abgeleiteten Klassen beschränkt.
- `internal`
  - Der Zugriff ist auf die aktuelle Assembly beschränkt („.exe“, „.dll“ usw.).
- `protected internal`
  - Der Zugriff ist auf die enthaltende Klasse, auf Klassen, die von der enthaltenden Klasse abgeleitet sind, oder auf Klassen innerhalb der gleichen Assembly beschränkt.
- `private`
  - Der Zugriff ist auf diese Klasse beschränkt.
- `private protected`
  - Der Zugriff ist auf die enthaltende Klasse oder auf Klassen beschränkt, die vom enthaltenden Typ in der gleichen Assembly abgeleitet werden.

## <a name="type-parameters"></a>Typparameter

Eine Klassendefinition kann einen Satz an Typparametern angeben, indem eine Liste der Typparameternamen in spitzen Klammern an den Klassennamen angehängt wird. Die Typparameter können dann im Körper der Klassendeklarationen zum Definieren der Klassenmember verwendet werden. Im folgenden Beispiel lauten die Typparameter von `Pair``TFirst` und `TSecond`:

[!code-csharp[Pair](~/samples/snippets/csharp/tour/classes-and-objects/Pair.cs#L3-L7)]

Ein Klassentyp, der zum Akzeptieren von Typparametern deklariert wird, wird als *generischer Klassentyp* bezeichnet. Struktur-, Schnittstellen- und Delegattypen können auch generisch sein.
Wenn die generische Klasse verwendet wird, müssen für jeden der Typparameter Typargumente angegeben werden:

[!code-csharp[PairExample](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L15-L17)]

Ein generischer Typ, für den Typargumente angegeben wurden (siehe `Pair<int,string>` oben), wird als *konstruierter Typ* bezeichnet.

## <a name="base-classes"></a>Basisklassen

Eine Klassendeklaration kann eine Basisklasse angeben, indem ein Doppelpunkt und der Name der Basisklasse an den Klassennamen und die Typparameter angehängt wird. Das Auslassen einer Basisklassenspezifikation ist dasselbe wie eine Ableitung vom Typ `object`. Im folgenden Beispiel ist `Point` die Basisklasse von `Point3D`, und die Basisklasse von `Point` ist `object`:

[!code-csharp[Point3DClass](~/samples/snippets/csharp/tour/classes-and-objects/Point.cs#L3-L20)]

Eine Klasse erbt die Member der zugehörigen Basisklasse. Vererbung bedeutet, dass eine Klasse implizit alle Member dieser Basisklasse enthält, mit Ausnahme der Instanzkonstruktoren und der statischen Konstruktoren sowie der Finalizer der Basisklasse. Eine abgeleitete Klasse kann den geerbten Membern neue Member hinzufügen, aber die Definition eines geerbten Members kann nicht entfernt werden. Im vorherigen Beispiel erbt `Point3D` die Felder `x` und `y` von `Point`, und jede `Point3D`-Instanz enthält drei Felder: `x`, `y` und `z`.

Ein Klassentyp kann implizit in einen beliebigen zugehörigen Basisklassentyp konvertiert werden. Eine Variable eines Klassentyps kann auf eine Instanz der Klasse oder eine Instanz einer beliebigen abgeleiteten Klasse verweisen. Beispielsweise kann in den vorherigen Klassendeklarationen eine Variable vom Typ `Point` entweder auf `Point` oder auf `Point3D` verweisen:

[!code-csharp[Point3DExample](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L22-L23)]

## <a name="fields"></a>Felder

Ein *Feld* ist eine Variable, die einer Klasse oder einer Instanz einer Klasse zugeordnet ist.

Ein Feld, das mit dem static-Modifizierer deklariert wurde, definiert ein statisches Feld. Ein statisches Feld identifiziert genau einen Speicherort. Unabhängig davon, wie viele Instanzen einer Klasse erstellt werden, gibt es immer nur eine Kopie eines statischen Felds.

Ein Feld, das ohne den static-Modifizierer deklariert wurde, definiert ein Instanzfeld. Jede Instanz einer Klasse enthält eine separate Kopie aller Instanzfelder dieser Klasse.

Im folgenden Beispiel weist jede Instanz der `Color`-Klasse eine separate Kopie der Instanzfelder `r`, `g` und `b` auf, aber es gibt nur eine Kopie der statischen Felder `Black`, `White`, `Red`, `Green` und `Blue`:

[!code-csharp[ColorClass](~/samples/snippets/csharp/tour/classes-and-objects/Color.cs#L3-L17)]

Wie im vorherigen Beispiel gezeigt, können *schreibgeschützte Felder* mit einem `readonly`-Modifizierer deklariert werden. Einem `readonly`-Feld können Werte nur als Teil einer Deklaration oder in einem Konstruktor derselben Klasse zugewiesen werden.

## <a name="methods"></a>Methoden

Eine *Methode* ist ein Member, das eine Berechnung oder eine Aktion implementiert, die durch ein Objekt oder eine Klasse durchgeführt werden kann. Auf *statische Methoden* wird über die Klasse zugegriffen. Auf *Instanzmethoden* wird über Instanzen der Klasse zugegriffen.

Methoden können über eine Liste von *Parametern* – diese repräsentieren die an die Methode übergebene Werte oder Variablenverweise – sowie über einen *Rückgabetyp* verfügen, der den Typ des Werts angibt, der von der Methode berechnet und zurückgegeben wird. Der Rückgabetyp einer Methode lautet `void`, wenn kein Wert zurückgegeben wird.

Ebenso wie Typen können Methoden einen Satz an Typparametern aufweisen, für den beim Aufruf der Methode Typargumente angegeben werden müssen. Im Gegensatz zu Typen können die Typargumente häufig aus den Argumenten eines Methodenaufrufs abgeleitet werden und müssen nicht explizit angegeben werden.

Die *Signatur* einer Methode muss innerhalb der Klasse eindeutig sein, in der die Methode deklariert ist. Die Signatur einer Methode besteht aus dem Namen der Methode, der Anzahl von Typparametern und der Anzahl, den Modifizierern und den Typen der zugehörigen Parameter. Die Signatur einer Methode umfasst nicht den Rückgabetyp.

### <a name="parameters"></a>Parameter

Parameter werden dazu verwendet, Werte oder Variablenverweise an Methoden zu übergeben. Die Parameter einer Methode erhalten ihre tatsächlichen Werte über *Argumente*, die angegeben werden, wenn die Methode aufgerufen wird. Es gibt vier Arten von Parametern: Wertparameter, Verweisparameter, Ausgabeparameter und Parameterarrays.

Ein *Wertparameter* wird zum Übergeben von Eingabeargumenten verwendet. Ein Wertparameter entspricht einer lokalen Variablen, die ihren Anfangswert von dem Argument erhält, das für den Parameter übergeben wurde. Änderungen an einem Wertparameter wirken sich nicht auf das Argument aus, das für den Parameter übergeben wurde.

Wertparameter können optional sein, indem ein Standardwert festgelegt wird, damit die zugehörigen Argumente weggelassen werden können.

Ein *Verweisparameter* wird zum Übergeben von Argumenten als Verweis verwendet. Das für einen Verweisparameter übergebene Argument muss eine Variable mit eindeutigem Wert sein, und während der Ausführung der Methode repräsentiert der Verweisparameter denselben Speicherort wie die Argumentvariable. Ein Verweisparameter wird mit dem `ref`-Modifizierer deklariert. Das folgende Beispiel veranschaulicht die Verwendung des `ref`-Parameters.

[!code-csharp[swapExample](~/samples/snippets/csharp/tour/classes-and-objects/RefExample.cs#L3-L18)]

Ein *Ausgabeparameter* wird zum Übergeben von Argumenten als Verweis verwendet. Er ist einem Verweisparameter ähnlich, außer dass er nicht erfordert, dass Sie explizit dem vom Aufrufer bereitgestellten Argument einen Wert zuweisen. Ein Ausgabeparameter wird mit dem `out`-Modifizierer deklariert. Das folgende Beispiel zeigt die Verwendung von `out`-Parametern mithilfe der in C# 7 eingeführten Syntax.

[!code-csharp[OutExample](~/samples/snippets/csharp/tour/classes-and-objects/OutExample.cs#L3-L17)]

Ein *Parameterarray* ermöglicht es, eine variable Anzahl von Argumenten an eine Methode zu übergeben. Ein Parameterarray wird mit dem `params`-Modifizierer deklariert. Nur der letzte Parameter einer Methode kann ein Parameterarray sein, und es muss sich um ein eindimensionales Parameterarray handeln. Die Write- und WriteLine-Methoden der <xref:System.Console?displayProperty=nameWithType>-Klasse sind gute Beispiele für die Verwendung eines Parameterarrays. Sie werden folgendermaßen deklariert.

[!code-csharp[ConsoleExample](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L78-L83)]

Innerhalb einer Methode mit einem Parameterarray verhält sich das Parameterarray wie ein regulärer Parameter des Arraytyps. Beim Aufruf einer Methode mit einem Parameterarray ist es jedoch möglich, entweder ein einzelnes Argument des Parameterarraytyps oder eine beliebige Anzahl von Argumenten des Elementtyps des Parameterarrays zu übergeben. Im letzteren Fall wird automatisch eine Arrayinstanz erstellt und mit den vorgegebenen Argumenten initialisiert. Dieses Beispiel:

[!code-csharp[StringFormat](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L55-L55)]

...entspricht dem folgenden Code:

[!code-csharp[StringFormat2](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L30-L35)]

### <a name="method-body-and-local-variables"></a>Methodenkörper und lokale Variablen

Der Methodenkörper gibt die Anweisungen an, die beim Aufruf der Methode ausgeführt werden sollen.

Ein Methodenkörper kann Variablen deklarieren, die für den Aufruf der Methode spezifisch sind. Diese Variable werden *lokale Variablen* genannt. Die Deklaration einer lokalen Variable gibt einen Typnamen, einen Variablennamen und eventuell einen Anfangswert an. Im folgenden Beispiel wird eine lokale Variable `i` mit einem Anfangswert von 0 und einer lokalen Variablen `j` ohne Anfangswert deklariert.

[!code-csharp[Squares](~/samples/snippets/csharp/tour/classes-and-objects/Squares.cs#L3-L17)]

In C# muss eine lokale Variable *definitiv zugewiesen* sein, bevor ihr Wert abgerufen werden kann. Wenn beispielsweise die vorherige Deklaration von `i` keinen Anfangswert enthielte, würde der Compiler bei der nachfolgenden Verwendung von `i` einen Fehler melden, weil `i` zu diesen Zeitpunkten im Programm nicht definitiv zugewiesen wäre.

Eine Methode kann `return`-Anweisungen verwenden, um die Steuerung an den zugehörigen Aufrufer zurückzugeben. In einer Methode, die `void` zurückgibt, können `return`-Anweisungen keinen Ausdruck angeben. In einer Methode, die nicht „void“ zurückgibt, müssen`return`-Anweisungen einen Ausdruck enthalten, der den Rückgabewert berechnet.

### <a name="static-and-instance-methods"></a>Statische Methoden und Instanzmethoden

Eine mit einem statischen Modifizierer deklarierte Methode ist eine *statische Methode*. Eine statische Methode führt keine Vorgänge für eine spezifische Instanz aus und kann nur direkt auf statische Member zugreifen.

Eine ohne einen statischen Modifizierer deklarierte Methode ist eine *Instanzmethode*. Eine Instanzmethode führt Vorgänge für eine spezifische Instanz aus und kann sowohl auf statische Member als auch auf Instanzmember zugreifen. Auf die Instanz, für die eine Instanzmethode aufgerufen wurde, kann explizit als `this` zugegriffen werden. Es ist ein Fehler, in einer statischen Methode auf `this` zu verweisen.

Die folgende `Entity`-Klasse umfasst sowohl statische Member als auch Instanzmember.

[!code-csharp[Entity](~/samples/snippets/csharp/tour/classes-and-objects/Entity.cs#L16-L36)]

Jede `Entity`-Instanz enthält eine Seriennummer (und vermutlich weitere Informationen, die hier nicht angezeigt werden). Der `Entity`-Konstruktor (der einer Instanzmethode ähnelt) initialisiert die neue Instanz mit der nächsten verfügbaren Seriennummer. Da der Konstruktor ein Instanzmember ist, kann er sowohl auf das `serialNo`-Instanzfeld als auch auf das statische `nextSerialNo`-Feld zugreifen.

Die statischen Methoden `GetNextSerialNo` und `SetNextSerialNo` können auf das statische Feld `nextSerialNo` zugreifen, aber es wäre ein Fehler, über diese Methoden direkt auf das Instanzfeld `serialNo` zuzugreifen.

Das folgende Beispiel zeigt die Verwendung der Entity-Klasse.

[!code-csharp[EntityExample](~/samples/snippets/csharp/tour/classes-and-objects/Entity.cs#L3-L15)]

Die statischen Methoden `SetNextSerialNo` und `GetNextSerialNo` werden für die Klasse aufgerufen, während die `GetSerialNo`-Instanzmethode für Instanzen der Klasse aufgerufen wird.

### <a name="virtual-override-and-abstract-methods"></a>Virtuelle, überschriebene und abstrakte Methoden

Wenn die Deklaration einer Instanzmethode einen `virtual`-Modifizierer enthält, wird die Methode als *virtuelle Methode* bezeichnet. Ist kein virtual-Modifizierer vorhanden, spricht man von einer *nicht virtuellen Methode*.

Beim Aufruf einer virtuellen Methode bestimmt der *Laufzeittyp* der Instanz, für die der Aufruf erfolgt, die tatsächlich aufzurufende Methodenimplementierung. Beim Aufruf einer nicht virtuellen Methode ist der *Kompilierzeittyp* der bestimmende Faktor.

Eine virtuelle Methode kann in einer abgeleiteten Klasse *überschrieben* werden. Wenn eine Instanzmethodendeklaration einen override-Modifizierer enthält, überschreibt die Methode eine geerbte virtuelle Methode mit derselben Signatur. Während eine Deklaration einer virtuellen Methode eine neue Methode einführt, spezialisiert eine Deklaration einer überschriebenen Methode eine vorhandene geerbte virtuelle Methode, indem eine neue Implementierung dieser Methode bereitgestellt wird.

Eine *abstrakte Methode* ist eine virtuelle Methode ohne Implementierung. Eine abstrakte Methode wird mit dem abstract-Modifizierer deklariert und ist nur in einer Klasse erlaubt, die auch als abstrakt deklariert wurde. Eine abstrakte Methode muss in jeder nicht abstrakten abgeleiteten Klasse überschrieben werden.

Im folgenden Beispiel wird die abstrakte Klasse `Expression` deklariert, die einen Ausdrucksbaumstrukturknoten sowie drei abgeleitete Klassen repräsentiert: `Constant`, `VariableReference` und `Operation`. Diese implementieren Ausdrucksbaumstrukturknoten für Konstanten, variable Verweise und arithmetische Operationen. (Dieses Beispiel ähnelt den Ausdrucksbaumstrukturtypen, sollte aber mit diesen nicht verwechselt werden.)

[!code-csharp[ExpressionClass](~/samples/snippets/csharp/tour/classes-and-objects/Expressions.cs#L3-L61)]

Die vorherigen vier Klassen können zum Modellieren arithmetischer Ausdrücke verwendet werden. Beispielsweise kann mithilfe von Instanzen dieser Klassen der Ausdruck `x + 3` folgendermaßen dargestellt werden.

[!code-csharp[ExpressionExample](~/samples/snippets/csharp/tour/classes-and-objects/Program.cs#L40-L43)]

Die `Evaluate`-Methode einer `Expression`-Instanz wird aufgerufen, um den vorgegebenen Ausdruck auszuwerten und einen `double`-Wert zu generieren. Die Methode verwendet ein `Dictionary`-Argument, das Variablennamen (als Schlüssel der Einträge) und Werte (als Werte der Einträge) enthält. Da `Evaluate` eine abstrakte Methode ist, müssen nicht-abstrakte Klassen, die von `Expression` abgeleitet sind, `Evaluate` außer Kraft setzen.

Eine Implementierung von `Constant` für `Evaluate` gibt lediglich die gespeicherte Konstante zurück. Eine Implementierung von `VariableReference` sucht im Wörterbuch nach dem Variablennamen und gibt den Ergebniswert zurück. Eine Implementierung von `Operation` wertet zunächst (durch einen rekursiven Aufruf der zugehörigen `Evaluate`-Methoden) den linken und rechten Operanden aus und führt dann die vorgegebene arithmetische Operation aus.

Das folgende Programm verwendet die `Expression`-Klassen zum Auswerten des Ausdrucks `x * (y + 2)` für verschiedene Werte von `x` und `y`.

[!code-csharp[ExpressionUsage](~/samples/snippets/csharp/tour/classes-and-objects/Expressions.cs#L66-L89)]

### <a name="method-overloading"></a>Methodenüberladung

Das *Überladen* von Methoden macht es möglich, dass mehrere Methoden in derselben Klasse denselben Namen verwenden, solange sie eindeutige Signaturen aufweisen. Beim Kompilieren des Aufrufs einer überladenen Methode verwendet der Compiler die *Überladungsauflösung*, um die spezifische Methode zu ermitteln, die aufgerufen werden soll. Mithilfe der Überladungsauflösung wird die Methode ermittelt, die den Argumenten am besten entspricht, bzw. es wird ein Fehler ausgegeben, wenn keine passende Methode gefunden wird. Das folgende Beispiel zeigt die Verwendung der Überladungsauflösung. Der Kommentar für jeden Aufruf in der `UsageExample`-Methode zeigt, welche Methode aufgerufen wird.

[!code-csharp[OverloadUsage](~/samples/snippets/csharp/tour/classes-and-objects/Overloading.cs#L3-L41)]

Wie im Beispiel gezeigt, kann eine bestimmte Methode immer ausgewählt werden, indem die Argumente explizit in die passenden Parametertypen konvertiert und/oder explizit Typargumente angegeben werden.

## <a name="other-function-members"></a>Andere Funktionsmember

Member, die ausführbaren Code enthalten, werden als *Funktionsmember* einer Klasse bezeichnet. Im vorherigen Abschnitt wurden Methoden beschrieben, die die Haupttypen von Funktionsmembern sind. In diesem Abschnitt werden die weiteren Funktionsmember behandelt, die C# unterstützt: Konstruktoren, Eigenschaften, Indexer, Ereignisse, Operatoren und Finalizer.

Im folgenden Beispiel wird eine generische Klasse namens `MyList<T>` gezeigt, die eine wachsende Liste von Objekten implementiert. Die Klasse enthält verschiedene Beispiele der gängigsten Arten von Funktionsmembern.

> [!NOTE]
> In diesem Beispiel wird eine `MyList`-Klasse erstellt, die nicht identisch ist mit der .NET-Standardklasse <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>. Sie veranschaulicht die für diesen Überblick erforderlichen Konzepte, ist aber kein Ersatz für diese Klasse.

[!code-csharp[ListClass](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L4-L89)]

### <a name="constructors"></a>Konstruktoren

C# unterstützt sowohl Instanzkonstruktoren als auch statische Konstruktoren. Ein *Instanzkonstruktor* ist ein Member, der die erforderlichen Aktionen zum Initialisieren einer Instanz einer Klasse implementiert. Ein *statischer Konstruktor* ist ein Member, der die zum Initialisieren einer Klasse erforderlichen Aktionen implementiert, um die Klasse beim ersten Laden selbst zu initialisieren.

Ein Konstruktor wird wie eine Methode ohne Rückgabetyp und mit demselben Namen wie die enthaltende Klasse deklariert. Wenn eine Konstruktordeklaration einen static-Modifizierer enthält, deklariert sie einen statischen Konstruktor. Andernfalls wird ein Instanzkonstruktor deklariert.

Instanzkonstruktoren können überladen werden und optionale Parameter verwenden. Die `MyList<T>`-Klasse deklariert z.B. einen Instanzkonstruktor mit einem einzelnen optionalen `int`-Parameter. Instanzkonstruktoren werden über den `new`-Operator aufgerufen. Die folgenden Anweisungen weisen zwei Instanzen von `MyList<string>` unter Verwendung des Konstruktors der `MyList`-Klasse zu, mit dem optionalen Argument und ohne das optionale Argument.

[!code-csharp[ListExample1](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L95-L96)]

Im Gegensatz zu anderen Members werden Instanzkonstruktoren nicht geerbt, und eine Klasse verfügt über keine anderen Instanzkonstruktoren auf als diejenigen, die tatsächlich in der Klasse deklariert werden. Wenn kein Instanzkonstruktor für eine Klasse angegeben ist, wird automatisch ein leerer Instanzkonstruktor ohne Parameter bereitgestellt.

### <a name="properties"></a>Eigenschaften

*Eigenschaften* sind eine natürliche Erweiterung der Felder. Beide sind benannte Member mit zugeordneten Typen, und für den Zugriff auf Felder und Eigenschaften wird dieselbe Syntax verwendet. Im Gegensatz zu Feldern geben Eigenschaften jedoch keine Speicherorte an. Stattdessen verfügen Eigenschaften über *Accessors* zum Angeben der Anweisungen, die beim Lesen oder Schreiben ihrer Werte ausgeführt werden sollen.

Eine Eigenschaft wird wie ein Feld deklariert, abgesehen davon, dass die Deklaration nicht auf ein Semikolon, sondern auf einen get- und/oder einen set-Accessor endet, der von den Trennzeichen `{` und `}` umschlossen wird. Eine Eigenschaft, die sowohl einen get- als auch einen set-Accessor aufweist, ist eine *Eigenschaft mit Lese- und Schreibzugriff*. Eine Eigenschaft, die nur einen get-Accessor aufweist, ist *schreibgeschützt*, eine Eigenschaft, die nur einen set-Accessor aufweist, ist *lesegeschützt*.

Ein get-Accessor entspricht einer Methode ohne Parameter mit einem Rückgabewert des Eigenschaftstyps. Wenn eine Eigenschaft kein Ziel einer Zuweisung ist, sondern in einem Ausdruck referenziert wird, wird der get-Accessor der Eigenschaft aufgerufen, um ihren Wert zu berechnen.

Ein set-Accessor entspricht einer Methode mit einem einzigen Parameter namens „value“ ohne Rückgabetyp. Wenn auf eine Eigenschaft als Ziel einer Zuweisung der als Operand ++ oder -- verwiesen wird, erfolgt der Aufruf des set-Accessors mit einem Argument, das den neuen Wert bereitstellt.

Die `MyList<T>`-Klasse deklariert die beiden Eigenschaften „`Count`“ und „`Capacity`“, von denen die eine schreibgeschützt ist und die andere Lese- und Schreibzugriff besitzt. Im folgenden Beispielcode wird die Verwendung dieser Eigenschaften veranschaulicht:

[!code-csharp[ListExample2](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L101-L104)]

Ähnlich wie bei Feldern und Methoden unterstützt C# sowohl Instanzeigenschaften als auch statische Eigenschaften. Statische Eigenschaften werden mit dem static-Modifizierer, Instanzeigenschaften werden ohne static-Modifizierer deklariert.

Die Accessors einer Eigenschaft können virtuell sein. Wenn eine Eigenschaftendeklaration einen `virtual`-, `abstract`- oder `override`-Modifizierer enthält, wird dieser auf den Accessor der Eigenschaft angewendet.

### <a name="indexers"></a>Indexer

Ein *Indexer* ist ein Member, mit dem Objekte wie ein Array indiziert werden können. Ein Indexer wird wie eine Eigenschaft deklariert, abgesehen davon, dass der Name des Members `this` ist, gefolgt von einer Parameterliste, die zwischen die Trennzeichen `[` und `]` geschrieben wird. Die Parameter stehen im Accessor des Indexers zur Verfügung. Ähnlich wie Eigenschaften können Indexer Lese-/Schreibzugriff besitzen, schreibgeschützt und lesegeschützt sein und virtuelle Accessors verwenden.

Die `MyList<T>`-Klasse deklariert einen einzigen Indexer mit Lese-/Schreibzugriff, der einen `int`-Parameter akzeptiert. Der Indexer ermöglicht es, Instanzen von `MyList<T>` mit `int`-Werten zu indizieren. Zum Beispiel:

[!code-csharp[ListExample3](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L109-L117)]

Indexer können überladen werden, d.h. eine Klasse kann mehrere Indexer deklarieren, solange sich die Anzahl oder Typen ihrer Parameter unterscheiden.

### <a name="events"></a>Ereignisse

Ein *Ereignis* ist ein Member, der es einer Klasse oder einem Objekt ermöglicht, Benachrichtigungen bereitzustellen. Ein Ereignis wird wie ein Feld deklariert, abgesehen davon, dass es ein event-Schlüsselwort enthält und einen Delegattyp aufweisen muss.

Innerhalb einer Klasse, die einen Ereignismember deklariert, verhält sich das Ereignis wie ein Feld des Delegattyps (vorausgesetzt, das Ereignis ist nicht abstrakt und deklariert keine Zugriffsmethoden). Das Feld speichert einen Verweis auf einen Delegaten, der die Ereignishandler repräsentiert, die dem Ereignis hinzugefügt wurden. Wenn keine Ereignishandler vorhanden sind, ist das Feld `null`.

Die `MyList<T>`-Klasse deklariert einen einzigen Ereignismember namens `Changed`, der angibt, dass der Liste ein neues Element hinzugefügt wurde. Das Changed-Ereignis wird durch die virtuelle Methode `OnChanged` ausgelöst, die zunächst prüft, ob das Ereignis `null` ist (d.h. nicht über Handler verfügt). Das Auslösen eines Ereignisses entspricht exakt dem Aufrufen des Delegaten, der durch das Ereignis repräsentiert wird, es gibt deshalb keine besonderen Sprachkonstrukte zum Auslösen von Ereignissen.

Clients reagieren über *Ereignishandler* auf Ereignisse. Ereignishandler werden unter Verwendung des `+=`-Operators angefügt und mit dem `-=`-Operator entfernt. Im folgenden Beispiel wird dem `Changed`-Ereignis von `MyList<string>` ein Ereignishandler hinzugefügt.

[!code-csharp[EventExample](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L132-L148)]

In fortgeschrittenen Szenarios, in denen die zugrunde liegende Speicherung eines Ereignisses gesteuert werden soll, kann eine Ereignisdeklaration explizit die Zugriffsmethoden `add` und `remove` bereitstellen, die der Zugriffsmethode `set` einer Eigenschaft ähneln.

### <a name="operators"></a>Operatoren

Ein *Operator* ist ein Member, der die Bedeutung der Anwendung eines bestimmten Ausdrucksoperators auf Instanzen einer Klasse definiert. Es können drei Arten von Operatoren definiert werden: unäre Operatoren, binäre Operatoren und Konvertierungsoperatoren. Alle Operatoren müssen als `public` und `static` deklariert werden.

Die `MyList<T>`-Klasse deklariert zwei Operatoren, `operator ==` und `operator !=`, und verleiht so Ausdrücken, die diese Operatoren auf `MyList`-Instanzen anwenden, eine neue Bedeutung. Insbesondere die Operatoren definieren die Gleichheit für zwei Instanzen von `MyList<T>`, indem alle enthaltenen Objekte mithilfe ihrer Equals-Methoden verglichen werden. Im folgenden Beispiel wird der `==`-Operator verwendet, um zwei Instanzen von `MyList<int>` zu vergleichen.

[!code-csharp[OperatorExample](~/samples/snippets/csharp/tour/classes-and-objects/ListBasedExamples.cs#L121-L129)]

Die erste Methode `Console.WriteLine` gibt `True` aus, weil die zwei Listen dieselbe Anzahl von Objekten mit denselben Werten in derselben Reihenfolge enthalten. Wenn `MyList<T>` nicht `operator ==` definieren würde, würde die Ausgabe der ersten `Console.WriteLine`-Methode `False` lauten, weil `a` und `b` auf unterschiedliche `MyList<int>`-Instanzen verweisen.

### <a name="finalizers"></a>Finalizer

Ein *Finalizer* ist ein Member, der die erforderlichen Aktionen zum Bereinigen einer Instanz einer Klasse implementiert. Finalizer können weder Parameter noch Zugriffsmodifizierer aufweisen und können nicht explizit aufgerufen werden. Der Finalizer für eine Instanz wird bei der Garbagecollection automatisch aufgerufen.

Der Garbage Collector kann weitestgehend selbst über den Zeitpunkt der Objektbereinigung und die Ausführung der Finalizer entscheiden. Insbesondere der Zeitpunkt für den Aufruf der Finalizer ist nicht festgelegt, und Finalizer können für beliebige Threads ausgeführt werden. Aus diesen und weiteren Gründen sollten Klassen Finalizer nur dann implementieren, wenn keine andere Lösung möglich ist.

Die `using`-Anweisung bietet einen besseren Ansatz für die Objektzerstörung.

> [!div class="step-by-step"]
> [Zurück](statements.md)
> [Weiter](arrays.md)
