---
ms.openlocfilehash: 21921156295d89aad04f3197fef9fa322f3c8c87
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614447"
---
### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a><span data-ttu-id="9c2a4-101">Sicherstellen, dass System.Uri einen konsistenten reservierten Zeichensatz verwendet</span><span class="sxs-lookup"><span data-stu-id="9c2a4-101">Ensure System.Uri uses a consistent reserved character set</span></span>

#### <a name="details"></a><span data-ttu-id="9c2a4-102">Details</span><span class="sxs-lookup"><span data-stu-id="9c2a4-102">Details</span></span>

<span data-ttu-id="9c2a4-103">In <xref:System.Uri?displayProperty=fullName> sind bestimmte prozentcodierte Zeichen, die manchmal decodiert wurden, jetzt konsistent linkscodiert.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-103">In <xref:System.Uri?displayProperty=fullName>, certain percent-encoded characters that were sometimes decoded are now consistently left encoded.</span></span> <span data-ttu-id="9c2a4-104">Dies tritt für die Eigenschaften und Methoden auf, die auf die Pfad-, Abfrage-, Fragment- oder Benutzerinformationenkomponenten des URIs zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-104">This occurs across the properties and methods that access the path, query, fragment, or userinfo components of the URI.</span></span> <span data-ttu-id="9c2a4-105">Das Verhalten ändert sich nur, wenn die beiden folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="9c2a4-105">The behavior will change only when both of the following are true:</span></span>

- <span data-ttu-id="9c2a4-106">Der URI enthält die codierte Form eines der folgenden reservierten Zeichen: `:`, `'`, `(`, `)`, `!` oder `*`.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-106">The URI contains the encoded form of any of the following reserved characters: `:`, `'`, `(`, `)`, `!` or `*`.</span></span>
- <span data-ttu-id="9c2a4-107">Der URI enthält ein Unicode- oder nicht codiertes reserviertes Zeichen.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-107">The URI contains a Unicode or encoded non-reserved character.</span></span> <span data-ttu-id="9c2a4-108">Wenn beide oben genannten Kriterien erfüllt sind, werden die codierten reservierten Zeichen linkscodiert.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-108">If both of the above are true, the encoded reserved characters are left encoded.</span></span> <span data-ttu-id="9c2a4-109">In früheren Versionen von .NET Framework wurden sie decodiert.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-109">In previous versions of the .NET Framework, they are decoded.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9c2a4-110">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="9c2a4-110">Suggestion</span></span>

<span data-ttu-id="9c2a4-111">Für Anwendungen mit Zielversionen von .NET Framework ab .NET Framework 4.7.2 ist dieses neue Decodierungsverhalten standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-111">For applications that target versions of .NET Framework starting with 4.7.2, the new decoding behavior is enabled by default.</span></span> <span data-ttu-id="9c2a4-112">Wenn diese Änderung nicht erwünscht ist, können Sie sie deaktivieren, indem Sie den Schalter [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) dem Abschnitt `<runtime>` Ihrer Anwendungskonfigurationsdatei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="9c2a4-112">If this change is undesirable, you can disable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true" />
</runtime>
```

<span data-ttu-id="9c2a4-113">Für Anwendungen mit früheren Zielversionen von .NET Framework, die aber mit Versionen ab .NET Framework 4.7.2 ausgeführt werden, ist das neue Decodierungsverhalten standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="9c2a4-113">For applications that target earlier versions of the .NET Framework but are running under versions starting with .NET Framework 4.7.2, the new decoding behavior is disabled by default.</span></span> <span data-ttu-id="9c2a4-114">Sie können sie aktivieren, indem Sie den Schalter [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) dem Abschnitt `<runtime>` Ihrer Anwendungskonfigurationsdatei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="9c2a4-114">You can enable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false" />
</runtime>
```

| <span data-ttu-id="9c2a4-115">name</span><span class="sxs-lookup"><span data-stu-id="9c2a4-115">Name</span></span>    | <span data-ttu-id="9c2a4-116">Wert</span><span class="sxs-lookup"><span data-stu-id="9c2a4-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9c2a4-117">Bereich</span><span class="sxs-lookup"><span data-stu-id="9c2a4-117">Scope</span></span>   | <span data-ttu-id="9c2a4-118">Gering</span><span class="sxs-lookup"><span data-stu-id="9c2a4-118">Minor</span></span>       |
| <span data-ttu-id="9c2a4-119">Version</span><span class="sxs-lookup"><span data-stu-id="9c2a4-119">Version</span></span> | <span data-ttu-id="9c2a4-120">4.7.2</span><span class="sxs-lookup"><span data-stu-id="9c2a4-120">4.7.2</span></span>       |
| <span data-ttu-id="9c2a4-121">Typ</span><span class="sxs-lookup"><span data-stu-id="9c2a4-121">Type</span></span>    | <span data-ttu-id="9c2a4-122">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="9c2a4-122">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="9c2a4-123">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="9c2a4-123">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
