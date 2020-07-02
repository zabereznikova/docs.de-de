---
ms.openlocfilehash: 5e2e8d1ec5d698d1c1649c2a0a1b4b77dbdf4022
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621281"
---
### <a name="wpf-printing-stack-update"></a><span data-ttu-id="b4812-101">Update für WPF-Druckstapel</span><span class="sxs-lookup"><span data-stu-id="b4812-101">WPF Printing Stack Update</span></span>

#### <a name="details"></a><span data-ttu-id="b4812-102">Details</span><span class="sxs-lookup"><span data-stu-id="b4812-102">Details</span></span>

<span data-ttu-id="b4812-103">Die Druck-APIs von WPF, die <xref:System.Printing.PrintQueue?displayProperty=fullName> verwenden, rufen nun die Paket-API von Windows zum Drucken von Dokumenten statt der veralteten XPS-Druck-API auf.</span><span class="sxs-lookup"><span data-stu-id="b4812-103">WPF's Printing APIs using <xref:System.Printing.PrintQueue?displayProperty=fullName> now call Window's Print Document Package API in favor of the now deprecated XPS Print API.</span></span> <span data-ttu-id="b4812-104">Diese Änderung wurde für die Wartbarkeit durchgeführt. Weder für Benutzer noch für Entwickler sollten Änderungen im Verhalten oder der API-Nutzung sichtbar werden.</span><span class="sxs-lookup"><span data-stu-id="b4812-104">The change was made with serviceability in mind; neither users nor developers should see any changes in behavior or API usage.</span></span> <span data-ttu-id="b4812-105">Der neue Druckstapel wird bei der Ausführung unter Windows 10 Creators Update standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b4812-105">The new printing stack is enabled by default when running in Windows 10 Creators Update.</span></span> <span data-ttu-id="b4812-106">Der alte Druckstapel funktioniert in älteren Windows-Versionen weiterhin wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="b4812-106">The old printing stack will still continue to work just as before in older Windows versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b4812-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b4812-107">Suggestion</span></span>

<span data-ttu-id="b4812-108">Legen Sie den <code>UseXpsOMPrinting</code>-REG_DWORD-Wert des <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code>-Registrierungsschlüssels auf <code>1</code> fest, um den alten Stapel in Windows 10 Creators Update zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b4812-108">To use the old stack in Windows 10 Creators Update, set the <code>UseXpsOMPrinting</code> REG_DWORD value of the <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> registry key to <code>1</code>.</span></span>

| <span data-ttu-id="b4812-109">Name</span><span class="sxs-lookup"><span data-stu-id="b4812-109">Name</span></span>    | <span data-ttu-id="b4812-110">Wert</span><span class="sxs-lookup"><span data-stu-id="b4812-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b4812-111">Bereich</span><span class="sxs-lookup"><span data-stu-id="b4812-111">Scope</span></span>   |<span data-ttu-id="b4812-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b4812-112">Edge</span></span>|
|<span data-ttu-id="b4812-113">Version</span><span class="sxs-lookup"><span data-stu-id="b4812-113">Version</span></span>|<span data-ttu-id="b4812-114">4.7</span><span class="sxs-lookup"><span data-stu-id="b4812-114">4.7</span></span>|
|<span data-ttu-id="b4812-115">Typ</span><span class="sxs-lookup"><span data-stu-id="b4812-115">Type</span></span>|<span data-ttu-id="b4812-116">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b4812-116">Runtime</span></span>|
