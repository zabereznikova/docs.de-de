---
title: Ungültige Datensatzlänge.
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 6967015572b2567f52697f7ddcb1ff594013a2c4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869263"
---
# <a name="bad-record-length"></a><span data-ttu-id="dab5c-102">Ungültige Datensatzlänge.</span><span class="sxs-lookup"><span data-stu-id="dab5c-102">Bad record length</span></span>

<span data-ttu-id="dab5c-103">Zu den möglichen Ursachen für diesen Fehler gehören:</span><span class="sxs-lookup"><span data-stu-id="dab5c-103">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="dab5c-104">Die Länge einer Daten Satz Variablen, die in einer-,-oder-Anweisung angegeben ist, unter `FileGet` `FileGetObject` scheidet sich `FilePut` `FilePutObject` von der in der entsprechenden-Anweisung angegebenen Länge `FileOpen` .</span><span class="sxs-lookup"><span data-stu-id="dab5c-104">The length of a record variable specified in a `FileGet`, `FileGetObject`, `FilePut` or `FilePutObject` statement differs from the length specified in the corresponding `FileOpen` statement.</span></span>  
  
- <span data-ttu-id="dab5c-105">Die-Variable in einer- `FilePut` oder `FilePutObject` -Anweisung ist oder enthält eine Zeichenfolge variabler Länge.</span><span class="sxs-lookup"><span data-stu-id="dab5c-105">The variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string.</span></span>  
  
- <span data-ttu-id="dab5c-106">Die-Variable in einem `FilePut` oder `FilePutObject` ist oder enthält einen- `Variant` Typ.</span><span class="sxs-lookup"><span data-stu-id="dab5c-106">The variable in a `FilePut` or `FilePutObject` is or includes a `Variant` type.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dab5c-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="dab5c-107">To correct this error</span></span>  
  
1. <span data-ttu-id="dab5c-108">Stellen Sie sicher, dass die Summe der Größen von Variablen fester Länge im benutzerdefinierten Typ, der den Typ der Daten Satz Variablen definiert, mit dem in der `FileOpen` -Klausel der-Anweisung angegebenen Wert übereinstimmt `Len` .</span><span class="sxs-lookup"><span data-stu-id="dab5c-108">Make sure the sum of the sizes of fixed-length variables in the user-defined type defining the record variable's type is the same as the value stated in the `FileOpen` statement's `Len` clause.</span></span>  
  
2. <span data-ttu-id="dab5c-109">Wenn die Variable in einer `FilePut` `FilePutObject` -oder-Anweisung ist oder eine Zeichenfolge variabler Länge enthält, stellen Sie sicher, dass die Zeichenfolge mit variabler Länge mindestens 2 Zeichen kürzer ist als die in der-Klausel der-Anweisung angegebene Daten Satz Länge `Len` `FileOpen` .</span><span class="sxs-lookup"><span data-stu-id="dab5c-109">If the variable in a `FilePut` or `FilePutObject` statement is or includes a variable-length string, make sure the variable-length string is at least 2 characters shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
3. <span data-ttu-id="dab5c-110">Wenn die Variable in einer `FilePut` oder `FilePutObject` ein ist oder ein-Element enthält, `Variant` Stellen Sie sicher, dass die Zeichenfolge mit variabler Länge mindestens 4 Bytes kürzer ist als die in der-Klausel der-Anweisung angegebene Daten Satz Länge `Len` `FileOpen` .</span><span class="sxs-lookup"><span data-stu-id="dab5c-110">If the variable in a `FilePut` or `FilePutObject` is or includes a `Variant` make sure the variable-length string is at least 4 bytes shorter than the record length specified in the `Len` clause of the `FileOpen` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab5c-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dab5c-111">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
