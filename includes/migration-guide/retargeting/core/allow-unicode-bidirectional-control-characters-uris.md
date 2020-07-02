---
ms.openlocfilehash: 53d74db1a77e62cc64250658281fd3e4706fe494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614426"
---
### <a name="allow-unicode-bidirectional-control-characters-in-uris"></a><span data-ttu-id="a8870-101">Zulassen bidirektionaler Unicode-Steuerzeichen in URIs</span><span class="sxs-lookup"><span data-stu-id="a8870-101">Allow Unicode Bidirectional Control Characters in URIs</span></span>

#### <a name="details"></a><span data-ttu-id="a8870-102">Details</span><span class="sxs-lookup"><span data-stu-id="a8870-102">Details</span></span>

<span data-ttu-id="a8870-103">Unicode gibt mehrere spezielle Steuerzeichen an, um die Ausrichtung von Text anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a8870-103">Unicode specifies several special control characters used to specify the orientation of text.</span></span> <span data-ttu-id="a8870-104">In früheren Versionen von .NET Framework wurden diese Zeichen selbst dann fälschlicherweise aus allen URIs entfernt, wenn sie in ihrer prozentcodierten Form vorlagen.</span><span class="sxs-lookup"><span data-stu-id="a8870-104">In previous versions of the .NET Framework, these characters were incorrectly stripped from all URIs even if they were present in their percent-encoded form.</span></span> <span data-ttu-id="a8870-105">Damit [RFC 3987](https://tools.ietf.org/html/rfc3987) besser berücksichtigt wird, sind diese Zeichen in URIs nun zulässig.</span><span class="sxs-lookup"><span data-stu-id="a8870-105">In order to better follow [RFC 3987](https://tools.ietf.org/html/rfc3987), we now allow these characters in URIs.</span></span> <span data-ttu-id="a8870-106">Wenn sie uncodiert in einem URI gefunden werden, werden sie prozentcodiert.</span><span class="sxs-lookup"><span data-stu-id="a8870-106">When found unencoded in a URI, they are percent-encoded.</span></span> <span data-ttu-id="a8870-107">Wenn sie prozentcodiert gefunden werden, bleiben sie unverändert.</span><span class="sxs-lookup"><span data-stu-id="a8870-107">When found percent-encoded they are left as-is.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a8870-108">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a8870-108">Suggestion</span></span>

<span data-ttu-id="a8870-109">Für Anwendungen mit Zielversionen von .NET Framework ab .NET Framework 4.7.2 ist Unterstützung für bidirektionale Uniccode-Zeichen standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a8870-109">For applications that target versions of .NET Framework starting with 4.7.2, support for Unicode bidirectional characters is enabled by default.</span></span> <span data-ttu-id="a8870-110">Wenn diese Änderung nicht erwünscht ist, können Sie sie deaktivieren, indem Sie den Schalter [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) dem Abschnitt `<runtime>` Ihrer Anwendungskonfigurationsdatei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="a8870-110">If this change is undesirable, you can disable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=true" />
</runtime>
```

<span data-ttu-id="a8870-111">Für Anwendungen mit früheren Zielversionen von .NET Framework, die aber mit Versionen ab .NET Framework 4.7.2 ausgeführt werden, ist Unterstützung für bidirektionale Uniccode-Zeichen standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a8870-111">For applications that target earlier versions of the .NET Framework but are running under versions starting with .NET Framework 4.7.2, support for Unicode bidirectional characters is disabled by default.</span></span> <span data-ttu-id="a8870-112">Sie können sie aktivieren, indem Sie den Schalter [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) dem Abschnitt `<runtime>` Ihrer Anwendungskonfigurationsdatei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="a8870-112">You can enable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the `<runtime>` section of the application configuration file::</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.Uri.DontKeepUnicodeBidiFormattingCharacters=false" />
</runtime>
```

| <span data-ttu-id="a8870-113">name</span><span class="sxs-lookup"><span data-stu-id="a8870-113">Name</span></span>    | <span data-ttu-id="a8870-114">Wert</span><span class="sxs-lookup"><span data-stu-id="a8870-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a8870-115">Bereich</span><span class="sxs-lookup"><span data-stu-id="a8870-115">Scope</span></span>   | <span data-ttu-id="a8870-116">Gering</span><span class="sxs-lookup"><span data-stu-id="a8870-116">Minor</span></span>       |
| <span data-ttu-id="a8870-117">Version</span><span class="sxs-lookup"><span data-stu-id="a8870-117">Version</span></span> | <span data-ttu-id="a8870-118">4.7.2</span><span class="sxs-lookup"><span data-stu-id="a8870-118">4.7.2</span></span>       |
| <span data-ttu-id="a8870-119">Typ</span><span class="sxs-lookup"><span data-stu-id="a8870-119">Type</span></span>    | <span data-ttu-id="a8870-120">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="a8870-120">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="a8870-121">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a8870-121">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>
