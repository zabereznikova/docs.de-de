---
ms.openlocfilehash: 57ca2ad839aab8d61da1a929660920efe1190334
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147535"
---
### <a name="typedescriptionproviderattribute-moved-to-another-assembly"></a><span data-ttu-id="2e645-101">TypeDescriptionProviderAttribute in andere Assembly verschoben</span><span class="sxs-lookup"><span data-stu-id="2e645-101">TypeDescriptionProviderAttribute moved to another assembly</span></span>

<span data-ttu-id="2e645-102">Die <xref:System.ComponentModel.TypeDescriptionProviderAttribute>-Klasse wurde verschoben.</span><span class="sxs-lookup"><span data-stu-id="2e645-102">The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class has been moved.</span></span>

#### <a name="change-description"></a><span data-ttu-id="2e645-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="2e645-103">Change description</span></span>

<span data-ttu-id="2e645-104">In .NET Core 2.2 und früheren Versionen befand sich die <xref:System.ComponentModel.TypeDescriptionProviderAttribute>-Klasse in der *System.ComponentModel.TypeConverter*-Assembly.</span><span class="sxs-lookup"><span data-stu-id="2e645-104">In .NET Core 2.2 and earlier versions, The <xref:System.ComponentModel.TypeDescriptionProviderAttribute> class is found in the *System.ComponentModel.TypeConverter* assembly.</span></span>

<span data-ttu-id="2e645-105">Seit .NET Core 3.0 befindet sie sich in der *System.ObjectModel*-Assembly.</span><span class="sxs-lookup"><span data-stu-id="2e645-105">Starting with .NET Core 3.0, it is found in the *System.ObjectModel* assembly.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2e645-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="2e645-106">Version introduced</span></span>

<span data-ttu-id="2e645-107">3.0</span><span class="sxs-lookup"><span data-stu-id="2e645-107">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2e645-108">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="2e645-108">Recommended action</span></span>

<span data-ttu-id="2e645-109">Diese Änderung betrifft nur Anwendungen, welche die Reflektion zum Laden des <xref:System.ComponentModel.TypeDescriptionProviderAttribute>-Typs durch Aufrufen einer Methode wie <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> oder eine Überladung von <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> nutzen, bei der vorausgesetzt wird, dass sich der Typ in einer bestimmten Assembly befindet.</span><span class="sxs-lookup"><span data-stu-id="2e645-109">This change only affects applications that use reflection to load the <xref:System.ComponentModel.TypeDescriptionProviderAttribute> type by calling a method such as <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or an overload of <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> that assumes the type is in a particular assembly.</span></span> <span data-ttu-id="2e645-110">Ist dies der Fall, muss die im Methodenaufruf referenzierte Assembly entsprechend dem neuen Assemblyspeicherort des Typs aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e645-110">If that is the case, the assembly referenced in the method call should be updated to reflect the type's new assembly location.</span></span>

#### <a name="category"></a><span data-ttu-id="2e645-111">Kategorie</span><span class="sxs-lookup"><span data-stu-id="2e645-111">Category</span></span>

<span data-ttu-id="2e645-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2e645-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2e645-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="2e645-113">Affected APIs</span></span>

<span data-ttu-id="2e645-114">Keine.</span><span class="sxs-lookup"><span data-stu-id="2e645-114">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
