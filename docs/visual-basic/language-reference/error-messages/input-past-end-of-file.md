---
title: Eingabe nach dem Dateiende.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 27de462d5d28ee09107d75afe8269e7401c4dc39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="90076-102">Eingabe nach dem Dateiende.</span><span class="sxs-lookup"><span data-stu-id="90076-102">Input past end of file</span></span>
<span data-ttu-id="90076-103">Entweder ein `Input` Anweisung ist das Lesen aus einer Datei, die leer ist oder in der alle Daten verwendet wird, oder Sie verwendet die `EOF` -Funktion mit einer Datei für den binären Zugriff geöffnet.</span><span class="sxs-lookup"><span data-stu-id="90076-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="90076-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="90076-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="90076-105">Verwenden der `EOF` Funktion unmittelbar vor der `Input` Anweisung, um das Ende der Datei zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="90076-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2.  <span data-ttu-id="90076-106">Wenn die Datei für den binären Zugriff geöffnet ist, verwenden Sie `Seek` und `Loc`.</span><span class="sxs-lookup"><span data-stu-id="90076-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90076-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90076-107">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
