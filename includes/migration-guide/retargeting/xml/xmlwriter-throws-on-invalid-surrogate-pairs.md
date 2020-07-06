---
ms.openlocfilehash: f87b70708398226516ab5eac32c24a9fc2c1106b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615735"
---
### <a name="xmlwriter-throws-on-invalid-surrogate-pairs"></a><span data-ttu-id="07d9f-101">XmlWriter löst bei ungültigen Ersatzzeichenpaaren Ausnahmen aus</span><span class="sxs-lookup"><span data-stu-id="07d9f-101">XmlWriter throws on invalid surrogate pairs</span></span>

#### <a name="details"></a><span data-ttu-id="07d9f-102">Details</span><span class="sxs-lookup"><span data-stu-id="07d9f-102">Details</span></span>

<span data-ttu-id="07d9f-103">Bei Apps, die auf .NET Framework 4.5.2 oder niedrigere Versionen abzielen, löst das Schreiben eines ungültigen Ersatzzeichenpaars mithilfe der Fallbackbehandlung nicht immer eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="07d9f-103">For apps that target the .NET Framework 4.5.2 or previous versions, writing an invalid surrogate pair using exception fallback handling does not always throw an exception.</span></span> <span data-ttu-id="07d9f-104">Bei Apps mit der Zielplattform .NET Framework 4.6 löst der Versuch, ein ungültiges Ersatzzeichenpaar zu schreiben, eine <xref:System.ArgumentException?displayProperty=fullName> aus.</span><span class="sxs-lookup"><span data-stu-id="07d9f-104">For apps that target the .NET Framework 4.6, attempting to write an invalid surrogate pair throws an <xref:System.ArgumentException?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="07d9f-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="07d9f-105">Suggestion</span></span>

<span data-ttu-id="07d9f-106">Falls erforderlich, kann dieser Fehler umgangen werden, indem als Zielplattform.NET Framework 4.5.2 oder eine ältere Version verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="07d9f-106">If necessary, this break can be avoided by targeting the .NET Framework 4.5.2 or earlier.</span></span> <span data-ttu-id="07d9f-107">Alternativ können ungültige Ersatzzeichenpaare vor dem Schreiben auch zuerst in gültigen XML-Code umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="07d9f-107">Alternatively, invalid surrogate pairs can be pre-processed into valid xml prior to writing them.</span></span>

| <span data-ttu-id="07d9f-108">Name</span><span class="sxs-lookup"><span data-stu-id="07d9f-108">Name</span></span>    | <span data-ttu-id="07d9f-109">Wert</span><span class="sxs-lookup"><span data-stu-id="07d9f-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="07d9f-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="07d9f-110">Scope</span></span>   | <span data-ttu-id="07d9f-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="07d9f-111">Edge</span></span>        |
| <span data-ttu-id="07d9f-112">Version</span><span class="sxs-lookup"><span data-stu-id="07d9f-112">Version</span></span> | <span data-ttu-id="07d9f-113">4.6</span><span class="sxs-lookup"><span data-stu-id="07d9f-113">4.6</span></span>         |
| <span data-ttu-id="07d9f-114">Typ</span><span class="sxs-lookup"><span data-stu-id="07d9f-114">Type</span></span>    | <span data-ttu-id="07d9f-115">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="07d9f-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="07d9f-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="07d9f-116">Affected APIs</span></span>

- <xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteAttributeStringAsync(System.String,System.String,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCData(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCDataAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteChars(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCharsAsync(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteComment(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCommentAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteEntityRef(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteEntityRefAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRaw(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteProcessingInstruction(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteProcessingInstructionAsync(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRaw(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRawAsync(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRawAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteString(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteStringAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteSurrogateCharEntity(System.Char,System.Char)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteSurrogateCharEntityAsync(System.Char,System.Char)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteValue(System.String)?displayProperty=nameWithType>
