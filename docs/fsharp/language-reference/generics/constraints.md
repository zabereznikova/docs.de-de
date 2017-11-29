---
title: "Einschränkungen (F#)"
description: "Informationen Sie zu F#-Einschränkungen, die für generische Typparameter an die Anforderungen für die ein Type-Argument in einem generischen Typ oder einer Funktion gültig."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2f232a3a-9486-48fb-9759-f23404ed4b52
ms.openlocfilehash: 91854fd2f692688e0f1c27aba1422eff64156048
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="constraints"></a>Einschränkungen

In diesem Thema wird beschrieben, Einschränkungen, die Sie für generische gelten können Typparameter an die Anforderungen für die ein Type-Argument in einer generischen Typ- oder Funktion.


## <a name="syntax"></a>Syntax

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a>Hinweise
Es gibt mehrere unterschiedliche Einschränkungen, die Sie anwenden können, um die Typen beschränken, die in einem generischen Typ verwendet werden kann. In der folgenden Tabelle aufgelistet und beschrieben von diesen Einschränkungen.

|Constraint|Syntax|Beschreibung|
|----------|------|-----------|
|Typeinschränkung|*Typparameter* :&gt; *Typ*|Der bereitgestellte Typ muss gleich oder abgeleiteten aus dem angegebenen Typ oder, wenn der Typ eine Schnittstelle ist, muss der angegebene Typ der Schnittstelle implementieren.|
|NULL-Einschränkung|*Typparameter* : null|Der angegebene Typ muss das null-Literal unterstützen. Dies schließt alle Objekttypen .NET jedoch nicht F#-Liste, Tupel, Funktion, Klasse, Datensatz oder union-Typen.|
|Explizites Mitglied-Einschränkung|[()]*Typparameter* [oder... oder *Typparameter*)]: (* Membersignatur *)|Mindestens eines der bereitgestellten Typargumente benötigen ein Element, das die angegebene Signatur verfügt; nicht für die allgemeine Verwendung vorgesehen. Mitglieder müssen entweder explizit auf den Typ oder die Teil einer Erweiterung impliziter Typ werden als gültige Ziele für eine explizite Schnittstellenmember-Einschränkung definiert werden.|
|Konstruktoreinschränkung|*Typparameter* : (new: Einheit -&gt; "ein)|Der bereitgestellte Typ muss einen Standardkonstruktor verfügen.|
|Werttypeinschränkung|: Struktur|Der angegebene Typ muss ein Werttyp .NET.|
|Reference-Typ-Einschränkung|: nicht-Struktur|Der angegebene Typ muss ein Verweistyp .NET.|
|Enumeration Typeinschränkung|: Enum&lt;*zugrunde liegenden Typ*&gt;|Der bereitgestellte Typ muss ein enumerierter Typ, mit dem angegebenen zugrunde liegenden Datentyp; nicht für die allgemeine Verwendung vorgesehen.|
|Delegieren der Einschränkung|: Delegieren&lt;*Tupel Parametertyp*, *Return-Type*&gt;|Der bereitgestellte Typ muss werden einem Delegattyp als Typ, der die angegebenen Argumenten verfügt und Rückgabewert; nicht für die allgemeine Verwendung vorgesehen.|
|Vergleich-Einschränkung|: Vergleich|Der angegebene Typ muss Vergleich unterstützen.|
|Equality-Einschränkung|: auf Gleichheit|Der angegebene Typ muss Gleichheit unterstützen.|
|Nicht verwaltete Einschränkung|: nicht verwaltete|Der angegebene Typ muss einen nicht verwalteten Typ. Nicht verwaltete Typen sind entweder bestimmte primitiven Typen (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, oder `decimal`), Enumerationstypen, `nativeptr&lt;_&gt;`, oder eine nicht generische Struktur, deren Felder alle nicht verwalteten Typen.|
Sie müssen eine Einschränkung hinzufügen, wenn der Code hat eine Funktion verwenden, die in der Regel auf den Einschränkungstyp jedoch nicht für Typen verfügbar ist. Wenn Sie die Einschränkung des Typs verwenden, um einen Klassentyp anzugeben, können Sie eine der Methoden dieser Klasse in der generischen Funktion oder einen Typ verwenden.

Angeben von Einschränkungen ist manchmal erforderlich, wenn Typparameter explizit zu schreiben, da ohne Einschränkung, hat der Compiler keine Möglichkeit zu überprüfen, dass die Funktionen, mit dem Sie, auf einen beliebigen Typ zur Verfügung stehen, der zur Laufzeit für den Typ angegeben werden kann Parameter.

Die am häufigsten verwendeten Einschränkungen, die in f#-Code verwendet werden, typeinschränkungen, die Basisklassen oder Schnittstellen angeben. Die anderen Einschränkungen werden entweder von der f#-Bibliothek verwendet, um bestimmte Funktionen, z. B. die Einschränkung explizites Mitglied zu implementieren, wird verwendet, um den Operator für arithmetische Operatoren überladen implementieren oder dienen hauptsächlich da f# das vollständige unterstützt ein Satz von Einschränkungen, die von der common Language Runtime unterstützt wird.

Beim Rückschlussprozess Typ sind einige Einschränkungen automatisch vom Compiler abgeleitet. Angenommen, Sie verwenden die `+` -Operator in einer Funktion, leitet der Compiler eine explizite Schnittstellenmember-Einschränkung für Variablentypen, die im Ausdruck verwendet werden.

Der folgende Code zeigt einige Einschränkung Deklarationen.

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
