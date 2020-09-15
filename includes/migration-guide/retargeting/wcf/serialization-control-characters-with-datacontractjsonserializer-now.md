---
ms.openlocfilehash: afdf1e20db7dc564ddfb6028238604f97e00971a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614529"
---
### <a name="serialization-of-control-characters-with-datacontractjsonserializer-is-now-compatible-with-ecmascript-v6-and-v8"></a><span data-ttu-id="797ef-101">Die Serialisierung von Steuerzeichen in DataContractJsonSerializer ist jetzt konform mit ECMAScript V6 und V8</span><span class="sxs-lookup"><span data-stu-id="797ef-101">Serialization of control characters with DataContractJsonSerializer is now compatible with ECMAScript V6 and V8</span></span>

#### <a name="details"></a><span data-ttu-id="797ef-102">Details</span><span class="sxs-lookup"><span data-stu-id="797ef-102">Details</span></span>

<span data-ttu-id="797ef-103">In .NET Framework 4.6.2 und früheren Versionen serialisierte <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> einige besondere Steuerzeichen, wie etwa \b, \f und \t nicht in einer Weise, die mit den Standards ECMAScript V6 und V8 kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="797ef-103">In .NET Framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> did not serialize some special control characters, such as \b, \f, and \t, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span> <span data-ttu-id="797ef-104">Ab .NET Framework 4.7 ist die Serialisierung dieser Steuerzeichen mit ECMAScript V6 und V8 kompatibel.</span><span class="sxs-lookup"><span data-stu-id="797ef-104">Starting with .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="797ef-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="797ef-105">Suggestion</span></span>

<span data-ttu-id="797ef-106">Standardmäßig wird dieses neue Feature nur für Apps aktiviert, die für .NET Framework 4.7 konzipiert sind.</span><span class="sxs-lookup"><span data-stu-id="797ef-106">For apps that target the .NET Framework 4.7, this feature is enabled by default.</span></span> <span data-ttu-id="797ef-107">Wenn dieses Verhalten unerwünscht ist, können Sie sich gegen diese Funktion entscheiden, indem Sie dem Abschnitt `<runtime>` der app.config- oder web.config-Datei die folgende Zeile hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="797ef-107">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```

| <span data-ttu-id="797ef-108">name</span><span class="sxs-lookup"><span data-stu-id="797ef-108">Name</span></span>    | <span data-ttu-id="797ef-109">Wert</span><span class="sxs-lookup"><span data-stu-id="797ef-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="797ef-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="797ef-110">Scope</span></span>   | <span data-ttu-id="797ef-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="797ef-111">Edge</span></span>        |
| <span data-ttu-id="797ef-112">Version</span><span class="sxs-lookup"><span data-stu-id="797ef-112">Version</span></span> | <span data-ttu-id="797ef-113">4.7</span><span class="sxs-lookup"><span data-stu-id="797ef-113">4.7</span></span>         |
| <span data-ttu-id="797ef-114">Typ</span><span class="sxs-lookup"><span data-stu-id="797ef-114">Type</span></span>    | <span data-ttu-id="797ef-115">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="797ef-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="797ef-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="797ef-116">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlDictionaryWriter,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType>
