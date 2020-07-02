---
ms.openlocfilehash: a1db9916c69c5974191eb6108fb54a0d9ff060d2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622038"
---
### <a name="sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a><span data-ttu-id="ed439-101">SqlConnection.Open schlägt unter Windows 7 mit vorhandenem Nicht-IFS-Winsock-BSP oder -LSP fehl</span><span class="sxs-lookup"><span data-stu-id="ed439-101">SqlConnection.Open fails on Windows 7 with non-IFS Winsock BSP or LSP present</span></span>

#### <a name="details"></a><span data-ttu-id="ed439-102">Details</span><span class="sxs-lookup"><span data-stu-id="ed439-102">Details</span></span>

<span data-ttu-id="ed439-103">Auf einem Windows 7-Computer mit einem Nicht-IFS-Winsock-BSP oder -LSP schlagen <xref:System.Data.SqlClient.SqlConnection.Open> und <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)> in .NET Framework 4.5 fehl. Verwenden Sie den Befehl <code>netsh WinSock Show Catalog</code>, und untersuchen Sie alle <code>Winsock Catalog Provider Entry</code>-Elemente, die zurückgegeben werden, um zu erkennen, ob ein Nicht-IFS-Winsock-BSP oder -LSP installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ed439-103"><xref:System.Data.SqlClient.SqlConnection.Open> and <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)> fail in the .NET Framework 4.5 if running on a Windows 7 machine with a non-IFS Winsock BSP or LSP are present on the computer.To determine whether a non-IFS BSP or LSP is installed, use the <code>netsh WinSock Show Catalog</code> command, and examine every <code>Winsock Catalog Provider Entry</code> item that is returned.</span></span> <span data-ttu-id="ed439-104">Wenn für den Servicekennzeichenwert das <code>0x20000</code>-Bit gesetzt ist, verwendet der Anbieter IFS-Handle und funktioniert daher ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="ed439-104">If the Service Flags value has the <code>0x20000</code> bit set, the provider uses IFS handles and will work correctly.</span></span> <span data-ttu-id="ed439-105">Wenn das <code>0x20000</code>-Bit leer (nicht festgelegt) ist, handelt es sich um ein Nicht-IFS-BSP oder -LSP.</span><span class="sxs-lookup"><span data-stu-id="ed439-105">If the <code>0x20000</code> bit is clear (not set), it is a non-IFS BSP or LSP.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ed439-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="ed439-106">Suggestion</span></span>

<span data-ttu-id="ed439-107">Dieses Problem wurde in .NET Framework 4.5.2 behoben, daher kann es durch ein Upgrade von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="ed439-107">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="ed439-108">Alternativ kann es durch Entfernen aller installierten Nicht-IFS-Winsock-LSPs vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="ed439-108">Alternatively, it can be avoided by removing any installed non-IFS Winsock LSPs.</span></span>

| <span data-ttu-id="ed439-109">name</span><span class="sxs-lookup"><span data-stu-id="ed439-109">Name</span></span>    | <span data-ttu-id="ed439-110">Wert</span><span class="sxs-lookup"><span data-stu-id="ed439-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ed439-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="ed439-111">Scope</span></span>   |<span data-ttu-id="ed439-112">Gering</span><span class="sxs-lookup"><span data-stu-id="ed439-112">Minor</span></span>|
|<span data-ttu-id="ed439-113">Version</span><span class="sxs-lookup"><span data-stu-id="ed439-113">Version</span></span>|<span data-ttu-id="ed439-114">4.5</span><span class="sxs-lookup"><span data-stu-id="ed439-114">4.5</span></span>|
|<span data-ttu-id="ed439-115">Typ</span><span class="sxs-lookup"><span data-stu-id="ed439-115">Type</span></span>|<span data-ttu-id="ed439-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ed439-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ed439-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="ed439-117">Affected APIs</span></span>

-<xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)?displayProperty=nameWithType></li></ul>|
