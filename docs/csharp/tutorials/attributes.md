---
title: Attribute – C#
description: Erfahren Sie, wie Attribute in C# funktionieren.
author: mgroves
ms.technology: csharp-fundamentals
ms.date: 03/06/2017
ms.assetid: b152cf36-76e4-43a5-b805-1a1952e53b79
ms.openlocfilehash: 54eb3038594e1d4becf8a1bddd58b1e0e6464d68
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039290"
---
# <a name="using-attributes-in-c"></a>Verwenden von Attributen in C\#

Attribute bieten die Möglichkeit, Informationen in deklarativer Form mit Code zu verknüpfen. Attribute können außerdem als wiederverwendbare Elemente genutzt werden, die auf eine Vielzahl von Zielen angewendet werden können.

Betrachten wir z.B. das `[Obsolete]`-Attribut. Es kann auf Klassen, Strukturen, Methoden, Konstruktoren und mehr angewendet werden. Mit ihm wird das Element als veraltet _deklariert_. Anschließend ist es die Aufgabe des C#-Compilers, nach diesem Attribut zu suchen und Aktionen auszuführen.

In diesem Tutorial erfahren Sie, wie Sie Attribute zu Ihrem Code hinzufügen sowie eigene Attribute erstellen und verwenden, und Sie lernen einige der Attribute kennen, die in .NET Core integriert sind.

## <a name="prerequisites"></a>Erforderliche Komponenten
Sie müssen Ihren Computer zur Ausführung von .NET Core einrichten. Die Installationsanweisungen finden Sie auf der Seite [.NET Core-Downloads](https://dotnet.microsoft.com/download).
Sie können diese Anwendung unter Windows, Ubuntu Linux, macOS oder in einem Docker-Container ausführen. Sie müssen Ihren bevorzugten Code-Editor installieren. In den folgenden Beschreibungen wird [Visual Studio Code](https://code.visualstudio.com/) verwendet. Hierbei handelt es sich um einen plattformübergreifenden Open Source-Editor. Sie können jedoch auch ein beliebiges anderes Tool verwenden, mit dem Sie vertraut sind.

## <a name="create-the-application"></a>Erstellen der Anwendung

Nachdem Sie alle Tools installiert haben, erstellen Sie eine neue .NET Core-Anwendung. Um den Befehlszeilengenerator zu verwenden, führen Sie den folgenden Befehl in Ihrer bevorzugten Shell aus:

`dotnet new console`

Mit diesem Befehl werden .NET Core-Basisprojektdateien erstellt. Sie müssen `dotnet restore` ausführen, um die abhängigen Komponenten wiederherzustellen, die zum Kompilieren dieses Projekts erforderlich sind.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Verwenden Sie zum Ausführen des Programms `dotnet run`. Es sollte „Hello, World“ auf der Konsole ausgegeben werden.

## <a name="how-to-add-attributes-to-code"></a>Hinzufügen von Attributen zum Code

In C# sind Attribute Klassen, die von der `Attribute`-Basisklasse erben. Alle Klassen, die von `Attribute` erben, können als eine Art von „Tag“ für andere Codeelemente verwendet werden.
Beispielsweise gibt es das Attribut `ObsoleteAttribute`. Mit diesem Attribut wird gekennzeichnet, dass der Code veraltet ist und nicht mehr verwendet werden sollte. Sie können eine Klasse beispielsweise mit diesem Attribut markieren, indem Sie eckige Klammern verwenden.

[!code-csharp[Obsolete attribute example](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ObsoleteExample1)]  

Obwohl der Name der Klasse `ObsoleteAttribute` lautet, kann im Code nur `[Obsolete]` verwendet werden. Dies ist eine Konvention von C#.
Wenn Sie möchten, können Sie auch den vollständigen Namen, `[ObsoleteAttribute]`, verwenden.

Wenn Sie eine Klasse als veraltet markieren, sollten Sie Informationen dazu geben, *warum* die Klasse veraltet ist und/oder *was* stattdessen verwendet werden sollte. Um dies zu tun, übergeben Sie einen Zeichenfolgenparameter an das Obsolete-Attribut.

[!code-csharp[Obsolete attribute example with parameters](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ObsoleteExample2)]

Die Zeichenfolge wird als Argument an einen `ObsoleteAttribute`-Konstruktor übergeben, so als ob Sie `var attr = new ObsoleteAttribute("some string")` schreiben würden.

Die Parameter für einen Attributkonstruktor sind auf einfache Typen/Literale beschränkt: `bool, int, double, string, Type, enums, etc` und Arrays dieser Typen.
Sie können keine Ausdrücke oder Variablen verwenden. Es ist möglich, Positionsparameter oder benannte Parameter einzusetzen.

## <a name="how-to-create-your-own-attribute"></a>Erstellen eigener Attribute

Das Erstellen eines Attributs ist so einfach wie das Erben von der `Attribute`-Basisklasse.

[!code-csharp[Create your own attribute](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#CreateAttributeExample1)]

Durch den Code oben kann jetzt `[MySpecial]` (oder `[MySpecialAttribute]`) als Attribut an anderer Stelle in der Codebasis verwendet werden.

[!code-csharp[Using your own attribute](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#CreateAttributeExample2)]

Attribute in der .NET-Basisklassenbibliothek, z.B. `ObsoleteAttribute`, lösen ein bestimmtes Verhalten im Compiler aus. Die erstellten Attribute dienen jedoch nur als Metadaten, sie führen nicht zu Code innerhalb der Attributklasse, der ausgeführt wird. Es liegt an Ihnen, diese Metadaten an anderer Stelle im Code einzusetzen (hierzu später mehr in diesem Tutorial).

Es gibt hierbei ein Problem, das beachtet werden muss. Wie oben erwähnt, können bei der Verwendung von Attributen nur bestimmte Typen als Argumente übergeben werden. Wenn Sie aber einen Attributtyp erstellen, hindert der C#-Compiler Sie nicht daran, diese Parameter zu erstellen. Im nachstehenden Beispiel habe ich ein Attribut mit einem Konstruktor erstellt, der problemlos kompiliert werden kann.

[!code-csharp[Valid constructor used in an attribute](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeGothca1)]

Dieser Konstruktor kann aber nicht mit der Attributsyntax verwendet werden.

[!code-csharp[Invalid attempt to use the attribute constructor](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeGotcha2)]

Der obige Code führt zu einem Compilerfehler wie diesem: `Attribute constructor parameter 'myClass' has type 'Foo', which is not a valid attribute parameter type`

## <a name="how-to-restrict-attribute-usage"></a>Einschränken der Attributverwendung

Attribute können für verschiedene Ziele verwendet werden. In den obigen Beispielen wurde die Verwendung für Klassen gezeigt, aber Attribute können auch für folgende Elemente verwendet werden:

* Assembly
* Klasse
* Konstruktor
* delegate
* Enum
* event
* Feld
* GenericParameter
* Interface
* Methode
* Modul
* Parameter
* Eigenschaft
* ReturnValue
* Struktur

Wenn Sie eine Attributklasse erstellen, lässt C# standardmäßig die Verwendung dieses Attributs für alle möglichen Attributziele zu. Wenn Sie Ihr Attribut auf bestimmte Ziele beschränken möchten, erreichen Sie dies durch Verwendung von `AttributeUsageAttribute` für Ihre Attributklasse. Ganz richtig, ein Attribut für ein Attribut!

[!code-csharp[Using your own attribute](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeUsageExample1)]

Wenn Sie versuchen, das oben gezeigte Attribut für ein Element zu verwenden, bei dem es sich nicht um eine Klasse oder eine Struktur handelt, erhalten Sie einen Compilerfehler wie diesen: `Attribute 'MyAttributeForClassAndStructOnly' is not valid on this declaration type. It is only valid on 'class, struct' declarations`

[!code-csharp[Using your own attribute](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#AttributeUsageExample2)]

## <a name="how-to-use-attributes-attached-to-a-code-element"></a>Verwenden von Attributen, die an Codeelemente angefügt sind

Attribute fungieren als Metadaten. Ohne Aktivität von außen bewirken sie zunächst nichts.

Um nach Attributen zu suchen und Aktionen auszuführen, ist im Allgemeinen eine [Reflektion](../programming-guide/concepts/reflection.md) erforderlich. In diesem Tutorial wird nicht ausführlich auf die Reflektion eingegangen. Die Grundidee hierbei ist jedoch folgende: Mithilfe der Reflektion ist es möglich, Code in C# zu schreiben, mit dem anderer Code untersucht wird.

Sie können beispielsweise mithilfe der Reflektion Informationen zu einer Klasse abrufen (fügen Sie `using System.Reflection;` im Kopf Ihres Codes hinzu): 

[!code-csharp[Getting type information with Reflection](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ReflectionExample1)]

Es wird eine Ausgabe ähnlich der folgenden erzeugt: `The assembly qualified name of MyClass is ConsoleApplication.MyClass, attributes, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null`

Sobald Sie über ein `TypeInfo`-Objekt (oder `MemberInfo`, `FieldInfo` usw.) verfügen, können Sie die `GetCustomAttributes`-Methode verwenden. Dadurch wird eine Auflistung von `Attribute`-Objekte zurückgegeben.
Sie können auch `GetCustomAttribute` verwenden und einen Attributtyp angeben.

Hier ein Beispiel zur Verwendung von `GetCustomAttributes` für eine `MemberInfo`-Instanz für `MyClass` (die, wie zuvor gezeigt, über ein `[Obsolete]`-Attribut verfügt).

[!code-csharp[Getting type information with Reflection](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#ReflectionExample2)]

Dies führt zur folgenden Konsolenausgabe: `Attribute on MyClass: ObsoleteAttribute`. Versuchen Sie, weitere Attribute zu `MyClass` hinzuzufügen.

Es ist wichtig, darauf hinzuweisen, dass diese `Attribute`-Objekte verzögert instanziiert werden. Anders ausgedrückt: Sie werden erst instanziiert, wenn Sie `GetCustomAttribute` oder `GetCustomAttributes` verwenden.
Sie werden außerdem jedes Mal instanziiert. Das zweimalige Aufrufen von `GetCustomAttributes` in einer Zeile führt zur Rückgabe von zwei unterschiedlichen Instanzen von `ObsoleteAttribute`.

## <a name="common-attributes-in-the-base-class-library-bcl"></a>Allgemeine Attribute in der Basisklassenbibliothek

Attribute werden in vielen Tools und Frameworks verwendet. NUnit verwendet Attribute wie z.B. `[Test]` und `[TestFixture]`, die vom NUnit Test Runner verwendet werden. ASP.NET MVC verwendet Attribute wie `[Authorize]` und stellt ein Aktionsfilterframework bereit, um übergreifende Anforderungen (Cross-Cutting Concerns) für MVC-Aktionen umzusetzen. [PostSharp](https://www.postsharp.net) verwendet die Attributsyntax, um eine aspektorientierte Programmierung in C# zu ermöglichen.

Nachfolgend werden einige wichtige Attribute aufgeführt, die in die .NET Core-Basisklassenbibliotheken integriert sind:

* `[Obsolete]`. Dieses Attribut wurde in den obigen Beispielen verwendet, es ist im `System`-Namespace enthalten. Es ist nützlich, um eine deklarative Dokumentation für eine sich ändernde Codebasis bereitzustellen. Eine Meldung kann in Form einer Zeichenfolge bereitgestellt werden, und ein weiterer, boolescher Parameter kann für eine Eskalation von einer Compilerwarnung zu einem Compilerfehler verwendet werden.

* `[Conditional]`. Dieses Attribut ist im `System.Diagnostics`-Namespace enthalten. Es kann auf Methoden (oder Attributklassen) angewendet werden. Sie müssen eine Zeichenfolge an den Konstruktor übergeben.
Wenn diese Zeichenfolge nicht einer `#define`-Anweisung entspricht, werden alle Aufrufe dieser Methode (aber nicht die Methode selbst) durch den C#-Compiler entfernt. Dieses Attribut wird typischerweise zum Debuggen (zu Diagnosezwecken) eingesetzt.

* `[CallerMemberName]`. Dieses Attribut kann für Parameter verwendet werden und ist im `System.Runtime.CompilerServices`-Namespace enthalten. Es handelt sich um ein Attribut, mit dem der Name der Methode eingeführt wird, die eine andere Methode aufruft. So werden typischerweise „magische Zeichenfolgen“ beim Implementieren von „INotifyPropertyChanged“ in verschiedenen UI-Frameworks beseitigt. Ein Beispiel:

[!code-csharp[Using CallerMemberName when implementing INotifyPropertyChanged](../../../samples/snippets/csharp/tutorials/attributes/Program.cs#CallerMemberName1)]

Im Code oben ist keine literale `"Name"`-Zeichenfolge erforderlich. Dies kann dazu beitragen, Programmfehler aufgrund von Rechtschreibfehlern zu vermeiden, und es erleichtert das Refactoring/Umbenennen.

## <a name="summary"></a>Zusammenfassung

Attribute verschaffen C# ein deklaratives Potenzial, aber sie sind eine Metadatenform von Code und agieren nicht selbst.
