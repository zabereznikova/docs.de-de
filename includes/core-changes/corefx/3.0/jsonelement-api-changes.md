---
ms.openlocfilehash: 79901d0b57816915ca7ea73cfe7fa3d40820434e
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568144"
---
### <a name="jsonelement-api-changes"></a><span data-ttu-id="11b5e-101">Änderungen der JsonElement-API</span><span class="sxs-lookup"><span data-stu-id="11b5e-101">JsonElement API changes</span></span>

<span data-ttu-id="11b5e-102">Ab . NET Core 3.0 Vorschau 7 wurden einige <xref:System.Text.Json.JsonElement>-APIs geändert, um einfachere Ermittlung und bessere Benutzerfreundlichkeit zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="11b5e-102">Starting with .NET Core 3.0 Preview 7, some <xref:System.Text.Json.JsonElement> APIs have changed to allow for easier discovery and greater usability.</span></span>

#### <a name="change-description"></a><span data-ttu-id="11b5e-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="11b5e-103">Change description</span></span>

<span data-ttu-id="11b5e-104">In . NET Core 3.0 Vorschau 7 wurden <xref:System.Text.Json.JsonElement>-APIs wie folgt geändert, um einfachere Ermittlung und bessere Benutzerfreundlichkeit zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="11b5e-104">In .NET Core 3.0 Preview 7, <xref:System.Text.Json.JsonElement> APIs have changed as follows to allow for easier discovery and greater usability.</span></span>

1. <span data-ttu-id="11b5e-105">Alle `WriteProperty`-Methodenüberladungen wurden aus <xref:System.Text.Json.JsonElement>entfernt.</span><span class="sxs-lookup"><span data-stu-id="11b5e-105">All `WriteProperty` method overloads were removed from <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="11b5e-106">Dies wirkt sich auf Code wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="11b5e-106">This affects code such as the following:</span></span>

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

1. <span data-ttu-id="11b5e-107">`WriteValue` wurde in <xref:System.Text.Json.JsonElement.WriteTo%2A> umbenannt.</span><span class="sxs-lookup"><span data-stu-id="11b5e-107">`WriteValue` was renamed as <xref:System.Text.Json.JsonElement.WriteTo%2A>.</span></span> <span data-ttu-id="11b5e-108">Dies wirkt sich auf Code wie den folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="11b5e-108">This affects code such as the following:</span></span>

   ```csharp
    using (JsonDocument doc = JsonDocument.Parse(jsonString))
    {
        JsonElement root = doc.RootElement;
        root.WriteValue(writer);
    }
    ```

1. <span data-ttu-id="11b5e-109"><xref:System.Text.Json.JsonElement.WriteTo%2A> löst nun eine <xref:System.ArgumentNullException> aus, wenn der Methodenparameter `null` ist.</span><span class="sxs-lookup"><span data-stu-id="11b5e-109"><xref:System.Text.Json.JsonElement.WriteTo%2A> now throws an <xref:System.ArgumentNullException> when its method parameter is `null`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="11b5e-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="11b5e-110">Version introduced</span></span>

<span data-ttu-id="11b5e-111">3.0 Vorschau 7</span><span class="sxs-lookup"><span data-stu-id="11b5e-111">3.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="11b5e-112">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="11b5e-112">Recommended action</span></span>

<span data-ttu-id="11b5e-113">Wenn Ihr Code von diesen Änderungen betroffen ist, können Sie wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="11b5e-113">If your code is affected by these changes, you can do the following:</span></span>

- <span data-ttu-id="11b5e-114">Es gibt keine Ersatz-API für die `WriteProperty`-Überladungen in <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="11b5e-114">There is no replacement API for the `WriteProperty` overloads in <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="11b5e-115">Stattdessen können Sie eine der <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType>-Überladungen zusammen mit der <xref:System.Text.Json.JsonElement.WriteTo%2A>-Methode aufrufen, um das gleiche Ergebnis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="11b5e-115">Instead, you can call one of the <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> overloads along with the <xref:System.Text.Json.JsonElement.WriteTo%2A> method to achieve the same result.</span></span> <span data-ttu-id="11b5e-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="11b5e-116">For example:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="11b5e-117">Benennen Sie die `WriteValue`-Methode in <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)> um.</span><span class="sxs-lookup"><span data-stu-id="11b5e-117">Rename the `WriteValue` method to <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>.</span></span> <span data-ttu-id="11b5e-118">Der Methodenparameter bleibt unverändert.</span><span class="sxs-lookup"><span data-stu-id="11b5e-118">The method parameter remains unchanged.</span></span> <span data-ttu-id="11b5e-119">Der vorherige Code sollte z.B. wie folgt geändert werden:</span><span class="sxs-lookup"><span data-stu-id="11b5e-119">For example, the previous code should be changed to the following:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="11b5e-120">Verarbeiten Sie die <xref:System.ArgumentNullException> in Aufrufen der <xref:System.Text.Json.JsonElement.WriteTo%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="11b5e-120">Handle the <xref:System.ArgumentNullException> in calls to the <xref:System.Text.Json.JsonElement.WriteTo%2A> method.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="11b5e-121">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="11b5e-121">Affected APIs</span></span>

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
