---
ms.openlocfilehash: 9a747d8fc15ca8fa2b915f89291f118d7344d172
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325234"
---
### <a name="httpsys-client-certificate-renegotiation-disabled-by-default"></a><span data-ttu-id="64a55-101">HttpSys: Neuverhandlung von Clientzertifikaten standardmäßig deaktiviert</span><span class="sxs-lookup"><span data-stu-id="64a55-101">HttpSys: Client certificate renegotiation disabled by default</span></span>

<span data-ttu-id="64a55-102">Die Option zum Neuverhandeln einer Verbindung und Anfordern eines Clientzertifikats wurde standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="64a55-102">The option to renegotiate a connection and request a client certificate has been disabled by default.</span></span> <span data-ttu-id="64a55-103">Weitere Informationen finden Sie im Issue [dotnet/aspnetcore#23181](https://github.com/dotnet/aspnetcore/issues/23181).</span><span class="sxs-lookup"><span data-stu-id="64a55-103">For discussion, see issue [dotnet/aspnetcore#23181](https://github.com/dotnet/aspnetcore/issues/23181).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="64a55-104">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="64a55-104">Version introduced</span></span>

<span data-ttu-id="64a55-105">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="64a55-105">ASP.NET Core 5.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="64a55-106">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="64a55-106">Old behavior</span></span>

<span data-ttu-id="64a55-107">Die Verbindung kann neu verhandelt werden, um ein Clientzertifikat anzufordern.</span><span class="sxs-lookup"><span data-stu-id="64a55-107">The connection can be renegotiated to request a client certificate.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="64a55-108">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="64a55-108">New behavior</span></span>

<span data-ttu-id="64a55-109">Clientzertifikate können nur während des ersten Verbindungshandshakes angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="64a55-109">Client certificates can only be requested during the initial connection handshake.</span></span> <span data-ttu-id="64a55-110">Weitere Informationen finden Sie im Pull Request [dotnet/aspnetcore#23162](https://github.com/dotnet/aspnetcore/pull/23162).</span><span class="sxs-lookup"><span data-stu-id="64a55-110">For more information, see pull request [dotnet/aspnetcore#23162](https://github.com/dotnet/aspnetcore/pull/23162).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="64a55-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="64a55-111">Reason for change</span></span>

<span data-ttu-id="64a55-112">Die Neuverhandlung hat eine Reihe von Leistungs- und Deadlockproblemen verursacht.</span><span class="sxs-lookup"><span data-stu-id="64a55-112">Renegotiation caused a number of performance and deadlock issues.</span></span> <span data-ttu-id="64a55-113">Sie wird auch in HTTP/2 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="64a55-113">It's also not supported in HTTP/2.</span></span> <span data-ttu-id="64a55-114">Weitere Kontextinformationen vom Zeitpunkt der Einführung der Option zur Steuerung dieses Verhaltens in ASP.NET Core 3.1 finden Sie im Issue [dotnet/aspnetcore#14806](https://github.com/dotnet/aspnetcore/issues/14806).</span><span class="sxs-lookup"><span data-stu-id="64a55-114">For additional context from when the option to control this behavior was introduced in ASP.NET Core 3.1, see issue [dotnet/aspnetcore#14806](https://github.com/dotnet/aspnetcore/issues/14806).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="64a55-115">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="64a55-115">Recommended action</span></span>

<span data-ttu-id="64a55-116">Apps, für die Clientzertifikate erforderlich sind, sollten *netsh.exe* verwenden, um die Option `clientcertnegotiation` auf `enabled` festzulegen.</span><span class="sxs-lookup"><span data-stu-id="64a55-116">Apps that require client certificates should use *netsh.exe* to set the `clientcertnegotiation` option to `enabled`.</span></span> <span data-ttu-id="64a55-117">Weitere Informationen finden Sie unter [netsh http-Befehle](/windows-server/networking/technologies/netsh/netsh-http).</span><span class="sxs-lookup"><span data-stu-id="64a55-117">For more information, see [netsh http commands](/windows-server/networking/technologies/netsh/netsh-http).</span></span>

<span data-ttu-id="64a55-118">Wenn Sie möchten, dass Clientzertifikate nur für Teile der App aktiviert sind, lesen Sie den Leitfaden unter [Optionale Clientzertifikate](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).</span><span class="sxs-lookup"><span data-stu-id="64a55-118">If you want client certificates enabled for only some parts of your app, see the guidance at [Optional client certificates](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).</span></span>

<span data-ttu-id="64a55-119">Wenn Sie das alte Neuverhandlungsverhalten benötigen, legen Sie `HttpSysOptions.ClientCertificateMethod` auf den alten Wert `ClientCertificateMethod.AllowRenegotiate` fest.</span><span class="sxs-lookup"><span data-stu-id="64a55-119">If you need the old renegotiate behavior, set `HttpSysOptions.ClientCertificateMethod` to the old value `ClientCertificateMethod.AllowRenegotiate`.</span></span> <span data-ttu-id="64a55-120">Dies wird aus den oben und im verlinkten Leitfaden genannten Gründen nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="64a55-120">This isn't recommended for the reasons outlined above and in the linked guidance.</span></span>

#### <a name="category"></a><span data-ttu-id="64a55-121">Kategorie</span><span class="sxs-lookup"><span data-stu-id="64a55-121">Category</span></span>

<span data-ttu-id="64a55-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="64a55-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="64a55-123">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="64a55-123">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate`
- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync`
- `Overload:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod`

-->
