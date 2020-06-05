---
title: Zu viele Dateien
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: 38d39ad20f350137d714ae5d09db5d2204b83621
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362799"
---
# <a name="too-many-files"></a><span data-ttu-id="401b3-102">Zu viele Dateien</span><span class="sxs-lookup"><span data-stu-id="401b3-102">Too many files</span></span>
<span data-ttu-id="401b3-103">Im Stammverzeichnis wurden entweder mehr Dateien erstellt, als das Betriebssystem zulässt, oder es wurden mehr Dateien geöffnet, als die in der Einstellung " **Dateien =** " in der Konfiguration angegebene Anzahl. SYS-Datei.</span><span class="sxs-lookup"><span data-stu-id="401b3-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="401b3-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="401b3-104">To correct this error</span></span>  
  
1. <span data-ttu-id="401b3-105">Wenn das Programmdateien im Stammverzeichnis öffnet, schließt oder speichert, ändern Sie das Programm so, dass es ein Unterverzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="401b3-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2. <span data-ttu-id="401b3-106">Erhöhen Sie die Anzahl der Dateien, die in Ihrer Konfiguration in Ihren **Dateien =** festgelegt sind. SYS-Datei, und starten Sie den Computer neu.</span><span class="sxs-lookup"><span data-stu-id="401b3-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="401b3-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="401b3-107">See also</span></span>

- [<span data-ttu-id="401b3-108">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="401b3-108">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
