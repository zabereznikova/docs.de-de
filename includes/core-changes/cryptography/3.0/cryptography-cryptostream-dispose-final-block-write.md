---
ms.openlocfilehash: 7766a59131fffe2b436c15a5ff58e67001be7941
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065101"
---
### <a name="cryptostreamdispose-transforms-final-block-only-when-writing"></a><span data-ttu-id="9ee85-101">CryptoStream.Dispose transformiert den abschließenden Block nur beim Schreiben</span><span class="sxs-lookup"><span data-stu-id="9ee85-101">CryptoStream.Dispose transforms final block only when writing</span></span>

<span data-ttu-id="9ee85-102">Die Methode <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType>, die verwendet wird, um `CryptoStream`-Vorgänge abzuschließen, versucht nicht mehr, den abschließenden Block beim Lesen zu transformieren.</span><span class="sxs-lookup"><span data-stu-id="9ee85-102">The <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=nameWithType> method, which is used to finish `CryptoStream` operations, no longer attempts to transform the final block when reading.</span></span>

#### <a name="change-description"></a><span data-ttu-id="9ee85-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="9ee85-103">Change description</span></span>

<span data-ttu-id="9ee85-104">In früheren Versionen von .NET konnte die Methode <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> eine Ausnahme auslösen, wenn ein Benutzer bei der Verwendung von <xref:System.Security.Cryptography.CryptoStream> im <xref:System.Security.Cryptography.CryptoStreamMode.Read>-Modus einen unvollständigen Lesevorgang durchführte (z. B. bei Verwendung von AES mit Auffüllung).</span><span class="sxs-lookup"><span data-stu-id="9ee85-104">In previous .NET versions, if a user performed an incomplete read when using <xref:System.Security.Cryptography.CryptoStream> in <xref:System.Security.Cryptography.CryptoStreamMode.Read> mode, the <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> method could throw an exception (for example, when using AES with padding).</span></span> <span data-ttu-id="9ee85-105">Die Ausnahme wurde ausgelöst, da versucht wurde, den abschließenden Block zu transformieren, die Daten aber unvollständig waren.</span><span class="sxs-lookup"><span data-stu-id="9ee85-105">The exception was thrown because the final block was attempted to be transformed but the data was incomplete.</span></span>

<span data-ttu-id="9ee85-106">Ab .NET Core 3.0 versucht <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> nicht mehr, den abschließenden Block beim Lesen zu transformieren, was unvollständige Lesevorgänge ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="9ee85-106">In .NET Core 3.0 and later versions, <xref:System.Security.Cryptography.CryptoStream.Dispose%2A> no longer tries to transform the final block when reading, which allows for incomplete reads.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9ee85-107">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="9ee85-107">Reason for change</span></span>

<span data-ttu-id="9ee85-108">Diese Änderung ermöglicht unvollständige Lesevorgänge aus CryptoStream, wenn ein Netzwerkvorgang abgebrochen wird, ohne dass eine Ausnahme abgefangen werden muss.</span><span class="sxs-lookup"><span data-stu-id="9ee85-108">This change enables incomplete reads from the crypto stream when a network operation is cancelled, without the need to catch an exception.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9ee85-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="9ee85-109">Version introduced</span></span>

<span data-ttu-id="9ee85-110">3.0</span><span class="sxs-lookup"><span data-stu-id="9ee85-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9ee85-111">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="9ee85-111">Recommended action</span></span>

<span data-ttu-id="9ee85-112">Die meisten Apps sollten von dieser Änderung nicht betroffen sein.</span><span class="sxs-lookup"><span data-stu-id="9ee85-112">Most apps should not be affected by this change.</span></span>

<span data-ttu-id="9ee85-113">Wenn Ihre Anwendung bisher bei unvollständigen Lesevorgängen eine Ausnahme abgefangen hat, können Sie diesen `catch`-Block löschen.</span><span class="sxs-lookup"><span data-stu-id="9ee85-113">If your application previously caught an exception in case of an incomplete read, you can delete that `catch` block.</span></span>
<span data-ttu-id="9ee85-114">Wenn Ihre App das Transformieren des abschließenden Blocks in Hashingszenarios verwendet hat, müssen Sie möglicherweise sicherstellen, dass der gesamte Datenstrom gelesen wird, bevor er verworfen wird.</span><span class="sxs-lookup"><span data-stu-id="9ee85-114">If your app used transforming of the final block in hashing scenarios, you might need to ensure that the entire stream is read before it's disposed.</span></span>

#### <a name="category"></a><span data-ttu-id="9ee85-115">Kategorie</span><span class="sxs-lookup"><span data-stu-id="9ee85-115">Category</span></span>

<span data-ttu-id="9ee85-116">Kryptografie</span><span class="sxs-lookup"><span data-stu-id="9ee85-116">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9ee85-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="9ee85-117">Affected APIs</span></span>

- <xref:System.Security.Cryptography.CryptoStream.Dispose%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.CryptoStream.Dispose`

-->
