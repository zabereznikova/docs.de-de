---
ms.openlocfilehash: 58dbb54d42d89b450134758072e3133ae4e6b13d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497237"
---
### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a>System.Threading.Tasks.Task löst kein ObjectDisposedException mehr aus, nachdem das Objekt verworfen wurde

#### <a name="details"></a>Details

Mit Ausnahme von <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle> lösen <xref:System.Threading.Tasks.Task?displayProperty=fullName>-Methoden keine <xref:System.ObjectDisposedException?displayProperty=fullName>-Ausnahme mehr aus, nachdem das Objekt freigegeben wurde. Durch diese Änderung wird die Verwendung von zwischengespeicherten Tasks unterstützt. Beispielsweise kann eine Methode eine zwischengespeicherte Aufgabe zurückgeben, um einen bereits abgeschlossenen Vorgang darzustellen, anstatt eine neue Aufgabe zuzuordnen. Dies war in früheren .NET Framework-Versionen nicht möglich, da jeder Consumer der Aufgabe diese freigeben konnte und somit unbrauchbar machte.

#### <a name="suggestion"></a>Vorschlag

Denken Sie daran, dass Task-Methoden in Situationen, in denen das Objekt verworfen wird, keine <xref:System.ObjectDisposedException?displayProperty=fullName> mehr auslösen. Wenn eine App von dieser Ausnahme (zu wissen, dass ein Task verworfen wurde) abhängig war, sollte sie explizit aktualisiert werden, um den Taskstatus mithilfe von <xref:System.Threading.Tasks.Task.Status> zu prüfen.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
