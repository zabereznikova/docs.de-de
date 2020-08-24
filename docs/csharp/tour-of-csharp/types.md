---
title: 'Einführung in C#: Definieren von Typen und ihren Membern'
description: Die Bausteine für Programme sind Typen. Hier erfahren Sie, wie Sie Klassen, Strukturen, Schnittstellen und mehr in C# erstellen.
ms.date: 08/06/2020
ms.openlocfilehash: 69d6f0fe1e11f287fb5e385761fc210a61929d10
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88068465"
---
# <a name="types-and-members"></a>Typen und Member

## <a name="classes-and-objects"></a>Klassen und Objekte

*Klassen* sind die grundlegendsten der C#-Typen. Eine Klasse ist eine Datenstruktur, die einen Zustand (Felder) und Aktionen (Methoden und andere Funktionsmember) in einer einzigen Einheit kombiniert. Eine Klasse stellt eine Definition für *Instanzen* der Klasse bereit, die auch *Objekte* genannt werden. Klassen unterstützen *Vererbung* und *Polymorphie*. Dies sind Mechanismen, durch die *abgeleitete Klassen* erweitert und *Basisklassen* spezialisiert werden können.

Neue Klassen werden mithilfe von Klassendeklarationen erstellt. Eine Klassendeklaration beginnt mit einem Header. Der Header legt Folgendes fest:

- Die Attribute und Modifizierer der Klasse
- Den Namen der Klasse
- Die Basisklasse (wenn von einer [Basisklasse](#base-classes) geerbt wird)
- Die von der Klasse implementierten Schnittstellen

Auf den Header folgt der Klassenkörper. Dieser besteht aus einer Liste der Memberdeklarationen, die zwischen den Trennzeichen `{` und `}` eingefügt werden.

Im folgenden Code wird die Deklaration einer einfachen Klasse namens `Point` veranschaulicht:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="PointClass":::

Instanzen von Klassen werden mit dem `new`-Operator erstellt. Dieser reserviert Speicher für eine neue Instanz, ruft einen Konstruktor zum Initialisieren der Instanz auf und gibt einen Verweis auf die Instanz zurück. Mit den folgenden Anweisungen werden zwei `Point`-Objekte erstellt und Verweise auf diese Objekte in zwei Variablen gespeichert:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="CreatePoints":::

Der von einem Objekt belegte Speicher wird automatisch wieder freigegeben, wenn das Objekt nicht mehr erreichbar ist. Es ist weder erforderlich noch möglich, die Zuweisung von Objekten in C# explizit aufzuheben.

### <a name="type-parameters"></a>Typparameter

Generische Typparameter definieren [***Typparameter***](../programming-guide/generics/index.md). Typparameter sind eine Liste von Typparameternamen, die in spitzen Klammern enthalten sind. Typparameter folgen auf den Klassennamen. Die Typparameter können dann im Körper der Klassendeklarationen zum Definieren der Klassenmember verwendet werden. Im folgenden Beispiel lauten die Typparameter von `Pair``TFirst` und `TSecond`:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="DefinePairClass":::

Ein Klassentyp, der zum Akzeptieren von Typparametern deklariert wird, wird als *generischer Klassentyp* bezeichnet. Struktur-, Schnittstellen- und Delegattypen können auch generisch sein.
Wenn die generische Klasse verwendet wird, müssen für jeden der Typparameter Typargumente angegeben werden:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="CreatePairObject":::

Ein generischer Typ, für den Typargumente angegeben wurden (siehe `Pair<int,string>` oben), wird als *konstruierter Typ* bezeichnet.

### <a name="base-classes"></a>Basisklassen

Mit einer Klassendeklaration kann eine Basisklasse angegeben werden. Fügen Sie nach dem Klassennamen und den Typparametern einen Doppelpunkt und den Namen der Basisklasse ein. Das Auslassen einer Basisklassenspezifikation ist dasselbe wie eine Ableitung vom Typ `object`. Im folgenden Beispiel ist `Point` die Basisklasse von `Point3D`. Im folgenden ersten Beispiel ist `object` die Basisklasse von `Point`:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="Create3DPoint":::

Eine Klasse erbt die Member der zugehörigen Basisklasse. Vererbung bedeutet, dass eine Klasse implizit nahezu alle Member der Basisklasse enthält. Eine Klasse erbt die Instanz- und statischen Konstruktoren sowie den Finalizer nicht. Eine abgeleitete Klasse kann den geerbten Membern neue Member hinzufügen, aber die Definition eines geerbten Members kann nicht entfernt werden. Im vorherigen Beispiel erbt `Point3D` die Member `X` und `Y` von `Point`, und alle `Point3D`-Instanzen enthalten die drei Eigenschaften `X`, `Y` und `Z`.

Ein Klassentyp kann implizit in einen beliebigen zugehörigen Basisklassentyp konvertiert werden. Eine Variable eines Klassentyps kann auf eine Instanz der Klasse oder eine Instanz einer beliebigen abgeleiteten Klasse verweisen. Beispielsweise kann in den vorherigen Klassendeklarationen eine Variable vom Typ `Point` entweder auf `Point` oder auf `Point3D` verweisen:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="ImplicitCastToBase":::

## <a name="structs"></a>Strukturen

Klassen definieren Typen, die die Vererbung und die Polymorphie unterstützen. Sie ermöglichen es Ihnen, komplexe Verhaltensweise anhand von Hierarchien abgeleiteter Klassen zu erstellen. Im Gegensatz dazu sind [***Strukturtypen***](../language-reference/builtin-types/struct.md) (struct) einfachere Typen, deren Hauptaufgabe darin besteht, Datenwerte zu speichern. Strukturen können keinen Basistyp deklarieren, sie leiten implizit von <xref:System.ValueType?displayProperty=nameWithType> ab. Sie können keine anderen `struct`-Typen von einem `struct`-Typ ableiten. Sie werden implizit versiegelt.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="PointStruct":::

## <a name="interfaces"></a>Schnittstellen

Eine [***Schnittstelle***](../programming-guide/interfaces/index.md) (interface) definiert einen Vertrag, der von Klassen und Strukturen implementiert werden kann. Eine Schnittstelle kann Methoden, Eigenschaften, Ereignisse und Indexer enthalten. Eine Schnittstelle stellt in der Regel keine Implementierungen der von ihr definierten Member bereit. Sie gibt lediglich die Member an, die von Klassen oder Strukturen bereitgestellt werden müssen, die die Schnittstelle implementieren.

Schnittstellen können ***Mehrfachvererbung*** einsetzen. Im folgenden Beispiel erbt die Schnittstelle `IComboBox` sowohl von `ITextBox` als auch `IListBox`.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="FirstInterfaces":::

Klassen und Strukturen können mehrere Schnittstellen implementieren. Im folgenden Beispiel implementiert die Klasse `EditBox` sowohl `IControl` als auch `IDataBound`.

:::code language="csharp" source="./snippets/shared/Types.cs" ID="ImplementInterfaces":::

Wenn eine Klasse oder Struktur eine bestimmte Schnittstelle implementiert, können Instanzen dieser Klasse oder Struktur implizit in diesen Schnittstellentyp konvertiert werden. Beispiel:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="UseInterfaces":::

## <a name="enums"></a>Enumerationen

[***Enumerationstypen***](../language-reference/builtin-types/enum.md) (Enum) definieren eine Gruppe konstanter Werte. Mit dem folgenden `enum`-Typ werden Konstanten deklariert, die verschiedene Wurzelgemüsesorten definieren:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="EnumDeclaration":::

Sie können einen `enum`-Typ definieren, der in Kombination als Flags verwendet werden sollen. In der folgenden Deklaration werden Flags für die vier Jahreszeiten deklariert. Jede Kombination der Jahreszeiten kann angewendet werden, einschließlich eines `All`-Werts, der alle Jahreszeiten umfasst:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="FlagsEnumDeclaration":::

Im folgenden Beispiel werden Deklaration der beiden Enumerationen veranschaulicht:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="UsingEnums":::

## <a name="nullable-types"></a>Nullable-Typen

Jede Art von Variable kann als ***Non-Nullable*** oder ***Nullable*** deklariert werden. Eine Nullable-Variable kann einen zusätzlichen `null`-Wert enthalten, der angibt, dass kein Wert vorliegt. Nullable-Werttypen (Strukturen oder Enumerationen) werden mit <xref:System.Nullable%601?displayProperty=nameWithType> dargestellt. Non-Nullable- und Nullable-Verweistypen werden beide vom zugrunde liegenden Verweistyp repräsentiert. Der Unterschied wird von Metadaten dargestellt, die vom Compiler und einigen Bibliotheken gelesen werden. Der Compiler gibt Warnungen aus, wenn Nullable-Verweise dereferenziert werden, ohne dass ihr Wert zunächst auf `null` geprüft wird. Der Compiler gibt auch Warnungen aus, wenn Non-Nullable-Verweise einem Wert zugewiesen werden, der `null` sein kann. Im folgenden Beispiel wird ein ***nullable int***-Wert deklariert und mit `null` initialisiert. Dann wird der Wert auf `5` festgelegt. Dasselbe Konzept wird mit ***nullable string*** veranschaulicht. Weitere Informationen finden Sie unter [Nullable-Werttypen](../language-reference/builtin-types/nullable-value-types.md) und [Nullable-Verweistypen](../nullable-references.md).

:::code language="csharp" source="./snippets/shared/Types.cs" ID="DeclareNullable":::

## <a name="tuples"></a>Tupel

C# unterstützt [***Tupel***](../language-reference/builtin-types/value-tuples.md), die eine kompakte Syntax zum Gruppieren mehrerer Datenelemente in einer einfachen Datenstruktur bereitstellen. Sie können ein Tupel instanziieren, indem Sie die Typen und Namen der Member zwischen `(` und `)` deklarieren. Dies wird im folgenden Beispiel veranschaulicht:

:::code language="csharp" source="./snippets/shared/Types.cs" ID="DeclareTuples":::

Tupel bieten eine Alternative für Datenstrukturen mit mehreren Membern, ohne dass die Bausteine verwendet werden müssen, die im nächsten Artikel beschrieben werden.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](program-building-blocks.md)
