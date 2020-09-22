---
title: Eingabe nach dem Dateiende.
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: c0cb0373fb0652e9600ac8651661708414561aca
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873971"
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="7166a-102">Eingabe nach dem Dateiende.</span><span class="sxs-lookup"><span data-stu-id="7166a-102">Input past end of file</span></span>

<span data-ttu-id="7166a-103">Eine- `Input` Anweisung liest entweder aus einer leeren oder einer Datei, in der alle Daten verwendet werden, oder verwendet die- `EOF` Funktion mit einer Datei, die für den binären Zugriff geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="7166a-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7166a-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="7166a-104">To correct this error</span></span>  
  
1. <span data-ttu-id="7166a-105">Verwenden Sie die- `EOF` Funktion unmittelbar vor der- `Input` Anweisung, um das Ende der Datei zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="7166a-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2. <span data-ttu-id="7166a-106">Wenn die Datei für den binären Zugriff geöffnet ist, verwenden Sie `Seek` und `Loc` .</span><span class="sxs-lookup"><span data-stu-id="7166a-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7166a-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7166a-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
