---
ms.openlocfilehash: e613f0c52c77efebf250f5935d5cbfc29bc09a6b
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760421"
---
### <a name="wpf-printing-stack-update"></a><span data-ttu-id="fecba-101">Update für WPF-Druckstapel</span><span class="sxs-lookup"><span data-stu-id="fecba-101">WPF Printing Stack Update</span></span>

|   |   |
|---|---|
|<span data-ttu-id="fecba-102">Details</span><span class="sxs-lookup"><span data-stu-id="fecba-102">Details</span></span>|<span data-ttu-id="fecba-103">Die Druck-APIs von WPF, die <xref:System.Printing.PrintQueue?displayProperty=name> verwenden, rufen nun die Paket-API von Windows zum Drucken von Dokumenten statt der veralteten XPS-Druck-API auf.</span><span class="sxs-lookup"><span data-stu-id="fecba-103">WPF's Printing APIs using <xref:System.Printing.PrintQueue?displayProperty=name> now call Window's Print Document Package API in favor of the now deprecated XPS Print API.</span></span> <span data-ttu-id="fecba-104">Diese Änderung wurde für die Wartbarkeit durchgeführt. Weder für Benutzer noch für Entwickler sollten Änderungen im Verhalten oder der API-Nutzung sichtbar werden.</span><span class="sxs-lookup"><span data-stu-id="fecba-104">The change was made with serviceability in mind; neither users nor developers should see any changes in behavior or API usage.</span></span> <span data-ttu-id="fecba-105">Der neue Druckstapel wird bei der Ausführung unter Windows 10 Creators Update standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fecba-105">The new printing stack is enabled by default when running in Windows 10 Creators Update.</span></span> <span data-ttu-id="fecba-106">Der alte Druckstapel funktioniert in älteren Windows-Versionen weiterhin wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="fecba-106">The old printing stack will still continue to work just as before in older Windows versions.</span></span>|
|<span data-ttu-id="fecba-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="fecba-107">Suggestion</span></span>|<span data-ttu-id="fecba-108">Legen Sie den <code>UseXpsOMPrinting</code>-REG_DWORD-Wert des <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code>-Registrierungsschlüssels auf <code>1</code> fest, um den alten Stapel in Windows 10 Creators Update zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fecba-108">To use the old stack in Windows 10 Creators Update, set the <code>UseXpsOMPrinting</code> REG_DWORD value of the <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> registry key to <code>1</code>.</span></span>|
|<span data-ttu-id="fecba-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="fecba-109">Scope</span></span>|<span data-ttu-id="fecba-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="fecba-110">Edge</span></span>|
|<span data-ttu-id="fecba-111">Version</span><span class="sxs-lookup"><span data-stu-id="fecba-111">Version</span></span>|<span data-ttu-id="fecba-112">4.7</span><span class="sxs-lookup"><span data-stu-id="fecba-112">4.7</span></span>|
|<span data-ttu-id="fecba-113">Typ</span><span class="sxs-lookup"><span data-stu-id="fecba-113">Type</span></span>|<span data-ttu-id="fecba-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="fecba-114">Runtime</span></span>|

