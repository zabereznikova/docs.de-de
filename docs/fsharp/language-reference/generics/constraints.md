---
title: Einschränkungen (F#)
description: Informationen Sie zu F#-Einschränkungen, die für generische Typparameter an die Anforderungen für die ein Typargument in einer generischen Typ oder eine Funktion gelten.
ms.date: 05/16/2016
ms.openlocfilehash: 7af064159d2722256f0db8286a99fc02435a99cd
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936864"
---
# <a name="constraints"></a>Einschränkungen

In diesem Thema wird beschrieben, Einschränkungen, die Sie auf generische anwenden können Geben Sie Parameter, um die Anforderungen für die ein Typargument in einer generischen Typ oder eine Funktion anzugeben.


## <a name="syntax"></a>Syntax

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a>Hinweise
Es gibt mehrere andere Einschränkungen, die Sie anwenden können, um die Typen beschränken, die in einem generischen Typ verwendet werden kann. Die folgende Tabelle enthält und beschreibt diese Einschränkungen.

|Constraint|Syntax|Beschreibung|
|----------|------|-----------|
|Typeinschränkung|*Typparameter* :&gt; *Typ*|Der bereitgestellte Typ muss gleich oder abgeleitet aus dem angegebenen Typ oder, wenn der Typ eine Schnittstelle ist, muss der angegebene Typ die Schnittstelle implementieren.|
|NULL-Einschränkung|*Typparameter* : null|Der angegebene Typ muss es sich um das null-Literal unterstützen. Dies schließt alle Objekttypen .NET, aber nicht F#-Liste, Tupel, Funktion, Klasse, Datensatz oder union-Typen.|
|Explizites Mitglied-Einschränkung|[()]*Typparameter* [oder... oder *Typparameter*)]: (*Membersignatur*)|Mindestens eines der bereitgestellten Typargumente müssen ein Mitglied, das die angegebene Signatur verfügt; nicht für die allgemeine Verwendung vorgesehen. Mitglieder müssen entweder explizit auf den Typ oder einem Teil einer Erweiterung impliziter Typ werden gültige Ziele für eine explizite Einschränkung für Member definiert werden.|
|Konstruktoreinschränkung|*Typparameter* : (neu: Unit -&gt; "ein)|Der angegebene Typ muss einen Standardkonstruktor verfügen.|
|Werttypeinschränkung|: Struktur|Der angegebene Typ muss ein.|
|Verweistypeinschränkung|: nicht-Struktur|Der angegebene Typ muss ein Verweistyp für .NET.|
|Eine Einschränkung für Enumeration|: Enumeration&lt;*vom zugrunde liegenden Typ*&gt;|Der bereitgestellte Typ muss es sich um ein enumerierter Typ sein, der den angegebenen zugrunde liegenden Typ aufweist; nicht für die allgemeine Verwendung vorgesehen.|
|Delegieren der Einschränkung|: Delegieren&lt;*Tupel-Parameter-Type*, *Rückgabetyp*&gt;|Der angegebene Typ muss ein Delegattyp, die die angegebenen Argumenten sein und Rückgabewert; nicht für die allgemeine Verwendung vorgesehen.|
|Comparison-Einschränkung|: Vergleich|Der angegebene Typ muss es sich um Vergleich unterstützen.|
|Equality-Einschränkung|: auf Gleichheit|Der angegebene Typ muss die Gleichheit unterstützen.|
|Nicht verwaltete Einschränkungen|: nicht verwaltete|Der angegebene Typ muss es sich um einen nicht verwalteten Typ sein. Nicht verwaltete Typen sind entweder bestimmten primitiven Typen (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, oder `decimal`), Enumerationstypen, `nativeptr&lt;_&gt;`, oder eine nicht generische Struktur, deren Felder alle nicht verwalteten Typen werden.|
Sie müssen eine Einschränkung hinzufügen, wenn Ihr Code muss eine Funktion verwenden, die in der Regel auf den Einschränkungstyp jedoch nicht für Typen verfügbar ist. Wenn Sie die typeinschränkung verwenden, um einen Klassentyp anzugeben, können Sie z. B. eine der Methoden dieser Klasse in der generischen Funktion oder einen Typ verwenden.

Angeben von Einschränkungen ist manchmal erforderlich, wenn Typparameter explizit zu schreiben, da ohne Einschränkung, der Compiler kann nicht überprüft haben, dass die Funktionen, die Sie verwenden in einen beliebigen Typ verfügbar sein werden, der zur Laufzeit für den Typ angegeben werden kann der Parameter.

Die am häufigsten verwendeten Einschränkungen, die Sie in F#-Code verwenden, sind die typeinschränkungen, die angeben, Basisklassen oder Schnittstellen. Die anderen Einschränkungen werden entweder von der F#-Bibliothek verwendet, um bestimmte Funktionen, z. B. die Einschränkung explizites Mitglied zu implementieren, die zum Implementieren von arithmetischen Operatoren überladen verwendet oder dienen hauptsächlich deshalb, weil f# die vollständige unterstützt Reihe von Einschränkungen, die von der common Language Runtime unterstützt wird.

Beim Rückschlussprozess geben sind einige Einschränkungen automatisch vom Compiler abgeleitet. Angenommen, Sie verwenden die `+` Operator in einer Funktion, leitet der Compiler eine explizite Mitglieder-Einschränkung auf Variablen Typen, die im Ausdruck verwendet werden.

Der folgende Code zeigt einige Einschränkung-Deklarationen.

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

// Member constraint with static member
type Class4<'T when 'T : (static member staticMethod1 : unit -> 'T) > =
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
[Generika](index.md)

[Einschränkungen](constraints.md)
