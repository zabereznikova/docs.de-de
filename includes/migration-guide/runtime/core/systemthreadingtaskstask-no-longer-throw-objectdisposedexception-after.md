---
ms.openlocfilehash: ab2907b05bff409fed9a370d5cbebbf3d1575d2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379659"
---
### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>System.Threading.Tasks.Task löst kein ObjectDisposedException mehr aus, nachdem das Objekt verworfen wurde

|   |   |
|---|---|
|Details|Mit Ausnahme von <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle> lösen <xref:System.Threading.Tasks.Task?displayProperty=name>-Methoden keine <xref:System.ObjectDisposedException?displayProperty=name>-Ausnahme mehr aus, nachdem das Objekt freigegeben wurde. Durch diese Änderung wird die Verwendung von zwischengespeicherten Tasks unterstützt. Beispielsweise kann eine Methode eine zwischengespeicherte Aufgabe zurückgeben, um einen bereits abgeschlossenen Vorgang darzustellen, anstatt eine neue Aufgabe zuzuordnen. Dies war in früheren .NET Framework-Versionen nicht möglich, da jeder Consumer der Aufgabe diese freigeben konnte und somit unbrauchbar machte.|
|Vorschlag|Denken Sie daran, dass Task-Methoden in Situationen, in denen das Objekt verworfen wird, keine <xref:System.ObjectDisposedException?displayProperty=name> mehr auslösen. Wenn eine App von dieser Ausnahme (zu wissen, dass ein Task verworfen wurde) abhängig war, sollte sie explizit aktualisiert werden, um den Taskstatus mithilfe von <xref:System.Threading.Tasks.Task.Status> zu prüfen.|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
