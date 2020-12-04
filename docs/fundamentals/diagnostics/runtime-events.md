---
title: Lauf Zeit Ereignisse
description: Überprüfen Sie die von der .NET-Runtime (CoreCLR) ausgegebenen Diagnose Ereignisse, die mit etw, lttng oder eventpipe verwendet werden können.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- runtime events (CoreCLR)
- ETW, EventPipe runtime events (CoreCLR)
ms.openlocfilehash: 33fa7275ce40934ce043b4d0dba5749c37515755
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "96592083"
---
# <a name="net-runtime-events"></a>.Net-Lauf Zeit Ereignisse

Die .NET-Runtime (CoreCLR) gibt verschiedene Ereignisse aus, die verwendet werden können, um Probleme mit der .NET-Anwendung zu diagnostizieren, die über verschiedene Mechanismen, wie z `ETW` . b., und, genutzt werden können `LTTng` `EventPipe` .

Dieses Dokument dient als Referenz zu den Ereignissen, die von der .net Core-Laufzeit ausgelöst werden.

Informationen zu Lauf Zeit Ereignissen in .NET Framework finden Sie unter [CLR-ETW-Ereignisse](../../framework/performance/clr-etw-events.md).

## <a name="in-this-section"></a>In diesem Abschnitt

[Konfliktereignisse](runtime-contention-events.md)\
Diese Ereignisse sammeln Informationen zu Monitor Sperr Konflikten.

[Garbage Collection-Ereignisse](runtime-garbage-collection-events.md)\
Diese Ereignisse sammeln Informationen, die die Garbage Collection betreffen. Sie helfen bei der Diagnose und beim Debuggen, einschließlich der Ermittlung, wie oft Garbage Collection ausgeführt wurde, wie viel Arbeitsspeicher während Garbage Collection freigegeben wurde usw.

[Ausnahme Ereignisse](runtime-exception-events.md)\
Diese Lauf Zeit Ereignisse erfassen Informationen zu Ausnahmen, die ausgelöst werden.

[Interop-Ereignisse](runtime-interop-events.md)\
Diese Lauf Zeit Ereignisse erfassen Informationen über Common Intermediate Language (CIL)-Stub-Generierung.

[Lade-und Binder Ereignisse](runtime-loader-binder-events.md)\
Diese Ereignisse sammeln Informationen in Bezug auf das Laden und Entladen von Assemblys und Modulen.

[Methoden Ereignisse](runtime-method-events.md)\
Diese Ereignisse sammeln Informationen, die für Methoden spezifisch sind. Die Nutzlast dieser Ereignisse ist für die Symbolauflösung erforderlich. Darüber hinaus bieten diese Ereignisse hilfreiche Informationen, beispielsweise, wie oft eine Methode aufgerufen wurde.

[Thread Ereignisse](runtime-thread-events.md)\
Diese Ereignisse sammeln Informationen zu Arbeits- und E/A-Threads.

[Typereignisse](runtime-type-events.md)\
Diese Ereignisse sammeln Informationen über das Typsystem.
