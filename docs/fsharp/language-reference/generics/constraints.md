---
title: Einschränkungen
description: Erfahren Sie F# mehr über Einschränkungen für generische Typparameter, um die Anforderungen für ein Typargument in einem generischen Typ oder einer generischen Funktion anzugeben.
ms.date: 05/16/2016
ms.openlocfilehash: 70a8bec1ad67d7e814cb7a96b1876bb22399c5e7
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425022"
---
# <a name="constraints"></a>Einschränkungen

In diesem Thema werden Einschränkungen beschrieben, die Sie auf generische Typparameter anwenden können, um die Anforderungen für ein Typargument in einem generischen Typ oder einer generischen Funktion anzugeben

## <a name="syntax"></a>Syntax

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a>Hinweise

Es gibt mehrere unterschiedliche Einschränkungen, die Sie anwenden können, um die Typen einzuschränken, die in einem generischen Typ verwendet werden können. In der folgenden Tabelle sind diese Einschränkungen aufgeführt und beschrieben.

|Constraint|Syntax|Beschreibung|
|----------|------|-----------|
|Typeinschränkung|*Type-Parameter* :&gt;- *Typ*|Der angegebene Typ muss mit dem angegebenen Typ übereinstimmen oder davon abgeleitet werden, oder, wenn der Typ eine Schnittstelle ist, muss der angegebene Typ die-Schnittstelle implementieren.|
|NULL-Einschränkung|*Type-Parameter* : NULL|Der angegebene Typ muss das NULL-Literalzeichen unterstützen. Dies schließt alle .NET-Objekttypen ein F# , jedoch keine Listen-, Tupel-, Funktions-, Klassen-, Datensatz-oder Union-Typen.|
|Explizite Member-Einschränkung|[(]*Type-Parameter* [oder... oder *Type-Parameter*)]: (*Member-Signature*)|Mindestens eines der bereitgestellten Typargumente muss über einen Member verfügen, der über die angegebene Signatur verfügt. nicht für die gemeinsame Verwendung vorgesehen. Member müssen entweder explizit für den Typ oder einen Teil einer impliziten Typerweiterung definiert sein, damit Sie gültige Ziele für eine explizite Element Einschränkung sind.|
|Konstruktoreinschränkung|*Type-Parameter* : (New: Unit-&gt; ' a)|Der angegebene Typ muss über einen Parameter losen Konstruktor verfügen.|
|Werttyp Einschränkung|:-Struktur|Der angegebene Typ muss ein .net-Werttyp sein.|
|Verweistyp Einschränkung|: Not-Struktur|Der angegebene Typ muss ein .net-Verweistyp sein.|
|Enumerationstyp Einschränkung|: *Aufzählung&lt;zugrunde liegenden Typs*&gt;|Der angegebene Typ muss ein enumerierter Typ sein, der den angegebenen zugrunde liegenden Typ aufweist. nicht für die gemeinsame Verwendung vorgesehen.|
|Delegateinschränkung|: Delegat&lt;*Tuple-Parameter-Type*, *Rückgabetyp*&gt;|Der angegebene Typ muss ein Delegattyp sein, der über die angegebenen Argumente und den Rückgabewert verfügt. nicht für die gemeinsame Verwendung vorgesehen.|
|Vergleichs Einschränkung|: Vergleich|Der angegebene Typ muss einen Vergleich unterstützen.|
|Gleichheits Einschränkung|: Gleichheit|Der angegebene Typ muss Gleichheit unterstützen.|
|Nicht verwaltete Einschränkung|: nicht verwaltet|Der angegebene Typ muss ein nicht verwalteter Typ sein. Nicht verwaltete Typen sind entweder bestimmte primitive Typen (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, oder `decimal`), Enumerationstypen, `nativeptr<_>`oder eine nicht generische Struktur, deren Felder alle nicht verwalteten Typen sind.|

Sie müssen eine Einschränkung hinzufügen, wenn Ihr Code eine Funktion verwenden muss, die für den Einschränkungstyp verfügbar ist, aber nicht für allgemeine Typen. Wenn Sie z. b. die Typeinschränkung verwenden, um einen Klassentyp anzugeben, können Sie eine beliebige Methode dieser Klasse in der generischen Funktion oder dem generischen Typ verwenden.

Das Angeben von Einschränkungen ist manchmal beim expliziten Schreiben von Typparametern erforderlich, da der Compiler ohne Einschränkung nicht überprüfen kann, ob die von Ihnen verwendeten Funktionen für jeden Typ verfügbar sind, der zur Laufzeit für den Typ bereitgestellt wird. Parame.

Die gängigsten Einschränkungen, die Sie F# im Code verwenden, sind Typeinschränkungen, die Basisklassen oder Schnittstellen angeben. Die anderen Einschränkungen werden entweder von der F# Bibliothek verwendet, um bestimmte Funktionen zu implementieren, wie z. b. die explizite Element Einschränkung, die zum Implementieren von Operator Überladungen für arithmetische Operatoren F# verwendet wird, oder Sie werden hauptsächlich bereitgestellt, wenn unterstützt den kompletten Satz von Einschränkungen, die von der Common Language Runtime unterstützt werden.

Beim Typrückschluss werden einige Einschränkungen automatisch vom Compiler abgeleitet. Wenn Sie z. b. den `+`-Operator in einer Funktion verwenden, leitet der Compiler eine explizite Element Einschränkung für Variablen Typen ab, die im Ausdruck verwendet werden.

Der folgende Code veranschaulicht einige Einschränkungs Deklarationen:

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> =
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a>Siehe auch

- [Generics](index.md)
- [Einschränkungen](constraints.md)
