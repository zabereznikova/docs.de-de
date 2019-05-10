---
title: Für das Ereignisprotokoll wurde ein ungültiger Name angegeben.
ms.date: 07/20/2015
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
ms.openlocfilehash: 05f37239510482de218847f069dc74cbef91f398
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609171"
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a><span data-ttu-id="4d09c-102">Für das Ereignisprotokoll wurde ein ungültiger Name angegeben.</span><span class="sxs-lookup"><span data-stu-id="4d09c-102">An invalid name was specified for the event log</span></span>
<span data-ttu-id="4d09c-103">Für das Ereignisprotokoll wurde ein ungültiger Name angegeben.</span><span class="sxs-lookup"><span data-stu-id="4d09c-103">An invalid name was specified for the event log.</span></span> <span data-ttu-id="4d09c-104">Dies liegt in der Regel an ungültigen Zeichen im Namen, an einem leeren Dateinamen oder an einem zu langen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="4d09c-104">Usually this is a result of invalid characters in the name, a blank file name, or a file name that is too long.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4d09c-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4d09c-105">To correct this error</span></span>  
  
- <span data-ttu-id="4d09c-106">Wenn der angegebene Name mehr als acht Zeichen lang ist, stellen Sie sicher, dass kein Konflikt mit den Namen anderer Ereignisprotokolle auftritt.</span><span class="sxs-lookup"><span data-stu-id="4d09c-106">If the specified name is more than eight characters, make sure there is no conflict with the names of other event logs.</span></span> <span data-ttu-id="4d09c-107">Bei der Ermittlung, ob der Name eindeutig ist, werden nur die ersten acht Zeichen ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="4d09c-107">Only the first eight characters are evaluated when determining if the name is unique.</span></span>  
  
- <span data-ttu-id="4d09c-108">Stellen Sie beim Angeben eines Pfads sicher, dass er ordnungsgemäß analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="4d09c-108">If supplying a path, make sure it is parsed correctly.</span></span>  
  
- <span data-ttu-id="4d09c-109">Vergewissern Sie sich, dass sich keine ungültigen Zeichen im Namen befinden.</span><span class="sxs-lookup"><span data-stu-id="4d09c-109">Check that there are no invalid characters in the name.</span></span> <span data-ttu-id="4d09c-110">Zu den Zeichen, die nicht in einem Dateinamen verwendet werden dürfen, zählen die Folgenden: `<`, `>`, `:`, `"`, `/`, `\`und `|`.</span><span class="sxs-lookup"><span data-stu-id="4d09c-110">Characters that cannot be used in a file name include `<`, `>`, `:`, `"`, `/`, `\`, and `|`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d09c-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d09c-111">See also</span></span>

- [<span data-ttu-id="4d09c-112">Vorgehensweise: Analysieren von Dateipfaden</span><span class="sxs-lookup"><span data-stu-id="4d09c-112">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
- [<span data-ttu-id="4d09c-113">Vorgehensweise: Umbenennen einer Datei</span><span class="sxs-lookup"><span data-stu-id="4d09c-113">How to: Rename a File</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
