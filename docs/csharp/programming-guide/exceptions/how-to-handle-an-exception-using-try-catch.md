---
title: 'Vorgehensweise: Behandeln einer Ausnahme mit „try/catch“ (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie eine Ausnahme mit einem try-catch-Block behandeln. Hier finden Sie ein Codebeispiel und zusätzliche verfügbare Ressourcen.
ms.date: 12/09/2020
helpviewer_keywords:
- exception handling [C#], try/catch blocks
- exceptions [C#], try/catch blocks
- try/catch blocks [C#]
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
ms.openlocfilehash: b6368660dbe037123f5bb6ce52502d4a94fcfc3a
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110519"
---
# <a name="how-to-handle-an-exception-using-trycatch-c-programming-guide"></a>Vorgehensweise: Behandeln einer Ausnahme mit „try/catch“ (C#-Programmierleitfaden)

Ein [try/catch](../../language-reference/keywords/try-catch.md)-Block soll von Arbeitscode generierte Ausnahmen abfangen und verarbeiten. Einige Ausnahmen können in einem `catch`-Block verarbeitet werden, und das Problem kann behoben werden, ohne dass die Ausnahme noch mal ausgelöst wird. Allerdings können Sie meistens nur sicherstellen, dass die passende Ausnahme ausgelöst wird.

## <a name="example"></a>Beispiel

In diesem Beispiel ist <xref:System.IndexOutOfRangeException> nicht die passendste Ausnahme: Für diese Methode ist <xref:System.ArgumentOutOfRangeException> sinnvoller, da der Fehler durch die Übergabe des Arguments `index` des Aufrufers verursacht wird.

:::code language="csharp" source="snippets/exceptions/ExampleTryCatch.cs" id="ExampleTryCatch":::

## <a name="comments"></a>Kommentare

Der Code, der eine Ausnahme auslöst, ist im `try`-Block eingeschlossen. Eine `catch`-Anweisung wird direkt danach hinzugefügt, um `IndexOutOfRangeException` zu verarbeiten, falls dies auftritt. Der `catch`-Block verarbeitet `IndexOutOfRangeException` und löst stattdessen die passendere Ausnahme `ArgumentOutOfRangeException` aus. Um dem Aufrufer so viele Informationen wie möglich bereitzustellen, können Sie die ursprüngliche Ausnahme auf <xref:System.Exception.InnerException%2A> der neuen Ausnahme festlegen. Da die Eigenschaft <xref:System.Exception.InnerException%2A> [schreibgeschützt](../../properties.md#read-only) ist, müssen Sie sie im Konstruktor der neuen Ausnahme zuweisen.
