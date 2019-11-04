---
title: Ausnahmebehandlung
description: Erlernen Sie die Grundlagen der Ausnahme F# Behandlung in, und finden Sie Links zu den Ausdrücken und Funktionen zur Ausnahmebehandlung.
ms.date: 05/16/2016
ms.openlocfilehash: e34a65dd7da9d706153254ac28e729de0745e4d0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423056"
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
