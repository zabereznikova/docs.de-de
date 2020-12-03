---
title: 'Breaking Change: Der Standardwert für FeedbackSize für mit TripleDES.Create erstellte Instanzen wurde geändert'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, bei dem der Standardwert für die Eigenschaft „FeedbackSize“ der TripleDES-Instanz, die von TripleDES.Create() zurückgegeben wird, von 64 in 8 geändert wird.
ms.date: 10/16/2020
ms.openlocfilehash: 4179da17bf2e5cc5fcc7d64d83ba92119f912042
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759506"
---
# <a name="default-feedbacksize-value-for-instances-created-by-tripledescreate-changed"></a><span data-ttu-id="bfa87-103">Der Standardwert für FeedbackSize für mit TripleDES.Create erstellte Instanzen wurde geändert</span><span class="sxs-lookup"><span data-stu-id="bfa87-103">Default FeedbackSize value for instances created by TripleDES.Create changed</span></span>

<span data-ttu-id="bfa87-104">Der Standardwert für die <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=nameWithType>-Eigenschaft in der von <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> zurückgegebenen <xref:System.Security.Cryptography.TripleDES>-Instanz wurde von 64 in 8 geändert, um die Migration vom .NET Framework zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="bfa87-104">The default value for the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=nameWithType> property on the <xref:System.Security.Cryptography.TripleDES> instance returned from <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> has changed from 64 to 8 to make migration from .NET Framework easier.</span></span> <span data-ttu-id="bfa87-105">Diese Eigenschaft wird nur verwendet, wenn für die <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode>-Eigenschaft <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType> gilt, es sei denn, sie wird direkt im aufrufenden Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="bfa87-105">This property, unless used directly in caller code, is used only when the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> property is <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="bfa87-106">Unterstützung für den <xref:System.Security.Cryptography.CipherMode.CFB>-Modus steht für .NET seit dem 5.0 RC1-Release zur Verfügung. Nur .NET 5.0 RC1 und .NET 5.0 RC2-Anwendungen sollten also von dieser Änderung betroffen sein.</span><span class="sxs-lookup"><span data-stu-id="bfa87-106">Support for the <xref:System.Security.Cryptography.CipherMode.CFB> mode was first added to .NET for the 5.0 RC1 release, so only .NET 5.0 RC1 and .NET 5.0 RC2 applications should be impacted by this change.</span></span>

## <a name="change-description"></a><span data-ttu-id="bfa87-107">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="bfa87-107">Change description</span></span>

<span data-ttu-id="bfa87-108">In .NET Core und vorherigen Vorabversionen von .NET 5.0 weist `TripleDES.Create().FeedbackSize` einen Standardwert von 64 auf.</span><span class="sxs-lookup"><span data-stu-id="bfa87-108">In .NET Core and previous pre-release versions of .NET 5.0, `TripleDES.Create().FeedbackSize` has a default value of 64.</span></span> <span data-ttu-id="bfa87-109">Ab der RTM-Version von .NET 5.0 weist `TripleDES.Create().FeedbackSize` einen Standardwert von 8 auf.</span><span class="sxs-lookup"><span data-stu-id="bfa87-109">Starting in the RTM version of .NET 5.0, `TripleDES.Create().FeedbackSize` has a default value of 8.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="bfa87-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="bfa87-110">Reason for change</span></span>

<span data-ttu-id="bfa87-111">Im .NET Framework legt die <xref:System.Security.Cryptography.TripleDES>-Basisklasse für <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> einen Standardwert von 64 fest, die <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>-Klasse überschreibt den Standardwert jedoch durch 8.</span><span class="sxs-lookup"><span data-stu-id="bfa87-111">In .NET Framework, the <xref:System.Security.Cryptography.TripleDES> base class defaults the value of <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> to 64, but the <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> class overwrites the default to 8.</span></span> <span data-ttu-id="bfa87-112">Als die <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>-Eigenschaft in der Version 2.0 von .NET Core eingeführt wurde, wurde dieses Verhalten beibehalten.</span><span class="sxs-lookup"><span data-stu-id="bfa87-112">When the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> property was introduced to .NET Core in version 2.0, this same behavior was preserved.</span></span> <span data-ttu-id="bfa87-113">Im .NET Framework gibt <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> jedoch eine Instanz von <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> zurück. Der Standardwert der Algorithmusfactory ist also 8.</span><span class="sxs-lookup"><span data-stu-id="bfa87-113">However, in .NET Framework, <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> returns an instance of <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>, so the default value from the algorithm factory is 8.</span></span> <span data-ttu-id="bfa87-114">Für .NET Core und .NET 5 und höher gibt die Algorithmusfactory eine nicht öffentliche Implementierung zurück, die bis jetzt einen Standardwert von 64 aufwies.</span><span class="sxs-lookup"><span data-stu-id="bfa87-114">For .NET Core and .NET 5+, the algorithm factory returns a non-public implementation, which, until now, had a default value of 64.</span></span>

<span data-ttu-id="bfa87-115">Das Ändern des <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>-Werts der <xref:System.Security.Cryptography.TripleDES>-Implementierungsklasse in 8 ermöglicht es, dass Anwendungen, die für das .NET Framework geschrieben wurden, in dem der Verschlüsselungsmodus auf <xref:System.Security.Cryptography.CipherMode.CFB> festgelegt war, die die <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>-Eigenschaft jedoch nicht explizit zuwiesen, in .NET 5 weiterhin funktionieren.</span><span class="sxs-lookup"><span data-stu-id="bfa87-115">Changing the <xref:System.Security.Cryptography.TripleDES> implementation class' <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> value to 8 allows for applications written for .NET Framework that specified the cipher mode as <xref:System.Security.Cryptography.CipherMode.CFB> but didn't explicitly assign the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> property, to continue to function on .NET 5.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="bfa87-116">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="bfa87-116">Version introduced</span></span>

<span data-ttu-id="bfa87-117">5.0</span><span class="sxs-lookup"><span data-stu-id="bfa87-117">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="bfa87-118">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="bfa87-118">Recommended action</span></span>

<span data-ttu-id="bfa87-119">Anwendungen, die Daten in den RC1- oder RC2-Versionen von .NET 5.0 verschlüsseln oder entschlüsseln, tun dies auch bei CFB64, wenn die folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="bfa87-119">Applications that encrypt or decrypt data in the RC1 or RC2 versions of .NET 5.0 do so with CFB64, when the following conditions are met:</span></span>

- <span data-ttu-id="bfa87-120">Eine <xref:System.Security.Cryptography.TripleDES>-Instanz von <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> ist vorhanden.</span><span class="sxs-lookup"><span data-stu-id="bfa87-120">With a <xref:System.Security.Cryptography.TripleDES> instance from <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="bfa87-121">Der Standardwert für <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="bfa87-121">Using the default value for <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>.</span></span>
- <span data-ttu-id="bfa87-122">Die <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode>-Eigenschaft ist auf <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType> festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bfa87-122">With the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> property set to <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="bfa87-123">Wenn dieses Verhalten beibehalten werden soll, weisen Sie die <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>-Eigenschaft `64` zu.</span><span class="sxs-lookup"><span data-stu-id="bfa87-123">To maintain this behavior, assign the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> property to `64`.</span></span>

<span data-ttu-id="bfa87-124">Nicht für alle `TripleDES`-Implementierungen wird derselbe Standardwert für <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> verwendet.</span><span class="sxs-lookup"><span data-stu-id="bfa87-124">Not all `TripleDES` implementations use the same default for <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>.</span></span> <span data-ttu-id="bfa87-125">Wenn Sie den <xref:System.Security.Cryptography.CipherMode.CFB>-Verschlüsselungsmodus für <xref:System.Security.Cryptography.TripleDES>-Instanzen verwenden, sollten Sie den <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>-Eigenschaftswert immer explizit zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bfa87-125">We recommend that if you use the <xref:System.Security.Cryptography.CipherMode.CFB> cipher mode on <xref:System.Security.Cryptography.TripleDES> instances, you should always explicitly assign the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> property value.</span></span>

```csharp
TripleDES cipher = TripleDES.Create();
cipher.Mode = CipherMode.CFB;
// Explicitly set the FeedbackSize for CFB to control between CFB8 and CFB64.
cipher.FeedbackSize = 8;
```

## <a name="affected-apis"></a><span data-ttu-id="bfa87-126">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="bfa87-126">Affected APIs</span></span>

- <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Security.Cryptography.TripleDES.Create`
- `P:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize`

### Category

- Cryptography

-->
