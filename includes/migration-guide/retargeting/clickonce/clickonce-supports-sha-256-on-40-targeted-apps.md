---
ms.openlocfilehash: c967a5b09b5e9ffeee7bff046f0c96469bc7fb02
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615653"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="d72ff-101">ClickOnce unterstützt SHA-256 auf Apps, die auf 4.0 ausgerichtet sind</span><span class="sxs-lookup"><span data-stu-id="d72ff-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

#### <a name="details"></a><span data-ttu-id="d72ff-102">Details</span><span class="sxs-lookup"><span data-stu-id="d72ff-102">Details</span></span>

<span data-ttu-id="d72ff-103">Bisher war für ClickOnce-Apps mit einem mit SHA-256 signierten Zertifikat auch dann .NET Framework 4.5 oder höher erforderlich, wenn die App auf 4.0 ausgelegt war.</span><span class="sxs-lookup"><span data-stu-id="d72ff-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="d72ff-104">Nun können ClickOnce-Apps, die auf .NET Framework 4.0 ausgelegt sind, auch dann in .NET Framework 4.0 ausgeführt werden, wenn sie mit SHA-256 signiert sind.</span><span class="sxs-lookup"><span data-stu-id="d72ff-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d72ff-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="d72ff-105">Suggestion</span></span>

<span data-ttu-id="d72ff-106">Diese Änderung beseitigt diese Abhängigkeit und ermöglicht die Verwendung von SHA-256-Zertifikaten zum Signieren von ClickOnce-Apps, die auf .NET Framework 4 und frühere Versionen ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="d72ff-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>

| <span data-ttu-id="d72ff-107">name</span><span class="sxs-lookup"><span data-stu-id="d72ff-107">Name</span></span>    | <span data-ttu-id="d72ff-108">Wert</span><span class="sxs-lookup"><span data-stu-id="d72ff-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d72ff-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="d72ff-109">Scope</span></span>   | <span data-ttu-id="d72ff-110">Gering</span><span class="sxs-lookup"><span data-stu-id="d72ff-110">Minor</span></span>       |
| <span data-ttu-id="d72ff-111">Version</span><span class="sxs-lookup"><span data-stu-id="d72ff-111">Version</span></span> | <span data-ttu-id="d72ff-112">4.6</span><span class="sxs-lookup"><span data-stu-id="d72ff-112">4.6</span></span>         |
| <span data-ttu-id="d72ff-113">Typ</span><span class="sxs-lookup"><span data-stu-id="d72ff-113">Type</span></span>    | <span data-ttu-id="d72ff-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="d72ff-114">Retargeting</span></span> |
