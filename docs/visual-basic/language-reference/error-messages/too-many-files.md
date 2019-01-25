---
title: Zu viele Dateien
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: 15e08cedbd58016959f00e1ca817019937775df2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737230"
---
# <a name="too-many-files"></a><span data-ttu-id="ee264-102">Zu viele Dateien</span><span class="sxs-lookup"><span data-stu-id="ee264-102">Too many files</span></span>
<span data-ttu-id="ee264-103">Weitere Dateien im Stammverzeichnis befindet als das Betriebssystem zulässig erstellt wurden, oder mehr Dateien geöffnet worden sein, als der Zahl in der **Dateien =** in Ihrer Konfiguration festlegen. SYS-Datei.</span><span class="sxs-lookup"><span data-stu-id="ee264-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ee264-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ee264-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="ee264-105">Wenn Ihr Programm öffnen, schließen oder Speichern von Dateien in das Stammverzeichnis ist, ändern Sie Ihr Programm so, dass es ein Unterverzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="ee264-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2.  <span data-ttu-id="ee264-106">Erhöhen Sie die Anzahl der angegebenen Dateien in Ihrem **Dateien =** in Ihrer Konfiguration festlegen. SYS Datei, und den Computer neu starten.</span><span class="sxs-lookup"><span data-stu-id="ee264-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee264-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee264-107">See also</span></span>
- [<span data-ttu-id="ee264-108">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="ee264-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
