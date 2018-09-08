---
title: Ungültiger Prüfsummenwert, keine hexadezimalen Ziffern oder ungerade Anzahl von hexadezimalen Ziffern.
ms.date: 07/20/2015
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
ms.openlocfilehash: e682c2c23dd6fe80aee87d2a86b3df2dae66b802
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213071"
---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a><span data-ttu-id="85e2e-102">Ungültiger Prüfsummenwert, keine hexadezimalen Ziffern oder ungerade Anzahl von hexadezimalen Ziffern.</span><span class="sxs-lookup"><span data-stu-id="85e2e-102">Bad checksum value, non hex digits or odd number of hex digits</span></span>
<span data-ttu-id="85e2e-103">Ein Prüfsummenwert enthält ungültige hexadezimale Ziffern oder hat eine ungerade Anzahl an Ziffern.</span><span class="sxs-lookup"><span data-stu-id="85e2e-103">A checksum value contains invalid hexadecimal digits or has an odd number of digits.</span></span>  
  
 <span data-ttu-id="85e2e-104">Wenn ASP.NET eine Visual Basic-Quelldatei (Dateierweiterung .vb) erstellt, berechnet es die Prüfsumme und platziert sie in einer ausgeblendeten Quelldatei, die mit `#externalchecksum` gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="85e2e-104">When ASP.NET generates a Visual Basic source file (extension .vb), it calculates a checksum and places it in a hidden source file identified by `#externalchecksum`.</span></span> <span data-ttu-id="85e2e-105">Ein Benutzer, der eine VB-Datei generiert, hat die Möglichkeit, dies selbst zu übernehmen, doch dieser Prozess sollte lieber intern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="85e2e-105">It is possible for a user generating a .vb file to do this also, but this process is best left to internal use.</span></span>  
  
 <span data-ttu-id="85e2e-106">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="85e2e-106">By default, this message is a warning.</span></span> <span data-ttu-id="85e2e-107">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="85e2e-107">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="85e2e-108">**Fehler-ID:** BC42033</span><span class="sxs-lookup"><span data-stu-id="85e2e-108">**Error ID:** BC42033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="85e2e-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="85e2e-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="85e2e-110">Wenn ASP.NET die Visual Basic-Quelldatei generiert, starten Sie den Projektbuild neu.</span><span class="sxs-lookup"><span data-stu-id="85e2e-110">If ASP.NET is generating the Visual Basic source file, restart the project build.</span></span>  
  
2.  <span data-ttu-id="85e2e-111">Wenn diese Warnung auch nach einem Neustart ausgegeben wird, installieren Sie ASP.NET neu, und führen Sie den Vorgang mit dem Build erneut aus.</span><span class="sxs-lookup"><span data-stu-id="85e2e-111">If this warning persists after restarting, reinstall ASP.NET and try the build again.</span></span>  
  
3.  <span data-ttu-id="85e2e-112">Wenn auch dann die Warnung weiterhin besteht oder wenn Sie nicht ASP.NET verwenden, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="85e2e-112">If the warning still persists, or if you are not using ASP.NET, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e2e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85e2e-113">See also</span></span>

- [<span data-ttu-id="85e2e-114">ASP.NET Overview (Übersicht über ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="85e2e-114">ASP.NET Overview</span></span>](/aspnet/overview)  
- [<span data-ttu-id="85e2e-115">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="85e2e-115">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
