---
title: Ungültige Datensatznummer
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: 400879ba37c6b3215d9570ca6eb8eaa06edea03b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600804"
---
# <a name="bad-record-number"></a><span data-ttu-id="27f8d-102">Ungültige Datensatznummer</span><span class="sxs-lookup"><span data-stu-id="27f8d-102">Bad record number</span></span>
<span data-ttu-id="27f8d-103">Die Datensatznummer in der `a FileGet`, `FilePut`, `FileGetObject`oder `FilePutObject` -Anweisung ist kleiner oder gleich 0 (null).</span><span class="sxs-lookup"><span data-stu-id="27f8d-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="27f8d-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="27f8d-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="27f8d-105">Überprüfen Sie die zum Generieren der Datensatznummer verwendeten Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="27f8d-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="27f8d-106">Überprüfen Sie die Rechtschreibung der Variablen, die die Datensatznummer enthalten oder bei der Berechnung von Datensatznummern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="27f8d-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="27f8d-107">Ein falsch geschriebener Variablenname wird implizit deklariert und zu 0 (null) initialisiert, es sei denn, Sie haben `Option Explicit On` im Modul verwendet.</span><span class="sxs-lookup"><span data-stu-id="27f8d-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27f8d-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27f8d-108">See Also</span></span>  
 [<span data-ttu-id="27f8d-109">Option Explicit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="27f8d-109">Option Explicit Statement</span></span>](../../visual-basic/language-reference/statements/option-explicit-statement.md)
