---
ms.openlocfilehash: 4ad7c4c2781480c08ad4cf27e40de445b1c50671
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617242"
---
### <a name="encoderparameter-ctor-is-obsolete"></a><span data-ttu-id="c1515-101">EncoderParameter ctor ist veraltet</span><span class="sxs-lookup"><span data-stu-id="c1515-101">EncoderParameter ctor is obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="c1515-102">Details</span><span class="sxs-lookup"><span data-stu-id="c1515-102">Details</span></span>

<span data-ttu-id="c1515-103">Der <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>-Konstruktor ist jetzt veraltet und gibt Buildwarnungen aus, wenn er verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c1515-103">The <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> constructor is obsolete now and will introduce build warnings if used.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c1515-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="c1515-104">Suggestion</span></span>

<span data-ttu-id="c1515-105">Obwohl der <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>-Konstruktor weiterhin funktioniert, sollte stattdessen der folgende Konstruktor verwendet werden, um die veraltete Buildwarnung zu vermeiden, wenn Code mit .NET Framework 4.5-Tools erneut kompiliert wird: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span><span class="sxs-lookup"><span data-stu-id="c1515-105">Although the <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>constructor will continue to work, the following constructor should be used instead to avoid the obsolete build warning when re-compiling code with .NET Framework  4.5 tools: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span></span>

| <span data-ttu-id="c1515-106">name</span><span class="sxs-lookup"><span data-stu-id="c1515-106">Name</span></span>    | <span data-ttu-id="c1515-107">Wert</span><span class="sxs-lookup"><span data-stu-id="c1515-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c1515-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="c1515-108">Scope</span></span>   | <span data-ttu-id="c1515-109">Gering</span><span class="sxs-lookup"><span data-stu-id="c1515-109">Minor</span></span>       |
| <span data-ttu-id="c1515-110">Version</span><span class="sxs-lookup"><span data-stu-id="c1515-110">Version</span></span> | <span data-ttu-id="c1515-111">4.5</span><span class="sxs-lookup"><span data-stu-id="c1515-111">4.5</span></span>         |
| <span data-ttu-id="c1515-112">Typ</span><span class="sxs-lookup"><span data-stu-id="c1515-112">Type</span></span>    | <span data-ttu-id="c1515-113">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="c1515-113">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="c1515-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="c1515-114">Affected APIs</span></span>

- <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>
