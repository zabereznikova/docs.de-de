---
ms.openlocfilehash: 87dc93ece10eaedbfbabddb5f857d0bcd12e05c4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615693"
---
### <a name="only-tls-10-11-and-12-protocols-supported-in-systemnetservicepointmanager-and-systemnetsecuritysslstream"></a><span data-ttu-id="d420e-101">Nur die Protokolle TLS 1.0, 1.1 und 1.2 werden in System.Net.ServicePointManager und System.Net.Security.SslStream unterstützt</span><span class="sxs-lookup"><span data-stu-id="d420e-101">Only Tls 1.0, 1.1 and 1.2 protocols supported in System.Net.ServicePointManager and System.Net.Security.SslStream</span></span>

#### <a name="details"></a><span data-ttu-id="d420e-102">Details</span><span class="sxs-lookup"><span data-stu-id="d420e-102">Details</span></span>

<span data-ttu-id="d420e-103">Ab .NET Framework 4.6 dürfen die Klassen <xref:System.Net.ServicePointManager> und <xref:System.Net.Security.SslStream> nur eines der folgenden drei Protokolle verwenden: TLS 1.0, TLS 1.1 oder TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="d420e-103">Starting with the .NET Framework 4.6, the <xref:System.Net.ServicePointManager> and <xref:System.Net.Security.SslStream> classes are only allowed to use one of the following three protocols: Tls1.0, Tls1.1, or Tls1.2.</span></span> <span data-ttu-id="d420e-104">Weder das SSL3.0-Protokoll noch das RC4-Verschlüsselungsverfahren werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d420e-104">The SSL3.0 protocol and RC4 cipher are not supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d420e-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="d420e-105">Suggestion</span></span>

<span data-ttu-id="d420e-106">Die empfohlene Risikominderung besteht darin, für die serverseitige App ein Upgrade auf TLS 1.0, TLS 1.1 oder TLS 1.2 vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="d420e-106">The recommended mitigation is to upgrade the sever-side app to Tls1.0, Tls1.1, or Tls1.2.</span></span> <span data-ttu-id="d420e-107">Wenn dies nicht möglich ist oder die Client-Apps fehlerhaft sind, kann die Klasse <xref:System.AppContext?displayProperty=fullName> verwendet werden, um das Feature auf zwei verschiedene Art und Weisen abzuwählen:</span><span class="sxs-lookup"><span data-stu-id="d420e-107">If this is not feasible, or if client apps are broken, the <xref:System.AppContext?displayProperty=fullName> class can be used to opt out of this feature in either of two ways:</span></span>

- <span data-ttu-id="d420e-108">durch programmgesteuertes Festlegen von Kompatibilitätsoptionen für <xref:System.AppContext?displayProperty=fullName>, wie [hier](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46) beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="d420e-108">By programmatically setting compat switches on the <xref:System.AppContext?displayProperty=fullName>, as explained [here](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</span></span>
- <span data-ttu-id="d420e-109">Durch Hinzufügen der folgenden Zeile zum Abschnitt `<runtime>` der app.config-Datei:</span><span class="sxs-lookup"><span data-stu-id="d420e-109">By adding the following line to the `<runtime>` section of the app.config file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>
```

| <span data-ttu-id="d420e-110">name</span><span class="sxs-lookup"><span data-stu-id="d420e-110">Name</span></span>    | <span data-ttu-id="d420e-111">Wert</span><span class="sxs-lookup"><span data-stu-id="d420e-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d420e-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="d420e-112">Scope</span></span>   | <span data-ttu-id="d420e-113">Gering</span><span class="sxs-lookup"><span data-stu-id="d420e-113">Minor</span></span>       |
| <span data-ttu-id="d420e-114">Version</span><span class="sxs-lookup"><span data-stu-id="d420e-114">Version</span></span> | <span data-ttu-id="d420e-115">4.6</span><span class="sxs-lookup"><span data-stu-id="d420e-115">4.6</span></span>         |
| <span data-ttu-id="d420e-116">Typ</span><span class="sxs-lookup"><span data-stu-id="d420e-116">Type</span></span>    | <span data-ttu-id="d420e-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="d420e-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d420e-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d420e-118">Affected APIs</span></span>

- <xref:System.Net.SecurityProtocolType.Ssl3?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl2?displayProperty=nameWithType>
- <xref:System.Security.Authentication.SslProtocols.Ssl3?displayProperty=nameWithType>
