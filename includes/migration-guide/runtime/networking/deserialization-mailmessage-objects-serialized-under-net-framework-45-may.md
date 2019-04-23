---
ms.openlocfilehash: a6f93bbdf39a1b525e2daeb12afc3a6392a66e30
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235750"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a><span data-ttu-id="15df5-101">Die Deserialisierung von MailMessage-Objekten, die unter .NET Framework 4.5 serialisiert wurden, kann möglicherweise fehlschlagen</span><span class="sxs-lookup"><span data-stu-id="15df5-101">Deserialization of MailMessage objects serialized under the .NET Framework 4.5 may fail</span></span>

|   |   |
|---|---|
|<span data-ttu-id="15df5-102">Details</span><span class="sxs-lookup"><span data-stu-id="15df5-102">Details</span></span>|<span data-ttu-id="15df5-103">Ab .NET Framework 4.5 können <xref:System.Web.Mail.MailMessage>-Objekte keine Zeichen mehr enthalten, die keine ASCII-Zeichen sind.</span><span class="sxs-lookup"><span data-stu-id="15df5-103">Starting with the .NET Framework 4.5, <xref:System.Web.Mail.MailMessage> objects can include non-ASCII characters.</span></span> <span data-ttu-id="15df5-104">In .NET Framework 4 werden nur ASCII-Zeichen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="15df5-104">In the .NET Framework 4, only ASCII characters are supported.</span></span> <xref:System.Web.Mail.MailMessage> <span data-ttu-id="15df5-105">-Objekte, die Zeichen enthalten, bei denen es sich nicht um ASCII-Zeichen handelt, und unter .NET Framework 4.5 oder höher serialisiert werden, können unter .NET Framework 4 nicht deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="15df5-105">objects that contain non-ASCII characters and that are serialized under the .NET Framework 4.5 or later cannot be deserialized under the .NET Framework 4.</span></span>|
|<span data-ttu-id="15df5-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="15df5-106">Suggestion</span></span>|<span data-ttu-id="15df5-107">Vergewissern Sie sich, dass Ihr Code die Behandlung von Ausnahmen umfasst, wenn Sie ein <xref:System.Web.Mail.MailMessage>-Objekt deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="15df5-107">Ensure that your code provides exception handling when deserializing a <xref:System.Web.Mail.MailMessage> object.</span></span>|
|<span data-ttu-id="15df5-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="15df5-108">Scope</span></span>|<span data-ttu-id="15df5-109">Gering</span><span class="sxs-lookup"><span data-stu-id="15df5-109">Minor</span></span>|
|<span data-ttu-id="15df5-110">Version</span><span class="sxs-lookup"><span data-stu-id="15df5-110">Version</span></span>|<span data-ttu-id="15df5-111">4.5</span><span class="sxs-lookup"><span data-stu-id="15df5-111">4.5</span></span>|
|<span data-ttu-id="15df5-112">Typ</span><span class="sxs-lookup"><span data-stu-id="15df5-112">Type</span></span>|<span data-ttu-id="15df5-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="15df5-113">Runtime</span></span>|
|<span data-ttu-id="15df5-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="15df5-114">Affected APIs</span></span>|<ul><li><xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|
