---
title: Pfad / Dateizugriffsfehler
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: 53f021faa9e4ae69a71d825ca823e1180421afc6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522478"
---
# <a name="pathfile-access-error"></a><span data-ttu-id="2f9d3-102">Pfad-/Dateizugriffsfehler</span><span class="sxs-lookup"><span data-stu-id="2f9d3-102">Path/File access error</span></span>
<span data-ttu-id="2f9d3-103">Während eines Datei- oder Datenträgerzugriffs könnte das Betriebssystem keine Verbindung zwischen dem Pfad und den Dateinamen herstellen.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2f9d3-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="2f9d3-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="2f9d3-105">Stellen Sie sicher, dass die Dateispezifikation richtig formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="2f9d3-106">Ein Dateiname darf eine vollqualifizierte (absolut) oder einen Pfad relativ Pfad.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="2f9d3-107">Ein vollqualifizierter Pfad beginnt mit den Namen des Laufwerks (wenn der Pfad auf einem anderen Laufwerk) und den expliziten Pfad vom Stamm zu der Datei aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="2f9d3-108">Alle, die nicht den vollqualifizierten Pfad ist relativ zu das aktuelle Laufwerk und Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2.  <span data-ttu-id="2f9d3-109">Stellen Sie sicher, dass Sie nicht versucht haben, zum Speichern einer Datei, die eine vorhandene schreibgeschützte Datei ersetzen.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="2f9d3-110">Wenn dies der Fall ist, ändern Sie das Attribut "schreibgeschützt" der Zieldatei oder speichern Sie die Datei mit einem anderen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3.  <span data-ttu-id="2f9d3-111">Stellen Sie sicher, dass Sie nicht versucht haben, öffnen Sie eine schreibgeschützte Datei in sequenziellen `Output` oder `Append` Modus.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-111">Make sure you did not attempt to open a read-only file in sequential `Output` or `Append` mode.</span></span> <span data-ttu-id="2f9d3-112">Wenn dies der Fall ist, öffnen Sie die Datei im `Input` Modus oder ändern Sie das Attribut "schreibgeschützt" der Datei.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4.  <span data-ttu-id="2f9d3-113">Stellen Sie sicher, dass Sie nicht versucht haben, um ein Visual Basic-Projekt in einer Datenbank oder das Dokument zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2f9d3-113">Make sure you did not attempt to change a Visual Basic project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f9d3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f9d3-114">See also</span></span>
- [<span data-ttu-id="2f9d3-115">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="2f9d3-115">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
