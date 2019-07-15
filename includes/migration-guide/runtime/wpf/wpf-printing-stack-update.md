---
ms.openlocfilehash: e613f0c52c77efebf250f5935d5cbfc29bc09a6b
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802537"
---
### <a name="wpf-printing-stack-update"></a><span data-ttu-id="9ee40-101">Update für WPF-Druckstapel</span><span class="sxs-lookup"><span data-stu-id="9ee40-101">WPF Printing Stack Update</span></span>

|   |   |
|---|---|
|<span data-ttu-id="9ee40-102">Details</span><span class="sxs-lookup"><span data-stu-id="9ee40-102">Details</span></span>|<span data-ttu-id="9ee40-103">Die Druck-APIs von WPF, die <xref:System.Printing.PrintQueue?displayProperty=name> verwenden, rufen nun die Paket-API von Windows zum Drucken von Dokumenten statt der veralteten XPS-Druck-API auf.</span><span class="sxs-lookup"><span data-stu-id="9ee40-103">WPF's Printing APIs using <xref:System.Printing.PrintQueue?displayProperty=name> now call Window's Print Document Package API in favor of the now deprecated XPS Print API.</span></span> <span data-ttu-id="9ee40-104">Diese Änderung wurde für die Wartbarkeit durchgeführt. Weder für Benutzer noch für Entwickler sollten Änderungen im Verhalten oder der API-Nutzung sichtbar werden.</span><span class="sxs-lookup"><span data-stu-id="9ee40-104">The change was made with serviceability in mind; neither users nor developers should see any changes in behavior or API usage.</span></span> <span data-ttu-id="9ee40-105">Der neue Druckstapel wird bei der Ausführung unter Windows 10 Creators Update standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9ee40-105">The new printing stack is enabled by default when running in Windows 10 Creators Update.</span></span> <span data-ttu-id="9ee40-106">Der alte Druckstapel funktioniert in älteren Windows-Versionen weiterhin wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="9ee40-106">The old printing stack will still continue to work just as before in older Windows versions.</span></span>|
|<span data-ttu-id="9ee40-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="9ee40-107">Suggestion</span></span>|<span data-ttu-id="9ee40-108">Legen Sie den <code>UseXpsOMPrinting</code>-REG_DWORD-Wert des <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code>-Registrierungsschlüssels auf <code>1</code> fest, um den alten Stapel in Windows 10 Creators Update zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9ee40-108">To use the old stack in Windows 10 Creators Update, set the <code>UseXpsOMPrinting</code> REG_DWORD value of the <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> registry key to <code>1</code>.</span></span>|
|<span data-ttu-id="9ee40-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="9ee40-109">Scope</span></span>|<span data-ttu-id="9ee40-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9ee40-110">Edge</span></span>|
|<span data-ttu-id="9ee40-111">Version</span><span class="sxs-lookup"><span data-stu-id="9ee40-111">Version</span></span>|<span data-ttu-id="9ee40-112">4.7</span><span class="sxs-lookup"><span data-stu-id="9ee40-112">4.7</span></span>|
|<span data-ttu-id="9ee40-113">Typ</span><span class="sxs-lookup"><span data-stu-id="9ee40-113">Type</span></span>|<span data-ttu-id="9ee40-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="9ee40-114">Runtime</span></span>|

