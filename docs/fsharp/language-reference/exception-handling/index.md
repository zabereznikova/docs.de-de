---
title: Ausnahmebehandlung (F#)
description: Ausnahmebehandlung (F#)
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ad475c4a-d94e-47d9-b27b-3ff000b65f8e
translationtype: Human Translation
ms.sourcegitcommit: 0a01ec92a90d99fafaacbd3f71f5177e5cf94a68
ms.openlocfilehash: d95aca8c511524f0b9af67b34a5999f885cf3aaf
ms.lasthandoff: 04/05/2017

---

# <a name="exception-handling"></a>Ausnahmebehandlung

Dieser Abschnitt enthält Informationen über die Unterstützung für die Ausnahmebehandlung in der Sprache F#.


## <a name="exception-handling-basics"></a>Grundlagen der Ausnahmebehandlung
Die Ausnahmebehandlung ist die Standardmethode zum Behandeln von Fehlerbedingungen in .NET Framework. Daher muss jede .NET-Sprache diesen Mechanismus unterstützen, einschließlich F#. Eine *Ausnahme* ist ein Objekt, das Information über einen Fehler kapselt. Wenn Fehler auftreten, werden Ausnahmen ausgelöst, und die reguläre Ausführung wird beendet. Stattdessen sucht die Laufzeit nach einem passenden Handler für die Ausnahme. Die Suche beginnt in der aktuellen Funktion und wird im Stapel in den höheren Ebenen der Aufrufer fortgesetzt, bis ein entsprechender Handler gefunden wird. Anschließend wird der Handler ausgeführt.

Zudem führt die Laufzeit beliebigen Code in `finally`-Blöcken aus, wenn der Stapel entladen wird, um sicherzustellen, dass Objekte ordnungsgemäß während des Endladungsprozesses bereinigt werden.


## <a name="related-topics"></a>Verwandte Themen

|Titel|Beschreibung|
|-----|-----------|
|[Ausnahmetypen](exception-types.md)|Beschreibt, wie ein Ausnahmetyp deklariert wird|
|[Ausnahmen: Der `try...with`-Ausdruck](the-try-with-expression.md)|Beschreibt das Sprachkonstrukt, das Ausnahmebehandlung unterstützt|
|[Ausnahmen: Der `try...finally`-Ausdruck](the-try-finally-expression.md)|Beschreibt das Sprachkonstrukt, mit dem Sie Bereinigungscode auszuführen können, während der Stapel entladen wird, wenn eine Ausnahme ausgelöst wird|
|[Ausnahmen: Die `raise`-Funktion](the-raise-Function.md)|Beschreibt, wie ein Ausnahmeobjekt ausgelöst wird|
|[Ausnahmen: Die `failwith`-Funktion](the-failwith-function.md)|Beschreibt, wie eine allgemeine F#-Ausnahme generiert wird|
|[Ausnahmen: Die `invalidArg`-Funktion](the-invalidArg-function.md)|Beschreibt, wie eine ungültige Argumentausnahme generiert wird|
