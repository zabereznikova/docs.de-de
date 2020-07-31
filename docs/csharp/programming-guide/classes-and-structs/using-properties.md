---
title: Verwenden von Eigenschaften – C#-Programmierhandbuch
description: Diese Beispiele veranschaulichen die Verwendung von Eigenschaften in C#. Hier erfahren Sie, wie die Zugriffsmethoden „get“ und „set“ Lese- und Schreibzugriff implementieren, und lernen Sie Verwendungsmöglichkeiten für Eigenschaften kennen.
ms.date: 07/20/2015
helpviewer_keywords:
- set accessor [C#]
- get accessor [C#]
- properties [C#], about properties
ms.assetid: f7f67b05-0983-4cdb-96af-1855d24c967c
ms.openlocfilehash: 51ca0a37022c99bfbd9d61f2cc47f529d535e72a
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864656"
---
# <a name="using-properties-c-programming-guide"></a>Verwenden von Eigenschaften (C#-Programmierhandbuch)

Eigenschaften kombinieren Aspekte der Felder und der Methoden. Für den Benutzer eines Objekts erscheint eine Eigenschaft wie ein Feld; der Zugriff auf die Eigenschaft erfordert dieselbe Syntax. Für den Implementierer einer Klasse, besteht eine Eigenschaft aus einem oder zwei Codeblöcken, die einen [get](../../language-reference/keywords/get.md)-Accessor und/oder einen [set](../../language-reference/keywords/set.md)-Accessor darstellen. Der Codeblock für den `get`-Accessor wird ausgeführt, wenn die Eigenschaft gelesen wird; der Codeblock für den `set`-Accessor wird ausgeführt, wenn der Eigenschaft ein neuer Wert zugewiesen wird. Eine Eigenschaft ohne einen `set`-Accessor ist schreibgeschützt. Eine Eigenschaft ohne einen `get`-Accessor ist lesegeschützt. Eine Eigenschaft, die beide Accessoren umfasst, ermöglicht Lese-/ Schreibzugriff.

Im Gegensatz zu Feldern, werden Eigenschaften nicht als Variablen klassifiziert. Aus diesem Grund können Sie Eigenschaften nicht als [ref](../../language-reference/keywords/ref.md) oder [out](../../language-reference/keywords/out-parameter-modifier.md)-Parameter übergeben.

Eigenschaften sind vielseitig verwendbar: Sie können Daten überprüfen, bevor sie eine Änderung zulassen. Sie können Daten in einer Klasse transparent verfügbar machen, in denen die Daten in Wirklichkeit von einer anderen Quelle abgerufen werden, z.B. einer Datenbank. Sie können eine Aktion ausführen, wenn Daten geändert werden, z.B. ein Ereignis auslösen, oder den Wert anderer Felder verändern.

Eigenschaften werden im Klassenblock deklariert, indem die Zugriffsebene des Felds angegeben wird, gefolgt vom Typ der Eigenschaft, gefolgt vom Namen der Eigenschaft und gefolgt von einem Codeblock, der einen `get`-Accessor und/oder einen `set` Accessor deklariert. Zum Beispiel:

[!code-csharp[csProgGuideProperties#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#7)]

In diesem Beispiel wird `Month` als Eigenschaft so deklariert, dass der `set`-Accessor dafür sorgen kann, dass der `Month`-Wert zwischen 1 und 12 festgelegt wird. Die `Month`-Eigenschaft verwendet ein privates Feld, um den tatsächlichen Wert nachzuverfolgen. Der tatsächliche Speicherort der Daten für eine Eigenschaft wird häufig als „Sicherungsspeicher“ der Eigenschaft bezeichnet. Es ist üblich für Eigenschaften, die privaten Felder als Sicherungsspeicher zu verwenden. Das Feld wird als privat gekennzeichnet um sicherzustellen, dass es nur durch Aufrufen der Eigenschaft geändert werden kann. Weitere Informationen zu öffentlichen und privaten Zugriffsbeschränkungen finden Sie unter [Zugriffsmodifizierer](./access-modifiers.md).

Automatisch implementierte Eigenschaften stellen eine vereinfachte Syntax für einfache Eigenschaftendeklarationen bereit. Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](auto-implemented-properties.md).

## <a name="the-get-accessor"></a>Der get-Accessor

Der Text des `get` Accessors ähnelt dem einer Methode. Er muss einen Wert des Eigenschaftentyps zurückgeben. Die Ausführung des `get` Accessors entspricht dem Lesen des Wert des Felds. Wenn Sie z.B. die private Variable vom `get` -Accessor zurückgeben und Optimierungen aktiviert sind, wird der Aufruf an die `get`-Accessor-Methode vom Compiler eingebettet, damit kein zusätzlicher Aufwand an Methodenaufrufen entsteht. Allerdings kann eine `get`-Accessor-Methode kann nicht eingebettet werden, da der Compiler zum Zeitpunkt der Kompilierung nicht erkennt, welche Methode zur Laufzeit tatsächlich aufgerufen wird. Im folgenden finden Sie einen `get`-Accessor, der den Wert eines privaten Felds zurückgibt `_name`:

[!code-csharp[csProgGuideProperties#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#8)]

Wenn Sie auf die Eigenschaft, außer als Ziel einer Zuweisung, verweisen, wird der `get`-Accessor aufgerufen, um den Wert der Eigenschaft zu lesen. Zum Beispiel:

[!code-csharp[csProgGuideProperties#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#9)]

Der `get` Accessor muss mit einer [return](../../language-reference/keywords/return.md)- oder einer [throw](../../language-reference/keywords/throw.md)-Anweisung enden, und die Steuerung darf nicht über den Accessortext hinausgehen.

Es ist ein unzulässiger Programmierstil den Zustand des Objekts mithilfe des `get`-Accessors zu verändern. Der folgende Accessor hat z.B. den Nebeneffekt, dass der Zustand des Objekts, bei jedem Zugriff auf das `_number`-Feld verändert wird.

[!code-csharp[csProgGuideProperties#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#10)]

Der `get`-Accessor kann verwendet werden, um den Wert des Felds zurückzugeben, oder um den Wert des Felds zu berechnen und zurückgeben. Zum Beispiel:

[!code-csharp[csProgGuideProperties#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#11)]

Im vorherigen Codesegment wird, wenn Sie der `Name`-Eigenschaft keinen Wert zuweisen, der Wert `NA` zurückgegeben.

## <a name="the-set-accessor"></a>Der set-Accessor

Der `set`-Accessor ähnelt einer Methode, deren Rückgabetyp [void](../../language-reference/builtin-types/void.md) ist. Er verwendet einen impliziten Parameter mit dem Namen `value`, dessen Typ der Typ der Eigenschaft ist. Im folgenden Beispiel wird ein `set`-Accessor der `Name`-Eigenschaft hinzugefügt.

[!code-csharp[csProgGuideProperties#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#12)]

Wenn Sie der Eigenschaft einen Wert zuweisen, wird der `set`-Accessor mit einem Argument aufgerufen, das den neuen Wert bereitstellt. Zum Beispiel:

[!code-csharp[csProgGuideProperties#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#13)]

Das Verwenden des impliziten Parameternamens, `value`, für die Deklaration einer lokalen Variablen in einem `set`-Accessor ist ein Fehler.

## <a name="remarks"></a>Hinweise

Eigenschaften können als `public`, `private`, `protected`, `internal`, `protected internal` oder `private protected` gekennzeichnet werden. Diese Zugriffsmodifizierer definieren, wie Benutzer der Klasse auf die Eigenschaft zugreifen können. Die `get`- und `set`-Accessoren für die gleiche Eigenschaft haben möglicherweise verschiedene Zugriffsmodifizierer. Z.B. kann `get` möglicherweise `public` sein, um den schreibgeschützten Zugriff von außerhalb des Typs zu ermöglichen, und `set` kann möglicherweise `private` oder `protected` sein. Weitere Informationen finden Sie unter [Zugriffsmodifizierer](./access-modifiers.md).

Eine Eigenschaft kann als statische Eigenschaft deklariert werden, mithilfe des `static`-Schlüsselworts. Dadurch steht das Feld Aufrufern jederzeit zur Verfügung, auch wenn keine Instanz der Klasse vorhanden ist. Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](./static-classes-and-static-class-members.md).

Ein Ereignis kann mithilfe des [virtual](../../language-reference/keywords/virtual.md)-Schlüsselworts als virtuelles Ereignis gekennzeichnet werden. Dies ermöglicht abgeleiteten Klassen, das Ereignisverhalten mithilfe des [override](../../language-reference/keywords/override.md)-Schlüsselworts zu überschreiben. Weitere Informationen zu diesen Optionen finden Sie unter [Vererbung](inheritance.md).

Ein Ereignis, das ein virtuelles Ereignis überschreibt, kann auch [sealed](../../language-reference/keywords/sealed.md)(verschlossen) sein, was angibt, dass es für abgeleitete Klassen nicht mehr virtuell ist. Schließlich kann eine Eigenschaft als [abstract](../../language-reference/keywords/abstract.md)(abstrakt) deklariert werden. Dies bedeutet, dass es keine Implementierung in der Klasse gibt, und abgeleitete Klassen müssen eine eigene Implementierung schreiben. Weitere Informationen zu abstrakten Klassen finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](abstract-and-sealed-classes-and-class-members.md).
  
> [!NOTE]
> Das Verwenden eines [virtual](../../language-reference/keywords/virtual.md)(virtuell)-, [abstract](../../language-reference/keywords/abstract.md)(abstrakt)- oder [override](../../language-reference/keywords/override.md)(außer Kraft setzen)- Modifizierers für einen Accessor einer [statischen](../../language-reference/keywords/static.md) Eigenschaft ist ein Fehler.

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt,Instanz-, statische- und schreibgeschützte Eigenschaften. Dieser Parameter akzeptiert den Namen des Mitarbeiters auf der Tastatur, Inkremente `NumberOfEmployees` durch 1, und zeigt den Mitarbeiternamen und die Nummer an.

[!code-csharp[csProgGuideProperties#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#2)]

## <a name="example"></a>Beispiel

In diesem Beispiel wird veranschaulicht, wie auf eine Eigenschaft in einer Basisklasse zugegriffen werden kann, die von einer anderen Eigenschaft ausgeblendet ist, die in einer abgeleiteten Klasse den gleichen Namen hat:

[!code-csharp[csProgGuideProperties#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#3)]

Die folgenden Punkte im vorherigen Beispiel sind wichtig:

- Die Eigenschaft `Name` in der abgeleiteten Klasse blendet die Eigenschaft `Name` in der Basisklasse aus. In solch einem Fall wird der `new`-Modifizierer in der Deklaration der Eigenschaft in der abgeleiteten Klasse verwendet:

     [!code-csharp[csProgGuideProperties#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#4)]  

- Die Umwandlung `(Employee)` wird für den Zugriff auf die ausgeblendete Eigenschaft in der Basisklasse verwendet:

     [!code-csharp[csProgGuideProperties#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#5)]

     Weitere Informationen zum Ausblenden von Mitgliedern finden Sie unter [new-Modifizierer](../../language-reference/keywords/new-modifier.md).

## <a name="example"></a>Beispiel

In diesem Beispiel implementieren zwei Klassen `Cube` und `Square` eine abstrakte Klasse `Shape`, und überschreiben die abstrakte `Area`-Eigenschaft. Beachten Sie die Verwendung des [überschreiben](../../language-reference/keywords/override.md)-Modifizierers in den Eigenschaften. Das Programm akzeptiert die Seite als Eingabe und berechnet die Bereiche für das Quadrat und den Cube. Das Programm akzeptiert auch den Bereich als Eingabe und berechnet die entsprechende Seite für das Quadrat und den Cube.

[!code-csharp[csProgGuideProperties#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#6)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Eigenschaften](properties.md)
- [Schnittstelleneigenschaften](interface-properties.md)
- [Automatisch implementierte Eigenschaften](auto-implemented-properties.md)
