---
title: Pfad-Dateizugriffsfehler
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bff3ec554a594e99bc65e5cd8df28a056dcc1ebd
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="pathfile-access-error"></a><span data-ttu-id="9ecab-102">Pfad-/Dateizugriffsfehler</span><span class="sxs-lookup"><span data-stu-id="9ecab-102">Path/File access error</span></span>
<span data-ttu-id="9ecab-103">Während eines Datei- oder Datenträgerzugriffs womöglich des Betriebssystems eine Verbindung zwischen den Pfad und den Dateinamen nicht.</span><span class="sxs-lookup"><span data-stu-id="9ecab-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9ecab-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9ecab-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="9ecab-105">Stellen Sie sicher, dass die Dateispezifikation korrekt formatiert sind.</span><span class="sxs-lookup"><span data-stu-id="9ecab-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="9ecab-106">Ein Dateiname darf einen vollqualifizierten (absoluten) oder einen relativen Pfad.</span><span class="sxs-lookup"><span data-stu-id="9ecab-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="9ecab-107">Ein vollständig qualifizierter Pfad beginnt mit dem Namen des Laufwerks (falls der Pfad auf einem anderen Laufwerk ist) und den expliziten Pfad vom Stamm der Datei aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="9ecab-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="9ecab-108">Alle nicht vollqualifiziert ist Pfad ist relativ zum aktuellen Laufwerks und des Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="9ecab-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2.  <span data-ttu-id="9ecab-109">Stellen Sie sicher, dass Sie nicht versuchen, eine Datei zu speichern, die eine vorhandene schreibgeschützte Datei ersetzen würde.</span><span class="sxs-lookup"><span data-stu-id="9ecab-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="9ecab-110">Wenn dies der Fall ist, ändern Sie das Attribut "schreibgeschützt" der Zieldatei oder speichern Sie die Datei mit einem anderen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="9ecab-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3.  <span data-ttu-id="9ecab-111">Stellen Sie sicher, dass Sie nicht versucht haben, öffnen Sie eine schreibgeschützte Datei in sequenziellen `Output` oder `Append` Modus.</span><span class="sxs-lookup"><span data-stu-id="9ecab-111">Make sure you did not attempt to open a read-only file in sequential `Output` or `Append` mode.</span></span> <span data-ttu-id="9ecab-112">Wenn dies der Fall ist, öffnen Sie die Datei im `Input` Modus, oder ändern Sie das Schreibschutzattribut der Datei.</span><span class="sxs-lookup"><span data-stu-id="9ecab-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4.  <span data-ttu-id="9ecab-113">Stellen Sie sicher, dass Sie nicht versuchen, ein Visual Basic-Projekt in einer Datenbank oder das Dokument zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9ecab-113">Make sure you did not attempt to change a Visual Basic project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ecab-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ecab-114">See Also</span></span>  
 [<span data-ttu-id="9ecab-115">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="9ecab-115">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
