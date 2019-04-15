---
ms.openlocfilehash: 0358450024607a985f38564ec9743ba964949e8f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234491"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="86f88-101">ClickOnce unterstützt SHA-256 auf Apps, die auf 4.0 ausgerichtet sind</span><span class="sxs-lookup"><span data-stu-id="86f88-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

|   |   |
|---|---|
|<span data-ttu-id="86f88-102">Details</span><span class="sxs-lookup"><span data-stu-id="86f88-102">Details</span></span>|<span data-ttu-id="86f88-103">Bisher war für ClickOnce-Apps mit einem mit SHA-256 signierten Zertifikat auch dann .NET Framework 4.5 oder höher erforderlich, wenn die App auf 4.0 ausgelegt war.</span><span class="sxs-lookup"><span data-stu-id="86f88-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="86f88-104">Nun können ClickOnce-Apps, die auf .NET Framework 4.0 ausgelegt sind, auch dann in .NET Framework 4.0 ausgeführt werden, wenn sie mit SHA-256 signiert sind.</span><span class="sxs-lookup"><span data-stu-id="86f88-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>|
|<span data-ttu-id="86f88-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="86f88-105">Suggestion</span></span>|<span data-ttu-id="86f88-106">Diese Änderung beseitigt diese Abhängigkeit und ermöglicht die Verwendung von SHA-256-Zertifikaten zum Signieren von ClickOnce-Apps, die auf .NET Framework 4 und frühere Versionen ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="86f88-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>|
|<span data-ttu-id="86f88-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="86f88-107">Scope</span></span>|<span data-ttu-id="86f88-108">Gering</span><span class="sxs-lookup"><span data-stu-id="86f88-108">Minor</span></span>|
|<span data-ttu-id="86f88-109">Version</span><span class="sxs-lookup"><span data-stu-id="86f88-109">Version</span></span>|<span data-ttu-id="86f88-110">4.6</span><span class="sxs-lookup"><span data-stu-id="86f88-110">4.6</span></span>|
|<span data-ttu-id="86f88-111">Typ</span><span class="sxs-lookup"><span data-stu-id="86f88-111">Type</span></span>|<span data-ttu-id="86f88-112">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="86f88-112">Retargeting</span></span>|
