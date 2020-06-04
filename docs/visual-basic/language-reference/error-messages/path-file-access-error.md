---
title: Pfad-/Dateizugriffsfehler
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: dfe96cd6eaa673438849fe8f799d46fa2617bfdd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387256"
---
# <a name="pathfile-access-error"></a><span data-ttu-id="fda07-102">Pfad-/Dateizugriffsfehler</span><span class="sxs-lookup"><span data-stu-id="fda07-102">Path/File access error</span></span>
<span data-ttu-id="fda07-103">Bei einem Datei Zugriffs-oder Datenträger Zugriffs Vorgang konnte das Betriebssystem keine Verbindung zwischen dem Pfad und dem Dateinamen herstellen.</span><span class="sxs-lookup"><span data-stu-id="fda07-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fda07-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fda07-104">To correct this error</span></span>  
  
1. <span data-ttu-id="fda07-105">Stellen Sie sicher, dass die Datei Spezifikation ordnungsgemäß formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="fda07-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="fda07-106">Ein Dateiname kann einen voll qualifizierten (absoluten) oder relativen Pfad enthalten.</span><span class="sxs-lookup"><span data-stu-id="fda07-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="fda07-107">Ein voll qualifizierter Pfad beginnt mit dem Laufwerks Namen (wenn sich der Pfad auf einem anderen Laufwerk befindet) und listet den expliziten Pfad vom Stamm zur Datei auf.</span><span class="sxs-lookup"><span data-stu-id="fda07-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="fda07-108">Alle Pfade, die nicht voll qualifiziert sind, sind relativ zum aktuellen Laufwerk und Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fda07-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2. <span data-ttu-id="fda07-109">Stellen Sie sicher, dass Sie nicht versucht haben, eine Datei zu speichern, die eine vorhandene schreibgeschützte Datei ersetzt.</span><span class="sxs-lookup"><span data-stu-id="fda07-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="fda07-110">Wenn dies der Fall ist, ändern Sie das Attribut "schreibgeschützt" der Zieldatei, oder speichern Sie die Datei unter einem anderen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="fda07-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3. <span data-ttu-id="fda07-111">Stellen Sie sicher, dass Sie nicht versucht haben, eine schreibgeschützte Datei in sequenzieller oder-Modus zu öffnen `Output` `Append` .</span><span class="sxs-lookup"><span data-stu-id="fda07-111">Make sure you did not attempt to open a read-only file in sequential `Output` or `Append` mode.</span></span> <span data-ttu-id="fda07-112">Wenn dies der Fall ist, öffnen Sie die Datei im- `Input` Modus, oder ändern Sie das schreibgeschützte Attribut der Datei.</span><span class="sxs-lookup"><span data-stu-id="fda07-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4. <span data-ttu-id="fda07-113">Stellen Sie sicher, dass Sie nicht versucht haben, ein Visual Basic Projekt innerhalb einer Datenbank oder eines Dokuments zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fda07-113">Make sure you did not attempt to change a Visual Basic project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fda07-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fda07-114">See also</span></span>

- [<span data-ttu-id="fda07-115">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="fda07-115">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
