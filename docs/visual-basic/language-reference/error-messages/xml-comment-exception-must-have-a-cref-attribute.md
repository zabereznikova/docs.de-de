---
title: Eine XML-Kommentarausnahme benötigen eine &#39;Cref&#39; Attribut
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: abe9fe0f6216f81fa223fe83a122b580577e1c32
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43404764"
---
# <a name="xml-comment-exception-must-have-a-39cref39-attribute"></a><span data-ttu-id="ea12c-102">Eine XML-Kommentarausnahme benötigen eine &#39;Cref&#39; Attribut</span><span class="sxs-lookup"><span data-stu-id="ea12c-102">XML comment exception must have a &#39;cref&#39; attribute</span></span>
<span data-ttu-id="ea12c-103">Die \<Ausnahme >-Tag bietet eine Möglichkeit, die Ausnahmen zu dokumentieren, die von einer Methode ausgelöst werden können.</span><span class="sxs-lookup"><span data-stu-id="ea12c-103">The \<exception> tag provides a way to document the exceptions that may be thrown by a method.</span></span> <span data-ttu-id="ea12c-104">Die erforderlichen `cref` -Attribut legt den Namen eines Members, der von der Dokumentations-Generator überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="ea12c-104">The required `cref` attribute designates the name of a member, which is checked by the documentation generator.</span></span> <span data-ttu-id="ea12c-105">Wenn das Element vorhanden ist, wird es in den kanonischen Elementnamen in der Dokumentationsdatei übersetzt.</span><span class="sxs-lookup"><span data-stu-id="ea12c-105">If the member exists, it is translated to the canonical element name in the documentation file.</span></span>  
  
 <span data-ttu-id="ea12c-106">**Fehler-ID:** BC42319</span><span class="sxs-lookup"><span data-stu-id="ea12c-106">**Error ID:** BC42319</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ea12c-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ea12c-107">To correct this error</span></span>  
  
-   <span data-ttu-id="ea12c-108">Hinzufügen der `cref` -Attribut auf die Ausnahme wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ea12c-108">Add the `cref` attribute to the exception as follows:</span></span>  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ea12c-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea12c-109">See Also</span></span>  
 [<span data-ttu-id="ea12c-110">\<exception></span><span class="sxs-lookup"><span data-stu-id="ea12c-110">\<exception></span></span>](../../../visual-basic/language-reference/xmldoc/exception.md)  
 [<span data-ttu-id="ea12c-111">Gewusst wie: Erstellen einer XML-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="ea12c-111">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
 [<span data-ttu-id="ea12c-112">XML-Kommentartags</span><span class="sxs-lookup"><span data-stu-id="ea12c-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
