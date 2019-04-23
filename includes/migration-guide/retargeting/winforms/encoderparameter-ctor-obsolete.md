---
ms.openlocfilehash: b4e062fe3a00b76da144e706841f87b2a95888e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774328"
---
### <a name="encoderparameter-ctor-is-obsolete"></a><span data-ttu-id="b9b14-101">EncoderParameter ctor ist veraltet</span><span class="sxs-lookup"><span data-stu-id="b9b14-101">EncoderParameter ctor is obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b9b14-102">Details</span><span class="sxs-lookup"><span data-stu-id="b9b14-102">Details</span></span>|<span data-ttu-id="b9b14-103">Der <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>-Konstruktor ist jetzt veraltet und gibt Buildwarnungen aus, wenn er verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b9b14-103">The <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> constructor is obsolete now and will introduce build warnings if used.</span></span>|
|<span data-ttu-id="b9b14-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b9b14-104">Suggestion</span></span>|<span data-ttu-id="b9b14-105">Obwohl der <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>-Konstruktor weiterhin funktioniert, sollte stattdessen der folgende Konstruktor verwendet werden, um die veraltete Buildwarnung zu vermeiden, wenn Code mit .NET Framework 4.5-Tools erneut kompiliert wird: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span><span class="sxs-lookup"><span data-stu-id="b9b14-105">Although the <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>constructor will continue to work, the following constructor should be used instead to avoid the obsolete build warning when re-compiling code with .NET Framework  4.5 tools: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span></span>|
|<span data-ttu-id="b9b14-106">Bereich</span><span class="sxs-lookup"><span data-stu-id="b9b14-106">Scope</span></span>|<span data-ttu-id="b9b14-107">Gering</span><span class="sxs-lookup"><span data-stu-id="b9b14-107">Minor</span></span>|
|<span data-ttu-id="b9b14-108">Version</span><span class="sxs-lookup"><span data-stu-id="b9b14-108">Version</span></span>|<span data-ttu-id="b9b14-109">4.5</span><span class="sxs-lookup"><span data-stu-id="b9b14-109">4.5</span></span>|
|<span data-ttu-id="b9b14-110">Typ</span><span class="sxs-lookup"><span data-stu-id="b9b14-110">Type</span></span>|<span data-ttu-id="b9b14-111">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="b9b14-111">Retargeting</span></span>|
|<span data-ttu-id="b9b14-112">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b9b14-112">Affected APIs</span></span>|<ul><li><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
