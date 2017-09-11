---
title: Pfad-Dateizugriffsfehler | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID75
dev_langs:
- VB
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6307c0d0115e3791d5ad6bf4243057e6ed90d9cd
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="pathfile-access-error"></a><span data-ttu-id="d0ba6-102">Pfad-/Dateizugriffsfehler</span><span class="sxs-lookup"><span data-stu-id="d0ba6-102">Path/File access error</span></span>
<span data-ttu-id="d0ba6-103">Während eines Datei- oder Datenträgerzugriffs konnte das Betriebssystem eine Verbindung zwischen dem Pfad und der Dateiname nicht auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d0ba6-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d0ba6-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d0ba6-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="d0ba6-105">Stellen Sie sicher, dass die Dateispezifikation richtig formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="d0ba6-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="d0ba6-106">Ein Dateiname darf einen vollqualifizierten (absoluten) oder ein relativer Pfad.</span><span class="sxs-lookup"><span data-stu-id="d0ba6-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="d0ba6-107">Ein vollqualifizierter Pfad beginnt mit dem Laufwerknamen (falls der Pfad auf einem anderen Laufwerk ist) und listet den expliziten Pfad vom Stammelement der Datei.</span><span class="sxs-lookup"><span data-stu-id="d0ba6-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="d0ba6-108">Alle, die nicht den vollqualifizierten Pfad ist relativ zum aktuellen Laufwerk und Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d0ba6-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2.  <span data-ttu-id="d0ba6-109">Stellen Sie sicher, dass Sie nicht versuchen, eine Datei zu speichern, die eine vorhandene schreibgeschützte Datei ersetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="d0ba6-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="d0ba6-110">Wenn dies der Fall ist, ändern Sie das Attribut "schreibgeschützt" der Zieldatei, oder speichern Sie die Datei mit einem anderen Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="d0ba6-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3.  <span data-ttu-id="d0ba6-111">Stellen Sie sicher, dass Sie nicht versucht haben, öffnen Sie eine schreibgeschützte Datei im sequenziellen`Output`oder `Append` Modus.</span><span class="sxs-lookup"><span data-stu-id="d0ba6-111">Make sure you did not attempt to open a read-only file in sequential`Output`or `Append` mode.</span></span> <span data-ttu-id="d0ba6-112">Wenn dies der Fall ist, öffnen Sie die Datei im `Input` Modus oder ändern Sie das Schreibschutzattribut der Datei.</span><span class="sxs-lookup"><span data-stu-id="d0ba6-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4.  <span data-ttu-id="d0ba6-113">Stellen Sie sicher, dass Sie nicht versucht haben, ändern Sie ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Projekt innerhalb einer Datenbank oder eines Dokuments.</span><span class="sxs-lookup"><span data-stu-id="d0ba6-113">Make sure you did not attempt to change a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ba6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0ba6-114">See Also</span></span>  
 [<span data-ttu-id="d0ba6-115">Fehlertypen</span><span class="sxs-lookup"><span data-stu-id="d0ba6-115">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
