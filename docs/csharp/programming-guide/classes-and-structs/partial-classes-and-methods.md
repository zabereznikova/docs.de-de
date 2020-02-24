---
title: Partielle Klassen und Methoden – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- partial methods [C#]
- partial classes [C#]
- C# language, partial classes and methods
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
ms.openlocfilehash: e359913aad4b8cea001a894d4ba5720fab54d42b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451914"
---
# <a name="partial-classes-and-methods-c-programming-guide"></a>Partielle Klassen und Methoden (C#-Programmierhandbuch)

Es ist möglich, die Definition einer [Klasse](../../language-reference/keywords/class.md), einer [Struktur](../../language-reference/keywords/struct.md), einer [Schnittstelle](../../language-reference/keywords/interface.md) oder einer Methode auf zwei oder mehr Quelldateien aufzuteilen. Jede Quelldatei enthält einen Abschnitt der Typ- oder Methodendefinition. Die Teile werden bei der Kompilierung der Anwendung miteinander kombiniert.

## <a name="partial-classes"></a>Teilklassen

Es gibt mehrere Situationen, bei denen das Aufteilen einer Klassendefinition wünschenswert ist:

- Wenn Sie an großen Projekten arbeiten, können durch das Verteilen einer Klasse auf mehrere Dateien mehrere Programmierer gleichzeitig daran arbeiten.

- Wenn Sie mit automatisch erzeugten Quellen arbeiten, kann Code einer Klasse hinzugefügt werden, ohne die Quelldatei neu zu erstellen. Visual Studio verwendet diesen Ansatz, wenn es Windows Forms, Webdienst-Wrappercode usw. erstellt. Sie können Code erstellen, der diese Klassen verwendet, ohne die von Visual Studio erstellte Datei ändern zu müssen.

- Um eine Klassendefinition aufzuteilen, verwenden Sie den Schlüsselwortmodifizierer [partial](../../language-reference/keywords/partial-type.md), wie hier gezeigt wird:

  [!code-csharp[csProgGuideObjects#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#26)]

Das Schlüsselwort `partial` gibt an, dass andere Teile der Klasse, Struktur oder Schnittstelle im Namespace definiert werden können. Alle Teile müssen das Schlüsselwort `partial` verwenden. Alle Teile müssen zur Kompilierzeit verfügbar sein, um den endgültigen Typ zu bilden. Alle Teile müssen die gleiche Zugriffsebene haben, z.B. `public`, `private` usw.

Wenn ein beliebiger Teil als abstrakt deklariert wird, wird anschließend der ganze Typ als abstrakt betrachtet. Wenn ein beliebiges Teil als versiegelt deklariert wird, wird anschließend der ganze Typ als versiegelt betrachtet. Wenn ein beliebiger Teil einen Basistyp deklariert, erbt der ganze Typ diese Klasse.

Alle Teile, die eine Basisklasse angeben, müssen übereinstimmen, aber Teile, die eine Basisklasse auslassen, erben weiterhin den Basistyp. Teile können unterschiedliche Basisschnittstellen angeben, und der letzte Typ implementiert alle Schnittstellen, die von allen Teildeklarationen aufgeführt sind. Alle Klassen-, Struktur- und Schnittstellenmember, die in einer Teildefinition deklariert wurden, sind für alle anderen Teile verfügbar. Der endgültige Typ besteht aus allen Teilen zur Kompilierzeit.

> [!NOTE]
> Der `partial`-Modifizierer ist nicht für Delegat- oder Enumerationsdeklarationen verfügbar.

Im folgenden Beispiel wird gezeigt, dass geschachtelte Typen eine Teilausführung sein können, selbst wenn der Typ, in dem sie geschachtelt sind, selbst keine ist.

[!code-csharp[csProgGuideObjects#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#25)]

Zur Kompilierzeit werden Attribute von partiellen Typdefinitionen zusammengeführt. Betrachten Sie beispielsweise die folgenden Deklarationen:

[!code-csharp[csProgGuideObjects#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#23)]

Sie entsprechen den folgenden Deklarationen:

[!code-csharp[csProgGuideObjects#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#24)]

Die folgenden werden aus allen partiellen Typdefinitionen zusammengeführt:

- XML-Kommentare

- Schnittstellen

- Generische Parameterattribute

- Klassenattribute

- Member

Betrachten Sie beispielsweise die folgenden Deklarationen:

[!code-csharp[csProgGuideObjects#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#21)]

Sie entsprechen den folgenden Deklarationen:

[!code-csharp[csProgGuideObjects#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#22)]

### <a name="restrictions"></a>Beschränkungen

Es sind mehrere Regeln zu beachten, wenn Sie partielle Klassendefinitionen verwenden:

- Alle partiellen Typdefinitionen, die als Teile des gleichen Typs vorgesehen sind, müssen mit `partial` geändert werden. Die folgenden Klassendeklarationen erzeugen z.B. einen Fehler:

  [!code-csharp[csProgGuideObjects#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#20)]

- Der `partial`-Modifizierer kann nur unmittelbar vor den Schlüsselwörtern `class`, `struct` oder `interface` erscheinen.

- Geschachtelte partielle Typen sind in partiellen Typdefinitionen zulässig, wie im folgenden Beispiel dargestellt wird:

  [!code-csharp[csProgGuideObjects#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#19)]

- Alle partiellen Typdefinitionen, die als Teile des gleichen Typs vorgesehen sind, müssen in der gleichen Assembly und demselben Modul (EXE- oder DLL-Datei) definiert werden. Partielle Definitionen können nicht mehrere Module umfassen.

- Der Klassenname und die generischen Typparameter müssen mit allen partiellen Typdefinitionen übereinstimmen. Generische Typen können partiell sein. Jede partielle Definition muss die gleichen Parameternamen in der gleichen Reihenfolge aufweisen.

- Die nachfolgenden Schlüsselwörter für eine partielle Typdefinition sind optional, wenn sie aber für eine partielle Definition vorhanden sind, können sie nicht mit anderen Schlüsselwörtern in Konflikt treten, die in anderen partiellen Definitionen desselben Typs angegeben wurden:

  - [public](../../language-reference/keywords/public.md)

  - [private](../../language-reference/keywords/private.md)

  - [protected](../../language-reference/keywords/protected.md)

  - [internal](../../language-reference/keywords/internal.md)

  - [abstract](../../language-reference/keywords/abstract.md)

  - [sealed](../../language-reference/keywords/sealed.md)

  - Basisklasse

  - [new](../../language-reference/keywords/new-modifier.md)-Modifizierer (geschachtelte Teile)

  - Generische Einschränkungen

Weitere Informationen finden Sie unter [Einschränkungen für Typparameter](../generics/constraints-on-type-parameters.md).

## <a name="example-1"></a>Beispiel 1

### <a name="description"></a>Beschreibung

Im folgenden Beispiel werden die Felder und der Konstruktor der Klasse (`Coords`) in einer partiellen Klassendefinition deklariert, und der Member (`PrintCoords`) wird in einer anderen partiellen Klassendefinition deklariert.

### <a name="code"></a>Code

[!code-csharp[csProgGuideObjects#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#17)]

## <a name="example-2"></a>Beispiel 2

### <a name="description"></a>Beschreibung

Im folgenden Beispiel wird gezeigt, dass Sie auch partielle Strukturen und Schnittstellen entwickeln können.

### <a name="code"></a>Code

[!code-csharp[csProgGuideObjects#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#18)]

## <a name="partial-methods"></a>Partielle Methoden

Eine partielle Klasse oder Struktur kann eine partielle Methode enthalten. Ein Teil der Klasse enthält die Signatur der Methode. Eine optionale Implementierung kann im gleichen oder in einem anderen Teil definiert werden. Wenn die Implementierung nicht bereitgestellt wird, werden anschließend die Methode sowie alle Aufrufe an die Methode zur Kompilierzeit entfernt.

Mit partiellen Methoden kann der Implementierer des einen Teils einer Klasse eine Methode definieren, die einem Ereignis ähnelt. Der Implementierer des anderen Teils der Klasse kann entscheiden, ob die Methode implementiert wird. Wenn die Methode nicht implementiert wird, kann der Compiler anschließend die Methodensignatur und alle Aufrufe an die Methode entfernen. Die Aufrufe an die Methode, einschließlich Ergebnissen, die bei der Auswertung eines Arguments im Aufruf auftreten würden, haben zur Laufzeit keine Auswirkung. Deshalb kann jeder Code in der partiellen Klasse eine partielle Methode frei verwenden, selbst wenn die Implementation nicht bereitgestellt wird. Es ergeben sich keine Laufzeit- oder Kompilierzeitfehler, wenn die Methode aufgerufen, aber nicht implementiert wird.

Partielle Methoden sind besonders nützlich, um generierten Code anzupassen. Sie ermöglichen, dass Methodenname und -signatur reserviert werden können, sodass generierter Code die Methode aufrufen kann, aber der Entwickler über die Implementierung der Methode entscheiden kann. Wie partielle Klassen ermöglichen partielle Methoden, dass Code, der von einem Codegenerator erstellt wurde, zusammen mit Code, der von einem menschlichen Entwickler erstellt wurde, ohne Laufzeitkosten ausgeführt wird.

Eine partielle Methodendeklaration besteht aus zwei Teilen: der Definition und der Implementierung. Diese können in separaten Teilen einer partiellen Klasse oder im gleichen Teil sein. Wenn es keine Implementierungsdeklaration gibt, optimiert der Compiler anschließend sowohl die definierende Deklaration als auch alle Aufrufe an die Methode.

```csharp
// Definition in file1.cs
partial void onNameChanged();

// Implementation in file2.cs
partial void onNameChanged()
{
  // method body
}
```

- Partielle Methodendeklarationen müssen mit dem Kontextschlüsselwort [partial](../../language-reference/keywords/partial-type.md) beginnen, und die Methode muss [void](../../language-reference/builtin-types/void.md) zurückgeben.

- Partielle Methoden können [in](../../language-reference/keywords/in-parameter-modifier.md)- oder [ref](../../language-reference/keywords/ref.md)-Parameter, aber keine [out](../../language-reference/keywords/out-parameter-modifier.md)-Parameter besitzen.

- Partielle Methoden sind implizit [privat](../../language-reference/keywords/private.md) und können daher nicht [virtuell](../../language-reference/keywords/virtual.md) sein.

- Partielle Methoden können nicht [extern](../../language-reference/keywords/extern.md) sein, da das Vorhandensein des Texts bestimmt, ob sie definierend oder implementierend sind.

- Partielle Methoden können [statische](../../language-reference/keywords/static.md) und [unsichere](../../language-reference/keywords/unsafe.md) Modifizierer besitzen.

- Partielle Methoden können generisch sein. Einschränkungen gelten für die definierende partielle Methodendeklaration und können optional für die implementierende wiederholt werden. Parameter- und Typparameternamen müssen in der implementierenden und definierenden Deklaration nicht gleich sein.

- Sie können einen [Delegaten](../../language-reference/builtin-types/reference-types.md) für eine partielle Methode erstellen, die definiert und implementiert wurde. Dies geht jedoch nicht für partielle Methoden, die nur definiert wurden.

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

Weitere Informationen finden Sie unter [Partielle Datentypen](~/_csharplang/spec/classes.md#partial-types) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Klassen](./classes.md)
- [Strukturen](./structs.md)
- [Schnittstellen](../interfaces/index.md)
- [partial (Typ)](../../language-reference/keywords/partial-type.md)
