---
title: Ungültige Datensatznummer
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: 44a11d95d33041de9d637684f41cb003dcc36b97
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84367541"
---
# <a name="bad-record-number"></a><span data-ttu-id="903a4-102">Ungültige Datensatznummer</span><span class="sxs-lookup"><span data-stu-id="903a4-102">Bad record number</span></span>
<span data-ttu-id="903a4-103">Die Datensatznummer in der `a FileGet`, `FilePut`, `FileGetObject`oder `FilePutObject` -Anweisung ist kleiner oder gleich 0 (null).</span><span class="sxs-lookup"><span data-stu-id="903a4-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="903a4-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="903a4-104">To correct this error</span></span>  
  
1. <span data-ttu-id="903a4-105">Überprüfen Sie die zum Generieren der Datensatznummer verwendeten Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="903a4-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="903a4-106">Überprüfen Sie die Rechtschreibung der Variablen, die die Datensatznummer enthalten oder bei der Berechnung von Datensatznummern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="903a4-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="903a4-107">Ein falsch geschriebener Variablenname wird implizit deklariert und zu 0 (null) initialisiert, es sei denn, Sie haben `Option Explicit On` im Modul verwendet.</span><span class="sxs-lookup"><span data-stu-id="903a4-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="903a4-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="903a4-108">See also</span></span>

- [<span data-ttu-id="903a4-109">Option Explicit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="903a4-109">Option Explicit Statement</span></span>](../language-reference/statements/option-explicit-statement.md)
