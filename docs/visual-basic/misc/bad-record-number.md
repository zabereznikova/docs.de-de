---
title: Ungültige Datensatznummer
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: fbf1a2db97d0474fb758ff5ed572e94395a187da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664751"
---
# <a name="bad-record-number"></a><span data-ttu-id="82b03-102">Ungültige Datensatznummer</span><span class="sxs-lookup"><span data-stu-id="82b03-102">Bad record number</span></span>
<span data-ttu-id="82b03-103">Die Datensatznummer in der `a FileGet`, `FilePut`, `FileGetObject`oder `FilePutObject` -Anweisung ist kleiner oder gleich 0 (null).</span><span class="sxs-lookup"><span data-stu-id="82b03-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="82b03-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="82b03-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="82b03-105">Überprüfen Sie die zum Generieren der Datensatznummer verwendeten Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="82b03-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="82b03-106">Überprüfen Sie die Rechtschreibung der Variablen, die die Datensatznummer enthalten oder bei der Berechnung von Datensatznummern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="82b03-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="82b03-107">Ein falsch geschriebener Variablenname wird implizit deklariert und zu 0 (null) initialisiert, es sei denn, Sie haben `Option Explicit On` im Modul verwendet.</span><span class="sxs-lookup"><span data-stu-id="82b03-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82b03-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82b03-108">See also</span></span>
- [<span data-ttu-id="82b03-109">Option Explicit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="82b03-109">Option Explicit Statement</span></span>](../../visual-basic/language-reference/statements/option-explicit-statement.md)
