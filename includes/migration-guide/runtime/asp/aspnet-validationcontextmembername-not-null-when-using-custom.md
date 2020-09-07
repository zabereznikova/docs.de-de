---
ms.openlocfilehash: 904a6abee2b4b2cf2f5727fb70e286c8a1a592c4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497385"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a><span data-ttu-id="73661-101">ASP.NET ValidationContext.MemberName ist bei Verwendung des benutzerdefinierten DataAnnotations.ValidationAttribute nicht NULL</span><span class="sxs-lookup"><span data-stu-id="73661-101">ASP.NET ValidationContext.MemberName is not NULL when using custom DataAnnotations.ValidationAttribute</span></span>

#### <a name="details"></a><span data-ttu-id="73661-102">Details</span><span class="sxs-lookup"><span data-stu-id="73661-102">Details</span></span>

<span data-ttu-id="73661-103">Wenn in .NET Framework 4.7.2 und früheren Versionen ein benutzerdefiniertes <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> verwendet wurde, wurde von der <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType>-Eigenschaft `null` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="73661-103">In .NET Framework 4.7.2 and earlier versions, when using a custom <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>, the <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> property returns `null`.</span></span> <span data-ttu-id="73661-104">In der .NET Framework 4.8-Version vor dem Update vom Oktober 2019 wird der Membername zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="73661-104">In .NET Framework 4.8 version prior to the October 2019 update, it returns the member name.</span></span> <span data-ttu-id="73661-105">Ab der [Vorschauversion des Qualitätsrollups für .NET Framework vom Oktober 2019](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) für .NET Framework 4.8 wird standardmäßig `null` zurückgegeben, aber Sie können sich dafür entscheiden, stattdessen den Membernamen zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="73661-105">Starting with [.NET Framework October 2019 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) for .NET Framework 4.8, it returns `null` by default, but you can opt in to return the member name instead.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="73661-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="73661-106">Suggestion</span></span>

<span data-ttu-id="73661-107">Fügen Sie die folgende Einstellung zu Ihrer Datei *web.config* hinzu, damit die Eigenschaft den Membernamen in der [Vorschauversion des Qualitätsrollups für .NET Framework vom Oktober 2019](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) für .NET Framework 4.8 und spätere Versionen zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="73661-107">Add the following setting to your *web.config* file for the property to return the member name in [.NET Framework October 2019 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) for .NET Framework 4.8 and later versions:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="73661-108">In der .NET Framework 4.8-Version vor dem Update vom Oktober 2019 stellt das Hinzufügen dieser Eigenschaft zu Ihrer Datei *web.config* das vorherige Verhalten wieder her, und die Eigenschaft gibt `null` zurück.</span><span class="sxs-lookup"><span data-stu-id="73661-108">In .NET Framework 4.8 version prior to the October 2019 update,  adding this to your *web.config* file restores the previous behavior and the property returns `null`.</span></span>

| <span data-ttu-id="73661-109">name</span><span class="sxs-lookup"><span data-stu-id="73661-109">Name</span></span>    | <span data-ttu-id="73661-110">Wert</span><span class="sxs-lookup"><span data-stu-id="73661-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="73661-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="73661-111">Scope</span></span>   |<span data-ttu-id="73661-112">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="73661-112">Unknown</span></span>|
|<span data-ttu-id="73661-113">Version</span><span class="sxs-lookup"><span data-stu-id="73661-113">Version</span></span>|<span data-ttu-id="73661-114">4.8</span><span class="sxs-lookup"><span data-stu-id="73661-114">4.8</span></span>|
|<span data-ttu-id="73661-115">Typ</span><span class="sxs-lookup"><span data-stu-id="73661-115">Type</span></span>|<span data-ttu-id="73661-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="73661-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="73661-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="73661-117">Affected APIs</span></span>

- <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.ComponentModel.DataAnnotations.ValidationContext.MemberName`

-->
