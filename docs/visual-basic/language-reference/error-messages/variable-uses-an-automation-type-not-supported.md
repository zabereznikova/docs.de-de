---
title: "Die Variable verwendet einen Automatisierungstyp, der in Visual Basic nicht unterstützt. | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID458
dev_langs:
- VB
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
caps.latest.revision: 12
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
ms.openlocfilehash: 74c4472230a3a8c54859771c0b2f7fc954ac0966
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="variable-uses-an-automation-type-not-supported-in-visual-basic"></a><span data-ttu-id="0b326-102">Die Variable verwendet einen Automatisierungstyp, der von Visual Basic nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="0b326-102">Variable uses an Automation type not supported in Visual Basic</span></span>
<span data-ttu-id="0b326-103">Sie haben versucht, eine Variable in einer Typbibliothek oder Objektbibliothek, die einen von nicht unterstützten Datentyp definierten [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b326-103">You tried to use a variable defined in a type library or object library that has a data type not supported by [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0b326-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="0b326-104">To correct this error</span></span>  
  
-   <span data-ttu-id="0b326-105">Verwenden Sie eine Variable eines Typs von erkannten [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b326-105">Use a variable of a type recognized by [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
     <span data-ttu-id="0b326-106">- oder - </span><span class="sxs-lookup"><span data-stu-id="0b326-106">-or-</span></span>  
  
-   <span data-ttu-id="0b326-107">Wenn dieser Fehler bei der Verwendung `FileGet` oder `FileGetOBject`, stellen Sie sicher, dass die Datei, die Sie verwenden möchten geschrieben wurde, mit `FilePut` oder `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="0b326-107">If you encounter this error while using `FileGet` or `FileGetOBject`, make sure the file you are trying to use was written to with `FilePut` or `FilePutObject`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b326-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b326-108">See Also</span></span>  
 [<span data-ttu-id="0b326-109">Datentypen</span><span class="sxs-lookup"><span data-stu-id="0b326-109">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)
