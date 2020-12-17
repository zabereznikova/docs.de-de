---
ms.openlocfilehash: dfa8235fcfd868b80d3a610bddb492899519e289
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009051"
---
### <a name="xml-parsing-changes"></a><span data-ttu-id="37917-101">Änderungen an der XML-Analyse</span><span class="sxs-lookup"><span data-stu-id="37917-101">XML parsing changes</span></span>

| <span data-ttu-id="37917-102">Name</span><span class="sxs-lookup"><span data-stu-id="37917-102">Name</span></span>    | <span data-ttu-id="37917-103">Wert</span><span class="sxs-lookup"><span data-stu-id="37917-103">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="37917-104">Bereich</span><span class="sxs-lookup"><span data-stu-id="37917-104">Scope</span></span>   | <span data-ttu-id="37917-105">Gering</span><span class="sxs-lookup"><span data-stu-id="37917-105">Minor</span></span>   |
| <span data-ttu-id="37917-106">Version</span><span class="sxs-lookup"><span data-stu-id="37917-106">Version</span></span> | <span data-ttu-id="37917-107">4.5.2</span><span class="sxs-lookup"><span data-stu-id="37917-107">4.5.2</span></span>   |
| <span data-ttu-id="37917-108">Typ</span><span class="sxs-lookup"><span data-stu-id="37917-108">Type</span></span>    | <span data-ttu-id="37917-109">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="37917-109">Runtime</span></span> |

#### <a name="details"></a><span data-ttu-id="37917-110">Details</span><span class="sxs-lookup"><span data-stu-id="37917-110">Details</span></span>

<span data-ttu-id="37917-111">Aus Sicherheitsgründen wurden die folgenden Änderungen in den XML-Analyse-APIs eingeführt:</span><span class="sxs-lookup"><span data-stu-id="37917-111">For security reasons, the following changes were introduced into XML parsing APIS:</span></span>

- <span data-ttu-id="37917-112"><xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=nameWithType> wird auf 10 Millionen festgelegt, wenn <xref:System.Xml.XmlReaderSettings> initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="37917-112"><xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=nameWithType> is set to 10 million when <xref:System.Xml.XmlReaderSettings> is initialized.</span></span>
- <span data-ttu-id="37917-113"><xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=nameWithType> ist standardmäßig auf `null` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="37917-113"><xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=nameWithType> is set to `null` by default.</span></span>

> [!NOTE]
> <span data-ttu-id="37917-114"><xref:System.Xml.XmlReaderSettings> wird von allen XML-Analysen verwendet. Diese Änderung unterstützt den <xref:System.Xml.XmlReader>-Fall, wirkt sich aber auch auf andere Szenarios aus.</span><span class="sxs-lookup"><span data-stu-id="37917-114"><xref:System.Xml.XmlReaderSettings> is used by all XML parsers, so while this change helps the <xref:System.Xml.XmlReader> case, it also affects other scenarios.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="37917-115">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="37917-115">Suggestion</span></span>

<span data-ttu-id="37917-116">Sie können einen Wert in der Registrierung festlegen, um das vorherige Verhalten wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="37917-116">To revert to the previous behavior, you can set a value in the registry.</span></span> <span data-ttu-id="37917-117">Fügen Sie einen DWORD-Wert namens `EnableLegacyXmlSettings` zum Registrierungsschlüssel `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\XML` hinzu, und legen Sie den Wert auf `1` fest.</span><span class="sxs-lookup"><span data-stu-id="37917-117">Add a DWORD value named `EnableLegacyXmlSettings` to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\XML` registry key, and set its value to `1`.</span></span> <span data-ttu-id="37917-118">Sie können den Registrierungswert stattdessen auch im HKEY_CURRENT_USER-Hive hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="37917-118">You can also add the registry value in the HKEY_CURRENT_USER hive instead.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="37917-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="37917-119">Affected APIs</span></span>

- <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName>
- <xref:System.Xml.XmlReaderSettings.XmlResolver?displayProperty=fullName>

<span data-ttu-id="37917-120">Darüber hinaus ist jede direkt oder indirekt von <xref:System.Xml.XmlResolver> abhängige XML-API betroffen.</span><span class="sxs-lookup"><span data-stu-id="37917-120">In addition, any XML API that depends on <xref:System.Xml.XmlResolver>, either directly or indirectly, is affected.</span></span>

<!--

#### Affected APIs

- `P:System.Xml.XmlReaderSettings.MaxCharactersFromEntities`
- `P:System.Xml.XmlReaderSettings.XmlResolver`

-->
