---
ms.openlocfilehash: 4fb1ffed97a5b7f906bed13a69f1e71563d11dae
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556173"
---
### <a name="serializableattribute-removed-from-some-windows-forms-types"></a><span data-ttu-id="5d0f3-101">SerializableAttribute aus einigen Windows Forms-Typen entfernt</span><span class="sxs-lookup"><span data-stu-id="5d0f3-101">SerializableAttribute removed from some Windows Forms types</span></span>

<span data-ttu-id="5d0f3-102"><xref:System.SerializableAttribute> wurde aus einigen Windows Forms-Klassen ohne bekannte Szenarios für binäre Serialisierung entfernt.</span><span class="sxs-lookup"><span data-stu-id="5d0f3-102">The <xref:System.SerializableAttribute> has been removed from some Windows Forms classes that have no known binary serialization scenarios.</span></span>

#### <a name="change-description"></a><span data-ttu-id="5d0f3-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="5d0f3-103">Change description</span></span>

<span data-ttu-id="5d0f3-104">Die folgenden Typen enthalten in .NET Framework das Attribut <xref:System.SerializableAttribute>, das in .NET Core entfernt wurde:</span><span class="sxs-lookup"><span data-stu-id="5d0f3-104">The following types are decorated with the <xref:System.SerializableAttribute> in .NET Framework, but the attribute has been removed in .NET Core:</span></span>

- `System.InvariantComparer`
- <xref:System.ComponentModel.Design.ExceptionCollection?displayProperty=nameWithType>
- <xref:System.ComponentModel.Design.Serialization.CodeDomSerializerException?displayProperty=nameWithType>
- `System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService.CodeDomSerializationStore`
- <xref:System.Drawing.Design.ToolboxItem?displayProperty=nameWithType>
- `System.Resources.ResXNullRef`
- `System.Resources.ResXDataNode`
- `System.Resources.ResXFileRef`
- <xref:System.Windows.Forms.Cursor?displayProperty=nameWithType>
- `System.Windows.Forms.NativeMethods.MSOCRINFOSTRUCT`
- `System.Windows.Forms.NativeMethods.MSG`

<span data-ttu-id="5d0f3-105">In der Vergangenheit bereitete dieser Serialisierungsmechanismus schwerwiegende Wartungs- und Sicherheitsprobleme.</span><span class="sxs-lookup"><span data-stu-id="5d0f3-105">Historically, this serialization mechanism has had serious maintenance and security concerns.</span></span> <span data-ttu-id="5d0f3-106">Die Beibehaltung von `SerializableAttribute` für Typen bedeutet, dass diese Typen auf Serialisierungsänderungen zwischen Versionen und auf potenzielle Serialisierungsänderungen zwischen Frameworks geprüft werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5d0f3-106">Maintaining `SerializableAttribute` on types means those types must be tested for version-to-version serialization changes and potentially framework-to-framework serialization changes.</span></span> <span data-ttu-id="5d0f3-107">Dies erschwert die Weiterentwicklung dieser Typen und verteuert die Beibehaltung.</span><span class="sxs-lookup"><span data-stu-id="5d0f3-107">This makes it harder to evolve those types and can be costly to maintain.</span></span> <span data-ttu-id="5d0f3-108">Da es für diese Typen keine bekannten Serialisierungsszenarios gibt, sind die Auswirkungen minimal, wenn das Attribut entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="5d0f3-108">These types have no known binary serialization scenarios, which minimizes the impact of removing the attribute.</span></span>

<span data-ttu-id="5d0f3-109">Weitere Informationen finden Sie unter [Binäre Serialisierung](~/docs/standard/serialization/binary-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="5d0f3-109">For more information, see [Binary serialization](~/docs/standard/serialization/binary-serialization.md).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5d0f3-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="5d0f3-110">Version introduced</span></span>

<span data-ttu-id="5d0f3-111">3.0</span><span class="sxs-lookup"><span data-stu-id="5d0f3-111">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5d0f3-112">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="5d0f3-112">Recommended action</span></span>

<span data-ttu-id="5d0f3-113">Aktualisieren Sie jeden Code, der von diesen als serialisierbar markierten Typen abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="5d0f3-113">Update any code that may depend on these types being marked as serializable.</span></span>

#### <a name="category"></a><span data-ttu-id="5d0f3-114">Kategorie</span><span class="sxs-lookup"><span data-stu-id="5d0f3-114">Category</span></span>

<span data-ttu-id="5d0f3-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5d0f3-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5d0f3-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="5d0f3-116">Affected APIs</span></span>

- <span data-ttu-id="5d0f3-117">Keiner</span><span class="sxs-lookup"><span data-stu-id="5d0f3-117">None</span></span>

<!--

#### Affected APIs

- Not detectable via API analysis

-->
