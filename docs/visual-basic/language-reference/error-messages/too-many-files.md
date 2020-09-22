---
title: Zu viele Dateien
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: cd168ce86569d2d7558e21a5b4cc5ef385b28313
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873543"
---
# <a name="too-many-files"></a><span data-ttu-id="fd76a-102">Zu viele Dateien</span><span class="sxs-lookup"><span data-stu-id="fd76a-102">Too many files</span></span>

<span data-ttu-id="fd76a-103">Im Stammverzeichnis wurden entweder weitere Dateien erstellt, die das Betriebssystem zulässt, oder es wurden mehr Dateien geöffnet, als die in der Einstellung " **Dateien =** " in der CONFIG.SYS Datei festgelegte Anzahl.</span><span class="sxs-lookup"><span data-stu-id="fd76a-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fd76a-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fd76a-104">To correct this error</span></span>  
  
1. <span data-ttu-id="fd76a-105">Wenn das Programmdateien im Stammverzeichnis öffnet, schließt oder speichert, ändern Sie das Programm so, dass es ein Unterverzeichnis verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd76a-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2. <span data-ttu-id="fd76a-106">Erhöhen Sie die Anzahl der Dateien, die Sie in ihrer CONFIG.SYS Datei in Ihren **Dateien =** festgelegt haben, und starten Sie den Computer neu.</span><span class="sxs-lookup"><span data-stu-id="fd76a-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd76a-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fd76a-107">See also</span></span>

- [<span data-ttu-id="fd76a-108">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="fd76a-108">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
