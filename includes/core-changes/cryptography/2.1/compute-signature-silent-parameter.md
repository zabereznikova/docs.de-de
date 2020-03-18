---
ms.openlocfilehash: 9583d868ee01117d7bd6e465e7d89a734489d1a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449217"
---
### <a name="boolean-parameter-of-signedcmscomputesignature-is-respected"></a><span data-ttu-id="82af9-101">Der boolesche Parameter von SignedCms.ComputeSignature wird beachtet</span><span class="sxs-lookup"><span data-stu-id="82af9-101">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>

<span data-ttu-id="82af9-102">In .NET Core wird der boolesche Parameter `silent` der Methode <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> beachtet.</span><span class="sxs-lookup"><span data-stu-id="82af9-102">In .NET Core, the Boolean `silent` parameter of the <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> method is respected.</span></span> <span data-ttu-id="82af9-103">Eine PIN-Eingabeaufforderung wird nicht angezeigt, wenn dieser Parameter auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="82af9-103">A PIN prompt is not shown if this parameter is set to `true`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="82af9-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="82af9-104">Change description</span></span>

<span data-ttu-id="82af9-105">Im .NET Framework wird der Parameter `silent` der Methode <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> ignoriert. Es wird stets eine PIN-Eingabeaufforderung angezeigt, wenn der Anbieter dies verlangt.</span><span class="sxs-lookup"><span data-stu-id="82af9-105">In .NET Framework, the `silent` parameter of the <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> method is ignored, and a PIN prompt is always shown if required by the provider.</span></span> <span data-ttu-id="82af9-106">In .NET Core wird der Parameter `silent` beachtet. Wenn er auf `true` festgelegt ist, wird keinesfalls eine PIN-Eingabeaufforderung angezeigt, selbst wenn dies vom Anbieter verlangt wird.</span><span class="sxs-lookup"><span data-stu-id="82af9-106">In .NET Core, the `silent` parameter is respected, and if set to `true`, a PIN prompt is never shown, even if it's required by the provider.</span></span>

<span data-ttu-id="82af9-107">Unterstützung für CMS/PKCS #7-Nachrichten wurde in .NET Core 2.1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="82af9-107">Support for CMS/PKCS #7 messages was introduced into .NET Core in version 2.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="82af9-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="82af9-108">Version introduced</span></span>

<span data-ttu-id="82af9-109">2.1</span><span class="sxs-lookup"><span data-stu-id="82af9-109">2.1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="82af9-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="82af9-110">Recommended action</span></span>

<span data-ttu-id="82af9-111">Um sicherzustellen, dass bei Bedarf eine PIN-Eingabeaufforderung angezeigt wird, sollten Desktopanwendungen <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> aufrufen und den booleschen Parameter auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="82af9-111">To ensure a PIN prompt appears if required, desktop applications should call <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> and set the Boolean parameter to `false`.</span></span> <span data-ttu-id="82af9-112">Das resultierende Verhalten ist das gleiche wie bei .NET Framework, und zwar unabhängig davon, ob der Kontext „silent“ dort deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="82af9-112">The resulting behavior is the same as on .NET Framework regardless of whether the silent context is disabled there.</span></span>

### <a name="category"></a><span data-ttu-id="82af9-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="82af9-113">Category</span></span>

<span data-ttu-id="82af9-114">Kryptografie</span><span class="sxs-lookup"><span data-stu-id="82af9-114">Cryptography</span></span>

### <a name="affected-apis"></a><span data-ttu-id="82af9-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="82af9-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)`

-->
