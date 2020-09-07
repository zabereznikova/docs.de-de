---
ms.openlocfilehash: e42bce91afab68e509cb35a8992fa3ca2f096872
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496157"
---
### <a name="wpf-printing-stack-update"></a><span data-ttu-id="9f9f9-101">Update für WPF-Druckstapel</span><span class="sxs-lookup"><span data-stu-id="9f9f9-101">WPF Printing Stack Update</span></span>

#### <a name="details"></a><span data-ttu-id="9f9f9-102">Details</span><span class="sxs-lookup"><span data-stu-id="9f9f9-102">Details</span></span>

<span data-ttu-id="9f9f9-103">Die Druck-APIs von WPF, die <xref:System.Printing.PrintQueue?displayProperty=fullName> verwenden, rufen nun die Paket-API von Windows zum Drucken von Dokumenten statt der veralteten XPS-Druck-API auf.</span><span class="sxs-lookup"><span data-stu-id="9f9f9-103">WPF's Printing APIs using <xref:System.Printing.PrintQueue?displayProperty=fullName> now call Window's Print Document Package API in favor of the now deprecated XPS Print API.</span></span> <span data-ttu-id="9f9f9-104">Diese Änderung wurde für die Wartbarkeit durchgeführt. Weder für Benutzer noch für Entwickler sollten Änderungen im Verhalten oder der API-Nutzung sichtbar werden.</span><span class="sxs-lookup"><span data-stu-id="9f9f9-104">The change was made with serviceability in mind; neither users nor developers should see any changes in behavior or API usage.</span></span> <span data-ttu-id="9f9f9-105">Der neue Druckstapel wird bei der Ausführung unter Windows 10 Creators Update standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9f9f9-105">The new printing stack is enabled by default when running in Windows 10 Creators Update.</span></span> <span data-ttu-id="9f9f9-106">Der alte Druckstapel funktioniert in älteren Windows-Versionen weiterhin wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="9f9f9-106">The old printing stack will still continue to work just as before in older Windows versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9f9f9-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="9f9f9-107">Suggestion</span></span>

<span data-ttu-id="9f9f9-108">Legen Sie den <code>UseXpsOMPrinting</code>-REG_DWORD-Wert des <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code>-Registrierungsschlüssels auf <code>1</code> fest, um den alten Stapel in Windows 10 Creators Update zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f9f9-108">To use the old stack in Windows 10 Creators Update, set the <code>UseXpsOMPrinting</code> REG_DWORD value of the <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> registry key to <code>1</code>.</span></span>

| <span data-ttu-id="9f9f9-109">Name</span><span class="sxs-lookup"><span data-stu-id="9f9f9-109">Name</span></span>    | <span data-ttu-id="9f9f9-110">Wert</span><span class="sxs-lookup"><span data-stu-id="9f9f9-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9f9f9-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="9f9f9-111">Scope</span></span>   |<span data-ttu-id="9f9f9-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9f9f9-112">Edge</span></span>|
|<span data-ttu-id="9f9f9-113">Version</span><span class="sxs-lookup"><span data-stu-id="9f9f9-113">Version</span></span>|<span data-ttu-id="9f9f9-114">4.7</span><span class="sxs-lookup"><span data-stu-id="9f9f9-114">4.7</span></span>|
|<span data-ttu-id="9f9f9-115">Typ</span><span class="sxs-lookup"><span data-stu-id="9f9f9-115">Type</span></span>|<span data-ttu-id="9f9f9-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="9f9f9-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="9f9f9-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="9f9f9-117">Affected APIs</span></span>

<span data-ttu-id="9f9f9-118">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="9f9f9-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
