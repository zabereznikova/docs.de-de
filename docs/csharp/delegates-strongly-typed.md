---
title: Stark typisierte Delegate
description: Stark typisierte Delegate
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 564a683d-352b-4e57-8bac-b466529daf6b
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ad73474ceb56f8610facd1668825bb0e71ccc7cb
ms.lasthandoff: 03/13/2017

---

# <a name="strongly-typed-delegates"></a>Stark typisierte Delegate

[Vorheriges](delegate-class.md)

Im vorherigen Artikel haben Sie gesehen, dass bestimmte Delegaten mithilfe des `delegate`-Schlüsselworts erstellen. 

Die abstrakte Klasse für den Delegaten stellt die Infrastruktur für die lose Kopplung und den losen Aufruf bereit. Konkrete Delegattypen werden durch die Einführung und das Erzwingen von Typsicherheit für die Methoden, die zur Aufrufliste für ein Delegatobjekt hinzugefügt werden, viel nützlicher. Wenn Sie das `delegate`-Schlüsselwort verwenden und einen konkreten Delegattyp definieren, generiert der Compiler diese Methoden.

In der Praxis würde dies zur Erstellung neuer Delegattypen führen, wann immer Sie eine andere Methodensignatur benötigen. Diese Arbeit könnte mit der Zeit ermüdend werden. Jede neue Funktion erfordert neue Delegattypen.

Glücklicherweise ist dies nicht erforderlich. Der .NET Core Framework enthält verschiedene Typen, die Sie wiederverwenden können, wenn Sie Delegattypen benötigen. Dies sind [generische](programming-guide/generics/index.md) Definitionen, damit Sie Anpassungen deklarieren können, wenn Sie neue Methodendeklarationen benötigen. 

Der erste dieser Typen ist der @System.Action-Typ, und verschiedene Varianten:

```csharp
public delegate void Action();
public delegate void Action<in T>(T arg);
public delegate void Action<in T1, in T2>(T1 arg1, T2 arg2);
// Other variations removed for brevity.
```

Die `in`-Modifizierer im generischen Typargument wird in diesem Artikel in Kovarianz behandelt.

Es gibt Variationen des `Action`-Delegaten, der bis zu 16 Argumente enthält, wie z.B. @System.Action%6016.
Es ist wichtig, dass diese Definitionen andere generische Argumente für jeden der Delegatargumente verwenden: Das bietet Ihnen maximale Flexibilität. Die Methodenargumente müssen nicht, aber können der gleiche Typ sein.

Verwenden Sie einen der `Action`-Typen für jeden Delegattyp, der über einen void-Rückgabetyp verfügt.

Das Framework enthält auch mehrere generische Delegattypen, die Sie für Delegattypen verwenden können, die Werte zurückgeben:

```csharp
public delegate TResult Func<out TResult>();
public delegate TResult Func<in T1, out TResult>(T1 arg);
public delegate TResult Func<in T1, in T2, out TResult>(T1 arg1, T2 arg2);
// Other variations removed for brevity
```

Der `out`-Modifizierer im Ergebnisargument des generischen Typs wird in diesem Artikel in Kovarianz behandelt.

Es gibt Variationen des `Func`-Delegaten mit bis zu 16 Eingabeargumenten, wie z.B. @System.Func%6017.
Der Typ des Ergebnisses ist immer der letzte Typparameter in allen `Func`-Deklarationen, gemäß der Konvention.

Verwenden Sie einen der `Func`-Typen für jeden Delegattyp, der einen Wert zurückgibt.

Es gibt auch einen spezialisierten @System.Predicate% 601-Typ für einen Delegaten, der einen Test für einen einzelnen Wert zurückgibt:

```csharp
public delegate bool Predicate<in T>(T obj);
```

Möglicherweise haben Sie bemerkt, dass für jeden `Predicate`-Typ ein strukturell äquivalenter `Func`-Typ vorhanden ist, beispielsweise:

```csharp
Func<string, bool> TestForString;
Predicate<string> AnotherTestForString;
```

Sie denken möglicherweise, dass diese beiden Typen äquivalent sind. Das sind sie nicht.
Diese beiden Variablen sind nicht austauschbar. Eine Variable eines Typs kann dem anderen Typ nicht zugewiesen werden. Das C#-Typsystem verwendet die Namen der definierten Typen, nicht die Struktur.

Alle diese Definitionen von Delegattypen in der .NET Core-Bibliothek sollten bedeuten, dass Sie keinen neuen Delegattypen für jede neue Funktion, die Sie erstellen und die Delegaten erfordert, definieren müssen. Diese generischen Definitionen sollten alle Delegattypen bereitstellen, die Sie in den meisten Fällen benötigen. Sie können einen dieser Typen mit den erforderlichen Parametern einfach instanziieren. Im Falle von Algorithmen, die generisch vorgenommen werden können, können diese Delegaten als generische Typen verwendet werden. 

Dies sollte Zeit sparen und die Anzahl neuer Typen minimieren, die Sie erstellen müssen, um mit Delegaten zu arbeiten.

Im nächsten Artikel sehen Sie einige allgemeine Muster für die praktische Arbeit mit Delegaten.

[Weiter](delegates-patterns.md)

