---
ms.openlocfilehash: 58dbb54d42d89b450134758072e3133ae4e6b13d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497237"
---
### <a name="systemthreadingtaskstask-no-longer-throw-objectdisposedexception-after-object-is-disposed"></a><span data-ttu-id="450fe-101">System.Threading.Tasks.Task löst kein ObjectDisposedException mehr aus, nachdem das Objekt verworfen wurde</span><span class="sxs-lookup"><span data-stu-id="450fe-101">System.Threading.Tasks.Task no longer throw ObjectDisposedException after object is disposed</span></span>

#### <a name="details"></a><span data-ttu-id="450fe-102">Details</span><span class="sxs-lookup"><span data-stu-id="450fe-102">Details</span></span>

<span data-ttu-id="450fe-103">Mit Ausnahme von <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle> lösen <xref:System.Threading.Tasks.Task?displayProperty=fullName>-Methoden keine <xref:System.ObjectDisposedException?displayProperty=fullName>-Ausnahme mehr aus, nachdem das Objekt freigegeben wurde. Durch diese Änderung wird die Verwendung von zwischengespeicherten Tasks unterstützt.</span><span class="sxs-lookup"><span data-stu-id="450fe-103">Except for <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle>, <xref:System.Threading.Tasks.Task?displayProperty=fullName> methods no longer throw an <xref:System.ObjectDisposedException?displayProperty=fullName> exception after the object is disposed.This change supports the use of cached tasks.</span></span> <span data-ttu-id="450fe-104">Beispielsweise kann eine Methode eine zwischengespeicherte Aufgabe zurückgeben, um einen bereits abgeschlossenen Vorgang darzustellen, anstatt eine neue Aufgabe zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="450fe-104">For example, a method can return a cached task to represent an already completed operation instead of allocating a new task.</span></span> <span data-ttu-id="450fe-105">Dies war in früheren .NET Framework-Versionen nicht möglich, da jeder Consumer der Aufgabe diese freigeben konnte und somit unbrauchbar machte.</span><span class="sxs-lookup"><span data-stu-id="450fe-105">This was impossible in previous .NET Framework versions, because any consumer of the task could dispose of it, which rendered it unusable.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="450fe-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="450fe-106">Suggestion</span></span>

<span data-ttu-id="450fe-107">Denken Sie daran, dass Task-Methoden in Situationen, in denen das Objekt verworfen wird, keine <xref:System.ObjectDisposedException?displayProperty=fullName> mehr auslösen.</span><span class="sxs-lookup"><span data-stu-id="450fe-107">Be aware that Task methods may no longer throw <xref:System.ObjectDisposedException?displayProperty=fullName> in cases when the object is disposed.</span></span> <span data-ttu-id="450fe-108">Wenn eine App von dieser Ausnahme (zu wissen, dass ein Task verworfen wurde) abhängig war, sollte sie explizit aktualisiert werden, um den Taskstatus mithilfe von <xref:System.Threading.Tasks.Task.Status> zu prüfen.</span><span class="sxs-lookup"><span data-stu-id="450fe-108">If an app was depending on this exception to know that a task was disposed, it should be updated to explicitly check the task's status using <xref:System.Threading.Tasks.Task.Status>.</span></span>

| <span data-ttu-id="450fe-109">name</span><span class="sxs-lookup"><span data-stu-id="450fe-109">Name</span></span>    | <span data-ttu-id="450fe-110">Wert</span><span class="sxs-lookup"><span data-stu-id="450fe-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="450fe-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="450fe-111">Scope</span></span>   |<span data-ttu-id="450fe-112">Gering</span><span class="sxs-lookup"><span data-stu-id="450fe-112">Minor</span></span>|
|<span data-ttu-id="450fe-113">Version</span><span class="sxs-lookup"><span data-stu-id="450fe-113">Version</span></span>|<span data-ttu-id="450fe-114">4.5</span><span class="sxs-lookup"><span data-stu-id="450fe-114">4.5</span></span>|
|<span data-ttu-id="450fe-115">Typ</span><span class="sxs-lookup"><span data-stu-id="450fe-115">Type</span></span>|<span data-ttu-id="450fe-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="450fe-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="450fe-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="450fe-117">Affected APIs</span></span>

<span data-ttu-id="450fe-118">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="450fe-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
