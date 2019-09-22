---
ms.openlocfilehash: e16f0c8ede5e1a24d4fc4606c3c25225ea72e750
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117121"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a><span data-ttu-id="d5602-101">Änderung der JsonFactoryConverter.CreateConverter-Signatur</span><span class="sxs-lookup"><span data-stu-id="d5602-101">JsonFactoryConverter.CreateConverter signature changed</span></span>

<span data-ttu-id="d5602-102">Um die Komposition von <xref:System.Text.Json.Serialization.JsonConverterFactory>-Klassen zu unterstützen, wurde die <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A>-Methode veröffentlicht und mit einem zweiten Argument vom Typ <xref:System.Text.Json.JsonSerializerOptions> versehen.</span><span class="sxs-lookup"><span data-stu-id="d5602-102">To facilitate the composition of <xref:System.Text.Json.Serialization.JsonConverterFactory> classes, the <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> method has been made public and given a second argument of type <xref:System.Text.Json.JsonSerializerOptions>.</span></span>

#### <a name="details"></a><span data-ttu-id="d5602-103">Details</span><span class="sxs-lookup"><span data-stu-id="d5602-103">Details</span></span>

<span data-ttu-id="d5602-104">Die Signatur der `CreateConverter`-Methode in .NET Core vor Preview 8 von Version 3.0 lautete wie folgt:</span><span class="sxs-lookup"><span data-stu-id="d5602-104">The signature of the `CreateConverter` method in .NET Core prior to version 3.0 Preview 8 was:</span></span> 

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

<span data-ttu-id="d5602-105">In NET. Core 3.0 Preview 8 und höher lautet sie:</span><span class="sxs-lookup"><span data-stu-id="d5602-105">In .NET Core 3.0 Preview 8 and later versions, it is:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

<span data-ttu-id="d5602-106">Vor dieser Änderung war es schwierig, versiegelte Factory-Konverter zu verfassen, da <xref:System.Text.Json.Serialization.JsonConverter%601> nicht einfach von diesen abgerufen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="d5602-106">Before this change, it was difficult to compose sealed factory converters, since there was no easy way to get the <xref:System.Text.Json.Serialization.JsonConverter%601> from it.</span></span> <span data-ttu-id="d5602-107">Die Veröffentlichung der Factorymethode und die Übergabe der aktuellen <xref:System.Text.Json.JsonSerializerOptions>-Klasse ermöglichen eine viel flexiblere Komposition.</span><span class="sxs-lookup"><span data-stu-id="d5602-107">Making the factory method public and also passing the current <xref:System.Text.Json.JsonSerializerOptions> allow for much more flexible composition.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d5602-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d5602-108">Version introduced</span></span>

<span data-ttu-id="d5602-109">3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="d5602-109">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d5602-110">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="d5602-110">Recommended action</span></span>

<span data-ttu-id="d5602-111">Abgeleitete Klassen müssen aktualisiert und neu kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="d5602-111">Derived classes need to be updated and recompiled.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d5602-112">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d5602-112">Affected APIs</span></span>

<span data-ttu-id="d5602-113"><xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d5602-113"><xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>.</span></span>

<!-- For tool use only

### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
