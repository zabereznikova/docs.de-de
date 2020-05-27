---
ms.openlocfilehash: b861dbaa02c97a03c015fdf4e63d25c40c90ea0a
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721675"
---
### <a name="boolean-parameter-of-signedcmscomputesignature-is-respected"></a><span data-ttu-id="23829-101">Der boolesche Parameter von SignedCms.ComputeSignature wird beachtet</span><span class="sxs-lookup"><span data-stu-id="23829-101">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>

<span data-ttu-id="23829-102">In .NET Core wird der boolesche Parameter `silent` der Methode <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> beachtet.</span><span class="sxs-lookup"><span data-stu-id="23829-102">In .NET Core, the Boolean `silent` parameter of the <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> method is respected.</span></span> <span data-ttu-id="23829-103">Eine PIN-Eingabeaufforderung wird nicht angezeigt, wenn dieser Parameter auf `true` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="23829-103">A PIN prompt is not shown if this parameter is set to `true`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="23829-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="23829-104">Change description</span></span>

<span data-ttu-id="23829-105">Im .NET Framework wird der Parameter `silent` der Methode <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> ignoriert. Es wird stets eine PIN-Eingabeaufforderung angezeigt, wenn der Anbieter dies verlangt.</span><span class="sxs-lookup"><span data-stu-id="23829-105">In .NET Framework, the `silent` parameter of the <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> method is ignored, and a PIN prompt is always shown if required by the provider.</span></span> <span data-ttu-id="23829-106">In .NET Core wird der Parameter `silent` beachtet. Wenn er auf `true` festgelegt ist, wird keinesfalls eine PIN-Eingabeaufforderung angezeigt, selbst wenn dies vom Anbieter verlangt wird.</span><span class="sxs-lookup"><span data-stu-id="23829-106">In .NET Core, the `silent` parameter is respected, and if set to `true`, a PIN prompt is never shown, even if it's required by the provider.</span></span>

<span data-ttu-id="23829-107">Unterstützung für CMS/PKCS #7-Nachrichten wurde in .NET Core 2.1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="23829-107">Support for CMS/PKCS #7 messages was introduced into .NET Core in version 2.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="23829-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="23829-108">Version introduced</span></span>

<span data-ttu-id="23829-109">2.1</span><span class="sxs-lookup"><span data-stu-id="23829-109">2.1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="23829-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="23829-110">Recommended action</span></span>

<span data-ttu-id="23829-111">Um sicherzustellen, dass bei Bedarf eine PIN-Eingabeaufforderung angezeigt wird, sollten Desktopanwendungen <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> aufrufen und den booleschen Parameter auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="23829-111">To ensure a PIN prompt appears if required, desktop applications should call <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> and set the Boolean parameter to `false`.</span></span> <span data-ttu-id="23829-112">Das resultierende Verhalten ist das gleiche wie bei .NET Framework, und zwar unabhängig davon, ob der Kontext „silent“ dort deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="23829-112">The resulting behavior is the same as on .NET Framework regardless of whether the silent context is disabled there.</span></span>

#### <a name="category"></a><span data-ttu-id="23829-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="23829-113">Category</span></span>

<span data-ttu-id="23829-114">Kryptografie</span><span class="sxs-lookup"><span data-stu-id="23829-114">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="23829-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="23829-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)`

-->
