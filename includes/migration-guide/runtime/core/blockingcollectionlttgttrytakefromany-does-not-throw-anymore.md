---
ms.openlocfilehash: 9e8f9c616d5ae4ed17f35665cff21acbbacda457
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235517"
---
### <a name="blockingcollectionttrytakefromany-does-not-throw-anymore"></a>BlockingCollection\<T>.TryTakeFromAny löst keine Ausnahmen mehr aus

|   |   |
|---|---|
|Details|Wenn eine der Eingabeauflistungen als abgeschlossen markiert ist, gibt <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> nicht länger „-1“ zurück und <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> löst keine Ausnahme mehr aus. Diese Änderung ermöglicht das Verwenden von Auflistungen, wenn eine der Auflistungen entweder leer oder abgeschlossen ist, die andere Auflistung aber weiterhin abrufbare Elemente enthält.|
|Vorschlag|Wenn die Rückgabe von „-1“ durch „TryTakeFromAny“ oder das Auslösen einer Ausnahme durch „TakeFromAny“ für solche Situationen zu Ablaufsteuerungszwecken verwendet wurde, in denen eine blockierende Auflistung abgeschlossen wurde, sollte dieser Code jetzt geändert werden, um <code>.Any(b =&gt; b.IsCompleted)</code> zum Erkennen dieser Bedingung zu verwenden.|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType></li></ul>|
