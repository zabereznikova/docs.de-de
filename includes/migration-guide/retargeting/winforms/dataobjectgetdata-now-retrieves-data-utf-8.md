---
ms.openlocfilehash: 3f330d5e601d599231ef0336b785e677fe1d114e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616060"
---
### <a name="dataobjectgetdata-now-retrieves-data-as-utf-8"></a><span data-ttu-id="6d736-101">DataObject.GetData ruft Daten jetzt als UTF-8 ab</span><span class="sxs-lookup"><span data-stu-id="6d736-101">DataObject.GetData now retrieves data as UTF-8</span></span>

#### <a name="details"></a><span data-ttu-id="6d736-102">Details</span><span class="sxs-lookup"><span data-stu-id="6d736-102">Details</span></span>

<span data-ttu-id="6d736-103">In Apps, die für .NET Framework 4 konzipiert sind oder die unter .NET Framework 4.5.1 oder früheren Versionen ausgeführt werden, ruft `DataObject.GetData` HTML-formatierte Daten als ASCII-Zeichenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="6d736-103">For apps that target the .NET Framework 4 or that run on the .NET Framework 4.5.1 or earlier versions, `DataObject.GetData` retrieves HTML-formatted data as an ASCII string.</span></span> <span data-ttu-id="6d736-104">Als Resultat werden nicht-ASCII-Zeichen (Zeichen mit ASCII-Codes größer als 0x7F) durch zwei zufällige Zeichen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6d736-104">As a result, non-ASCII characters (characters whose ASCII codes are greater than 0x7F) are represented by two random characters.</span></span><p/><span data-ttu-id="6d736-105">In Apps, die .NET Framework 4.5 oder eine neuere Version als Ziel verwenden und unter .NET Framework 4.5.2 ausgeführt werden, ruft `DataObject.GetData` HTML-formatierte Daten als UTF-8 ab und stellt Zeichen größer als „0x7F“ korrekt dar.</span><span class="sxs-lookup"><span data-stu-id="6d736-105">For apps that target the .NET Framework 4.5 or later and run on the .NET Framework 4.5.2, `DataObject.GetData` retrieves HTML-formatted data as UTF-8, which represents characters greater than 0x7F correctly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6d736-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="6d736-106">Suggestion</span></span>

<span data-ttu-id="6d736-107">Wenn Sie eine Problemumgehung für das Codierungsproblem mit HTML-formatierten Zeichenfolgen implementiert haben (z.B. durch explizites Codieren der HTML-Zeichenfolge aus der Zwischenablage durch Übergabe an <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>) und das Ziel Ihrer App von Version 4 zu 4.5 neu zuweisen, sollten Sie diese Problemumgehung entfernen. Wenn das alte Verhalten benötigt wird, kann die App auf .NET Framework 4.0 ausgerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="6d736-107">If you implemented a workaround for the encoding problem with HTML-formatted strings (for example, by explicitly encoding the HTML string retrieved from the Clipboard by passing it to <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=fullName>) and you're retargeting your app from version 4 to 4.5, that workaround should be removed.If the old behavior is needed for some reason, the app can target the .NET Framework 4.0 to get that behavior.</span></span>

| <span data-ttu-id="6d736-108">name</span><span class="sxs-lookup"><span data-stu-id="6d736-108">Name</span></span>    | <span data-ttu-id="6d736-109">Wert</span><span class="sxs-lookup"><span data-stu-id="6d736-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6d736-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="6d736-110">Scope</span></span>   | <span data-ttu-id="6d736-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6d736-111">Edge</span></span>        |
| <span data-ttu-id="6d736-112">Version</span><span class="sxs-lookup"><span data-stu-id="6d736-112">Version</span></span> | <span data-ttu-id="6d736-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="6d736-113">4.5.2</span></span>       |
| <span data-ttu-id="6d736-114">Typ</span><span class="sxs-lookup"><span data-stu-id="6d736-114">Type</span></span>    | <span data-ttu-id="6d736-115">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="6d736-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="6d736-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6d736-116">Affected APIs</span></span>

- <xref:System.Windows.DataObject.GetData(System.String)?displayProperty=nameWithType>
- <xref:System.Windows.DataObject.GetData(System.Type)?displayProperty=nameWithType>
- <xref:System.Windows.DataObject.GetData(System.String,System.Boolean)?displayProperty=nameWithType>
