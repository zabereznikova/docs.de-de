---
title: Eingabe nach dem Dateiende.
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: abd5f5c6e5df262d1deadd74f0a146a8d436ceb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586740"
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="3c1d0-102">Eingabe nach dem Dateiende.</span><span class="sxs-lookup"><span data-stu-id="3c1d0-102">Input past end of file</span></span>
<span data-ttu-id="3c1d0-103">Entweder ein `Input` Anweisung ist das Lesen aus einer Datei, die leer ist oder in der alle Daten verwendet wird, oder Sie verwendet die `EOF` -Funktion mit einer Datei für den binären Zugriff geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3c1d0-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3c1d0-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="3c1d0-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="3c1d0-105">Verwenden der `EOF` Funktion unmittelbar vor der `Input` Anweisung, um das Ende der Datei zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="3c1d0-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2.  <span data-ttu-id="3c1d0-106">Wenn die Datei für den binären Zugriff geöffnet ist, verwenden Sie `Seek` und `Loc`.</span><span class="sxs-lookup"><span data-stu-id="3c1d0-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c1d0-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c1d0-107">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
