---
ms.openlocfilehash: 4d479636f41095610eaf39f92ad0dad4863ab8b5
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568237"
---
### <a name="typedescriptionproviderattribute-moved-to-another-assembly"></a><span data-ttu-id="55eb2-101">TypeDescriptionProviderAttribute in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="55eb2-101">TypeDescriptionProviderAttribute moved to another assembly</span></span>

<span data-ttu-id="55eb2-102">Die <xref:System.ComponentModel.TypeDescriptionProviderAttribute>-Klasse wurde verschoben.</span><span class="sxs-lookup"><span data-stu-id="55eb2-102">The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="55eb2-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="55eb2-103">Change description</span></span>

<span data-ttu-id="55eb2-104">In .NET Core 2.2 und früheren Versionen befand sich die <xref:System.ComponentModel.TypeDescriptionProviderAttribute>-Klasse in der *System.ComponentModel.TypeConverter*-Assembly.</span><span class="sxs-lookup"><span data-stu-id="55eb2-104">In .NET Core 2.2 and earlier versions, The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="55eb2-105">Seit .NET Core 3.0 befindet sie sich in der *System.ObjectModel*-Assembly.</span><span class="sxs-lookup"><span data-stu-id="55eb2-105">Starting with .NET Core 3.0, it is found in the *System.ObjectModel* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="55eb2-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="55eb2-106">Version introduced</span></span>

<span data-ttu-id="55eb2-107">3.0</span><span class="sxs-lookup"><span data-stu-id="55eb2-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="55eb2-108">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="55eb2-108">Recommended action</span></span>

<span data-ttu-id="55eb2-109">Diese Änderung betrifft nur Anwendungen, welche die Reflektion zum Laden des <xref:System.ComponentModel.TypeDescriptionProviderAttribute>-Typs durch Aufrufen einer Methode wie <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> oder eine Überladung von <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> nutzen, bei der vorausgesetzt wird, dass sich der Typ in einer bestimmten Assembly befindet.</span><span class="sxs-lookup"><span data-stu-id="55eb2-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.TypeDescriptionProviderAttribute> type by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="55eb2-110">Ist dies der Fall, muss die im Methodenaufruf referenzierte Assembly entsprechend dem neuen Assemblyspeicherort des Typs aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="55eb2-110">If that is the case, the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="55eb2-111">Kategorie</span><span class="sxs-lookup"><span data-stu-id="55eb2-111">Category</span></span>

<span data-ttu-id="55eb2-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55eb2-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="55eb2-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="55eb2-113">Affected APIs</span></span>

- <span data-ttu-id="55eb2-114">Keine</span><span class="sxs-lookup"><span data-stu-id="55eb2-114">None</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
