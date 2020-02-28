---
ms.openlocfilehash: dc733ee32184db5af59bb06e294cd73765977581
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449554"
---
### <a name="fieldinfosetvalue-throws-exception-for-static-init-only-fields"></a><span data-ttu-id="3feee-101">FieldInfo.SetValue löst eine Ausnahme für statische reine Initialisierungsfelder aus</span><span class="sxs-lookup"><span data-stu-id="3feee-101">FieldInfo.SetValue throws exception for static, init-only fields</span></span>

<span data-ttu-id="3feee-102">Ab .NET Core 3.0 wird eine Ausnahme ausgelöst, wenn Sie versuchen, einen Wert in einem statischen <xref:System.Reflection.FieldAttributes.InitOnly>-Feld durch Aufrufen von <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName> festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3feee-102">Starting in .NET Core 3.0, an exception is thrown when you attempt to set a value on a static, <xref:System.Reflection.FieldAttributes.InitOnly> field by calling <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3feee-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="3feee-103">Change description</span></span>

<span data-ttu-id="3feee-104">In .NET Framework und Versionen von .NET Core vor 3.0 konnten Sie den Wert eines statischen Felds, das nach der Initialisierung konstant ist ([schreibgeschützt in C#](~/docs/csharp/language-reference/keywords/readonly.md)), durch Aufrufen von <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName> festlegen.</span><span class="sxs-lookup"><span data-stu-id="3feee-104">In .NET Framework and versions of .NET Core prior to 3.0, you could set the value of a static field that's constant after it is initialized ([readonly in C#](~/docs/csharp/language-reference/keywords/readonly.md)) by calling <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="3feee-105">Allerdings führte das Festlegen eines solchen Felds auf diese Weise je nach Zielframework und Optimierungseinstellungen zu einem unvorhersehbaren Verhalten.</span><span class="sxs-lookup"><span data-stu-id="3feee-105">However, setting such a field in this way resulted in unpredictable behavior based on the target framework and optimization settings.</span></span>

<span data-ttu-id="3feee-106">Ab . NET Core 3.0 wird beim Aufrufen von <xref:System.Reflection.FieldInfo.SetValue%2A> für ein statisches <xref:System.Reflection.FieldAttributes.InitOnly>-Feld eine <xref:System.FieldAccessException?displayProperty=nameWithType>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="3feee-106">In .NET Core 3.0 and later versions, when you call <xref:System.Reflection.FieldInfo.SetValue%2A> on a static, <xref:System.Reflection.FieldAttributes.InitOnly> field, a <xref:System.FieldAccessException?displayProperty=nameWithType> exception is thrown.</span></span>

> [!TIP]
> <span data-ttu-id="3feee-107">Ein <xref:System.Reflection.FieldAttributes.InitOnly>-Feld ist ein Feld, das nur zum Zeitpunkt seiner Deklaration oder im Konstruktor für die enthaltende Klasse festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="3feee-107">An <xref:System.Reflection.FieldAttributes.InitOnly> field is one that can only be set at the time it's declared or in the constructor for the containing class.</span></span> <span data-ttu-id="3feee-108">Das heißt, dass es nach der Initialisierung konstant ist.</span><span class="sxs-lookup"><span data-stu-id="3feee-108">In other words, it's constant after it is initialized.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3feee-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="3feee-109">Version introduced</span></span>

<span data-ttu-id="3feee-110">3.0</span><span class="sxs-lookup"><span data-stu-id="3feee-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3feee-111">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="3feee-111">Recommended action</span></span>

<span data-ttu-id="3feee-112">Initialisieren Sie statische <xref:System.Reflection.FieldAttributes.InitOnly>-Felder in einem statischen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="3feee-112">Initialize static, <xref:System.Reflection.FieldAttributes.InitOnly> fields in a static constructor.</span></span> <span data-ttu-id="3feee-113">Dies gilt sowohl für dynamische als auch für nicht dynamische Typen.</span><span class="sxs-lookup"><span data-stu-id="3feee-113">This applies to both dynamic and non-dynamic types.</span></span>

<span data-ttu-id="3feee-114">Alternativ können Sie das <xref:System.Reflection.FieldAttributes.InitOnly?displayProperty=nameWithType>-Attribut aus dem Feld entfernen und dann <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=nameWithType>aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3feee-114">Alternatively, you can remove the <xref:System.Reflection.FieldAttributes.InitOnly?displayProperty=nameWithType> attribute from the field, and then call <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="3feee-115">Kategorie</span><span class="sxs-lookup"><span data-stu-id="3feee-115">Category</span></span>

<span data-ttu-id="3feee-116">CoreFx</span><span class="sxs-lookup"><span data-stu-id="3feee-116">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3feee-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="3feee-117">Affected APIs</span></span>

- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)?displayProperty=nameWithType>
- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)`
- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)`

-->
