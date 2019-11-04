---
ms.openlocfilehash: ff156afb3da4b921517fd841c5de2295265a8d7b
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198434"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a><span data-ttu-id="b754d-101">Standardwert von HttpRequestMessage.Version wurde in 1.1 geändert</span><span class="sxs-lookup"><span data-stu-id="b754d-101">Default value of HttpRequestMessage.Version changed to 1.1</span></span>

<span data-ttu-id="b754d-102">Der Standardwert der Eigenschaft <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> wurde aus 2.0 in 1.1 geändert.</span><span class="sxs-lookup"><span data-stu-id="b754d-102">The default value of the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property has changed from 2.0 to 1.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b754d-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="b754d-103">Version introduced</span></span>

<span data-ttu-id="b754d-104">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b754d-104">.NET Core 3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="b754d-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="b754d-105">Change description</span></span>

<span data-ttu-id="b754d-106">In .NET Core 1.0 bis 2.0 ist der Standardwert der Eigenschaft <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> 1.1.</span><span class="sxs-lookup"><span data-stu-id="b754d-106">In .NET Core 1.0 through 2.0, the default value of the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property is 1.1.</span></span> <span data-ttu-id="b754d-107">Ab .NET Core 2.1 wurde er in 2.1 geändert.</span><span class="sxs-lookup"><span data-stu-id="b754d-107">Starting with .NET Core 2.1, it was changed to 2.1.</span></span>

<span data-ttu-id="b754d-108">Ab .NET Core 3.0 ist die Standardversionsnummer, die von der <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>-Eigenschaft zurückgegeben wird, erneut 1.1.</span><span class="sxs-lookup"><span data-stu-id="b754d-108">Starting with .NET Core 3.0, the default version number returned by the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property is once again 1.1.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b754d-109">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="b754d-109">Recommended action</span></span>

<span data-ttu-id="b754d-110">Aktualisieren Sie Ihren Code, wenn die <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>-Eigenschaft einen Standardwert von 2.0 zurückgeben muss.</span><span class="sxs-lookup"><span data-stu-id="b754d-110">Update your code if it depends on the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property returning a default value of 2.0.</span></span>

#### <a name="category"></a><span data-ttu-id="b754d-111">Kategorie</span><span class="sxs-lookup"><span data-stu-id="b754d-111">Category</span></span>

<span data-ttu-id="b754d-112">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="b754d-112">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b754d-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b754d-113">Affected APIs</span></span>

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--
a def
### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-- >

