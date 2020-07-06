---
ms.openlocfilehash: d3e0a61601f60a389b662f6f74934b6e6dc6e663
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614585"
---
### <a name="the-default-hash-algorithm-for-wpf-packagedigitalsignaturemanager-is-now-sha256"></a><span data-ttu-id="f9388-101">SHA256 ist jetzt der Standardhashalgorithmus für WPF-PackageDigitalSignatureManager</span><span class="sxs-lookup"><span data-stu-id="f9388-101">The default hash algorithm for WPF PackageDigitalSignatureManager is now SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="f9388-102">Details</span><span class="sxs-lookup"><span data-stu-id="f9388-102">Details</span></span>

<span data-ttu-id="f9388-103">Der `System.IO.Packaging.PackageDigitalSignatureManager` stellt Funktionen zur digitalen Signatur von WPF-Paketen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f9388-103">The `System.IO.Packaging.PackageDigitalSignatureManager` provides functionality for digital signatures in relation to WPF packages.</span></span>  <span data-ttu-id="f9388-104">In .NET Framework 4.7 und früheren Versionen, war SHA1 der Standardhashalgorithmus (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>), der zum Signieren von Paketbestandteilen verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f9388-104">In the .NET Framework 4.7 and earlier versions, the default algorithm (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>) used for signing parts of a package was SHA1.</span></span>  <span data-ttu-id="f9388-105">Diese Standardeinstellung wurde ab .NET Framework 4.7.1 aufgrund von Sicherheitsbedenken im Zusammenhang mit SHA1 auf SHA256 geändert.</span><span class="sxs-lookup"><span data-stu-id="f9388-105">Due to recent security concerns with SHA1, this default has been changed to SHA256 starting with the .NET Framework 4.7.1.</span></span>  <span data-ttu-id="f9388-106">Diese Änderung betrifft die Signierung aller Pakete, einschließlich XPS-Dokumenten.</span><span class="sxs-lookup"><span data-stu-id="f9388-106">This change affects all package signing, including XPS documents.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f9388-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="f9388-107">Suggestion</span></span>

<span data-ttu-id="f9388-108">Ein Entwickler, der diese Änderung nutzen will, aber seine Anwendung auf eine ältere Version von .NET Framework als Version 4.7.1 auslegt, oder ein Entwickler, der die veraltete Funktion verwenden möchte, seine Anwendung jedoch auf .NET Framework 4.7.1 oder höher auslegt, können das „AppContext“-Flag entsprechend festlegen.</span><span class="sxs-lookup"><span data-stu-id="f9388-108">A developer who wants to utilize this change while targeting a framework version below .NET Framework 4.7.1 or a developer who requires the previous functionality while targeting .NET Framework 4.7.1 or greater can set the following AppContext flag appropriately.</span></span>  <span data-ttu-id="f9388-109">Wenn ein TRUE-Wert zurückgegeben wird, wird SHA1 als Standardalgorithmus verwendet. Bei FALSE-Werten wird SHA256 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f9388-109">A value of true will result in SHA1 being used as the default algorithm; false results in SHA256.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.UseSha1AsDefaultHashAlgorithmForDigitalSignatures=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="f9388-110">Name</span><span class="sxs-lookup"><span data-stu-id="f9388-110">Name</span></span>    | <span data-ttu-id="f9388-111">Wert</span><span class="sxs-lookup"><span data-stu-id="f9388-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f9388-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="f9388-112">Scope</span></span>   | <span data-ttu-id="f9388-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f9388-113">Edge</span></span>        |
| <span data-ttu-id="f9388-114">Version</span><span class="sxs-lookup"><span data-stu-id="f9388-114">Version</span></span> | <span data-ttu-id="f9388-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="f9388-115">4.7.1</span></span>       |
| <span data-ttu-id="f9388-116">Typ</span><span class="sxs-lookup"><span data-stu-id="f9388-116">Type</span></span>    | <span data-ttu-id="f9388-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="f9388-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="f9388-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f9388-118">Affected APIs</span></span>

- <xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>
