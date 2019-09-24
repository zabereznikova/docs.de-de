---
ms.openlocfilehash: 98893470b64de4abf7f04817871e3053bf25b86d
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119101"
---
### <a name="jsonelement-api-changes"></a><span data-ttu-id="a2941-101">Änderungen der JsonElement-API</span><span class="sxs-lookup"><span data-stu-id="a2941-101">JsonElement API changes</span></span>

<span data-ttu-id="a2941-102">Ab . NET Core 3.0 Vorschau 7 wurden einige <xref:System.Text.Json.JsonElement>-APIs geändert, um einfachere Ermittlung und bessere Benutzerfreundlichkeit zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a2941-102">Starting with .NET Core 3.0 Preview 7, some <xref:System.Text.Json.JsonElement> APIs have changed to allow for easier discovery and greater usability.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a2941-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a2941-103">Change description</span></span>

<span data-ttu-id="a2941-104">In . NET Core 3.0 Vorschau 7 wurden <xref:System.Text.Json.JsonElement>-APIs wie folgt geändert, um einfachere Ermittlung und bessere Benutzerfreundlichkeit zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a2941-104">In .NET Core 3.0 Preview 7, <xref:System.Text.Json.JsonElement> APIs have changed as follows to allow for easier discovery and greater usability.</span></span>

1. <span data-ttu-id="a2941-105">Alle `WriteProperty`-Methodenüberladungen wurden aus <xref:System.Text.Json.JsonElement>entfernt.</span><span class="sxs-lookup"><span data-stu-id="a2941-105">All `WriteProperty` method overloads were removed from <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="a2941-106">Dies wirkt sich auf Code wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="a2941-106">This affects code such as the following:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
      JsonElement root = doc.RootElement;
      root.WriteProperty(propertyNameString, writer);
      // ..
      root.WriteProperty(propertyNameSpan, writer);
      // ..
      root.WriteProperty(propertyNameJsonEncoded, writer);
      // ..
      root.WriteProperty(utf8PropertyName, writer);
      //..
   }
   ```

1. <span data-ttu-id="a2941-107">`WriteValue` wurde in <xref:System.Text.Json.JsonElement.WriteTo%2A> umbenannt.</span><span class="sxs-lookup"><span data-stu-id="a2941-107">`WriteValue` was renamed as <xref:System.Text.Json.JsonElement.WriteTo%2A>.</span></span> <span data-ttu-id="a2941-108">Dies wirkt sich auf Code wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="a2941-108">This affects code such as the following:</span></span>

```csharp
using (JsonDocument doc = JsonDocument.Parse(jsonString))
{
    JsonElement root = doc.RootElement;
    root.WriteValue(writer);
}

```

1. <span data-ttu-id="a2941-109"><xref:System.Text.Json.JsonElement.WriteTo%2A> löst nun eine <xref:System.ArgumentNullException> aus, wenn der Methodenparameter `null` ist.</span><span class="sxs-lookup"><span data-stu-id="a2941-109"><xref:System.Text.Json.JsonElement.WriteTo%2A> now throws an <xref:System.ArgumentNullException> when its method parameter is `null`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a2941-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a2941-110">Version introduced</span></span>

<span data-ttu-id="a2941-111">3.0 Vorschau 7</span><span class="sxs-lookup"><span data-stu-id="a2941-111">3.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a2941-112">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="a2941-112">Recommended action</span></span>

<span data-ttu-id="a2941-113">Wenn Ihr Code von diesen Änderungen betroffen ist, können Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="a2941-113">If your code is affected by these changes, you can do the following:</span></span>

- <span data-ttu-id="a2941-114">Es gibt keine Ersatz-API für die `WriteProperty`-Überladungen in <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="a2941-114">There is no replacement API for the `WriteProperty` overloads in <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="a2941-115">Stattdessen können Sie eine der <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType>-Überladungen zusammen mit der <xref:System.Text.Json.JsonElement.WriteTo%2A>-Methode aufzurufen, um das gleiche Ergebnis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a2941-115">Instead, you can call one of the <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> overloads along with the <xref:System.Text.Json.JsonElement.WriteTo%2A> method to achive the same result.</span></span> <span data-ttu-id="a2941-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a2941-116">For example:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="a2941-117">Benennen Sie die `WriteValue`-Methode in <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)> um.</span><span class="sxs-lookup"><span data-stu-id="a2941-117">Rename the `WriteValue` method to <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>.</span></span> <span data-ttu-id="a2941-118">Der Methodenparameter bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="a2941-118">The method parameter remains unchanged.</span></span> <span data-ttu-id="a2941-119">Der vorherige Code sollte z.B. wie folgt geändert werden:</span><span class="sxs-lookup"><span data-stu-id="a2941-119">For example, the previous code should be changed to the following:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="a2941-120">Verarbeiten Sie die <xref:System.ArgumentNullException> in Aufrufen der <xref:System.Text.Json.JsonElement.WriteTo%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="a2941-120">Handle the <xref:System.ArgumentNullException> in calls to the <xref:System.Text.Json.JsonElement.WriteTo%2A> method.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a2941-121">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a2941-121">Affected APIs</span></span>

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
