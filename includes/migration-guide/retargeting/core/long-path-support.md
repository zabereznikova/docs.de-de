---
ms.openlocfilehash: 67e3ff5000ebd38064ed8a57e4fe561afa31f8d8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614479"
---
### <a name="long-path-support"></a><span data-ttu-id="32fb7-101">Unterstützung für lange Pfade</span><span class="sxs-lookup"><span data-stu-id="32fb7-101">Long path support</span></span>

#### <a name="details"></a><span data-ttu-id="32fb7-102">Details</span><span class="sxs-lookup"><span data-stu-id="32fb7-102">Details</span></span>

<span data-ttu-id="32fb7-103">Für Apps mit der Zielplattform .NET Framework 4.6.2 und höher werden lange Pfade (bis zu 32.000 Zeichen) unterstützt, und die Beschränkung auf 260 Zeichen (oder `MAX_PATH`) für die Pfadlänge wurde aufgehoben. Bei Apps, die neu kompiliert werden, um .NET Framework 4.6.2 als Zielplattform zu verwenden, lösen Codepfade, die zuvor aufgrund der Überschreitung der Pfadlänge von 260 Zeichen <xref:System.IO.PathTooLongException?displayProperty=fullName> ausgelöst haben, nun unter den folgenden Bedingungen <xref:System.IO.PathTooLongException?displayProperty=fullName> aus:</span><span class="sxs-lookup"><span data-stu-id="32fb7-103">Starting with apps that target the .NET Framework 4.6.2, long paths (of up to 32K characters) are supported, and the 260-character (or `MAX_PATH`) limitation on path lengths has been removed.For apps that are recompiled to target the .NET Framework 4.6.2, code paths that previously threw a <xref:System.IO.PathTooLongException?displayProperty=fullName> because a path exceeded 260 characters will now throw a <xref:System.IO.PathTooLongException?displayProperty=fullName> only under the following conditions:</span></span>

- <span data-ttu-id="32fb7-104">Die Zahl der Pfadzeichen überschreitet <xref:System.Int16.MaxValue> (32.767).</span><span class="sxs-lookup"><span data-stu-id="32fb7-104">The length of the path is greater than <xref:System.Int16.MaxValue> (32,767) characters.</span></span>
- <span data-ttu-id="32fb7-105">Das Betriebssystem gibt `COR_E_PATHTOOLONG` oder einen dazu äquivalenten Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="32fb7-105">The operating system returns `COR_E_PATHTOOLONG` or its equivalent.</span></span>
<span data-ttu-id="32fb7-106">Bei Apps mit der Zielplattform .NET Framework 4.6.1 und früheren Versionen löst die Laufzeit automatisch eine <xref:System.IO.PathTooLongException?displayProperty=fullName> aus, wenn ein Pfad die Länge von 260 Zeichen überschreitet.</span><span class="sxs-lookup"><span data-stu-id="32fb7-106">For apps that target the .NET Framework 4.6.1 and earlier versions, the runtime automatically throws a <xref:System.IO.PathTooLongException?displayProperty=fullName> whenever a path exceeds 260 characters.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="32fb7-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="32fb7-107">Suggestion</span></span>

<span data-ttu-id="32fb7-108">Für Apps mit der Zielplattform .NET Framework 4.6.2 können Sie sich gegen die Unterstützung von langen Pfaden entscheiden, wenn sie nicht erwünscht ist, indem Sie Folgendes dem Abschnitt `<runtime>` Ihrer `app.config`-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="32fb7-108">For apps that target the .NET Framework 4.6.2, you can opt out of long path support if it is not desirable by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />
</runtime>
```

<span data-ttu-id="32fb7-109">Sie können bei Anwendungen, die für frühere Versionen von .NET Framework vorgesehen sind, aber in .NET Framework 4.6.2 oder höher ausgeführt werden, lange Pfade unterstützen, indem Sie dem Abschnitt `<runtime>` der `app.config`-Datei Folgendes hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="32fb7-109">For apps that target earlier versions of the .NET Framework but run on the .NET Framework 4.6.2 or later, you can opt in to long path support by adding the following to the `<runtime>` section of your `app.config` file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />
</runtime>
```

| <span data-ttu-id="32fb7-110">Name</span><span class="sxs-lookup"><span data-stu-id="32fb7-110">Name</span></span>    | <span data-ttu-id="32fb7-111">Wert</span><span class="sxs-lookup"><span data-stu-id="32fb7-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="32fb7-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="32fb7-112">Scope</span></span>   | <span data-ttu-id="32fb7-113">Gering</span><span class="sxs-lookup"><span data-stu-id="32fb7-113">Minor</span></span>       |
| <span data-ttu-id="32fb7-114">Version</span><span class="sxs-lookup"><span data-stu-id="32fb7-114">Version</span></span> | <span data-ttu-id="32fb7-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="32fb7-115">4.6.2</span></span>       |
| <span data-ttu-id="32fb7-116">Typ</span><span class="sxs-lookup"><span data-stu-id="32fb7-116">Type</span></span>    | <span data-ttu-id="32fb7-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="32fb7-117">Retargeting</span></span> |
