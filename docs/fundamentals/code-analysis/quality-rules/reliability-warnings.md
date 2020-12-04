---
title: Zuverlässigkeits Regeln (Code Analyse)
description: Erfahren Sie mehr über die Zuverlässigkeits Regeln für die Code Analyse.
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.reliabilityrules
helpviewer_keywords:
- rules, reliability
- reliability rules
- managed code analysis rules, reliability rules
author: gewarren
ms.author: gewarren
ms.openlocfilehash: a747dd4dcda351a1ddb0f3d069bb7bac895c32f8
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "96591773"
---
# <a name="reliability-rules"></a>Zuverlässigkeitsregeln

Zuverlässigkeits Regeln unterstützen die Zuverlässigkeit von Bibliotheken und Anwendungen, z. b. die korrekte Arbeitsspeicher-und Thread Verwendung Die Zuverlässigkeits Regeln umfassen Folgendes:

|Regel|Beschreibung|
|----------|-----------------|
|[CA2000: Objekte verwerfen, bevor Bereich verloren geht.](ca2000.md)|Da eine Ausnahme auftreten kann, durch die die Ausführung eines Objektfinalizers verhindert wird, sollte das Objekt explizit verworfen werden, bevor sich sämtliche Verweise auf dieses außerhalb des Bereichs befinden.|
|[CA2002: Auf Objekten mit schwacher Identität nicht sperren.](ca2002.md)|Ein Objekt hat eine schwache Identität, wenn ein Zugriff darauf über Grenzen von Anwendungsdomänen hinweg möglich ist. Ein Thread, der eine Sperre für ein Objekt zu erhalten versucht, das über eine schwache Identität verfügt, kann durch einen zweiten Thread in einer anderen Anwendungsdomäne blockiert werden, der eine Sperre für das gleiche Objekt besitzt.|
|[CA2007: Eine Aufgabe nicht direkt abwarten](ca2007.md)|Eine asynchrone Methode [erwartet](../../../csharp/language-reference/operators/await.md) <xref:System.Threading.Tasks.Task> direkt ein.|
|[CA2008: Keine Tasks ohne Übergabe eines TaskSchedulers erstellen](ca2008.md)|Ein Task Erstellungs-oder Fortsetzungs Vorgang verwendet eine Methoden Überladung, die keinen <xref:System.Threading.Tasks.TaskScheduler> Parameter angibt.|
|[CA2009: „ToImmutableCollection“ nicht für einen ImmutableCollection-Wert aufrufen.](ca2009.md)|`ToImmutable` die Methode wurde für eine unveränderliche Auflistung aus dem <xref:System.Collections.Immutable> Namespace unnötig aufgerufen.|
|[CA2011: Eigenschaft nicht innerhalb ihres Setters zuweisen](ca2011.md) | Einer Eigenschaft wurde versehentlich ein Wert innerhalb ihrer eigenen [Set-Zugriffs](../../../csharp/programming-guide/classes-and-structs/using-properties.md#the-set-accessor)Methode zugewiesen. |
|[CA2012: Verwenden Sie ValueTasks ordnungsgemäß.](ca2012.md) | Valuetasks, die von Element aufrufen zurückgegeben wurden, sollen direkt gewartet werden.  Versucht, eine valuetask mehrmals zu verwenden oder direkt auf das Ergebnis zuzugreifen, bevor es als abgeschlossen bezeichnet wird, kann zu einer Ausnahme oder Beschädigung führen.  Das ignorieren einer solchen valuetask ist wahrscheinlich ein Hinweis auf einen Funktionsfehler und kann die Leistung beeinträchtigen. |
|[CA2013: Verwenden Sie ReferenceEquals nicht mit Werttypen.](ca2013.md) | Beim Vergleichen von Werten mit werden bei <xref:System.Object.ReferenceEquals%2A?displayProperty=fullName> objA und objB Werttypen verwendet, bevor Sie an die-Methode übermittelt werden <xref:System.Object.ReferenceEquals%2A> . Dies bedeutet, dass auch dann, wenn objA und objB dieselbe Instanz eines Werttyps darstellen, die <xref:System.Object.ReferenceEquals%2A> Methode trotzdem false zurückgibt. |
|[CA2014: Verwenden Sie stackzuweisung nicht in Schleifen.](ca2014.md) | Der von stackzugewiesc zugewiesene Stapel Speicher wird nur am Ende des Aufruf der aktuellen Methode freigegeben.  Die Verwendung in einer-Schleife kann zu unbegrenzten Stapel Vergrößerung und letztlichen Stapelüberlauf Bedingungen führen. |
|[CA2015: Finalizer nicht für Typen definieren, die von memorymanager &lt; T abgeleitet sind&gt;](ca2015.md) | Durch das Hinzufügen eines Finalizers zu einem von abgeleiteten Typ <xref:System.Buffers.MemoryManager%601> kann der Speicher freigegeben werden, während er noch von einem verwendet wird <xref:System.Span%601> . |
|[CA2016: Parameter "CancellationToken" an Methoden weiterleiten, die diesen Parameter akzeptieren.](ca2016.md) | Leiten Sie den- `CancellationToken` Parameter an Methoden weiter, die einen annehmen, um sicherzustellen, dass die Vorgangs Abbruch Benachrichtigungen ordnungsgemäß weitergegeben werden, oder übergeben Sie `CancellationToken.None` explizit, um anzugeben, dass das Token absichtlich nicht |
