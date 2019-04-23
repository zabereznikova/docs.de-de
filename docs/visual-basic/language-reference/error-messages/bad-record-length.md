---
title: Ungültige Datensatzlänge.
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 1bc75303bcc2f46e54c06e89347da28997e59786
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979737"
---
# <a name="bad-record-length"></a><span data-ttu-id="c2024-102">Ungültige Datensatzlänge.</span><span class="sxs-lookup"><span data-stu-id="c2024-102">Bad record length</span></span>
<span data-ttu-id="c2024-103">Zu den möglichen Ursachen für diesen Fehler gehören:</span><span class="sxs-lookup"><span data-stu-id="c2024-103">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="c2024-104">Die Länge einer Datensatz-Variablen, die im angegebenen ein `FileGet`, `FileGetObject`, `FilePut` oder `FilePutObject` Anweisung unterscheidet sich von der entsprechenden angegebene Länge `FileOpen` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c2024-104">The length of a record variable specified in a `FileGet`, `FileGetObject`, `FilePut` or `FilePutObject` statement differs from the length specified in the corresponding `FileOpen` statement.</span></span>  
  
-   <span data-ttu-id="c2024-105">Die Variable in einem `FilePut` oder `FilePutObject` Anweisung oder eine Zeichenfolge variabler Länge enthält.</span><span class="sxs-lookup"><span data-stu-id="c2024-105">The variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string.</span></span>  
  
-   <span data-ttu-id="c2024-106">Die Variable in einem `FilePut` oder `FilePutObject` ist oder enthält ein `Variant` Typ.</span><span class="sxs-lookup"><span data-stu-id="c2024-106">The variable in a `FilePut` or `FilePutObject` is or includes a `Variant` type.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c2024-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c2024-107">To correct this error</span></span>  
  
1. <span data-ttu-id="c2024-108">Stellen Sie sicher, dass die Summe der Größen der Variablen im Datensatz den Typ der Variable definieren den benutzerdefinierten Typ fester Länge ist identisch, wie der Wert in der angegeben die `FileOpen` Anweisung `Len` Klausel.</span><span class="sxs-lookup"><span data-stu-id="c2024-108">Make sure the sum of the sizes of fixed-length variables in the user-defined type defining the record variable's type is the same as the value stated in the `FileOpen` statement's `Len` clause.</span></span>  
  
2. <span data-ttu-id="c2024-109">Wenn die Variable in einer `FilePut` oder `FilePutObject` Anweisung oder eine Zeichenfolge variabler Länge enthält, stellen Sie sicher, dass die Zeichenfolge variabler Länge, die kürzer als die Datensätze in angegebene Länge von mindestens 2 Zeichen der `Len` -Klausel der `FileOpen` -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c2024-109">If the variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string, make sure the variable-length string is at least 2 characters shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
3. <span data-ttu-id="c2024-110">Wenn die Variable in einer `FilePut` oder `FilePutObject` ist oder enthält ein `Variant` sicherzustellen, dass die Zeichenfolge variabler Länge ist kürzer als die Datensatzlänge mindestens 4 Bytes der `Len` -Klausel der `FileOpen` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c2024-110">If the variable in a `FilePut` or `FilePutObject` is or includes a `Variant` make sure the variable-length string is at least 4 bytes shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2024-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2024-111">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
